# Deel 1 - De basics
> Sommige oefeningen zijn van de vorm "Maak een methode die...". Het is steeds de bedoeling dat je de werking van je methode ook test in je main door deze aan te roepen.

## Intro methode
### Basic
Maak een methode die jezelf voorstelt op het scherm in de vorm van "Ik ben Tim Dams, ik ben 18 jaar oud en woon in de Lambrisseringsstraat 666".
Deze informatie mag hardcoded in je methode staan. Bedoeling is dat je de methode kan aanroepen als volgt:
```csharp
MyIntro();
```
> Deze methode toont enkel zaken op het scherm en heeft dus als returntype ``void``.
### Basic 2
Zorg er voor dat je nu je naam, leeftijd en adres via parameters kan meegeven en dus de methode als volgt kunt aanhouden:
```csharp
MyIntro("Jos",34, "Trammezantlei 21");
``` 



## Grootste methode
Schrijf een methode die 3 ints aanvaardt en vervolgens de grootste van de 3 parameters als resultaat terug geeft.



## Paswoord generator methode
Maak een paswoord generator die paswoorden van bepaalde lengte generereert en bestaat uit willekeurige letters, hoofdletters en cijfers. Plaats deze ode in een methode die 1 parameter aanvaardt namelijk de lengte van het paswoord dat gemaakt moet worden. De methode geeft het gegenereerde paswoord terug als resultaat.



# Deel 2 Geavanceerde methode concepten

## Film Default
Maak een methode FilmRuntime() die 3 parameters accepteert:
1. Een string die de naam van de film bevat
2. Een integer die duur in minuten van de film bevat
3. Een enum-type die het genre van de film bevat (Drama, Actie, etc.)
Indien de duur van de film niet wordt meegeven wordt een standaard  lengte van 90 minuten ingesteld. Indien het genre niet wordt meegeven dan wordt deze default op Onbekend ingesteld.

De methode geeft niets terug maar toont eenvoudigweg de film op het scherm, gevolgd door z’n duur.
Toon aan in je main dat de methode werkt met zowel 1, 2 als 3 parameters. Toon ook aan dat je met ‘named arguments’ de methode kan aanroepen.

## Grote Som
Maak een methode Som() die eender welke hoeveelheid paramaters van het type int aanvaardt en vervolgens de som van al deze parameters teruggeeft (als int).

Toon in je main aan dat de methode werkt door onder andere 1, 3,5 en 10 gehele getalen mee te geven.

Toon ook aan dat je een array van 50 ints als parameter kan meegeven aan de methode. (hint:je moet het ``params``  keyword gebruiken).

# Deel 3 -  Overal methoden!
## Oude oefeningen leesbaarder maken
Kan je code uit vorige hoofdstukken herbruiken door deze in handige methoden te plaatsen zodat je code leesbaarder én bruikbaarder wordt?

## Module 1 test herschrijven
Bekijk terug jouw (of mijn) oplossing van de vaardigheidsproef 18/19 of de [module 1 eindetest] (4_beslissingen/b_allinonemodule1.md)in deze cursus. 

Kan je deze code leesbaarder maken door methoden (en loops) toe te voegen?

