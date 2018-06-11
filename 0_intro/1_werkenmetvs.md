# Kennismaken met C# en Visual Studio {#kennismaken-met-c-en-visual-studio}

Het grootste deel van het leven van een beginnende software-ontwikkelaar ("programmeur") vindt plaats in een ontwikkelomgeving. Dit is de plek waar je je computercode zal schrijven, die vervolgens zal omgezet worden naar een uitvoerbare applicatie. 

visual Studio (VS) is een pakket dat een groot deel tools samenvoegt (debuger, code editor, compiler, etc) zodat je niet tientalle paketten moet gebruiken om software te schrijven.

Visual Studio is een zogenaamde IDE("Integrated Development Environment") en is op maat gemaakt om C#.NET applicaties te ontwikkelen. Je bent echter verre van verplicht om enkel C# applicaties in VS te ontwikkelen, je kan gerust VB.NET, TypeScript, Pythong en andere talen gebruiken.


## Visual Studio Code - de lightweight VS
Visual Studio vindt eindelijk ook z'n weg op andere platformen. Zoek je een lightweight versie dan moet je zeker eens [Visual Studio Code](https://code.visualstudio.com/) eens proberen.

# Visual studio opstarten

Na het opstarten van VS krijg je het startvenster te zien van waaruit je verschillende dingen kan doen, zoals eerder aangemaakte projecten opstarten, informatie opzoeken of een totaal nieuw project starten.



### Een nieuw project aanmaken 

We zullen nu een nieuw project aanmaken. Dit kan op verschillende manieren. De eenvoudigste manier is door te klikken op File -&gt; New -&gt; Project…

Het "New Project" venster dat nu verschijnt geeft je hopelijk al een glimps van de veelzijdigheid van VS. In het linkerdeel zie je bijvoorbeeld alle Project Types staan. M.a.w. dit zijn alle soorten programma’s die jan kan maken in VS. Naargelang de geïnstalleerde opties en bibliotheken zal deze lijst groter of kleiner zijn.

In ons geval kiezen we als Project Type **‘Visual C#’** en als template **Console Application**. Onderaan kan je een naam geven voor je project alsook de locatie op de harde schijf waar het project dient opgeslagen te worden. **Onthoudt waar je je project aanmaakt zodat je dit later terugvind**.

Geef volgende informatie op:

Druk ok.

VS heeft nu reeds een aantal bestanden aangemaakt die je nodig hebt om een ‘Console Applicatie’ te maken. 
Een console applicatie is een programma dat alle uitvoer naar een zogenaamde ‘console’ stuurt,een shell. Maw, je kan enkel tekst (ASCII/Unicode) als uitvoer genereren en dus geen multimedia elementen zoals afbeeldingen, geluid, etc.

## Goed nakijken
Kijk steeds goed volgende zaken na voor je je nieuwe project aanmaakt:
*	Kies **Visual C#** als taal (en niet Visual Basic ofzo)
*	Kies **Console Application** (en niet Windows Form Application ofzo)
*	Zet al je projecten op een vaste locatie op je hd (of nog beter op je dropbox o.i.d.)



# IDE Layout {#ide-layout}

We zullen nu eerst eens bekijken wat we allemaal zien in VS na het aanmaken van een nieuw programma.

Je kan meerdere bestanden tegelijkertijd openen in VS. Ieder bestand zal z’n eigen tab krijgen. De actieve tab is het bestand wiens inhoud je in het hoofdgedeelte eronder te zien krijgt.

De "solution explorer" toont alle bestanden en elementen die tot het huidige project behoren. Als we dus later nieuwe bestanden toevoegen dan kan je die hier zien (en openen).

Het properties venster (eigenschappen) is een belangrijk venster. Hier komen alle eigenschappen van het huidige geselecteerde element. Selecteer bijvoorbeeld maar eens Program.cs in de solution explorer en merk op dat er allerlei eigenschappen getoond worden. Onderaan het Propertis venster wordt steeds meer informatie getoond over de huidig geselecteerde eigenschap (zoals in dit geval de Build Action).

## Layout kapot/kwijt/vreemd
Het gebeurt al eens dat je layout een beetje om zeep is.  
* Voor eenvoudige venster terug te krijgen, bijvoorbeeld het properties window of de solution explorer: klik bovenaan in de menubalk op "View" en kies dan het gewenste venster (soms staat dit in een submenu)
* Je kan ook altijd je layout in z'n geheel resette: Ga naar "Window" en kies "Reset window layout".

# Je programma starten 
De code die VS voor je heeft gemaakt is reeds een werkend programma. Je kan de code compileren naar een uitvoerbaar bestand door te klikken op Build-&gt;Build Solution. Als dit gelukt is zal er onderaan VS in de statusbar ‘Build succeeded’ verschijnen.

Je kan nu je gecompileerde bestand uitvoeren door te kiezen voor Debug-&gt;Start without debugging (of door te drukken op ctrl+F5).

Veel doet je programma nog niet natuurlijk, dus sluit dit venster maar terug af door een willekeurige toets in te drukken.