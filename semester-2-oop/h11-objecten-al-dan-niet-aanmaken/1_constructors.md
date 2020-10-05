# Constructors

## Constructors

### Werking new operator

Objecten die je aanmaakt komen niet zomaar tot leven. Nieuwe objecten maken we aan met behulp van de `new` operator zoals we al gezien hebben:

```csharp
Auto auto1 = new Auto();
```

De `new` operator doet 2 dingen:

* Hij reserveert ruimte voor dit object in het geheugen
* Hij zorgt ervoor dat initialisatiecode uitvoert om het object klaar te maken voor gebruik

Via de constructor van een klasse kunnen we code meegeven die moet uitgevoerd worden **telkens een nieuw object van dit type wordt aangemaakt**.

Constructors lijken erg op methodes. We zullen vaak zeggen dat het speciale methodes zijn, al bestaat daar wat technische discussie over. De constructor wordt in elk geval aangeroepen op een gelijkaardige manier aan een gewone methode. Daarom zetten we ronde haakjes: `new Auto()`.

## Soorten constructors

Als programmeur van eigen klassen zijn er 3 opties voor je:

* Je gebruikt geen \(expliciete\) constructors: het leven gaat voort zoals het is. Je kunt objecten aanmaken zoals eerder getoond. Achter de schermen gebruik je wel een zogenaamde **default** constructor.
* Je hebt enkel een **parameterloze** constructor nodig. Je kan nog steeds objecten met `new Auto()` aanmaken, maar je gaat zelf beschrijven wat er moet gebeuren bij de parameterloze constructor.
* Je wenst gebruik te maken van een of meerdere constructoren met parameters. Hierbij zal je dan extra argumenten kunnen meegeven bij de creatie van een object, bijvoorbeeld: `new Auto(25,25000)`. Dit kan bijvoorbeeld een auto maken met 25l benzine in de tank en 25000km op de teller. De betekenis van de getallen hangt af van hoe je de constructor schrijft.

{% hint style="warning" %}
### Constructors zijn soms gratis, soms niet

Een lege default constructor voor je klasse krijg je standaard wanneer je een nieuwe klasse aanmaakt. Je ziet deze niet en kan deze niet aanpassen. Je kan echter daarom altijd objecten met `new myClass()` aanmaken.

Van zodra je echter beslist om zelf een of meerdere constructors te schrijven zal C\# zeggen "Oké, jij je zin, nu doe je alles zelf". De default constructor die je gratis kreeg zal ook niet meer bestaan en heb je die dus nodig dan zal je die dus zelf moeten schrijven!
{% endhint %}

### Default constructor

De default constructor is een constructor die je zelf niet schrijft. Hij heeft nooit parameters.

* Standaard is hij `public` \([meer info](https://stackoverflow.com/questions/30995942/do-constructors-always-have-to-be-public)\)
* Heeft \(zoals alle constructoren\) als naam de naam van de klasse zelf

Stel dat we een klasse `Auto` hebben:

```csharp
class Auto
{
    private int benzine = 5;
    private int kilometers;
}
```

We schrijven nergens code voor de constructor. Dan nog kunnen we `new Auto()` schrijven, maar dan wordt de auto aangemaakt met 5l in de tank en 0km \(de defaultwaarde van `int`\) op de teller.

### Parameterloze constructor

We willen telkens een Auto-object wordt aangemaakt dat dit een random aantal kilometers op de teller heeft. Via een parameterloze constructor kunnen we dat oplossen \(je kan namelijk niet schrijven `private int kilometers = random.Next(0,200000)` , je kan alleen een letterlijke waarde als initiële waarde nemen\)

Eerst schrijven de parameterloze constructor, deze ziet er als volgt uit:

```csharp
class Auto
{
    private int benzine = 5;
    private int kilometers;
    
    public Auto()
    {
        // zet hier de code die bij initialisatie moet gebeuren
        // d.w.z. wat er moet gebeuren zodra de auto wordt gemaakt
    }
}
```

De constructor moet de naam van de klasse hebben, public zijn en geen returntype definiëren.

Vervolgens voegen we de code toe die we nodig hebben:

{% hint style="danger" %}
Dit is in veel programmeertalen slecht gebruik van `Random`, maar we hebben nog niet de nodige achtergrond om de juiste werkwijze te tonen. Dat komt binnenkort!
{% endhint %}

```csharp
class Auto
{
    private int benzine = 5;
    private int kilometers;
    
    public Student()
    {
        Random r = new Random();
        // ook in de constructor kan je this gebruiken
        this.kilometers = r.Next(0,200000);
    }
}
```

Telkens we nu een object zouden aanmaken met `new Auto()` zal deze een willekeurige kilometerstand hebben. Je kan trouwens ook in de constructor een initiële waarde aan `benzine` geven.

{% hint style="info" %}
Zelfs als er een letterlijke initiële waarde wordt toegekend, gebeurt dit meestal in de constructor. Het is een kwestie van smaak, maar een constructor dient toch om te initialiseren.
{% endhint %}

#### Opmerking bij voorgaande code

* Als je op een gelijkaardige manier in andere programmeertalen twee of meerdere Auto-objecten snel na mekaar aanmaakt zullen deze dezelfde kilometerstand hebben. Dit is omdat ieder object z'n eigen `Random` aanmaakt en zoals we weten zal een random generator dezelfde getallen genereren als deze vlak na mekaar \(in tijd\) zijn aangemaakt. Een oplossing zullen we hier later voor zien. Spoiler, `static` is de oplossing hiervoor:

```csharp
class Auto
{
    static Random r = new Random();
    private int kilometers;
    public Auto()
    {
        this.kilometers = r.Next(0,200000);
    }
}
```

#### Constructor met parameter\(s\)

Soms wil je argumenten aan een object meegeven bij creatie. We willen bijvoorbeeld de leeftijd meegeven die het object moet hebben bij het aanmaken. Met andere woorden, stel dat we dit willen schrijven:

```csharp
Student jos= new Student(19);
```

Als we dit met voorgaande klasse , die enkel een default constructor heeft, uitvoeren zal de code een fout geven. C\# vindt geen constructor die een int als parameter aanvaardt.

[Net zoals bij overloading van methoden](https://github.com/v-nys/cursusprogrammeren/tree/e865f37d2ea41dc32c32aa2e02a9a763c7ea56f5/semester-1-programming-principles/h6-methoden/3_advancedmethod.md) kunnen we ook constructors overloaden. De code is verrassen gelijkaardig als bij method overloading:

```csharp
class Student
{
    public Student(int startage)
    {
        age= startage
    }

    private int age;
}
```

Dat was eenvoudig. **Maar** denk eraan: je hebt een eigen constructor geschreven en dus heeft C\# gezet "ok, je schrijft zelf constructor, trek je plan. Maar de default zal je ook zal moeten schrijven!" Je kan nu enkel je objecten met `new Student(25)` aanmaken. Schrijf je `new Student()` dan zal je een error krijgen. Wil je die constructor nog hebben, dan zal je die met de hand moeten schrijven, bijvoorbeeld:

```csharp
class Student
{
    public Student(int startage) // met parameter
    {
        age= startage;
    }

    public Student() //default
    {
        Random r= new Random();
        age= r.Next(10,20);
    }

    private int age;
}
```

#### Wanneer heb ik constructoren nodig?

Tot zeer recent maakten we onze objecten steeds aan met de default constructor. Pas daarna gaven we eventuele properties de juiste waarde. Dat houdt een risico in: er is een periode waarin onze objecten nog niet "af" zijn. In het slechtste geval vergeten we zelfs om de properties in te stellen en krijgen we objecten die misschien ongeldig zijn.

Constructoren helpen dit probleem te voorkomen. Als we één constructor hebben, bijvoorbeeld `Student(string name)`, **moeten** we die gebruiken. We kunnen dus niet vergeten bijvoorbeeld `frankVermeulen.Name = "Frank Vermeulen"` te schrijven, want we worden gedwongen meteen `new Student("Frank Vermeulen")` te schrijven.

Samengevat: **als er eigenschappen zijn die je meteen bij het aanmaken van een object wil instellen, maak er dan parameters van een constructor voor**.

**Overloaded constructoren**

Wil je meerdere overloaded constructors, dan mag dat ook. Je wilt misschien een constructor die de leeftijd vraag alsook een bool om mee te geven of het om een werkstudent gaat:

```csharp
class Student
{
    public Student(int startage) //overloaded
    {
        age= startage;
    }

    public Student(int startage, bool werkstart) //overloaded
    {
        age= startage;
        isWerkStudent= werkstart;
    }

    public Student() //default
    {
        Random r= new Random();
        age= r.Next(10,20);
    }

    private int age;
    private bool isWerkStudent
}
```

**Constructor chaining**

Als je meerdere overloaded constructoren hebt, hoef je niet in elke constructor alle code voor objectinitialisatie te schrijven. Het sleutelwoordje `this` biedt de mogelijkheid **eerst** een andere constructor aan te roepen en eventueel andere operaties toe te voegen. Dit heet **constructor chaining**. In bovenstaand voorbeeld kan je ook dit schrijven:

```csharp
class Student
{
    public Student(int startage) : this(startage, false)
    {
    // niet nodig hier code uit uitgebreidere constructor te herhalen
    // hier kan nog extra code worden uitgevoerd na de oproep van de uitgebreide constructor
    }

    public Student(int startage, bool werkstart) //overloaded
    {
        age= startage;
        isWerkStudent=werkstart;
    }

    public Student() //default
    {
        // helaas wordt onderstaande code pas **na** de chained constructor opgeroepen
    // gebruik van this heeft hier dus niet veel zin
        Random r= new Random();
        age= r.Next(10,20);
    }

    private int age;
    private bool isWerkStudent
}
```

