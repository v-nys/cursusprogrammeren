# Basistypen voor getallen

De belangrijkste basistypen van C\# om getallen weer te geven zijn

* Voor gehele getallen: `sbyte, byte, short, ushort, int, uint, long`
* Voor kommagetallen: `double , float, decimal`

## Bereik van datatypes

Deze datatypes hebben allemaal een bepaald bereik, wat een rechtstreeks gevolg is van de hoeveelheid geheugen die ze innemen.

Voor de gehele getallen:

| **Type** | **Geheugen** | **Range** |
| :--- | :--- | :--- |
| sbyte | 8 bits | -128 tot 127 |
| byte | 8 bits | 0 tot 255 |
| short | 16 bits | -32768 tot 32767 |
| ushort | 16 bits | 0 tot 65535 |
| int | 32 bits | -2147483658 tot +2147483657 |
| uint | 32 bits | 0 tot 4294967295 |
| long | 64 bits | Zie boek |
| char | 16 bits | 0 tot 65535 |

Voor de kommagetallen:

| **Type** | **Geheugen** | **Range** | **Precisie** |
| :--- | :--- | :--- | :--- |
| float | **32 bits** | 1,5\*10-45tot 3,4\*1048 | 7 digits |
| double | 64 bits | **5\*10-324tot 1,7\*10308 ** | 15 digits |
| decimal | 128 bits | 1\*10-28tot 7,9\*1028 | **28-29 digits** |

### Bereik in code weten

Het bereik van deze typen is weliswaar opgegeven in het handboek. Maar het is belangrijk om weten dat deze ook in de compiler gekend is. Het volgende voorbeeld toont dit aan:

```java
string zinnetje = "Het bereik van het type double is:";
Console.WriteLine(zinnetje + double.MinValue + " en " + double.MaxValue);
```

Je kan met andere woorden met `int.MaxValue` en `int.MinValue` het minimum- en maximumbereik van het type int verkrijgen. Wil je dit van een double, dan gebruik je `double.MaxValue` etc.

## Variabelen aanmaken en gebruiken

Telkens wanneer je een variabele wenst aan te maken, om te gebruiken als werkgeheugen in je programma, dan dien je eerst deze variabele te definieren.

Hiervoor dien je minstens op te geven:

1. Het datatype \(bv int, double\)
2. Een identifier zodat de variabele uniek kan geïdentificeerd worden
3. \(optioneel\) Een beginwaarde die de variabele krijgt bij het aanmaken ervan

Voorbeeld:

```java
int mijnLeeftijd;
```

We maken variabele van het type ‘int’ \(geheel getal\) dat als identifier ‘eenVariabele’ heeft.

Indien je reeds weet wat de beginwaarde moet zijn van de variabele dan mag je de variabele ook reeds deze waarde toekennen bij het aanmaken:

```java
int mijnLeeftijd = 37;
```

Vanaf dit punt kunnen we dus ten allen tijde deze variabele gebruiken om een waarde aan toe te kennen, de bestaande waarde te overschrijven, of de waarde te gebruiken:

* Waarde toekennen: `mijnGetal= 15;`

* Waarde tonen op scherm: `Console.WriteLine(mijnGetal);`

Je kan natuurlijk ook een waarde uit een variabele uitlezen en toewijzen aan een andere variabele:  
`int eenAndereLeeftijd= mijnLeeftijd;`





