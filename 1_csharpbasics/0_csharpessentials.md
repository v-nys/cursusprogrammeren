# Het algoritme
De essentie van een computerprogramma is het zogenaamde **algoritme** (het "recept" zeg maar). Dit is de reeks instructies die het programma moet uitvoeren telkens het wordt opgestart.
Het algoritme van een programma moet je zelf verzinnen. De volgorde waarin de instructies worden uitgevoerd zijn uiteraard zeer belangrijk. Dit is exact hetzelfde als in het echte leven: een algoritme om je fiets op te pompen kan zijn:
```
1. Haal dop van het ventiel
2. Plaats pomp op ventiel
3. Begin te pompen
```

Eender welke andere volgorde van bovenstaande algoritme zal vreemde (en soms fatale) fouten geven.

# C#
Om een algoritme te schrijven dat onze computer begrijpt dienen we een programmeertaal te gebruiken. Net zoals er ontelbare spreektalen in de wereld zijn, zijn er ook vele programmeertalen. C# ('siejarp') is er een van de vele. In tegenstelling tot onze spreektalen moet een computertaal 'exact' zijn en moet het op ondubbelzinnige manier door de computer verstaan worden. C# is een taal die deel uitmaakt van de .NET omgeving die meer dan 15 jaar geleden door Microsoft werd ontwikkeld.

De geschiedenis en de hele .NET-wereld vertellen zou een cursus op zich betekenen en gaan we hier niet doen. Het is nuttig om weten dat er een gigantische bron aan informatie over .NET en C# online te vinden is, beginnende met [docs.microsoft.com](https://docs.microsoft.com/en-us/dotnet/csharp/getting-started/)

> Deze cursus heeft als doel om je de programmeertaal C# aan te leren. Terwijl we dit doen zullen we ook geregeld andere .NET gerelateerde zaken aanraken.

# De compiler en Visual Studio
Jouw taak als **programmeur** in deze cursus is algoritmes in C# taal uitschrijven. We zouden dit in een eenvoudige tekstverwerker kunnen doen, maar dan maken we het onszelf lastig. Net zoals je tekst in notepad kunt schrijven, is het handiger dit in bijvoorbeeld Word te doen: je krijgt een spellingchecker en allerlei handige extra's. Ook voor het schrijven van computer code is het handiger om een zogenaamde IDE te gebruiken, een omgeving die ons zal helpen foutloze C# code te schrijven. Visual Studio is zo een IDE (Integrated Development Environment) die we in het vorige hoofdstuk reeds hebben besproken.

Het hart van Visual Studio bestaat uit de **compiler**. De compiler zal je C# code omzetten naar een uitvoerbaar bestand zodat jij (of anderen) je applicatie op een computer (of ander apparaat) kan gebruiken. Zolang de C# niet exact voldoet aan de C# syntax (zie verder) zal de compiler het vertikken een uitvoerbaar bestand voor je te genereren. 

![](/assets/1_csharpbasics/compiler.png)

[(Bron afbeelding)](https://docs.microsoft.com/en-us/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework)

Merk op dat we veel details van de compiler achterwege laten hier. De compiler is een uitermate complex element , maar in deze fase van je (prille) programmeursleven hoeven we enkel de kern van de compiler te begrijpen: **het omzetten van C# code naar een uitvoerbaar bestand**.


# Statements en de C# syntax
Om een werkend C#-programma te maken moeten we de C#-taal beheersen. Net zoals iedere taal bestaat ook C# uit enerzijds grammatica, in de vorm van de **C# syntax** en de te gebruiken keywords.

Een C#-programma bestaat uit een opeenvolging van instructies ook wel **statements** genoemd. **Deze eindigen steeds met een kommapunt (``;``)** (zoals ook in het Nederlands een zin eindigt met een punt).

De volgorde van de woorden (keywords, variabelen, etc.) zijn niet vrijblijvend en moeten aan (grammaticale) regels voldoen.  Enkel indien alle statements correct zijn zal het programma gecompileerd worden naar een werkend en uitvoerbaar programma (zoals in vorige sectie besproken).

# Keywords: de woordenschat
C# bestaat zoals gezegd uit enkel grammaticale regels. Grammatica zonder woordeschat is nutteloos. Er ijn binnen C# dan ook 80 woorden, zogenaamde **keywords** gereserveerd die de woordenschat voorstellen.
In dze cursus zullen we stelselmatig deze keywords leren kennen en gebruiken op een correcte manier om zo werkende code te maken.

Deze keywords zijn:
|   |     |     |   |
|----|----|-----|----|
|*abstract*	|*as*	|*base*	|**bool**|
|**break**|	**byte**|	**case**|	catch|
|**char**|	checked|	*class*|	**const**|
|continue|	**decimal**|	*default*	|delegate|
|**do**|	**double**|	**else**|	**enum**|
|event|	explicit|	extern|	**false**|
|finally|	fixed|	**float**|	**for**|
|*foreach*|	goto|	**if**|	implicit|
|*in*|	**int**|	*interface*|	internal|
|*is*|	lock|	**long**|	**namespace**|
|*new*|	*null*|	*object*|	*operator*|
|**out**|	*override*|	params|	*private*|
|*protected*|	*public*|	readonly|	**ref**|
|**return**|	**sbyte**|	*sealed*|	**short**|
|sizeof|	stackalloc|	*static*|	**string**|
|*struct*|	**switch**|	*this*|	throw|
|**true**|	try|	typeof|	**uint**|
|**ulong**|	unchecked|	unsafe|	**ushort**|
|using	|using static|	*virtual*|	**void**|
|volatile	|**while**| |

> De keywords in vet zijn keywords die we dit semester zullen kennen. Die in cursief in het tweede semester.

# Variabelen, identifiers en naamgeving
We hebben variabelen nodig om (tijdelijke) data in op te slaan. Wanneer we een statement schrijven dat bijvoorbeeld input van de gebruiker moet vragen, dan willen we ook die input bewaren, zodat we verderop in het programma (het algoritme) iets met deze data kunnen doen.
We doen hetzelfde in ons hoofd wanneer we bijvoorbeeld zegen "tel 3 en 4 op en vermenigvuldig dat resultaat met 5". Eerst zullen we het resultaat van 3+4 in een variabele moeten bewaren. Vervolgens zullen we de inhoud van die variabele vermenigvuldigen met 5 en dat nieuwe resultaat ook in een nieuwe variabele opslaan (om vervolgens bijvoorbeeld naar het scherm te sturen).

Wanneer we een variabele aanmaken zal deze moeten voldoen aan enkele afspraken. Zo moeten we minstens 2 zaken meegeven:
* Het type van de variabele: het **datatype**  dat aangeeft wat voor data we wensen op te slaan (tekst, getal, afbeelding, etc)
* De naam van de variabele: de **identifier** waarmee we snel aan de variabele-waarde aankunnen

De verschillende datatypes bespreken we in een volgende [hoofdstuk](1_datatypes.md).

## Regels voor identifiers
De code die we gaan schrijven moet voldoen aan een hoop regels. Wanneer we in onze code zelf namen (**identifiers**) moeten geven aan variabelen (en later ook methoden, objecten, etc) dan moeten we een aantal regels volgen:

* Hoofdlettergevoelig: de identifiers ``tim`` en ``Tim`` zijn verschillend. Je mag dus perfect twee verschillende variabelen aanmaken met deze name. 
* Geen keywords: identifiers mogen geen gereserveerd C# keyword zijn. De keywords van hierboven mogen dus niet. Varianten wel: denk maar aan ``goTO`` (``goto`` is een gereserveerd keyword, maar dankzij de hoofdlettergevoeligregel is dit dus toegelaten) en ``INT`` (tegenover keyword ``int``)
* Eerste karakter-regel: het eerste karakter van de identifier mag enkel zijn:
    * kleine of grote letter
    * liggend streepje ( ``_``)
* Alle andere karakters: de overige karakters moeten mogen enkel zijn:
    * kleine of groter| letter
    * liggend streepje
    * een cijfer (``1`` tot en met ``9`` en ``0``)
* Lengte: een legale identifier mag zo lang zijn als je wenst, maar hou het best leesbaar

# Commentaar
Soms wil je misschien extra commentaar bij je code zetten. Als je dat gewoon zou doen (bv ``Dit deel zal alles verwijderen``) dan zal je compiler niet begrijpen wat die zin doet. Hij verwacht namelijk C# syntax en niet een Nederlandstalige zin. Om dit op te lossen kan je in je code op twee manieren aangeven dat een stuk tekst gewoon commentaar is en mag genegeerd worden door de compiler:

## Enkele lijn commentaar  met //
Eén lijn commentaar geef je aan door de lijn te starten met twee voorwaartse slashes ``//``. Uiteraard mag je ook meerdere lijnen op deze manier in commentaar zetten. Zo wordt dit ook vaak gebruik om tijdelijk een stuk code "uit te schakelen". Ook mogen we commenaar *achter* een stuk C# code plaatsen (zie onderaan voorbeeld)
```csharp
//De start van het programma
int getal=3;
//Nu gaan we rekenen
int result = getal * 5;
// result= 5* 4;
Console.WriteLine(result); //We tonen resultaat op scherm
```
## Blok commentaar met /* en */
We kunnen een stuk tekst als commentaar aangeven door voor de tekst ``/*`` te plaatsen en achteraan de blok tekst ``*/``. Een voorbeeld:
```csharp
/*
    Veel commentaar.
    Een heel verhaal
    Mooi he.
    Is dit een haiku?
*/
int leeftijd= 0;
leeftijd++;
```