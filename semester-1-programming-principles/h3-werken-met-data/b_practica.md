# Uibreidingsoefeningen

## Oefening: H3-maaltafels-binair

### Leerdoelen

* werken met binaire getalvoorstelling
* werken met willekeurige getallen
* stringformattering

### Functionele analyse

De opdracht is gelijkaardig aan die van H1-maaltafels. Ditmaal vermenigvuldig je echter niet steeds hetzelfde getal, maar wel een willekeurig getal tussen 1 en 10 \(beide inclusief\). Bovendien toont het programma alle getallen als reeksen van bits.

### Technische analyse

Gebruik hiervoor de `Convert` klasse en stringformattering.

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

{% hint style="warning" %}
Bij jou moeten de bitreeksen aan de linkerkant van `*` er hetzelfde uitzien als in deze reeks resultaten, maar de andere zijn niet gegarandeerd er hetzelfde uit te zien. Als je nog niet vertrouwd bent met binaire operatoren, doe je er goed aan uit te tellen of je resultaten kloppen.
{% endhint %}

```text
1 * 1001 is 1001
```

```text
10 * 110 is 1100
```

```text
11 * 1 is 11
```

```text
100 * 11 is 1100
```

```text
101 * 111 is 100011
```

```text
110 * 10 is 1100
```

```text
111 * 10 is 1110
```

```text
1000 * 1 is 1000
```

```text
1001 * 110 is 110110
```

```text
1010 * 1000 is 1010000
```

## Oefening: H3-xor

### Leerdoelen

* werken met bitwise operatoren

### Functionele analyse

De gebruiker geeft drie getallen in. De eerste twee stellen zichzelf voor. Het derde stelt een bepaalde bit voor, te tellen vanaf die met de kleinste waarde \(dus 1 stelt de bit voor die bepaalt of een getal even of oneven is\). Het programma zegt of precies één van de twee eerste getallen diezelfde bit op 1 heeft staan.

### Technische analyse

Gebruik hiervoor een combinatie van de `^` operator en van een verschuiving.

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```text
Geef een eerste getal?
520
Geef een tweede getal?
7
Geef nummer van de bit (te tellen vanaf de kleinste)?
1
Precies één bit met waarde 1: True
```

## Oefening: H3-zonder-xor

### Leerdoelen

* werken met bitwise operatoren

### Functionele analyse

De opdracht is dezelfde als in H3-zonder-xor. Maar je mag de `^` operator niet gebruiken!

### Technische analyse

Denk na welke combinatie van andere operatoren hetzelfde uitdrukt als `^`!

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

Dit programma gedraagt zich exact hetzelfde als het vorige.

