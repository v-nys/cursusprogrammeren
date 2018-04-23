# For each loops
Wanneer je geen indexering nodig hebt, maar toch snel over alle elementen in een array wenst te gaan, dan is het **foreach** statement een zeer nuttig is.
Een foreach loop zal ieder element in de array een voor een in een tijdelijke variabele plaatsen (de **iteration variable**). 
Volgende code toont de werking waarbij we een array van doubles hebben en alle elementen er in op het scherm willen tonen:
```java
double[] killdeathRates= {1.2, 0.89, 3.15, 0.1};
foreach (double kdrate in killdeathRates)
{
   Console.WriteLine($"Kill/Death rate is {kdrate}");
}
```

De eerste keer dat we in de loop gaan zal het element killdeathRates[0] aan ``kdrate`` toegewezen worden voor gebruik in de loop-body, vervolgens wordt killdeathRates[1] toegewezen, enz.

Het voordeel is dat je dus geen teller/index nodig hebt en dat foreach zelf de lengte van de array zal bepalen.

## Opgelet
* De foreach iteration variable is *read-only*: je kan dus geen waarden in de array aanpassen, enkel uitlezen.
* De foreach gebruik je enkel als je alle elementen van een array wenst te benaderen. In alle andere gevallen zal je een ander soort loop (for, while, etc.) moeten gebruiken.
