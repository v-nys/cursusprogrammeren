# Oefeningen

> Ook dit hoofdstuk bevat meer oefeningen dan je lief zijn. Zoek zelf de oefeningen uit die je aanspreken en focus je op het leren werken met methoden en deze te integreren in een grotere applicatie.

## Deel 0 - Opwarmers

Een extra grote hoop oefeningen om je methoden te drillen \([originele bron](https://codeforwin.org/2016/03/functions-programming-exercises-and-solutions-in-c.html)\). De oefeningen zijn ongeveergerangschikt naar moeilijkheid, je moet deze allemaal met loops oplossen! Hoe ver geraak je?

Iedere oefening verwacht dat je steeds een methode schrijft en de werking ervan aantoont:

1. Methode `Kwadraat` die het kwadraat van een ingevoerd getal berekend.
2. Methode `BerekenStraal` die de straal van een cirkel kan berekenen waarvan je de diameter meegeeft
3. Idem voor omtrek en oppervlakte
4. Methode die het grootste van 2 getallen teruggeeft
5. Methode `IsEven` die bepaald of een getal even of oneven is \(geeft een `bool` terug die `true` is indien even\)
6. Methode `IsArmstrong` die bepaald of een getal een Armstrong getal is.
7. Methode `ToonEvenNummers` die alle oneven getallen van 1 tot n toont waarbij n als parameter wordt meegegeven.
8. Methode `ToonArmstrongNummers` die idem alle [Armstrong](https://github.com/v-nys/cursusprogrammeren/tree/13ea122a2e92d805feb8b618811589d4f57a8b23/5_herhalingen/a_practica.md#armstrong-nummer) nummers tot n toont.

## Deel 1 - De basics

> Sommige oefeningen zijn van de vorm "Maak een methode die...". Het is steeds de bedoeling dat je de werking van je methode ook test in je main door deze aan te roepen.

### Intro methode

#### Basic

Maak een methode die jezelf voorstelt op het scherm in de vorm van "Ik ben Tim Dams, ik ben 18 jaar oud en woon in de Lambrisseringsstraat 666". Deze informatie mag hardcoded in je methode staan. Bedoeling is dat je de methode kan aanroepen als volgt:

```csharp
MyIntro();
```

> Deze methode toont enkel zaken op het scherm en heeft dus als returntype `void`.

#### Basic 2

Zorg er voor dat je nu je naam, leeftijd en adres via parameters kan meegeven en dus de methode als volgt kunt aanhouden:

```csharp
MyIntro("Jos",34, "Trammezantlei 21");
```

## Oefening: H6-grootste-methode

### Leerdoelen

* methodes

### Functionele analyse
Schrijf een methode die drie `int`s aanvaardt en de grootste als resultaat teruggeeft.

### Technische analyse
Aangezien het maar om 3 argumenten gaat, kan je dit oplossen met `if`s die het eerste en het tweede argument vergelijken, het eerste en het derde argument,...
Test je methode uit in een voorbeeldprogrammaatje.

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```text
Geef 3 ints.
> 7
> 10
> 4
Het grootste getal is 10.
```

### Rekenmachine

Maak minimaal methoden genaamd `TelOp`, `TrekAf`, `VermenigVuldig` en `Deel`. Je kan aan deze methoden steeds twee doubles meegeven en het resultaat dat terugkomt is uiteraard de bewerking van die twee parameters. Maak een eenvoudig programma'tje waarin je die methoden test. Kan je een eenvoudige rekenmachine maken? \(inclusief geheugen\) Voeg extra methoden naar keuze toe \(denk aan Macht, Sinus, Cosinus, Modulo, etc.\)

## Oefening: H6-paswoord-generator

### Leerdoelen

* methodes

### Functionele analyse

Maak een paswoord generator die paswoorden van bepaalde lengte genereert en bestaat uit willekeurige letters, hoofdletters en cijfers. Plaats deze code in een methode met 1 parameter, namelijk de lengte van het paswoord dat gemaakt moet worden. De methode geeft het gegenereerde paswoord terug als resultaat.

### Technische analyse
Maak gebruik van `Random` en een `for`-lus. Een `Random` genereert normaal alleen getallen, maar via casting kan je die getallen omzetten in `char`s. Raadpleeg een Unicode tabel voor de juiste getallen *of* (iets sneller) cast eerst `'a'` en `'z'` naar getallen en gebruik die om te bepalen welke willekeurige resultaten je mag genereren. Demonstreer je methode met een kort programma.

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```text
> 8
dIh8ez10
```

## Deel 2 Geavanceerde methode concepten

### Film Default

Maak een methode FilmRuntime\(\) die 3 parameters accepteert:

1. Een string die de naam van de film bevat
2. Een integer die duur in minuten van de film bevat
3. Een enum-type die het genre van de film bevat \(Drama, Actie, etc.\)

Indien de duur van de film niet wordt meegeven wordt een standaard lengte van 90 minuten ingesteld. Indien het genre niet wordt meegeven dan wordt deze default op Onbekend ingesteld.

De methode geeft niets terug maar toont eenvoudigweg de film op het scherm, gevolgd door z’n duur en genre in volgende formaat.

```text
The Matrix (120minuten, Actie)
```

Toon aan in je main dat de methode werkt met zowel 1, 2 als 3 parameters. Toon ook aan dat je met ‘named arguments’ de methode kan aanroepen.

## Deel 3 -  Overal methoden!

### Oude oefeningen leesbaarder maken

Kan je code uit vorige hoofdstukken herbruiken door deze in handige methoden te plaatsen zodat je code leesbaarder én bruikbaarder wordt?

### Module 1 test herschrijven

Bekijk terug jouw \(of mijn\) oplossing van de vaardigheidsproef 18/19 of de [module 1 eindetest]() in deze cursus.

Kan je deze code leesbaarder maken door methoden \(en loops\) toe te voegen?

