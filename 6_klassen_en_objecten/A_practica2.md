# Pokémon

We gaan een programma schrijven dat ons toelaat enkele basis-eigenschappen van specifieke pokémon te berekenen terwijl ze levellen. 
Nadruk van deze oefening is het juist gebruiken van properties. Bekijk de cheat sheet bij twijfel.

>Disclaimer: de informatie in deze tekst is een vereenvoudigde versie van de echte Pokémon-stats in de mate dat ik het allemaal een beetje kon begrijpen en juist interpreteren.

## Hoe Pokémons werken

Korte uitleg over Pokémons en hun interne werking: Iedere Pokémon wordt uniek gemaakt door z’n base-stats, deze zijn voor iedere Pokémon anders. Deze base-stats  (punt 3) zijn onveranderlijk en blijven dus doorheen het hele leven van een Pokémon dezelfde. Je kan de base-stats als het dna van een Pokémon beschouwen.

De full-stats (punt 9) zijn echter de stats die de effectieve ‘krachten’ van een Pokémon bepalen in een gevecht. Deze stats worden berekend gebaseerd op de vaste base-stats en het huidige level van de Pokémon. Hoe hoger het level van de Pokémon, hoe hoger dus zijn full-stats. 

![pokemon](/assets/6_klassen/pokemon.png)

## De Pokémonopdracht

1.	Maak een consoleapplicatie.
2.	Maak een klasse Pokémon.
3.	Maak een klasse Pokémon die je toelaat om de basiseigenschappen (base stats) van een Pokémon te bewaren.

Maak voor al deze basis-eigenschappen full properties  van het type int:

a.	HP_Base
b.	Attack_Base
c.	Defense_Base
d.	SpecialAttack_Base
e.	SpecialDefense_Base
f.	Speed_Base
4.	Voorts wordt een pokémon ook gedefinieerd door z’n naam (string) ,type (string, bv "grass & poison") en nummer (int), maak hiervoor auto properties aan.

5.	Voeg een fullproperty Level toe(type int). Deze heeft een public get, maar een private setter.
6.	Voeg een publieke methode "VerhoogLevel" toe. Deze methode zal , via de private setter van Level (zie vorig punt), de level van de Pokémon met 1 verhogen.
7.	Voeg 2 read-only properties toe (enkel get, géén set) genaamd "Average" en "Total". De Average-property geeft het gemiddelde van de 6 basestats terug , dus (HP_Base+Attack_Base+Defense_Base +SpAttack_Base +SpDefense_Base +Speed_Base)/6. De Total-property geeft de som terug van de 6 basestats.
8.	Voeg een read-only HP_Full property (int) toe om de maximum health voor te stellen. Deze wordt berekend als volgt: 
(( (HP_Base + 50 ) * Level ) / 50 ) + 10  
Zie hier voor de exacte berekening voor de Pokémon-fans onder ons.
9.	Voeg voor iedere basetats een stat_full toe (int). Dus Defense_Full, Speed_Full, etc. Ook deze properties zijn readonly. Deze stats worden berekend als volgt: 
( (stat_Base*Level) / 50 ) + 5 
a.	Bv: Attack_Full wordt berekend als: ((Attack_Base*Level)/50)+5
10.	Kies enkele Pokémon uit [deze lijst](http://bulbapedia.bulbagarden.net/wiki/List_of_Pok%C3%A9mon_by_base_stats_(Generation_VI-present) en maak in je Main enkele Pokémon-objecten aan met de juiste eigenschappen. Toon aan dat de Average, Total , HP en andere stats correct berekend worden (controleer in de tabel op de voorgaande url).
11.	Maak een kleine loop die je toelaat om per loop een bepaalde pokémon z’n level met 1 te verhogen en vervolgens toon je dan z’n nieuwe stats.
12.	Test eens hoe de stats na bv 100 levels evolueren. Je zal zien dat bepaalde stats pas na een paar keer levelen ook effectief beginnen stijgen.
13.	Voeg extra functionaliteit naar keuze toe

## Pokémons en constructors

Pas de kennis van constructors toe op je Pokémon-project. Zorg ervoor dat je Pokémons op 3 kunt aanmaken als volgt:

* Via een default constructor: alle base stats worden daarbij op 10 standaard ingesteld via de constructor
* Via een overloaded constructor die de gebruiker toelaat om de 6 base stats als parameters mee te geven
* Via object initializer syntax waarbij je eender welke stat kunt instellen.

 ## Deel 2: De Pokémontester

 [vergelijk je oplossing uit het vorige deel [met volgende oplossing](/assets/6_klassen/Pokemon.cs) ]
Maak een nieuwe console-applicatie genaamd "Pokémon Tester":

1. voeg de Pokémon-klasse-bestand toe aan dit project. Verander de "namespace" van dit bestand naar de namespace van je nieuwe console-applicatie  (zie "Aanpassen van klasse" in [volgende uitleg](https://codevan1001nacht.wordpress.com/2013/11/06/werken-met-klassen-in-visual-studio/))
2. Voeg een overloaded constructor aan de Pokémon-klasse toe die toelaat dat je pokémons kunt aanmaken door de zes base-stats als parameters mee te geven (bv new Pokémon(45,42,50,65,34,67)
3. Schrijf een applicatie die aan de gebruiker eerst de 6 base-stats vraagt. Vervolgens wordt de pokémon aangemaakt met die stats en worden de full-stats aan de gebruiker getoond
4. Vraag nu aan de gebruiker tot welke level de pokémon moet gelevelled worden. Roep zoveel keer de LevelUp-methode aan van de Pokémon.
5. Toon terug de full-stats van de nu ge-levelde Pokémon

# Digitale kluis
Maak een klasse DigitaleKluis die we gaan gebruiken om een kluis voor te stellen.

De klasse heeft volgende elementen: 

* Een private variabele die de toegangscode van de kluis bewaard als geheel getal (naam: code) 
* Een overloaded constructor die als parameter een geheel getal toelaat. Dit getal zal worden toegewezen aan de private variabele code.
* Een full property "CanShowCode" die kan ingesteld worden op true or false, om aan te geven of de code van buitenuit kan gezien worden.
* Een read-only property “CodeLevel” van type int. Deze property zal de "level" van de code teruggeven. Het level is eenvoudigweg de code gedeeld door 1000 als geheel getal (dus indien de code 500 is zal 0 worden teruggegeven, indien de code 2000 is wordt 2 teruggegeven, etc.) 
* Een fullproperty Code met private set. De get van deze property zal -666 teruggeven, tenzij CanShowcode op true staat, in dit geval zal de effectieve code worden terug gegeven. 
* Een methode "TryCode" die een geheel getal als parameter aanvaardt. De methode geeft een true terug indien de code correct was, anders false. Deze methode kan gebruikt worden om extern een code te testen , indien deze overeenkomt met de bewaarde code dan zal gemeld worden dat de code geldig is en wordt ook getoond hoeveel keer de gebruiker geprobeerd heeft. Indien de gebruiker -666 meegaf dan meldt de methode dat de gebruiker een cheater is . Indien de gebruiker een foute code meegaf dan meldt de methode dat dit een foute code was en wordt het aantal pogingen met 1 verhoogd.  
* Een private variabele “aantalpogingen” om bij te houden hoe vaak de gebruiker geprobeerd heeft de code te vinden. 
Maak enkele Digitale Kluis objecten aan in je main en test of je bovenstaande klasse correct is geïmplementeerd.