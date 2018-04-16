## Meer-dimensionale Arrays
Voorlopig hebben we enkel met 1-dimensionale array gewerkt. Je kan er echter ook meerdimensionale maken. Denk maar aan een n-bij-m array om een matrix voor te stellen.

Door een komma tussen rechte haakjes te plaatsen tijdens de declaratie kunnen we meer-dimensionele arrays maken. Bijvoorbeeld:

```java
string[,] books;
```
Om een array ook onmiddellijk te initialiseren gebruiken we dan volgende uitdrukking:

```java
string[,] books = {
        {"Macbeth", "Shakespeare", "ID12341"},
        {"Before I Get Old", "Dave Marsh", "ID234234"},
        {"Security+", "Mike Pastore", "ID3422134"}
    };
```

Merk op dat we dus nu een 3 bij 3 array maken. Iedere rij bestaat uit 3 elementen.

Stel dat we uit de books-array bijvoorbeeld de auteur van het derde boek wensen te tonen dan kunnen we schrijven:

```java
System.Console.WriteLine(books[2, 1]);
```

Dit zal “Mike Pastore” op het scherm zetten.
## Lengte van iedere dimensie in een n-dimensionale matrix

Indien je de lengte opvraagt van een meer-dimensionele array dan krijg je de som van iedere lengte van iedere dimensie. Onze books array zal bijvoorbeeld dus lengte 9 hebben. Je kan echter de lengte van iedere aparte dimensie te weten komen met de GetLength() methode die iedere array heeft. Als parameter geef je de dimensie mee van de welke je de lengte wenst.

```java
int arrayRijen = books.GetLength(0);
int arrayKolommen = books.GetLength(1);
```
Het aantal dimensies van een array wordt trouwens weergegeven door de rank eigenschap die ook iedere array heeft. Bijvoorbeeld:

```java
int arrayDimensions = myColors.Rank;
```