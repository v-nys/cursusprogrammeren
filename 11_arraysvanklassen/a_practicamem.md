# Oefening 1: prijzen met `foreach` (h11-prijzen)

## Leerdoelen

* `foreach`
* combinatie controlestructuren

## Functionele analyse

We willen enkele gegevens (prijzen) inlezen van de gebruiker en slechts sommige van deze prijzen tonen.

## Technische analyse

* Werk onderstaande opdracht uit in een statische methode `AskForPrices`.
* Maak eerst een array die tot 20 prijzen (type `double`) kan bewaren.
* Vraag aan de gebruiker om 20 prijzen in te voeren en bewaar elke prijs in de array.
* Doorloop vervolgens **m.b.v. een `foreach`-lus** de volledige array.
  * Toon enkel de elementen op het scherm wiens prijs hoger of gelijk is aan €5.00.
* Toon op het einde van het programma het gemiddelde van alle prijzen (dus inclusief de lagere prijzen).
* Toon alles afgerond tot twee cijfers na de komma.

### Voorbeeldinteractie
```text
Gelieve 20 prijzen in te geven.
> 1
> 1
> 1
> 21
> 1
> 1
> 1
> 1
> 1
> 17
> 1
> 1
> 1
> 14
> 1
> 1
> 1
> 1
> 1
> 1
21.00
17.00
14.00
Het gemiddelde bedrag is 3.00.
```


# Oefening 2: speelkaarten (h11-speelkaarten)

## Leerdoelen

* `foreach` genest
* `List`

## Functionele analyse

We willen een kaartenspel programmeren. Om dat te doen, moeten we zeker een lijst kaarten kunnen aanmaken en ook kaarten te kunnen trekken.

## Technische analyse

* Maak een klasse ``PlayingCard``.
  * Een kaart heeft 2 eigenschappen (properties)
    * een getal van 1 tot en met 13 (boer=11, koningin= 12, heer= 13):
    * een kleur, de zogenaamde "suite". Deze stel je voor via een enumtype `Suites` en kan als waarden `Clubs` (klaveren), `Hearts` (harten), `Spades` (schoppen) of `Diamonds` (ruiten) zijn.
* Schrijf een statische methode `GenerateDeck` die een boek kaarten teruggeeft.
  * Schrijf om dit te bereiken twee `foreach` loops die de 52 kaarten van een standaard pak in een ``List<PlayingCard>`` plaatsen.
    * Doe dit door één lus in een andere te nesten.
* Schrijf ook een statische methode `ShowShuffledDeck(List<PlayingCard> cards)` die telkens een willekeurige kaart uit de deck trekt en deze aan de gebruiker toont. De kaart wordt na het tonen dus uit de lijst verwijderd.
  * Doe dit door in iedere stap een willekeurige, geldige index in de lijst met kaarten te berekenen en die kaart uit de lijst te halen.

## Voorbeeldinteractie
```
9 Hearts
4 Clubs
... (er volgen nog 50 willekeurige combinaties)
Alle kaarten zijn getoond.
```

# Student Organizer

We gaan nu de Student-klasse uit een vorige hoofdstuk (zie onderaan de opgave) gebruiken om een ``List<Student>`` van studenten te vullen.

Maak daarom een studenten-lijst aan die 5 studenten bevat:

Initialiseer alle properties van iedere student op een standaard-waarde via de default constructor.
 
Het programma start op en geeft de gebruiker een menu waaruit kan gekozen worden:

1. Student gegevens invoeren (eerstvolgende student wordt ingevuld)
Vervolgens moet de gebruiker kiezen welke student (nummer) moet ingevuld worden, van 1 tot 5. Vervolgens kan de gebruiker de gegevens 1 voor 1 invullen (oude gegevens worden zonder pardon overschreven).

 
2. Student gegevens tonen (alle studenten)
Wanneer de gebruiker voor 2 kiest dan wordt de GeefOverzicht-methode aangeroepen van iedere student zodat de 5 ‘rapportjes’ onder elkaar op het scherm 

Extra's:
Bouw extra functionaliteit naar keuze bij de StudentOrganizer, zoals:
* Vragen aan de gebruiker of de oude gegevens overschreven mogen worden, indien deze reeds ingevuld zijn.
* Inbouwen van een eenvoudige zoekfunctie. Je kan bijvoorbeeld zoeken op naam (exacte invoer) of alle studenten tonen die in een bepaalde klas zitten of wiens punten onder/boven een bepaalde waarde zitten. Je kan dit als extra menuitem inbouwen, waarbij een nieuw menu verschijnt dat de gebruiker de verschillende zoekmogelijkheden voorstelt.
* Verwijderen van een student (waarbij alle gegevens worden gewist)
* Controle in alle methode inbouwen zodat ‘lege studenten’ worden genegeerd. Wanneer bijvoorbeeld menu item 2 wordt uitgevoerd (alle studenten tonen) dan worden enkel de ingevulde studenten getoond.

{% hint style="warning" %}
Volgende oefeningen kunnen nog licht wijzigen.
{% endhint %}

### StudentKlasse
```csharp
enum Klassen { EA1, EA2, EA3, EA4}

class Student
{
    public string Naam { get; set; }
    public int Leeftijd { get; set; }
    public Klassen Klas { get; set; }

    public int PuntenCommunicatie { get; set; }
    public int PuntenProgrammingPrinciples { get; set; }
    public int PuntenWebTech { get; set; }

    public double BerekenTotaalCijfer()
    {
        return (PuntenCommunicatie + PuntenProgrammingPrinciples + PuntenWebTech) / 3.0;
    }

    public void GeefOverzicht()
    {
        Console.WriteLine($"{Naam}, {Leeftijd} jaar");
        Console.WriteLine($"Klas: {Klas}");
        Console.WriteLine();
        Console.WriteLine("Cijferrapport");
        Console.WriteLine("*************");
        Console.WriteLine($"Communicatie:\t\t{PuntenCommunicatie}");
        Console.WriteLine($"Programming Principles:\t{PuntenProgrammingPrinciples}");
        Console.WriteLine($"Web Technology:\t\t{PuntenWebTech}");
        Console.WriteLine($"Gemiddelde:\t\t{BerekenTotaalCijfer():0.0}");
    }
}
```

# Bookmark Manager

Maak een "bookmark manager". Deze tool zal in de console aan de gebruiker 5 favoriete sites vragen: naam en url. Vervolgens zal de tool alle sites in een lijst tonen met een nummer voor. De gebruiker kan dan de nummer intypen en de tool zal automatisch de site in de browser openen. 

Je opdracht:

1. Maak een array waarin je 5 bookmark objecten kan plaatsen. 
2. Vul de applicatie aan zodat de gebruiker: een bestaand bookmark kan verwijderen en een bestaand bookmark kan aanpassen

Enkele zaken die je nodig hebt:

**BookMark klasse:**
```csharp
class BookMark
{

    public string Naam { get; set; }
    public string URL { get; set; }
    public void OpenSite()
    {
        Process.Start("chrome.exe", URL);  //Voeg bovenaan using System.Diagnostics; toe
    }
}
```

Opmerking: je mag gerust een andere browser hier zetten (bv ``iexplore.exe``). Om te weten of hij dat proces kent, klikt op Start->Run/uitvoeren en voer daar bijvoorbeeld ``chrome.exe`` in. Als je op enter duwt en je browser opent, dan weet je dat hij dat proces zal vinden.

Voorbeeld van hoe de bookmark klasse zal werken:

```csharp
BookMark u = new BookMark();
u.Naam = "Windows";
u.URL = "www.google.be";
u.OpenSite();
```
