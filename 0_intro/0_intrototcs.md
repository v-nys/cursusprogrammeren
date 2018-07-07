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
Om een algoritme te schrijven dat onze computer begrijpt dienen we een programmeertaal te gebruiken. Net zoals er ontelbare spreektalen in de wereld zijn, zijn er ook vele programmeertalen. C# ('siejarp') is er een van de vele. In tegenstelling tot onze spreektalen moet een computertaal 'exact' zijn en moet het op ondubbelzinnige manier door de computer verstaan worden. C# is een taal die deel uitmaakt van de .NET omgeving die meer dan 15 jaar geleden door Microsoft werd ontwikkeld (juli 2000).

De geschiedenis en de hele .NET-wereld vertellen zou een cursus op zich betekenen en gaan we hier niet doen. Het is nuttig om weten dat er een gigantische bron aan informatie over .NET en C# online te vinden is, beginnende met [docs.microsoft.com](https://docs.microsoft.com/en-us/dotnet/csharp/getting-started/)

# Microsoft .NET
Bij de geboorte van .NET in 2000 zat dus ook de taal C#. .NET is een zogenaamd **framework**. Dit framework bestaat uit een grote groep van bibliotheken (**class libraries**) en een *virtual execution system* genaamd de **Common Language Runtume (CLR)**. De CLR zal ervoor zorgen dat C#, of andere .NET talen (F#, VB.NET,etc), kunnen samenwerken met de vele bibliotheken. 

Om een uitvoer bestand te maken (**executable**, vandaar de extensie .exe bij uitvoerbare programma's in windows)
 zal de broncode die je hebt geschreven in C# worden omgezet naar een **Intermediate Language** (IL) code. Op zich is deze IL code nog niet uitvoerbaar, maar dat is niet ons probleem. Wanneer een gebruiker een in IL geschreven bestand zal willen uitvoeren dan zal, achter de schermen, deze code ogenblikkelijk door de CLR naar machine code omzetten (**Just -In-Time** of JIT compilatie) en uitvoeren. De gebruiken zal dus nooit dit proces merken (tenzij hij geen .NET framework heeft geinstalleerd).

 ![](/assets/1_csharpbasics/compiler.png)

[(Bron afbeelding)](https://docs.microsoft.com/en-us/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework)

Merk op dat we veel details van de compiler achterwege laten hier. De compiler is een uitermate complex element , maar in deze fase van je (prille) programmeursleven hoeven we enkel de kern van de compiler te begrijpen: **het omzetten van C# code naar een uitvoerbaar bestand geschreven in IL code**.

> Deze cursus heeft als doel om je de programmeertaal C# aan te leren. Terwijl we dit doen zullen we ook geregeld andere .NET framework gerelateerde zaken aanraken.

# De compiler en Visual Studio
Jouw taak als **programmeur** in deze cursus is algoritmes in C# taal uitschrijven. We zouden dit in een eenvoudige tekstverwerker kunnen doen, maar dan maken we het onszelf lastig. Net zoals je tekst in notepad kunt schrijven, is het handiger dit in bijvoorbeeld Word te doen: je krijgt een spellingchecker en allerlei handige extra's. Ook voor het schrijven van computer code is het handiger om een zogenaamde IDE te gebruiken, een omgeving die ons zal helpen foutloze C# code te schrijven. Visual Studio is zo een IDE (Integrated Development Environment) die we in het vorige hoofdstuk reeds hebben besproken.

Het hart van Visual Studio bestaat uit de **compiler**. De compiler zal je C# code omzetten naar de ILcode  zodat jij (of anderen) je applicatie op een computer (of ander apparaat) kan gebruiken. Zolang de C# niet exact voldoet aan de C# syntax (zie verder) zal de compiler het vertikken een uitvoerbaar bestand voor je te genereren. 
