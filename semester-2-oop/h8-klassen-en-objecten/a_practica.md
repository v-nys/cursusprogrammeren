# Oefeningen

## Richtlijnen

### Structuur oefeningen

Vanaf hier veronderstellen we dat je in één groot project werkt dat één klasse `Program` heeft. Deze klasse heeft een `Main` methode die een keuzemenu opstart. Oefeningen rond eenzelfde topic worden \(statische\) methodes van één klasse met een methode `ShowSubmenu`, die je een menu toont van alle oefeningen over dat topic en die je toestaat een oefening naar keuze te testen. Dit wordt uitgelegd in de eerste oefening.

## Oefening: H10-voorbereiding

### Leerdoelen

* een ordelijke menustructuur voor je code voorzien

### Functionele analyse

We willen dat we alle oefeningen die we in dit vak maken op een ordelijke manier kunnen opstarten. We doen dit door een keuzemenu met twee niveaus te voorzien: de gebruiker kan elke reeds geschreven oefening uitvoeren door eerst het algemene onderwerp aan te geven en vervolgens de specifieke oefening.

### Technische analyse

* Laat in je Main methode een lijst van alle topics zien waarover oefeningen gemaakt zijn. In het begin is dit enkel `DateTime`. De gebruiker kan een topic aanduiden door een nummer in te geven, want voor elk topic staat ook een nummer.
* Gebruik een switch op de gebruikersinput om te bepalen van welk topic de `ShowSubmenu` methode moet worden opgeroepen. Deze methode heeft return type `void` en geen parameters.
* Voorzie een eerste klasse, `DateTimeExercises`, met deze methode `ShowSubmenu`. Totdat je oefeningen hebt om te demonstreren, toont `ShowSubmenu` gewoonweg de tekst `"Er zijn nog geen oefeningen over dit topic"`.
* Indien er wel oefeningen zijn \(deze oefening moet je dus updaten naarmate je vordert\), wordt elke reeds geprogrammeerde oefening genummerd en getoond en kan de gebruiker kiezen om deze uit te voeren.
* Nadat een oefening getest is, kan je opnieuw een topic en een oefening kiezen. Het programma eindigt nooit.

#### Voorbeeldinteractie

{% hint style="warning" %}
Dit is maar een voorbeeld! De getoonde topics en oefeningen gaan afhangen van wat je al gedaan hebt.
{% endhint %}

```text
Welkom bij de demo Objectgeoriënteerd Programmeren!
Topic van de uit te voeren oefening?
1. DateTime
2. Properties en access modifiers
> 1
Uit te voeren oefening?
1. H10-dag-van-de-week
2. H10-ticks-sinds-2000
3. H10-schrikkelteller
> 2
Sinds 1 januari 2000 zijn er (...) ticks voorbijgegaan.
Topic van de uit te voeren oefening?
(...)
```

## Oefening: H10-dag-van-de-week

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
* maak deze methode toegankelijk via `ShowSubmenu` van de klasse `DateTimeExercises`
* noem de methode waarin je dit schrijft `DayOfWeekProgram`

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

## Oefening: H10-ticks-sinds-2000

### Leerdoelen

* aanmaken van `DateTime` objecten

### Functionele analyse

We willen weten hoe veel fracties van een seconde al verlopen zijn sinds het begin van de jaren 2000.

### Technische analyse

* .NET stelt deze fracties \(1 / 10000 milliseconden\) voor als "ticks"
* We willen weten hoe veel ticks er voorbijgegaan zijn sinds het absolute begin van het jaar 2000
* maak deze methode toegankelijk via `ShowSubmenu` van de klasse `DateTimeExercises`
* Noem de methode waarin je dit schrijft `Ticks2000Program`

### Voorbeeldinteractie

```text
Sinds 1 januari 2000 zijn er (hier wordt het aantal getoond) ticks voorbijgegaan.
```

## Oefening: H10-schrikkelteller

### Leerdoelen

* gebruik van een statische methode

### Functionele analyse

We willen bepalen hoe veel schrikkeljaren er zijn tussen 1799 en 2021.

### Technische analyse

* implementeer zelf geen logica voor schrikkeljaren, maar laat dit over aan de klassen `DateTime`
* maak gebruik van een statische methode van deze klasse
* maak deze methode toegankelijk via `ShowSubmenu` van de klasse `DateTimeExercises`
* noem je methode `LeapYearProgram`

### Voorbeeldinteractie

```text
Er zijn (hier wordt het aantal getoond) schrikkeljaren tussen 1799 en 2021.
```

## Oefening: H10-simpele-timing

### Leerdoelen

* eenvoudig code leren timen
* gebruiken van `DateTime`
* herhaling arrays

### Functionele analyse

We zijn benieuwd hoe lang het duurt een array van 1 miljoen `int`s te maken en op te vullen met de waarden 1,2,...

### Technische analyse

* Bepaal het tijdstip voor en na aanmaken van de array.
* Vul de array in met een `for`-lus.
* maak deze methode toegankelijk via `ShowSubmenu` van de klasse `DateTimeExercises`
* Noem de methode waarin je dit schrijft `ArrayTimerProgram`

### Voorbeeldinteractie

```text
Het duurt (hier wordt het aantal getoond) milliseconden om een array van een miljoen elementen aan te maken en op te vullen met opeenvolgende waarden.
```

## Oefening: H10-verjaardag-v2

Leerdoelen

* leren werken met objecten
* gebruik maken van properties en methodes

### Functionele analyse

We zullen het programma uit om het aantal dagen tot een verjaardag te bepalen aanpassen zodat het aantal dagen tot de volgende verjaardag wordt getoond. Dit betekent dat er nooit 0 dagen tot een verjaardag zijn, maar in extreme gevallen duizenden dagen kunnen over gaan \(bijvoorbeeld: van 29 februari 1996 tot 29 februari 2004\).

### Technische analyse

Je moet één geval toevoegen, namelijk het geval waarin het oude programma 0 dagen tot de volgende verjaardag zou geven. Je kan dus eerst berekenen wat het oude programma zou berekenen en dan een if toevoegen om te bepalen of je de berekening moet aanpassen.

Noem je methode `BirthdayProgram`. Maak deze methode toegankelijk via `ShowSubmenu` van de klasse `DateTimeExercises`

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

Je hoeft voorlopig geen rekening te houden met ongeldige waarden. Test je klasse door `ResultV1` ook van een statische methode `Main` te voorzien, waarin je enkele objecten van deze klasse aanmaakt en de verschillende properties waarden te geeft en vervolgens `PrintHonors` oproept.

## Oefening: H8-RapportModule-V2

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van simpele properties en methodes

### Functionele analyse

Dit programma geeft op basis van de input van een percentage de graad weer die je met dit gegeven zou behaald hebben.

### Technische analyse

Ontwerp een klasse `ResultV2` die je zal vertellen wat je graad is gegeven een bepaald behaald percentage. Het enige dat je aan een `ResultV2`-object moet kunnen geven is het behaalde percentage. Enkel het totaal behaalde percentage wordt bijgehouden. Via een methode `ComputeHonors` kan de behaalde graad worden teruggegeven. Dit werkt op dezelfde manier als in versie 1 van deze oefening, maar de verschillende graden worden voorgesteld met een `Enum`, `Honors`. De methode `ComputeHonors` toont het resultaat niet, maar geeft een waarde van deze `Enum` terug. Het is aan de `Main` om deze waarde af te printen, zodat je kan zien of je code werkt.

Test je klasse op dezelfde manier als versie 1. De teruggegeven waarden van `Honors` mag je in de `Main` meegeven aan `Console.WriteLine`.

## Oefening: H8-Getallencombinatie

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van properties

### Functionele analyse

Dit programma geeft op basis van de input van twee getallen de som van beide getallen, het verschil, het product en de deling. In het laatste geval en indien er een deling door nul zou worden uitgevoerd, wordt dit woordelijk weergegeven.

### Technische analyse

Maak een eenvoudige klasse `NumberCombination`. Deze klasse bevat 2 getallen \(type `int`\). Er zijn 4 methoden, die allemaal een `double` teruggeven:

* `Sum`: geeft som van beide getallen weer
* `Difference`: geeft verschil van beide getallen weer
* `Product`: geeft product van beide getallen weer
* `Quotient`: geeft deling van beide getallen weer. Print `"Error"` naar de console indien je zou moeten delen door 0 en voer dan de deling uit. Wat er dan gebeurt, is niet belangrijk.

Gebruik **full properties** voor `Number1` en `Number2` en toon in je `Main` aan dat je code werkt.

Volgende code zou namelijk onderstaande output moeten geven:

```csharp
NumberCombination pair1 = new NumberCombination();
pair1.Number1 = 12;
pair1.Number2 = 34;
Console.WriteLine("Paar:" + pair1.Number1 + ", " + pair1.Number2);
Console.WriteLine("Sum = " + pair1.Sum());
Console.WriteLine("Verschil = " + pair1.Difference());
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

Er is een klasse `Rectangle` met **properties** `Width` en `Height` en een klasse `Triangle` met `Base` en `Height`. Je programma maakt de figuren die hierboven beschreven worden aan met waarde `1.0` voor elke afmeting en stelt daarna hun afmetingen in via de setters voor deze properties. De oppervlakte wordt bepaald in een read-only property, `Surface` van het type `double`.

Indien om het even welk van deze properties wordt ingesteld op `0` \(of minder\) wordt er een foutboodschap afgeprint en wordt de afmeting niet aangepast.

De wiskundige formule voor de oppervlakte van een driehoek is basis \* hoogte / 2.

Schrijf de voorbeelden uit in de `Main` van een extra klasse, `FigureProgram`.

#### Voorbeeldinteractie\(s\)

\(Er worden twee rechthoeken en twee driehoeken aangemaakt. De afmetingen van de eerste rechthoek worden eerst op `-1` en `0` ingesteld.

```text
Het is verboden een breedte van -1 in te stellen!
Het is verboden een breedte van 0 in te stellen!
Een rechthoek met een breedte van 2,2m en een hoogte van 1,5m heeft een oppervlakte van 3,3m².
Een rechthoek met een breedte van 3m en een hoogte van 1m heeft een oppervlakte van 3m².
Een driehoek met een basis van 3m en een hoogte van 1m heeft een oppervlakte van 1,5m².
Een driehoek met een basis van 2m en een hoogte van 2m heeft een oppervlakte van 2m².
```

## Oefening: H8-Studentklasse

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van properties om geldige waarden af te dwingen

### Functionele analyse

Dit programma vraagt om de naam en leeftijd van een student. Er moet ook worden meegeven in welke klasgroep de student is ingeschreven. De groepen zijn `EA1`, `EA2` en `EB1`. Vervolgens worden de punten voor 3 vakken gevraagd, waarna het gemiddelde wordt teruggegeven.

### Technische analyse

Maak een nieuwe klasse `Student`. Deze klasse heeft 6 properties. Leeftijd en de punten stel je voor met **full properties**. Een student kan nooit ouder zijn dan 120. Je kan ook nooit een cijfer boven 20 behalen. Over leeftijden en cijfers onder 0 hoef je je geen zorgen te maken, want de achterliggende variabelen zijn `byte`s en die zijn altijd minstens 0.

* Name \(string\)
* Age \(byte\)
* ClassGroup \(maak hiervoor een `enum` `ClassGroups`\)
* MarkCommunication \(byte\)
* MarkProgrammingPrinciples \(byte\)
* MarkWebTech \(byte\)

Voeg aan de klasse een read-only property `OverallMark` toe. Deze berekent het gemiddelde van de 3 punten als `double`.

Voeg aan de klasse ook de methode `ShowOverview()` toe. Deze methode zal een volledig rapport van de student tonen \(inclusief het gemiddelde m.b.v. de `OverallMark`-property\).

Test je programma door enkele studenten aan te maken en in te stellen. Volgende statische methode `Main` zet je in de klasse `Student`.

```csharp
Student student1= new Student();
student1.Class = ClassGroups.EA2;
student1.Age = 21;
student1.Name = "Joske Vermeulen";
student1.MarkCommunication = 12;
student1.MarkProgrammingPrinciples = 15;
student1.MarkWebTech = 13;
student1.ShowOverview();
```

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

## Oefening: H8-RapportModule-V3

### Leerdoelen

* werken met klassen en objecten
* gebruik maken van properties om geldige waarden af te dwingen

### Functionele analyse

Deze is gelijkaardig aan de vorige versie van het programma, maar gebruikt iets geavanceerdere technieken.

### Technische analyse

Maak een nieuwe versie van H8-RapportModule-V2, waarbij je een full property gebruikt voor het percentage. Zorg ervoor dat dit steeds tussen 0 en 100 ligt. Vervang ook `ComputeHonors` door een read-only property, `Honors`.

