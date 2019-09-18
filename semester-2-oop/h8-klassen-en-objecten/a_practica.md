# Labo-oefeningen

## Alledaags

Zoek een foto naar keuze \(nieuws, privé, etc\) waarop meer dan één element opstaat \(dus geen pasfoto of foto van blauwe lucht zonder wolken\). Tracht de nodige klassen te verzinnen en verzin minstens 1 auto-property en 1 methode per klasse. Maak in een console-applicatie vervolgens objecten van deze klassen aan en test ze. Voeg de foto aan je solution-folder toe.

Bijvoorbeeld: een foto van een betoging. Je zou minstens 3 klassen kunnen verzinnen \(gebouw, politie, betoger\). Van ieder van deze klassen maak je dan objecten aan zoals je ze op de foto ziet \(uiteraard gaan we geen 30 betoger-instanties maken, enkele zijn genoeg, als voorbeeld\).

## RapportModule

Ontwerp een klasse Resultaat die je zal tonen wat je graad is gegeven een bepaald behaald percentage. Het enige dat je aan een Resultaat-object moet kunnen geven is het behaalde percentage. Enkel het totaal behaalde % wordt bijgehouden via een auto-property. Via een methode PrintGraad kan de behaalde graad worden weergegeven. Dit zijn de mogelijkheden:

* &lt; 50: niet geslaagd;
* tussen 50 en 68: voldoende;
* tussen 68 en 75: onderscheiding;
* tussen 75 en 85: grote onderscheiding;
* &gt; 85: grootste onderscheiding.

Test je klasse door enkele objecten in je main aan te maken en de verschillende properties waarden te geven en methoden aan te roepen.

## Nummers

Maak een eenvoudige klasse Nummers. Deze klasse bevat 2 getallen \(type int\) die via een autoproperty kunnen aangepast worden. Er zijn 4 methoden:

* `Som`: geeft som van beide getallen weer
* `Verschil`: geeft verschil van beide getallen weer
* `Product`: geeft product van beide getallen weer
* `Quotient`: geeft deling van beide getallen weer. Toon "Error" indien je zou moeten delen door 0.

Toon in je main aan dat je code werkt.

Volgende code zou namelijk onderstaande output moeten geven:

```csharp
    Nummers paar1 = new Nummers();
    paar1.Getal1 = 12;
    paar1.Getal2 = 34;

    Console.WriteLine("Paar:" + paar1.Getal1 + ", " + paar1.Getal2);
    Console.WriteLine("Som = " + paar1.Som());
    Console.WriteLine("Verschil = " + paar1.Verschil());
    Console.WriteLine("Product = " + paar1.Product());
    Console.WriteLine("Quotient = " + paar1.Quotient());
```

Output:

```text
Paar: 12, 34
Som = 46
Verschil = -22
Product = 408
Quotient = 0,352941176470588
```

## Oefening: H8-figuren
### Leerdoelen
* werken met klassen en objecten
* gebruik maken van properties om geldige waarden af te dwingen

### Functionele analyse
Dit programma maakt enkele rechthoeken en driehoeken met gegeven afmetingen (in m.) aan, berekent hun oppervlakte en toont deze info aan de gebruiker. De rechthoeken en driehoeken die worden aangemaakt, zijn al gecodeerd in het programma. De gebruiker hoeft dus niets anders te doen dan het programma te starten.

### Technische analyse
#### UI
console applicatie
#### voorbeeldinteractie(s)
```
Een rechthoek met een breedte van 2.2m en een hoogte van 1.5 m heeft een oppervlakte van 3.3m².
Een rechthoek met een breedte van 3m en een hoogte van 1 m heeft een oppervlakte van 3m².
Een driehoek met een basis van 3m en een hoogte van 1 m heeft een oppervlakte van 1.5m².
Een driehoek met een basis van 2m en een hoogte van 2 m heeft een oppervlakte van 2m².
```

### Technische hulp
#### Programmaverloop
Er is een klasse `Rectangle` met **properties** `width` en `height` en een klasse `Triangle` met `base` en `height`. Je programma maakt de figuren die hierboven beschreven worden aan via constructoren zonder parameters en stelt daarna hun afmetingen in. Wanneer je de setter probeert uit te voeren met een waarde kleiner dan 1, wordt er een exception gegooid. De oppervlakte wordt berekend door middel van een methode `ComputeSurface`, zonder parameters.

#### Testscenario's
* Test uit dat je geen enkele afmeting kleiner kan maken dan 1, of het nu gaat om rechthoeken of driehoeken.
* Test uit met de figuren beschreven in de voorbeeldinteractie.

## PizzaTime

Maak een klasse Pizza. Deze klasse heeft een aantal private fields:

* toppings \(string\): bevat beschrijving van wat er op ligt, bv. ananas, pepperoni, etc.
* diameter \(integer\): doorsnede van de pizza in cm.
* price \(double\): prijs van de pizza in euro.

Zorg ervoor dat je met behulp van properties deze 3 velden kan uitlezen en aanpassen. Bouw controle in zodat de fields geen foute waarden kunnen gegeven worden \(denk maar aan negatieve prijs en diameter, pizza zonder topping, etc.\). Maak in je main een aantal pizza-instanties aan en toon de werking van de properties aan.

## Studentklasse

Maak een nieuwe klasse `Student`. Deze klasse heeft 6 properties:

* Naam \(string\)
* Leeftijd \(int\)
* Klas \(maak dit van een `enum`\)
* PuntenCommunicatie \(int\)
* PuntenProgrammingPrinciples \(int\)
* PuntenWebTech \(int\)

Voeg aan de klasse een methode `BerekenTotaalCijfer` toe. Wanneer deze methode wordt aangeroepen dan wordt het gemiddelde van de 3 punten teruggegeven als double zodat dit op het scherm kan getoond worden.

Voeg aan de klasse ook de methode `GeefOverzicht` toe. Deze methode zal een volledig "Rapport" van de student tonen \(inclusief het gemiddelde m.b.v. de BerekenTotaalCijfer-methode\).

Test je programma door enkele studenten aan te maken en in te stellen. Volgende main zou dan de bijhorende output moeten krijgen:

```csharp
    Student student1= new Student();
    student1.Klas = Klassen.EA2;
    student1.Leeftijd = 21;
    student1.Naam = "Joske Vermeulen";
    student1.PuntenCommunicatie = 12;
    student1.PuntenProgrammingPrinciples = 15;
    student1.PuntenWebTech = 13;

    student1.GeefOverzicht();
```

Output:

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

