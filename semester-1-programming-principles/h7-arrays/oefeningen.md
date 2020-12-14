# Oefeningen

{% hint style="warning" %}
Onderstaande oefeningen worden ondergebracht ik de klasse `HoostdtukAcht`.
{% endhint %}

## Oefening: H8-Opwarmers

### Leerdoelen

* arrays

### Functionele analyse

Schrijf in de klasse `HoofdstukAcht` de methode `Opwarmers`.

Onderaan staan enkele opdrachten, voeg ze allemaal toe in de aangemaakte methode.  
Gebruik steeds een loop om de opdrachten uit te lossen.  
Druk voor elke opdracht eerst af wat de opdracht gaat doen. \(Console.WriteLine\)  
Voer vervolgens de opdracht uit.

### Technische analyse

* Maak een array gevuld met de getallen 0 tot 10
* Maak een array gevuld met de getallen van 100 tot 1
* Maak een array gevuld met de letters a tot z
* Maak een array gevuld met willekeurige getallen tussen 1 en 100 \(de array is 20 lang\)
* Maak een array gevuld met afwisselend `true` en `false` \(de array is 30 lang\)

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```csharp
Maak een array gevuld met de getallen 0 tot 10
0 1 2 3 4 5 6 7 8 9 10

Maak een array gevuld met de getallen van 100 tot 1
100 99 98 97 96 95 94 93 92 91 90 89 88 87 86 85 84 83 82 81 80 79 78 77 76 75 74 73 72 71 70 69 68 67 66 65 64 63 62 61 60 59 58 57 56 55 54 53 52 51 50 49 48 47 46 45 44 43 42 41 40 39 38 37 36 35 34 33 32 31 30 29 28 27 26 25 24 23 22 21 20 19 18 17 16 15 14 13 12 11 10 9 8 7 6 5 4 3 2 1

Maak een array gevuld met de letters a tot z
a b c d e f g h i j k l m n o p q r s t u v w x y z

Maak een array gevuld met willekeurige getallen tussen 1 en 100 (de array is 20 lang)
76 64 49 8 97 38 24 63 47 70 86 84 21 39 47 83 79 14 20 41

Maak een array gevuld met afwisselend true en false (de array is 30 lang)
True False True False True False True False True False True False True False True False True False True False True False True False True False True False True False
```

## Oefening: H8-ArrayOefener1

### Leerdoelen

* arrays

### Functionele analyse

Schrijf in de klasse `HoofdstukAcht` de methode `ArrayOefener1`.

Maak een programma dat aan de gebruiker vraagt om 10 waarden in te voeren. Vervolgens toont het programma de som, het gemiddelde en het grootste getal van deze 10.

Vervolgens vraagt het programma de gebruiker om een getal in te voeren. Het programma toont dan alle getallen die groter of gelijk zijn aan dit ingevoerde getal zijn die in de array aanwezig zijn. Indien geen getallen groter zijn dan verschijnt een bericht `Niets is groter` op het scherm.

### Technische analyse

De 10 ingevoerde getallen zijn van het type int en worden bewaard in een array.

De som en het grootste getal worden m.b.v. een loop berekend. Het gemiddelde wordt buiten deze loop berekend en daarvoor is de som nodig.

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```csharp
Voer 10 gehele getallen in
2
44
1
22
3
4
87
5
1
12
******
Som is 181, Gemiddelde is 18,1, Grootste getal is 87
******
Geef minimum getal in?
34
De getallen groter dan 34 zijn: 44,87
```



