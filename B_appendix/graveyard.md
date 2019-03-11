Op deze pagina vind je alle briljante en minder briljante oefeningen terug die niet meer bij een bepaald hoofdstuk staan. Meestal staan deze oefeningen hier omdat ze leerstof behandelen die niet meer bij de verplichte leerstof hoort.

# APCenture-Job Agency

> Opgave is niet erg duidelijk.
> 
Maak een klasse ``Job``. Deze klasse heeft vier private fields

* Description (``string``) bijvoorbeeld "ruiten wassen"
* Duration (``int``) , stelt tijd voor die nodig is om job uit te voeren
* RatePerHour (``int``), stelt kostprijs per uur voor van deze job
* TotalFee (``int``), stelt totale prijs voor zijnde  ``Duration * RatePerHour``

Voorzie properties voor deze 4 velden, echter de TotalFee heeft geen ‘set’ daar deze een berekening van andere properties is en dus een read-only property is.

Telkens de Duration of RatePerHour wordt aangepast (set) wordt de TotalFee herberekend (je zal dus een private totalFee nodig hebben waar de public property TotalFee z’n waarde van krijgt).

Voorzie 2 constructors:

* Default constructor: stelt de description in op "onbekend" en zet duration en rateperhour op 0.
* Overloaded constructor: waarbij je de 3 velden (behalve TotalFee) kan aanpassen tijdens de constructie van een Job-object.

Toon de werking van je klasse aan door enkele objecten aan te maken met zowel de default als de overloaded constructor. Toon vervolgens dat TotalFee correct werkt.

# APCenture-Job Agency, deel 2: Operator Overloading

Pas de klasse ``Job`` aan zodat de + operator kan gebruikt worden om 2 job-objecten bij elkaar op te tellen.
Bv:

```csharp
Job epicDuoJob= jobOne+jobTwo;  //jobOne en jobTwo zijn ook van het type Job
```

De som van 2 job-objecten gaat als volgt te werk:

* Description: beide description worden na elkaar geplakt, waarbij het voegwoord ‘en’ tussen beide wordt gezet.
* Duration: som van beide durations
* RatePerHour: gemiddelde de ``rateperhour``van beide objecten

Toon in je main aan dat je nieuwe klasse werkt en dat je 2 jobs kan samenvoegen. Toon ook aan dat je vervolgens deze nieuwe samenvoeging op zijn beurt kan samenvoegen met een andere job (of zelfs met een andere samengevoegde job!).

# Breuk
Maak een klasse ``Breuk`` dat dus een breuk zal voorstellen met een noemer en teller.

Voorzie properties voor noemer en teller, waarbij de noemer niet 0 mag zijn (zet deze op 1 indien de gebruiker dit toch probeert).

Voeg 2 constructors toe:

* Default constructor: de breuk wordt ingesteld op 0/1
* Overloaded constructor: zowel de noemer als teller worden als parameter meegegeven

Voorts:

1. Voeg een ``+ operator`` toe die het mogelijk maakt om 2 breuken bij elkaar op te tellen. Wanneer de + operatie is toegepast wordt ook automatisch de Vereenvoudig-methode aangeroepen (zie verder) voor het resultaat wordt teruggegeven. Belangrijk: je dient aan operator overloading te doen. We willen dus dat je bijvoorbeeld kan schrijven ``Breuk breuksom= breuk1 + breuk2;``
2. Voeg voorts een ``* operator`` toe die breuken vermenigvuldigen mogelijk maakt (ook hier wordt het resultaat vereenvoudigd teruggegeven).
3. Voeg een methode ``AlsString`` toe die de breuk als string teruggeeft, waarbij de breuklijn als slash wordt voorgesteld.

Maak een array van 4 breuken in je main en laat de gebruiker deze alle 4 invullen. Toon vervolgens de som en vermenigvuldiging van deze 4 breuken als strings op het scherm.

Pro: Voeg een methode ``Vereenvoudig`` toe. Deze zal de breuk vereenvoudigen indien mogelijk. Als dus de breuk op 2/4 staat dan wordt deze na het uitvoeren van deze methode 1/2.