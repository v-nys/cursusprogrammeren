# Bookmark Manager
Maak een "bookmark manager". Deze tool zal in de console aan de gebruiker 5 favoriete sites vragen: naam en url. Vervolgens zal de tool alle sites in een lijst tonen met een nummer voor. De gebruiker kan dan de nummer intypen en de tool zal automatisch de site in de browser openen. 

Je opdracht:

1. Maak een array waarin je 5 bookmark objecten kan plaatsen. 
2. Vul de applicatie aan zodat de gebruiker: een bestaand bookmark kan verwijderen en een bestaand bookmark kan aanpassen

Enkele zaken die je nodig hebt:

**BookMark klasse:**
```csharp
class BookMark
{

    public string Naam { get; set; }
    public string URL { get; set; }
    public void OpenSite()
    {
        Process.Start("Iexplore.exe", URL);
    }
}
```
**Voorbeeld van hoe de bookmark klasse zal werken:** 
```csharp
BookMark u = new BookMark();
u.Naam = "Windows";
u.URL = "www.google.be";
u.OpenSite();
```

## Prijzen met foreach

Maak een array die tot 20 prijzen (double) kan bewaren. Vraag aan de gebruiker om 20 prijzen in te voeren en bewaar deze in de array. Doorloop vervolgens m.b.v. een foreach-lus de volledige array en toon enkel de elementen op het scherm wiens prijs hoger of gelijk is aan €5.00. Toon op het einde van het programma het gemiddelde van alle prijzen (dus inclusief de lagere prijzen).


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
