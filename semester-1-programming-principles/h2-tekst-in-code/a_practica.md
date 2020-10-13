# Oefeningen

Al deze oefeningen maak je in een klasse `HoofdstukDrie`.

## Oefening: H3-string-interpolation

### Leerdoelen

* gebruik van string interpolation

### Functionele analyse

Oefening H2-maaltafels en H2-ruimte dienen we te herschrijven volgens de principes van string interpolation.

### Technische analyse

Noem de methode voor deze oefening `StringInterpolation`.

#### voorbeeldinteractie\(s\)

Zie oefening H2-maaltafels en H2-ruimte.

### Technische hulp

#### Programmaverloop

Pas string interpolatie mbv `$` \(manier 2\) toe.

#### Testscenario's

* Zie oefening H2-maaltafels en H2-ruimte.

### Ondersteunend materiaal

Hou het voorlopig op de cursus.

## Oefening: H3-bereken-btw

### Leerdoelen

* gebruik van string interpolation

### Functionele analyse

Een programma vraagt een bedrag en vervolgens btw percentage in te geven waarna het bedrag incl. btw-percentage wordt weergegeven.

### Technische analyse

Noem de methode voor deze oefening `BerekenBtw`.

#### voorbeeldinteractie\(s\)

![](../../.gitbook/assets/image%20%2863%29.png)

### Technische hulp

#### Programmaverloop

Het bedrag dat wordt ingevoerd moet geconverteerd worden naar een int met `Convert.ToInt32`.

Pas string interpolatie mbv `$` \(manier 2\) toe.

#### Testscenario's

* Typ tekst in
* Geef een veel te groot bedrag in

## Oefening: H3-leetspeak

### Leerdoelen

* functionaliteit van strings leren kennen

### Functionele analyse

We willen tekst omvormen naar een ander formaat. Laat de gebruiker een lijn tekst ingeven en haal er alle tussenliggende spaties uit en vervang de a's door @

### Technische analyse

Gebruik Console.ReadLine om tekst in te lezen en hou bij in een variabele. Bereken uit deze variabele een waarde voor een variabele, die je ten slotte weergeeft via WriteLine. Noem je methode `LeetSpeak`.

#### Programmaverloop

```text
Geef je tekst in
> Oefening baart kunst!
Oefeningb@@rtkunst!
```

#### Testscenario's

* test met een zin zonder a's
* test met een zin met vijf a's of meer
* test met een lege string

## Oefening: H3-instructies

### Leerdoelen

* leren werken met stringinterpolatie
* leren werken met verbatim strings

### Functionele analyse

We willen met behulp van een programma instructies genereren voor de gebruiker. Meerbepaald wordt automatisch aangegeven in welke map de gebruiker bepaalde bestanden op een Windows systeem moet bijhouden.

{% hint style="warning" %}
Voor deze oefening is het verplicht gebruik te maken van een \(geïnterpoleerde\) verbatim string.
{% endhint %}

### Technische analyse

Op basis van de voornaam van de cursist en de naam van de cursus wordt de map gegeven die de cursist moet aanmaken \(eerste 3 letters voornaam, in hoofdletters met submap de naam van de cursus. Noem je methode `Instructies`.

#### Programmaverloop

```text
Wat is je naam?
> Vincent
Wat is de naam van de cursus?
> Programmeren
Maak een map als volgt: \VIN\Programmeren
```

## Oefening: H3-lotto

### Leerdoelen

* functionaliteit van strings
* stringinterpolatie
* escape sequenties

### Functionele analyse

De gebruiker voert zijn lottocijfers in. We willen deze op een overzichtelijke manier weergeven.

### Technische analyse

Laat de lottocijfers allemaal achter elkaar ingeven, gescheiden door komma's, zonder spaties. De gebruiker wordt verondersteld cijfers onder de 10 in te geven voorafgegaan door een nul. Gebruik de juiste methode om de cijfers uit te string te "knippen" en gebruik **tabs \(geen spaties!\)** om de uitvoer te scheiden. Noem je methode Lotto.

#### Voorbeeldinteractie

```text
Wat zijn je cijfers (tussen 01 en 45)?
> 05,08,13,18,27,44
Je cijfers zijn:
05    08    13
18    27    44
```

