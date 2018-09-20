# Kennismaken met C# en Visual Studio Code {#kennismaken-met-c-en-visual-studio}
Visual Studio Code (VS) is het lightweight, corssplatform broertje van Visual Studio. Via VS kan je tal van projecten,inclusief C# projecten op een snelle, eenvoudige manier maken.  

# De compiler en Visual Studio Code
Jouw taak als programmeur in deze cursus is algoritmes in C# taal uitschrijven. We zouden dit in een eenvoudige tekstverwerker kunnen doen, maar dan maken we het onszelf lastig. Net zoals je tekst in notepad kunt schrijven, is het handiger dit in bijvoorbeeld Word te doen: je krijgt een spellingchecker en allerlei handige extra's. Ook voor het schrijven van computer code is het handiger om een zogenaamde IDE (Integrated Development Environment) te gebruiken, een omgeving die ons zal helpen foutloze C# code te schrijven.

Het hart van Visual Studio Code bestaat uit de **compiler** die we hiervoor besproken. De compiler zal je C# code omzetten naar de ILcode  zodat jij (of anderen) je applicatie op een computer (of ander apparaat) kan gebruiken. Zolang de C# niet exact voldoet aan de C# syntax (zie verder) zal de compiler het vertikken een uitvoerbaar bestand voor je te genereren. 
![](/assets/0_intro/compilereenvoudig.png)

**Opmerking**: In deze cursus zullen we steeds werken met Visual Studio Code. Niet met Visual Studio Enterprise. Uiteraard zal je alles dat we hier beschrijven in beide IDE's kunnen doen. 

# Visual Studio Code Installeren
Je kan Visual Studio Code downloaden via [https://code.visualstudio.com/](https://code.visualstudio.com/) 


# Een nieuw project aanmaken 

Wanneer je je eerste C# project aanmaakt (of opent) in VS Code zal de IDE een aantal extensies installeren. Als je VS Code dit niet laat doen zal je geen C# projecten kunnen uitvoeren.

Het maken van een C# project bestaat uit volgende stappen:
1. Bestaande of nieuwe folder aanmaken
2. Deze folder openen in VS Code 
3. VS Code vertellen in deze folder een nieuw C# project aan te maken via terminalcommande: ``dotnet new console``

Je kan via het terminal venster (View-> new Terminal) heel snel deze stappen uitvoeren. Stel dat je op de huidige locatie een project wil aanmaken in de folder "EERSTEPROJECT", schrijf dan:
```
mkdir EERSTEPROJECT
cd EERSTEPROJECT
dotnet new console
code .
```

> Indien ``dotnet new console`` een error geeft moet je eerst via [https://www.microsoft.com/net/download](https://www.microsoft.com/net/download) de ".NET Core SDK" downloaden installeren!(linkerzijde op de pagina!)

## Toelichting bij deze commando's
De commando's die je hier staan zijn zogenaamde shell-commando's:
* ``mkdir`` : "make directory". Dit zal in de huidige folder een nieuwe folder aanmaken met de naam die je als extra argument meegeeft (EERSTEPROJECT in dit geval)
* ``cd``: "change directory" . Hiermee gaan we 'in' de directory/folder die we meegeven als argument. Indien je gewoon de naam geeft (zonder het gehele path zoals C:\Temp\Test) dan wordt veronderstelt dat de folder zich in de huidige folder bevindt.
* ``dotnet new console``: dit geeft aan dat in de huidige folder (dus EERSTEPROJECT nu) een nieuw C# moet aangemaakt worden.
* ``code .`` : open een nieuw Visual Studio Code venster waarin je nieuw project/folder het actieve project is.


# Je project
Er werden enkele files aangemaat, de enige belangrijke momenteel zijn:
* Program.cs: hierin plaats je de effectieve code van je project
* Een .csproj file: hierin staan alle gegevens over je project die nodig zijn om het project te kunnen builden 

** Een andere ontwikkelaar heeft de HELE map nodig om met jouw project te kunnen werken. Enkel de program.cs file is niet genoeg.**

# Je programma starten 
De code die VS voor je heeft gemaakt is reeds een werkend, maar weinig nuttig, programma. Je kan de code compileren naar een uitvoerbaar bestand door te klikken op Debug-&gt;Start Debugging (of via F5 shortcut). Als dit gelukt is zal er onderaan VS in de statusbar ‘Build succeeded’ verschijnen en even later zal je de uitvoer van je programma zien.
>> Indien dit de eerste keer is dat je je project build dan zal je mogelijk nog de nodige extra door VS Code moeten laten installeren (*restore*), laat dit toe.

