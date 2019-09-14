# Oefeningen

## Oefening: H1-variabelen\_hoofdletters

### Leerdoelen

* gebruik van variabelen om input en output via `Console.ReadLine` en `Console.WriteLine` op te slaan en terug te tonen

### Functionele analyse

Een applicatie vraagt je tekst in te voeren die dan daarna zal worden getoond met allemaal hoofdletters.

### Technische analyse

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

![](../../.gitbook/assets/image%20%281%29.png)

### Technische hulp

#### Programmaverloop

Lees de gebruikersinvoer van de console en slaag dit op in een variabele. 

Zet de inhoud van deze variabele om in hoofdletters. 

Uiteindelijk geef je dan deze variabele weer in de console.

#### Testscenario's

* Voer tekst in met spaties
* Voer tekst in van meer dan 100 karakters
* Voer tekst in van 1 karakter
* Voer geen tekst in

### Ondersteunend materiaal

Hou het voorlopig op de cursus.

## Oefening: H1-optellen

### Leerdoelen

* gebruik van variabelen om input via `Console.ReadLine` op te slaan 
* berekeningen met de opgeslagen data uitvoeren
* het resultaat dat werd opgeslagen in een variabele via `onsole.WriteLine` te tonen

### Functionele analyse

Een applicatie vraagt je twee getallen in te voeren. Na de invoer van het tweede getal worden beide getallen bij elkaar opgeteld. Het resultaat wordt uiteindelijk weergeven.

### Technische analyse

#### UI

console applicatie

**Werking**

1. De vraag wordt gesteld om een getal in te typen en daarna op enter/return te drukken.
2. Er wordt gevraagd een tweede getal in te typen en dan op enter/return te drukken.
3. De twee getallen worden opgeteld.
4. Het resultaat wordt weergegeven.

#### voorbeeldinteractie\(s\)

![](../../.gitbook/assets/image%20%284%29.png)

### Technische hulp

#### Programmaverloop

Lees de gebruikersinvoer van de console en slaag dit op in een variabele voor wat het eerste getal betreft. Herhaal dit voor het tweede getal. Tel de twee getallen samen en bewaar deze in een derde variabele. Uiteindelijk geef je dan de inhoud van deze derde variabele weer in de console. Tip: getal1 = Convert.ToInt32\(invoer1\);

#### Testscenario's

* Voer tekst in.
* Voer een getal met 100 cijfers in.
* Voer geen getal in.

### Ondersteunend materiaal

Hou het voorlopig op de cursus.

## Oefening: H1-verbruik-wagen

### Leerdoelen

* gebruik van variabelen om input via `Console.ReadLine` op te slaan 
* berekeningen met de opgeslagen data uitvoeren
* het resultaat dat werd opgeslagen in een variabele via `onsole.WriteLine` te tonen

### Functionele analyse

Een applicatie zal voor jou het gemiddelde verbruik van een wagen berekenen. 

Hiervoor worden volgende vragen gesteld: 

1. Hoeveel liter is er nog aanwezig in de benzinetank. 
2. Hoeveel liter zit er nog in de benzinetank na de rit. 
3. Ook de kilometerstand van bij de aanvang van de rit wordt gevraagd en ook deze nadat de rit werd uitgevoerd. 

Op basis van deze parameters wordt het gemiddelde verbruik berekend en weergegeven.

### Technische analyse

#### UI

console applicatie

**Werking**

1. De vraag wordt gesteld om het aantal liter, aanwezig in de benzinetank, op te geven. 
2. Daarna wordt gevraagd om ook het aantal liter op te geven na de rit. 
3. De kilometerstand van de aanvang van de rit wordt gevraagd. 
4. Uiteindelijk ook de kilometerstand na het beëindigen van de rit wordt opgevraagd.

#### voorbeeldinteractie\(s\)

![](../../.gitbook/assets/image.png)

### Technische hulp

#### Programmaverloop

Lees de gebruikersinvoer van de console en slaag dit op in variabelen. 

Zorg ervoor dat je het juiste gegevenstype kiest voor de verschillende variabelen. 

Nadien voer je de berekening uit om op basis van de ingevoerde gegevens het gemiddeld verbruik te berekenen \(100 \* \(aantalLiterinTank1 - aantalLiterinTank2\) / \(kilometerstand2 - kilometerstand1\)\) 

Uiteindelijk geef je dan het resultaat weer in de console.

#### Testscenario's

* Voer tekst in.
* Voer een getal met 100 cijfers in.
* Voer geen getal in.

### Ondersteunend materiaal

Hou het voorlopig op de cursus.

## Simple maths

Schrijf een programma dat de uitkomst van volgende resultaten op het scherm toont:

-1 + 4 \* 6

\( 35+ 5 \) % 7

14 + -4 \* 6 / 11

2 + 15 / 6 \* 1 - 7 % 2

## Gemiddelde

Schrijf een programma dat het gemiddele van drie int-variabelen berekend \(de variabelen geef je uiteraard een waarde in code\).

## Euro naar dollar

Ontwerp een toepassing waarmee je een bedrag, inclusief komma-getallen in euro kan omrekenen naar dollar. Gebruik hierbij de huidige wisselkoers Je hoeft niet af te ronden. Het resultaat in een label wordt als volgt weergegeven: `[x] EUR is gelijk aan [y] USD`.

## Tafel en Console.Clear\(\)

Met het statement `Console.Clear();` kan je de console ...je raadt het nooit... leegmaken. Test deze code in het volgende programma.

Schrijf een programma dat de tafels van vermenigvuldigen geeft van 411 \(dus 1x411=411, 2x411= 822 tot en met 10x411=4110\). Toon telkens 1 zin en wacht dan tot de gebruiker op enter duwt om de volgende vermenigvuldiging op een nieuw scherm te tonen. De output ziet er dus als volgt uit:

```text
1 x 411 = 411
Druk op enter voor de volgende lijn. 
[Scherm leeg gemaakt]
2 x 411 = 822
Druk op enter voor de volgende lijn
[Scherm leeg gemaakt]
...
```

**Plaats 411 in een variabele aan de start van het programma en gebruik deze in je berekeningen verderop. Toon dat je code ook werkt door de inhoud van de variabele in een ander getal te veranderen zodat je van dat nieuwe getal nu de tafels van vermenigvuldiging krijgt.**

## Kill/Death-ratio

Maak twee variabelen `double kills` en `double deaths` aan. Wijs er jouw typische scores aan toe die je haalt in een spel naar keuze. Bereken en toon vervolgens je kill/death-ratio.

\(**opgelet: begrijp je waarom we best een van beide variabelen in double zetten?** Lees de warning bij Expressies zeker nog eens na...OF test eens wat er gebeurt indien je met int zou werken\)

## Gewicht in space

Je massa is overal dezelfde. Je gewicht daarentegen is afhankelijk van de zwaartekracht van de plek waar je bent. Zo is je gewicht veel groter op Jupiter dan op Mars.

Maak een variabele `double gewichtOpAarde` aan. Wijs een gewicht toe \(bv het jouwe\). Schrijf nu een programma dat onder elkaar jouw gewicht op verschillende planeten toont.

Hier de omzettingstabel \(je gewicht op Mercurius is dus je gewicht op aarde x 0.38\):

* Mercurius: 0.38
* Venus: 0.91
* Aarde: 1.00
* Mars: 0.38
* Jupiter: 2.34
* Saturnus: 1.06
* Uranus: 0.92
* Neptunus: 1.19
* Pluto: 0.06  \(we laten de discussie achterwege of pluto wel of niet een planeet is\)

De output zijn verschillende lijnen onder elkaar in de vorm van:

`Je weegt op [planeet] [gewichtopdieplaneet] kg.`

Plaats de zin met Jupiter in het rood, daar je daar het zwaarst weegt, en die van pluto in het groen.

> In de verdere hoofdstukken zal je geregeld oefeningen tegenkomen waar PRO voor staat. Dit zijn iets pittigere oefeningen die je enkel vlot zal kunnen als je de standaard oefeningen hebt gemaakt. Ik raad iedereen echter aan ze te \(proberen\) maken.

