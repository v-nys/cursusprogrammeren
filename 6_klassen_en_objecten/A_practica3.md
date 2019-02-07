# Grotere oefeningen

## Studentklasse
Maak een nieuwe klasse ``Student``.
Deze klasse heeft 6 public fields:

* Naam (string)
* Leeftijd (int)
* Klas (maak dit van een ``enum``)
* PuntenCommunicatie (int)
* PuntenProgrammingPrinciples (int)
* PuntenWebTech (int)	 
Daar deze fields allemaal public zijn kunnen we deze dus rechtstreeks veranderen.

Voeg aan de klasse een methode ``BerekenTotaalCijfer`` toe. Wanneer deze methode wordt aangeroepen dan wordt het gemiddelde van de 3 punten  teruggegeven als double zodat dit op het scherm kan getoond worden.

Voeg aan de klasse  ook de methode ``GeefOverzicht`` toe. Deze methode zal een volledig "Rapport" van de student tonen (inclusief het gemiddelde m.b.v. de BerekenTotaalCijfer-methode).

Test je programma door enkele studenten aan te maken en in te stellen. Volgende main zou dan de bijhorende output moeten krijgen:
```csharp
    Student student1;
    student1.Klas = Klassen.EA2;
    student1.Leeftijd = 21;
    student1.Naam = "Joske Vermeulen";
    student1.PuntenCommunicatie = 12;
    student1.PuntenProgrammingPrinciples = 15;
    student1.PuntenWebTech = 13;

    student1.GeefOverzicht();
```
Output:
```csharp
Joske Vermeulen, 21 jaar
Klas: EA2

Cijferrapport:
**********
Communicatie:             12
Programming Principles:   15
Web Technology:           13
Gemiddelde:               13.3
```
## Student Organizer

We gaan nu de Student-klasse gebruiken om een array van studenten te vullen.

Maak daarom een studenten-array aan die 5 studenten bevat :
```csharp
Student[] alleStudenten= new Student[5];
for(int i =0 ;  i<5;++)
    alleStudenten[i]= new Student();
```
Initialiseer alle fields van iedere student op een standaard-waarde (mbv een for-loop), bv:
 
Het programma start op en geeft de gebruiker een menu waaruit kan gekozen worden:

1. Student gegevens invoeren (eerstvolgende student wordt ingevuld)
Vervolgens moet de gebruiker kiezen welke student (nummer) moet ingevuld worden, van 1 tot 5. Vervolgens kan de gebruiker de gegevens 1 voor 1 invullen (oude gegevens worden zonder pardon overschreven).

 
2. Student gegevens tonen (alle studenten)
Wanneer de gebruiker voor 2 kiest dan wordt de GeefOverzicht-methode aangeroepen van iedere student zodat de 5 ‘rapportjes’ onder elkaar op het scherm 

Extra's:
Bouw extra functionaliteit naar keuze bij de StudentOrganizer, zoals: 
* Vragen aan de gebruiker of de oude gegevens overschreven mogen worden, indien deze reeds ingevuld zijn.
* Inbouwen van een eenvoudige zoekfunctie. Je kan bijvoorbeeld zoeken op naam (exacte invoer) of alle studenten tonen die in een bepaalde klas zitten of wiens punten onder/boven een bepaalde waarde zitten. Je kan dit als extra menuitem inbouwen, waarbij een nieuw menu verschijnt dat de gebruiker de verschillende zoekmogelijkheden voorstelt.
* Verwijderen van een student (waarbij alle gegevens worden gewist)
* Controle in alle methode inbouwen zodat ‘lege studenten’ worden genegeerd. Wanneer bijvoorbeeld menu item 2 wordt uitgevoerd (alle studenten tonen) dan worden enkel de ingevulde studenten getoond.



## APCenture-Job Agency
### Deel 1: constructors
Maak een klasse ``Job``. Deze klasse heeft vier data fields:
* Description (string) bijvoorbeeld “ruiten wassen”
* Duration (int) , stelt tijd voor die nodig is om job uit te voeren
* RatePerHour (int), stelt kostprijs per uur voor van deze job
* TotalFee (int), stelt totale prijs voor zijnde  duration x rateperhour
Voorzie properties voor deze 4 velden, echter de TotalFee heeft geen ‘set’  daar deze een berekening van andere properties is. 
Telkens de Duration of RatePerHour wordt aangepast (set) wordt de TotalFee herberekend (je zal dus een private totalFee nodig hebben waar de public property TotalFee z’n waarde van krijgt).

Voorzie 2 constructors:
* Default constructor: stelt de description in op “onbekend” en zet duration en rateperhour in op 0.
* Overloaded constructor: waarbij je de 3 velden (behalve TotalFee) kan aanpassen tijdens de constructie van een Job-object

Toon de werking van je klasse aan door enkele objecten aan te maken met zowel de default als de overloaded constructor. Toon vervolgens dat TotalFee correct werkt.

### Deel 2: Operator Overloading
Pas de klasse ‘Job’ aan zodat de + operator kan gebruikt worden om 2 job-objecten bij elkaar op te tellen.
Bv:
```csharp
Job epicDuoJob= jobOne+jobTwo;  //jobOne en jobTwo zijn ook van het type Job
```
De som van 2 job-objecten gaat als volgt te werk:
* Description: beide description worden na elkaar geplakt, waarbij het voegwoord ‘en’ tussen beide wordt gezet.
* Duration: som van beide durations
* RatePerHour: gemiddelde de ``rateperhour``van beide objecten
Toon in je main aan dat je nieuwe klasse werkt en dat je 2 jobs kan samenvoegen. Toon ook aan dat je vervolgens deze nieuwe samenvoeging op zijn beurt kan samenvoegen met een andere job (of zelfs met een andere samengevoegde job!).

### Breuk
Maak een klasse ‘Breuk’ dat dus een breuk zal voorstellen met een noemer en teller.

Voorzie properties voor noemer en teller, waarbij de noemer niet 0 mag zijn (zet deze op 1 indien de gebruiker dit toch probeert).

Voeg 2 constructors toe:

* Default constructor: de breuk wordt ingesteld op 0/1
* Overloaded constructor: zowel de noemer als teller worden als parameter meegegeven

Voorts:
1. Voeg een + operator toe die het mogelijk maakt om 2 breuken bij elkaar op te tellen. Wanneer de +operatie is toegepast wordt ook automatisch de Vereenvoudig-methode aangeroepen (zie verder) voor het resultaat wordt teruggegeven. Belangrijk: je dient aan operator overloading te doen. We willen dus dat je bijvoorbeeld kan schrijven Breuk breuksom= breuk1 + breuk2;
2. Voeg voorts een * operator toe die breuken vermenigvuldigen mogelijk maakt (ook hier wordt het resultaat vereenvoudigd teruggegeven).
3. Voeg een methode ‘AlsString’ toe die de breuk als string teruggeeft, waarbij de breuklijn als slash wordt voorgesteld.

 
Maak een array van 4 breuken in je main en laat de gebruiker deze alle 4 invullen. Toon vervolgens de som en vermenigvuldiging van deze 4 breuken als strings op het scherm.

Pro: Voeg een methode ‘Vereenvoudig’ toe. Deze zal de breuk vereenvoudigen indien mogelijk. Als dus de breuk op 2/4 staat dan wordt deze na het uitvoeren van deze methode 1/2.
