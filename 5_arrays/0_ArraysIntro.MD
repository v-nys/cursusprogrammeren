# Arrays

Arrays zijn een veelgebruikt principe in vele programmeertalen. Het grote voordeel van arrays is dat je een enkele variabele kunt hebben die een grote groep waarden voorstelt van eenzelfde type. Hierdoor wordt je code leesbaarder en eenvoudiger in onderhoud. Arrays zijn een zeer krachtig hulpmiddel, maar er zitten wel enkele venijnige addertjes onder het gras.

Een array is niet meer dan een verzameling waarden van hetzelfde type (bijvoorbeeld een verzameling ints, doubles of chars). Deze waarden kunnen benaderd worden via 1 enkele variabele, de array zelf. Door middel van een *index* kan ieder afzonderlijk element uit de array aangepast of uitgelezen worden.

Een nadeel van arrays is dat, eens we de lengte van een array hebben ingesteld, deze lengte niet meer kan veranderen. Later zullen we leren werken met lists en andere collections die dit nadeel niet meer hebben (zie [hier](5_arrays/8_Collections_Generics.md)).



## Nut van arrays
Stel dat je de dagelijkse neerslag wenst te bewaren. Dit kan je zonder arrays eenvoudig:
```csharp
int dag1=34;
int dag2=45;
int dag3=0;
int dag4=34;
int dag5=12;
int dag6=0;
int dag7=23;
```

Maar wat als je plots de neerslag van een heel jaar, 365 dagen, wenst te bewaren. Of een hele eeuw? Van zodra je een bepaalde soort data hebt die je veelvuldig wenst te bewaren dan zijn arrays de oplossing. 

## Bron
Grote delen van dit hoofdstuk zijn vertaald uit het handboek C# 4.0 Essentials.