## Nuttige array methoden

Net zoals we hebben gezien dat de Math-klasse een hele boel nuttige methoden in zich, zo ook heeft iedere array een aantal methoden waar handig gebruik van kan gemaakt worden.

Wanneer een array hebt gemaakt, dan kan je met de IntelliSense van Visual studio bekijken wat je allemaal kan doen met de array:

![](/assets/5_arrays/arrays2.png)


Al deze methoden hier beschrijven zal ons te ver nemen. De volgende methoden zijn echter zeer handig om te gebruiken:

Max(), Min(), Sum() en Average()

Volgende code geeft bijvoorbeeld het grootste getal terug uit een array genaamd "leeftijden":
```csharp
int oudsteleeftijd=leeftijden.Max();
```

## System.Array
Alle C# arrays erven over van de System.Array klasse (klasse en overerving zien we later dit semester), hierdoor kan je zaken zoals Length gebruiken op je array. De System.Array klasse heeft echter ook nog een hoop andere nuttige methoden zoals de BinarySearch(), Sort() en Reverse() methoden. Het gebruik hiervan is steeds dezelfde zoals volgende voorbeelden tonen:

### Arrays sorteren
Om arrays te sorteren roep je de Sort() methode op als volgt, als parameter geef je de array mee die gesorteerd moet worden.

Volgende voorbeeld toont hier het gebruik van:

```csharp
string[] myColors = { "red", "green", "yellow", "orange", "blue" };
//Sorteer
System.Array.Sort(myColors);
 
//Toon resultaat van sorteren
for (int i = 0; i < myColors.Length; i++)
{
    System.Console.WriteLine(myColors[i]);
}
```
Wanneer je de Sort-methode toepast op een array van string dan zullen de arrays alfabetisch gerangschikt worden.

### Arrays omkeren
Met de System.Array.Reverse() methode kunnen we dan weer de elementen van de array omkeren (dus het laatste element vooraan zetten en zo verder:

```csharp
System.Array.Reverse(myColors);
```

### Arrays leegmaken
Een array volledig leegmaken (alle elementen op ‘null’ zetten) doe je met de System.Array.Clear methode, als volgt:

```csharp
System.Array.Clear(myColors);
```
## Zoeken in arrays
De ``BinarySearch``-methode maakt het mogelijk om te zoeken naar de index van een gegeven element in een index. *Deze methode werkt enkel indien de elementen in de array gesorteerd staan!* Je geeft aan de methode 2 parameters mee, enerzijds de array in kwestie en anderzijds het element dat we zoeken. Als resultaat wordt de index van het gevonden element teruggegeven. Indien niets wordt gevonden zal het resultaat -1 zijn.

```csharp
System.Array.BinarySearch(myColors, "red" );
```

### Manueel zoeken in arrays
Het zoeken in arrays kan met behulp van while of for-loops tamelijk snel. Volgende programmaatje gaat zoeken of het getal 12 aanwezig is in de array. Indien ja dan wordt de index bewaard van de positie in de array waar het getal staat:

```csharp
int teZoekenGetal = 12;
 
int[] getallen = { 5, 10, 12, 25, 16 };
 
bool gevonden = false;
int index = -1;
 
for (int i = 0; i < getallen.Length; i++)
{
    if (getallen[i] == teZoekenGetal)
    {
        gevonden = true;
        index = i;
    }
}
```

Voorgaande stukje code is de meest naïeve oplossing. Bedenk echter wat er gebeurt indien het getal dat we zoeken 2 of meerdere keren in de array staat. Index zal dan de positie bevatten van de laatst gevonden 12 in de array.

Het is zéér belangrijk dat je vlot dit soort algoritmen kan schrijven, zoals:

* Zoeken van elementpositie in array
* Tellen hoe vaak een element in een array voorkomt
* Elementen in een array 1 of meerdere plaatsen opschuiven


### Manueel zoeken met for en while

We tonen nu twee voorbeelden hoe je kan zoeken in een array wanneer we bijvoorbeeld 2 arrays hebben die 'synchroon' zijn. Daarmee bedoel ik: de eerste array bevat producten, de tweede array bevat de prijs van ieder product. De prijs van de producten staat steeds op dezelfde index in de andere array:

```csharp
string[] products = { "apples", "pears", "melons" };
double[] prices = { 3.3, 6.2, 2.9 };
```

We vragen nu aan de gebruiker van welk product de prijs moet getoond worden:

```csharp
Console.WriteLine("Which price do you need?");
string userchoice = Console.ReadLine();
```

We tonen nu hoe we met ``for`` eerst het juiste product zoeken en dan vervolgens die index bewaren en gebruiken om de prijs te tonen:

```csharp
bool found = false;
int productIndex = -1;

int counter = 0;
while (counter < products.Length && userchoice != products[counter])
{
    counter++;
}

if (counter != products.Length)//product found!
{
    found = true;
    productIndex = counter;
}


if (found == true)
{
    Console.WriteLine($"Price for {userchoice} is {prices[productIndex]}");
}
else
{
    Console.WriteLine("Not found");
}
```

Een nadeel van deze oplossing is dat we steeds de hele for doorlopen (we gebruiken geen ``break`` vanwege een allergie hiervoor bij de auteur). Bij heel lange arrays is dit dus niet erg performant.

Volgende oplossing met een ``while`` toont een performantere oplossing:

```csharp
bool found = false;
int productIndex = -1;

int counter = 0;
while (counter < products.Length && userchoice != products[counter])
{
    counter++;
}

if (counter != products.Length)//product found!
{
    found = true;
    productIndex = counter;
}

if (found == true)
{
    Console.WriteLine($"Price for {userchoice} is {prices[productIndex]}");
}
else
{
    Console.WriteLine("Not found");
}
```

# String en arrays

## String naar char array
Het type ``string`` is niet meer dan een arrays van karakters, ``char[]``. Om een string per karakter te bewerken is het aanbevolen om deze naar een char-array om te zetten en nadien terug naar een string. Dit kan gebruikmakend van ``.ToCharArray()`` als volgt:

```csharp
string origineleZin= "Ik ben Tom";
char[] karakters = origineleZin.ToCharArray();
karakters[8]= 'i';
string nieuweZin= new string(karakters);
Console.WriteLine(nieuweZin);
```

De uitvoer zal worden:``Ik ben Tim``.

## Char array naar string

Ook de omgekeerde weg is mogelijk.  De werking is iets anders, let vooral op hoe we de char array doorgeven als argument bij het aanmaken van een nieuwe ``string`` in lijn 3:

```csharp
char[] arrayOfLetters = { 'h', 'a', 'l', 'l', 'o' };
arrayOfLetters[2] = 'x';
string word = new string(arrayOfLetters);
Console.WriteLine(word);
```

De uitvoer van deze code zal zijn: ``haxlo``.