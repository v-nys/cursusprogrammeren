# Oefeningen

## Richtlijnen
### Structuur oefeningen
Vanaf hier veronderstellen we dat je in één groot project werkt dat één klasse `Program` heeft. De oefeningen worden los van elkaar omschreven, maar je zorgt ervoor dat ze getest kunnen worden via het keuzemenu in je klasse `Program`.

### Opmerkingen *na* de les over `DateTime` en *voor* de les over properties en objectmethodes
Als je een object wil voorzien van een bepaalde eigenschap (met andere woorden, data), doe je dit voorlopig als volgt:

#### bijhouden van data
```csharp
...
class MyClass {
    public <datatype> MyAttribute {
        get;
	set;
    }
}
```

Hier is `<datatype>` het soort data dat je wil bijhouden in een object (`int`,`string`,...) en is `MyAttribute` de naam die je geeft aan deze data.

Bijvoorbeeld:
```csharp
...
class Car {
    public double Speed {
        get;
	set;
    }
}
```

Dit wil zeggen dat een auto een snelheid heeft. Als `myCar` een object is van type `Car`, kan je `myCar.Speed` opvragen en aanpassen.

#### bijhouden van gedrag
Als je een object van gedrag wil voorzien, doe je dit voorlopig als volgt:

```csharp
...
public class MyClass {
    public <datatype> MyMethod(<datatype><argument 1>,...) {
        // hier pas je data van dit object aan, print je dingen op het scherm, enz.
    }
}
```

Bijvoorbeeld:
```csharp
...
public class Car {
    public void IncreaseSpeed() {
        // als we de property Speed van boven hebben
	Speed = 1.1 * Speed;
	Console.WriteLine("Snelheid van deze auto is verhoogd.");
    }
}
```

## Oefening: H8-dag-van-de-week

### Leerdoelen

* aanmaken van `DateTime` objecten
* formatteren van `DateTime` objecten

### Functionele analyse

We willen voor een willekeurige datum kunnen bepalen welke dag van de week het is.

### Technische analyse
* je moet eerst de dag, maand en jaar opvragen en een `DateTime` aanmaken
* daarna moet je laten zien over welke dag van de week het gaat
  * gebruik hiervoor formattering van een `DateTime`
  * laat ook de datum zelf zien in een formaat dat leesbaar is voor de gebruiker
  * als je computer niet volledig ingesteld is op Belgisch Nederlands, kan het resultaat er wat anders uitzien.
* noem de klasse waarin je dit schrijft `DayOfWeekProgram`
  * schrijf je code in de statische methode `Main`
  * roep de statische `Main` van `DayOfWeekProgram` op in het keuzemenu van `Program`

### Voorbeeldinteractie
```text
Welke dag?
> 14
Welke maand?
> 2
Welk jaar?
> 2020
14 februari 2020 is een vrijdag.
```

## Oefening: H8-ticks-sinds-2000

### Leerdoelen

* aanmaken van `DateTime` objecten

### Functionele analyse

We willen weten hoe veel fracties van een seconde al verlopen zijn sinds het begin van de jaren 2000.

### Technische analyse
* .NET stelt deze fracties (1 / 10000 milliseconden) voor als "ticks"
* We willen weten hoe veel ticks er voorbijgegaan zijn sinds het absolute begin van het jaar 2000
* Noem de klasse waarin je dit schrijft `Ticks2000Program`

### Voorbeeldinteractie
```text
Sinds 1 januari 2000 zijn er (hier wordt het aantal getoond) ticks voorbijgegaan.
```

## Oefening: H8-schrikkelteller

### Leerdoelen

* gebruik van een statische property

### Functionele analyse

We willen bepalen hoe veel schrikkeljaren er zijn tussen 1800 en 2020.

### Technische analyse
* implementeer zelf een logica voor schrikkeljaren, maar laat dit over aan de klassen `DateTime`
* maak gebruik van een statische methode van deze klasse

### Voorbeeldinteractie
```text
Er zijn (hier wordt het aantal getoond) schrikkeljaren tussen 1800 en 2020.
```


## Oefening: H8-simpele-timing

### Leerdoelen
* eenvoudig code leren timen
* gebruiken van `DateTime`
* herhaling arrays

### Functionele analyse
We zijn benieuwd hoe lang het duurt een array van 1 miljoen `int`s te maken en op te vullen met de waarden 1,2,...

### Technische analyse
* Bepaal het tijdstp voor en na aanmaken van de array.
* Vul de array in met een `for`-lus.
* Noem de klasse waarin je dit schrijft `ArrayTimerProgram`

### Voorbeeldinteractie
```text
Het duurt (hier wordt het aantal getoond) milliseconden om een array van een miljoen elementen aan te maken en op te vullen met opeenvolgende waarden.
```

## Oefening: H8-RapportModule-V1

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van simpele properties en methodes

### Functionele analyse

Dit programma geeft op basis van de input van een percentage de graad weer die je met dit gegeven zou behaald hebben.

### Technische analyse

Ontwerp een klasse `ResultV1` die je zal tonen wat je graad is gegeven een bepaald behaald percentage. Het enige dat je aan een `ResultV1`-object moet kunnen geven is het behaalde percentage. Enkel het totaal behaalde percentage wordt bijgehouden. Via een methode `PrintHonors` kan de behaalde graad worden weergegeven. Dit zijn de mogelijkheden:

* &lt; 50: niet geslaagd;
* tussen 50 en 68: voldoende;
* tussen 68 en 75: onderscheiding;
* tussen 75 en 85: grote onderscheiding;
* &gt; 85: grootste onderscheiding.

Je hoeft voorlopig geen rekening te houden met ongeldige waarden. Test je klasse door enkele objecten van de klasse `ResultV1` in je Main aan te maken en de verschillende properties waarden te geven en methoden aan te roepen.

## Oefening: H8-RapportModule-V2

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van simpele properties en methodes

### Functionele analyse

Dit programma geeft op basis van de input van een percentage de graad weer die je met dit gegeven zou behaald hebben.

### Technische analyse

Ontwerp een klasse `ResultV2` die je zal vertellen wat je graad is gegeven een bepaald behaald percentage. Het enige dat je aan een `ResultV2`-object moet kunnen geven is het behaalde percentage. Enkel het totaal behaalde percentage wordt bijgehouden. Via een methode `ComputeHonors` kan de behaalde graad worden teruggegeven. Dit werkt op dezelfde manier als in versie 1 van deze oefening, maar de verschillende graden worden voorgesteld met een `Enum`, `Honors`. De methode `ComputeHonors` toont het resultaat niet, maar geeft een waarde van deze `Enum` terug. Het is aan de `Main` om deze waarde af te printen, zodat je kan zien of je code werkt.

Test je klasse op dezelfde manier als versie 1.

## Oefening: H8-Getallencombinatie

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van properties om geldige waarden af te dwingen

### Functionele analyse

Dit programma geeft op basis van de input van twee getallen de som van beide getallen, het verschil, het product en de deling. In het laatste geval en indien er een deling door nul zou worden uitgevoerd, wordt dit woordelijk weergegeven.

### Technische analyse

Maak een eenvoudige klasse `NumberCombination`. Deze klasse bevat 2 getallen \(type `int`\). Er zijn 4 methoden:

* `Sum`: geeft som van beide getallen weer
* `Difference`: geeft verschil van beide getallen weer
* `Product`: geeft product van beide getallen weer
* `Quotient`: geeft deling van beide getallen weer. Print `"Error"` indien je zou moeten delen door 0.

Toon in je main aan dat je code werkt.

Volgende code zou namelijk onderstaande output moeten geven:

```csharp
    NumberCombination pair1 = new NumberCombination();
    pair1.Number1 = 12;
    pair1.Number2 = 34;
    Console.WriteLine("Paar:" + pair1.Number1 + ", " + pair1.Number2);
    Console.WriteLine("Sum = " + pair1.Som());
    Console.WriteLine("Verschil = " + pair1.Verschil());
    Console.WriteLine("Product = " + pair1.Product());
    Console.WriteLine("Quotient = " + pair1.Quotient());
```

#### Voorbeeldinteractie\(s\)

```text
Paar: 12, 34
Som = 46
Verschil = -22
Product = 408
Quotient = 0,352941176470588
```

## Oefening: H8-Figuren

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van properties om geldige waarden af te dwingen

### Functionele analyse

Dit programma maakt enkele rechthoeken en driehoeken met gegeven afmetingen \(in meter\) aan, berekent hun oppervlakte en toont deze info aan de gebruiker. De rechthoeken en driehoeken die worden aangemaakt, zijn al gecodeerd in het programma. De gebruiker hoeft dus niets anders te doen dan het programma te starten.

### Technische analyse

#### Voorbeeldinteractie\(s\)

```text
Een rechthoek met een breedte van 2,2m en een hoogte van 1,5 m heeft een oppervlakte van 3,3m².
Een rechthoek met een breedte van 3m en een hoogte van 1 m heeft een oppervlakte van 3m².
Een driehoek met een basis van 3m en een hoogte van 1 m heeft een oppervlakte van 1,5m².
Een driehoek met een basis van 2m en een hoogte van 2 m heeft een oppervlakte van 2m².
```

### Technische hulp

#### Programmaverloop

Er is een klasse `Rectangle` met **properties** `Width` en `Height` en een klasse `Triangle` met `Base` en `Height`. Je programma maakt de figuren die hierboven beschreven worden aan via constructoren zonder parameters en stelt daarna hun afmetingen in. De oppervlakte wordt berekend door middel van een methode `ComputeSurface`, zonder parameters, met een `double` als resultaat.

#### Testscenario's
* Test uit met de figuren beschreven in de voorbeeldinteractie. Doe dit door de objecten aan te maken in de `Main`, hen zelf hun oppervlakte te laten berekenen en deze te printen in de `Main`.

## Oefening: H8-Studentklasse

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van properties om geldige waarden af te dwingen

### Functionele analyse

Dit programma vraagt om de naam en leeftijd van een student. Er moet ook worden meegeven in welke klasgroep de student is ingeschreven. Vervolgens worden de punten voor 3 vakken gevraagd, waarna het gemiddelde wordt teruggegeven. 

### Technische analyse

Maak een nieuwe klasse `Student`. Deze klasse heeft 6 properties:

* Name \(string\)
* Age \(int\)
* Class \(maak hiervoor een `enum`\)
* MarkCommunication \(int\)
* MarkProgrammingPrinciples \(int\)
* MarkWebTech \(int\)

Voeg aan de klasse een methode `ComputeOverallMark` toe. Wanneer deze methode wordt aangeroepen dan wordt het gemiddelde van de 3 punten teruggegeven als double zodat dit op het scherm kan getoond worden.

Voeg aan de klasse ook de methode `ShowOverview` toe. Deze methode zal een volledig rapport van de student tonen \(inclusief het gemiddelde m.b.v. de `ComputeOverallMark`-methode\).

Test je programma door enkele studenten aan te maken en in te stellen. Volgende main zou dan de bijhorende output moeten krijgen:

```csharp
    Student student1= new Student();
    student1.Class = Classes.EA2;
    student1.Age = 21;
    student1.Name = "Joske Vermeulen";
    student1.MarkCommunication = 12;
    student1.MarkProgrammingPrinciples = 15;
    student1.MarkWebTech = 13;
    student1.ShowOverview();
```

#### UI

Console applicatie

#### Voorbeeldinteractie\(s\)

```text
Joske Vermeulen, 21 jaar
Klas: EA2

Cijferrapport:
**********
Communicatie:             12
Programming Principles:   15
Web Technology:           13
Gemiddelde:               13.3
```

# Voorbeeld abstractie (h8-honden)
## Doelstelling
- Kennismaking met OOP
- Kennismaking met refactoring
- Toepassing van abstractie

## Functionele analyse
We krijgen een programma dat al objecten bevat, maar dit programma moet zelf nog veel rekening houden met hoe deze objecten in elkaar zitten. We **refactoren** het om zo een meer objectgericht en beter onderhoudbaar programma te bekomen.

## Technische analyse
Je krijgt volgende twee files. De bestandsnamen volgen de afspraak:
```
using System;

namespace OOP {
    class BarkingProgram {

        // nu maken we onze randomgenerator *buiten* Main
        public static Random rng = new Random();
        public static void Main() {
            BarkingDog dog1 = new BarkingDog();
            BarkingDog dog2 = new BarkingDog();
            dog1.Name = "Swieber";
            dog2.Name = "Misty";
	    dog1BreedNumber = rng.Next(0,3);
	    dog2BreedNumber = rng.Next(0,3);
            if(dog1BreedNumber == 0) {
                dog1.Breed = "German Shepherd";
            }
            else if(dog1BreedNumber == 1) {
                dog1.Breed = "Wolfspitz";
            }
	    else {
	        dog1.Breed = "Chihuahua";
            }
            if(dog2BreedNumber == 0) {
                dog2.Breed = "German Shepherd";
            }
            else if(dog2BreedNumber == 1) {
                dog2.Breed = "Wolfspitz";
            }
	    else {
	        dog2.Breed = "Chihuahua";
            }
            while(true) {
                Console.WriteLine(dog1.Bark());
                Console.WriteLine(dog2.Bark());
            }
        }
    }
}
```
en
```
namespace OOP {
    class BarkingDog {
        public string Name;
        public string Breed;

        public string Bark() {
            if(Breed == "German Shepherd") {
                return "RUFF!";
            }
            else if(Breed == "Wolfspitz") {
                return "AwawaWAF!";
            }
	    else if(Breed == "Chihuahua") {
		return "ARF ARF ARF!";
	    }
            // dit zou nooit mogen gebeuren
            // maar als de programmeur van Main iets fout doet, kan het wel
            else {
                return "Euhhh... Miauw?";
            }
        }
    }
}
```

Volg hierbij volgende stappen:
- Maak de random generator statisch onderdeel van de klasse `BarkingDog`.
- Voeg volgende code toe **binnen** de klasse `BarkingDog`:
```
        public BarkingDog() {
	      // bepaal hier met de randomgenerator het ras van de hond
	      // deze code wordt uitgevoerd wanneer een nieuwe hond wordt aangemaakt
        }
```

Test uiteindelijk via de `Main` van `Program` de `Main` van `BarkingProgram`.

## H8-uniform-soldiers

### Functionele analyse
Je krijgt code die deel zou kunnen uitmaken van een videogame. Met deze code wordt bijgehouden hoe veel schade elke soldaat aanricht. De schade is niet constant. Als je een upgrade aankoopt, doen al je soldaten dubbel zo veel schade als eerder. We hebben al werkende code, maar ze maakt het moeilijk te verzekeren dat elke soldaat even veel schade aanricht. Pas aan zodat dit ingebakken is in de code.

### Technische analyse
Je krijgt volgende klassen (`SoldierGame` en `Soldier`):
```text
using System;

namespace OOP {
    class SoldierGame {
        public static void Main() {
            Soldier soldier1 = new Soldier();
            soldier1.Health = 100;
            soldier1.Damage = 20;
            Soldier soldier2 = new Soldier();
            soldier2.Health = 99; // om maar te tonen dat dit mag verschillen per soldaat
            soldier2.Damage = 20;
            Soldier soldier3 = new Soldier();
            soldier3.Health = 98;
            soldier3.Damage = 20;
            // beeld je in dat de game wat verder loopt
            // nu volgt de upgrade
            soldier1.Damage *= 2;
            soldier2.Damage *= 2;
            soldier3.Damage *= 2;
        }
    }
}
```

```text
namespace OOP {
    class Soldier {
        public int Health;
        public int Damage;
    }
}
```

Zorg ervoor dat alle soldaten automatisch dezelfde hoeveelheid schade doen. Gebruik hiervoor een sleutelwoordje dat aan bod gekomen is in de les rond `DateTime`.

## H8-utility-methode

### Functionele analyse
We hebben code voor een berekening. Deze werkt, maar vereist dat we een object aanmaken dat geen duidelijke functie heeft, namelijk een `MyMath`-object. Het is moeilijk te zeggen wat "één wiskunde" betekent, dus we zouden liefst niet met objecten werken.

### Technische analyse
Je krijgt twee klassen, `MathProgram` en `MyMath`. Pas aan zodat je dezelfde berekening kan uitvoeren, zonder dat je objecten van de klasse `MyMath` hoeft aan te maken.

```text
using System;

namespace OOP {
    class MathProgram {
        public static void Main() {
            MyMath calculcator = new MyMath();
            Console.WriteLine(calculator.DoubleAddTwo(13));
        }
    }
}
```
en
```text
namespace OOP {
    class MyMath {
        public int DoubleAddTwo(int n) {
            return 2*n+2;
        }
    }
}
```

## Alledaags

Zoek een foto naar keuze \(nieuws, privé, etc\) waarop meer dan één element opstaat \(dus geen pasfoto of foto van blauwe lucht zonder wolken\). Tracht de nodige klassen te verzinnen en verzin minstens 1 auto-property en 1 methode per klasse. Maak in een console-applicatie vervolgens objecten van deze klassen aan en test ze. Voeg de foto aan je solution-folder toe.

Bijvoorbeeld: een foto van een betoging. Je zou minstens 3 klassen kunnen verzinnen \(gebouw, politie, betoger\). Van ieder van deze klassen maak je dan objecten aan zoals je ze op de foto ziet \(uiteraard gaan we geen 30 betoger-instanties maken, enkele zijn genoeg, als voorbeeld\).

## Oefening: H8-RapportModule-V3

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van properties om geldige waarden af te dwingen

### Functionele analyse

Dit programma geeft op basis van de input van een percentage de graad weer die je met dit gegeven zou behaald hebben.

### Technische analyse

Ontwerp een klasse Resultaat die je zal tonen wat je graad is gegeven een bepaald behaald percentage. Het enige dat je aan een Resultaat-object moet kunnen geven is het behaalde percentage. Enkel het totaal behaalde % wordt bijgehouden via een auto-property. Via een methode PrintGraad kan de behaalde graad worden weergegeven. Dit zijn de mogelijkheden:

* &lt; 50: niet geslaagd;
* tussen 50 en 68: voldoende;
* tussen 68 en 75: onderscheiding;
* tussen 75 en 85: grote onderscheiding;
* &gt; 85: grootste onderscheiding.

Test je klasse door enkele objecten in je main aan te maken en de verschillende properties waarden te geven en methoden aan te roepen.

#### UI

Console applicatie


## PizzaTime

Maak een klasse Pizza. Deze klasse heeft een aantal private fields:

* toppings \(string\): bevat beschrijving van wat er op ligt, bv. ananas, pepperoni, etc.
* diameter \(integer\): doorsnede van de pizza in cm.
* price \(double\): prijs van de pizza in euro.

Zorg ervoor dat je met behulp van properties deze 3 velden kan uitlezen en aanpassen. Bouw controle in zodat de fields geen foute waarden kunnen gegeven worden \(denk maar aan negatieve prijs en diameter, pizza zonder topping, etc.\). Maak in je main een aantal pizza-instanties aan en toon de werking van de properties aan.

## Sports

### Sportspeler

Kies je favoriete sport of game \(voor zij die enkel pc/console-sporten \). Maak een klasse aan die een speler uit deze sport kan voorstellen. Verzin een 4-tal private datavelden die deze spelers hebben, alsook 2 methoden die de speler moet kunnen uitvoeren.

Voorzie een methode `StelIn` die je toelaat om de private datafields in te stellen:

Voorzie ook minstens 1 "Naam" \(string\) dataveld.

Voorzie per data field ook telkens een full property. Waar nodig zorg je er voor dat er geen illegale waarden kunnen ingesteld worden \(bv mutsnummer bij waterpolo gaat maar van 1 tot 13\).

Bijvoorbeeld:

* klasse Waterpolospeler
* datavelden:
  * spelerNaam\(string\)
  * mutsnummer \(int\)
  * isDoelman \(bool\)
  * isReserve\(bool\)
  * reeks \(string, bv "Cadet"\)

Methoden: GooiBal, Watertrappen, StelIn

De methode `StelIn` zou dan zou kunnen aangeroepen worden:

```csharp
speler1.StelIn("Tim", 5, false, true, "tweedeklas");
```

Wanneer de methoden worden aangeroepen zal er een tekst \(mbv Console.WriteLine in de methode\) op het scherm verschijnen die bv zegt `Ik (Jos) gooi de bal`. Waarbij de naam van de speler in kwestie uit het Naam dataveld wordt gebruikt om mee getoond te worden.

Maak vervolgens een console-applicatie aan waarin je de werking van de klasse aantoont. Maar in de applicatie een aantal speler-objecten aan, vervolgens stel je hun properties in. Vervolgens roep je enkele methoden van de spelers aan en toon je via \(Console.WriteLine\) ook de properties van de individuele spelerobjecten.

Toon maw aan dat je:

* Een klasse kunt maken \(in een aparte file!\)
* Instanties \(objecten\) van deze klasse kunt maken
* Kunt werken met deze instanties \(properties instellen én uitlezen, aanroepen van methoden\)

### Sport simulator

Schrijf een methode genaamd: `static void SimuleerSpeler(Waterpolospeler testspeler)`

\(vervang Waterpolospeler door de klasse die je zelf hebt gemaakt\)

De SimuleerSpeler-methode zal beide methoden van je klasse telkens 3x aanroepen m.b.v. een for-loop in de methode \(dus in mijn geval 3x GooiBal en 3xWatertrappen\)

Test je methode door 2 objecten aan te maken en telkens mee te geven als parameter.

### Pro enums

Kan je in voorgaand voorbeeld het dataveld `reeks` vervangen door een dataveld reeks dat een enum als datatype heeft?

