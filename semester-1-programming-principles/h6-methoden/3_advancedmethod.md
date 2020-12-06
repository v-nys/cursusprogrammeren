# Geavanceerde methoden

{% hint style="info" %}
Volgende sectie is grotendeels gebaseerd op het volgende [artikel](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments).
{% endhint %}

## Named parameters

Wanneer je een methode aanroept is de volgorde van je argumenten belangrijk: deze moeten meegeven worden in de volgorde zoals de methode parameters ze verwachten.

Met behulp van named parameters kan je echter expliciet aangeven welke argument aan welke methode-parameter moet meegegeven worden.

Stel dat we een methode hebben met volgende signatuur:

```csharp
 static void PrintOrderDetails(string sellerName, int orderNum, string productName)
 {
     Console.WriteLine($"Verkoper: {sellerName}");
     Console.WriteLine($"Ordernummer: {orderNum}");
     Console.WriteLine($"Product: {productName}");
 }
```

Zonder named parameters zou een aanroep van deze methode als volgt kunnen zijn:

```csharp
PrintOrderDetails("Gift Shop", 31, "Red Mug");
```

We kunnen named parameters aangeven door de naam van de parameter gevolg door een dubbel punt en de waarde. Als we dus bovenstaande methode willen aanroepen kan dat ook als volgt met named parameters:

```csharp
 PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");
```

of ook:

```csharp
 PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);
```

### Volgorde van named parameters belangrijk

Je mag ook een combinatie doen van named en gewone parameters, maar **dan is de volgorde belangrijk**: je moet je dan houden aan de volgorde van de methode-volgorde. Je verbetert hiermee de leesbaarheid van je code dus \(maar krijgt niet het voordeel van een eigen volgorde te hanteren\). Enkele voorbeelden:

```csharp
PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");
PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");    // C# 7.2 onwards
PrintOrderDetails("Gift Shop", orderNum: 31, "Red Mug");
```

Enkele **NIET GELDIGE** voorbeelden:

```csharp
PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
PrintOrderDetails(31, sellerName: "Gift Shop", "Red Mug");
PrintOrderDetails(31, "Red Mug", sellerName: "Gift Shop");
```

## Optionele parameters

Soms wil je dat een methode een standaard waarde voor een parameter gebruikt indien de programmeur in z'n aanroep geen waarde meegaf. Dat kan met behulp van optionele of default parameters.

Je geef aan dat een parameter optioneel is door deze een default waarde te geven in de methode-signatuur. Deze waarde zal dan gebruikt worden indien de parameter geen waarde van de aanroeper heeft gekregen.

**Optionele parameters worden steeds achteraan de parameterlijst van de methode geplaatst** .

In het volgende voorbeeld maken we een nieuwe methode aan en geven aan dat de laatste parameters optioneel zijn. `discountPercentage` past een "gewone" korting toe op de aankoop van het aantal items. `doubleDiscount` is een speciale extra korting die het percentage verdubbelt. We veronderstellen dat items meestal verkocht worden zonder korting:

```csharp
static double ComputePrice(int numberOfItems, double itemPrice, double discountPercentage = 0, bool doubleDiscount = false) {
    if (not doubleDiscount) {
        return (numberOfItems * itemPrice) * (1.0 - discountPercentage / 100) - storeCredit;
    }
    else {
    return (numberOfItems * itemPrice) * (1.0 - 2 * discountPercentage / 100) - storeCredit;
    }
}
```

Volgende manieren zijn nu geldige manieren om de methode aan te roepen:

```csharp
Console.WriteLine(ComputePrice(4,10.0)); // klassieke aanroep
Console.WriteLine(ComputePrice(4,10.0,5.0)); // 5% korting op de totaalprijs
Console.WriteLine(ComputePrice(4,10.0,5.0,true)); // 10% korting op de totaalprijs omdat de korting verdubbeld wordt
```

Je mag enkel de optionele parameters van achter naar voor weglaten. Volgende aanroep is dus **niet geldig**:

```csharp
Console.WriteLine(ComputePrice(4,10.0,true)); // derde argument moet een double zijn!
```

Door de argumenten te benoemen, kunnen we dit indien gewenst omzeilen. Volgende aanroep is wel geldig:

```csharp
// dit heeft weinig zin want we verdubbelen 0% korting, maar voor C# werkt dit wel
Console.WriteLine(ComputePrice(4,10.0,doubleDiscount: true));
```

## Method overloading

Method overloading wil zeggen dat je een **methode met dezelfde naam en returntype** meerdere keren definieert maar met andere parameters qua type en aantal. De compiler zal dan zelf bepalen welke methode moet aangeroepen worden gebaseerd op het aantal en type parameters dat je meegeeft.

Volgende methoden zijn overloaded:

```csharp
static int ComputeArea(int lengte, int breedte)
{
    int opp = lengte*breedte;
    return opp;
}

static int ComputeArea(int radius)
{
    int opp = (int)(Math.PI*radius*radius);
    return opp;
}
```

Afhankelijk van de aanroep zal dus de ene of andere uitgevoerd worden. Volgende code zal dus werken:

```csharp
            Console.WriteLine($"Rechthoek: {ComputeArea(5, 6)}");
            Console.WriteLine($"Circle: {ComputeArea(7)}");
```

### Betterness rule

Indien de compiler twijfelt tijdens de **overload resolution** \(welke versie moet aangeroepen worden\) zal de betterness rule worden gehanteerd: de best 'passende' methode zal aangeroepen worden. Stel dat we volgende overloaded methoden hebben:

```csharp
static int ComputeArea(int radius) //versie A
{
    int opp = (int)(Math.PI*radius*radius);
    return opp;
}

static int ComputeArea(double radius) //versie B
{
    int opp = (int)(Math.PI * radius * radius);
    return opp;
}
```

Volgende aanroepen zullen dus als volgt uitgevoerd worden:

```csharp
Console.WriteLine($"Circle 1: {ComputeArea(7)}"); //versie A
Console.WriteLine($"Circle 2: {ComputeArea(7.5)}"); //versie B
Console.WriteLine($"Circle 3: {ComputeArea(7.3f)}"); //versie B
```

De betterness rule is als volgt:

| Meegegeven type | Voorkeur \(betterness\) van meeste voorkeur naar minste |
| :--- | :--- |
| byte | short, ushort, int, uint, long, ulong, float, double, decimal |
| sbyte | short, int long, float, double, decimal |
| short | int, long, float, double, decimal |
| ushort | int, uint, long, ulong, float, double, decimal |
| int | long, float, double, decimal |
| uint | long, ulong, float, double, decimal |
| long | float, double, decimal |
| ulong | float, double, decimal |
| float | double |
| char | ushort, int, uint, long, ulong, float, double, decimal |

Als je dus bijvoorbeeld een parameter van het type int meegeeft bij een methode aanroep \(eerste kolom\), dan zal een long geprefereerd worden boven een float, enz.

Indien de betterness regel niet werkt, dan zal de eerste parameter bepalen wat er gebruikt wordt. Dat zien we in volgende voorbeeld:

```csharp
static void Main(string[] args)
{
    Toonverhouding(5, 3.4); //versie A
    Toonverhouding(6.2, 3); //versie B
}


static void Toonverhouding(int a, double b) //versie A
{
    Console.WriteLine($"{a}/{b}");
}


static void Toonverhouding(double a, int b) //versie B
{
    Console.WriteLine($"{a}/{b}");
}
```

Indien ook die regel niet werkt dan zal een error optreden zoals hier wat zal resulteren in een **Ambigious overload error**:

```csharp
static void Main(string[] args)
{

    Toonverhouding(5.6, 3.4);  
}


static void Toonverhouding(int a, double b)
{
    Console.WriteLine($"{a}/{b}");
}


static void Toonverhouding(double a, int b)
{
    Console.WriteLine($"{a}/{b}");
}
```

