# Basis van Arrays
## ArrayOefener 1
Maak een programma dat aan de gebruiker vraagt om 10 waarden (int) in te voeren in een array. Vervolgens toont het programma De som, het gemiddelde en het grootste getal van deze 10.

Vervolgens vraagt het programma de gebruiker om een getal in te voeren. Het programma toont dan alle getallen die groter of gelijk zijn aandit ingevoerde getal zijn die in de array aanwezig zijn. Indien geen getallen groter zijn dan verschijnt een bericht “Niets is groter” op het scherm.

![](/assets/5_arrays/practarray1.png)
## ArrayOefener 1

## ArrayOefener 2
Maak een programma dat aan de gebruiker vraagt om 2 keer 5 getallen in te voeren. Bewaar de eerste reeks waarden in een array A, de tweede reeks waarden in array B. Maak een nieuwe array C aan die steeds de som bevat van het respectievelijke element uit arrays A en B. Toon het resultaat.

![](/assets/5_arrays/practarray2.png)

## Vraag Array
Maak een array die 10 string kan bevatten. Ieder element van de array bevat een vraag (naar keuze te verzinnen) als string waar de gebruiker met een getal op moet antwoorden.
Maak een array aan die tot 10 ints kan bevatten. Lees 1 voor 1 de vraag uit de array-string uit en toon deze op het scherm. Lees vervolgens het antwoord uit dat de gebruiker intypt en bewaar dit als int in de 2e array.

Na de 10 vragen toon je vervolgens de 10 vragen met achter iedere vraag het antwoord van de gebruiker.

## Array Zoeker
Maak een programma dat eerst weer aan de gebruiker om 10 waarden vraagt die in een array worden gezet. 

Vervolgens vraagt het programma welke waarde moet verwijderd worden. Wanneer de gebruiker hierop antwoord met een nieuwe waarde dan zal deze nieuw ingevoerde waarde in de array gezocht worden. Indien deze gevonden wordt dan wordt deze waarde uit de array verwijderd en worden alle waarden die erachter komen met een plaatsje naar links opgeschoven, zodat achteraan de array terug een lege plek komt. 

Deze laatste plek krijgt de waarde -1.

Toon vervolgens alle waarden van de array.

Indien de te zoeken waarde meer dan 1 keer voorkomt, wordt enkel de eerst gevonden waarde verwijderd.

![](/assets/5_arrays/practarray3.png)

## LeveringsBedrijf
Maak een programma voor een koerierbedrijf.  Maak een array die 10 postcodes bevat (zelf te kiezen) van gemeenten waar het bedrijf naar levert. Maakt een tweede array die de prijs bevat per  kg van iedere respectievelijke gemeente.  Het eerste element  van deze array bevat dus de prijs/kg om naar de gemeente die als eerste in de array met postcodes staat.

Vraag aan de gebruiker een postcode en het gewicht van het pakket. Vervolgens wordt de prijs opgezocht voor die gemeente en wordt deze berekend gegeven het ingegeven gewicht.

Indien het bedrijf niet levert aan de ingetypte postcode dan wordt een foutmelding weergegeven.

# Methoden met arrays als parameter
## Parkeergarage
Een parkinggarage vraagt sowieso €2.00 om tot maximum 3uur te parkeren. Per extra uur NA die 3uur wordt telkens €0.5 aangerekend (dus 4uur parkeren kost €2.5. Er wordt maximum €10 aangerekend per dag. En veronderstel dat er nooit langer dan 1 dag (24u) kan geparkeerd worden.

Schrijf een programma dat het verschuldigde bedrag toont gegeven de duur van een auto. Bij het opstarten van het programma wordt eerst gevraagd hoeveel auto’s ingevoerd zullen worden, dan wordt per auto de duur van het parkeren gevraagd. Finaal wordt, netjes getabuleerd, alle informatie getoond, inclusief het totaal bedrag. Gebruik minstens 1 methode ‘berekenKosten’ die de kost voor 1 gebruiker telkens teruggeeft, gegeven de duur als parameter. Gebruik ook een methode die een array als parameter aanvaard (bijvoorbeeld de array met daarin de respectievelijke uren per auto).

Voorbeeldoutput:
Opstart:

 ![](/assets/5_arrays/practarray4.png)
 
Resultaat:

![](/assets/5_arrays/practarray5.png)

## Array Viewer
Maak een programma dat een methode VisualiseerArray implementeert. De methode zal een array (type int) als parameter hebben en niets teruggeven (void). Echter, de methode zal met behulp van Write() de array, van eender welke grootte, op het scherm tonen. Tussen ieder element van dezelfde rij dient een tab (‘\t’) gezet te worden. Je dient in de methode gebruik te maken van een for-loop.
Voorbeeld van main:
```java
int[] array={15,6,9};
int[] array2={0,1,2,3,4,5,6};
VisualiseerArray(array);
VisualiseerArray(array2);
```
Geeft volgende output:

![](/assets/5_arrays/practarray6.png)

## Caesar-encryptie
Maak 2 methoden ``Encrypt`` en ``Decrypt`` die als parameters telkens een array krijgen en een integer. Bedoeling is dat de Encrypt-methode de array van het type string encrypteert gegeven de sleutel x volgens het Caesar cipher (zie hieronder). Als resultaat komt er uit de methode de geëncrypteerde array. 
De decrypt-methode doet hetzelfde maar omgekeerd: je kan er een versleutelde tekst insteken en de sleutel en de ontcijferde tekst komt terug (merk op dat je decrypt-methode gebruik kan maken van de encrypt-methode!).

Toon in je main aan dat je methoden werken (door bijvoorbeeld aan de gebruiker een stuk tekst te vragen en een sleutel en deze dan te encrypteren/decrypteren).

> Encryptie is de kunst van het vercijferen van data. Hierbij gaat men een gewone tekst zodanig omvormen (‘scramblen’) zodat deze onleesbaar is en enkel kan ontcijferd worden door de ontvanger die weet hoe de tekst terug kan verkregen worden en enkel indien deze ook de ‘private’ sleutel heeft.

> Een klassiek encryptie-algoritme uit de oudheid is de Caesar substitutie. Hierbij gaan we het alfabet met x  plaatsen opschuiven en vervolgens de te vercijferen tekst letter per letter te vervangen met z’n respectievelijke opgeschoven versie. Hierbij is x dus de geheime sleutel die zender en ontvanger moeten afspreken.

![](/assets/5_arrays/practarray8.png) 

Stel bijvoorbeeld dat x=3  dan krijgen we volgende nieuwe alfabet:
    DEFGHIJKLMNOPQRSTUVWXYZABC
Waarbij dus de A zal vervangen worden door een D, de Z door een C, etc.

Willen we deze tekst dus ‘encrypteren’:
    the quick brown fox jumps over the lazy dog

dan krijgen we:
    WKH TXLFN EURZQ IRA MXPSV RYHU WKH ODCB GRJ

# Meer-dimensionale arrays

## Determinant
Schrijf een programma dat een methode BerekenDeterminant heeft. Deze methode heeft één paramater als input: een 2 bij 2 array van integers. Als resultaat geeft de methode de determinant als integer terug. Zoek zelf op hoe je de determinant van een matrix kunt berekenen.

Volgende voorbeeld-main dient te werken, 
```java
int[,] aMatrix={ 
                  {2,4},
                  {3,5}
                };
Console.WriteLine($"Determinant van matrix is {BerekenDeterminant(aMatrix)}");
```

geeft als output: 
```
Determinant van matrix is -2
```

Extra:
Breidt uit zodat de BerekenDeterminant-methode ook werkt voor 3-bij-3 matrices. De methodeaanroep blijft dezelfde, enkel de interne code van de methode zal nu rekening moeten houden met de grootte van de matrix .

## 2D Array Viewer
Breidt het ArrayViewer programma uit zodat ook 2-dimensionale arrays gevisualiseerd kunnen worden. (Hint: gebruik  de GetLength() methode van een array).

Voorbeeld van main:
```java
int [,] array= { {15,6,9},{1,2,3},{6,9,12}};
VisualiseerArray(array);
```
Output:
```
15  6  9
1   2  3
6   9  12
```

## MatrixMultiplier
Schrijf een methode VermenigvuldigMatrix die 2 matrices als invoer verwacht en als resultaat een nieuwe matrix teruggeeft die het product van beide matrices bevat.

# Pro

## Galgje
Maak een spel , vergelijkbaar als galgje, waarin de speler een woord moet raden. Zie [Wiki](http://nl.wikipedia.org/wiki/Galgje) voor de spelregels indien je deze niet kent.

Voorbeeld  output:

![](/assets/5_arrays/practarray9.png) 
