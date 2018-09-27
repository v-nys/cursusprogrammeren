# String interpolation
Kies 2 oefeningen uit het vorige hoofdstuk waarin je output op het scherm moest geven. Pas string interpolatie m.b.v. ``$`` (manier 2) toe in deze 2 oefeningen.

> Volgende 2 oefeningen zijn al iets stevigers. Iedere oefening eindigt met een [PRO] gedeelte dat je best enkel doet als je een uitdaging wenst.

# Systeem informatie
## Deel 1
Maak een applicatie die de belangrijkste computer-informatie (geheugen, etc) aan de gebruiker toont.

Deze computer-informatie kan je verkrijgen mbv de Environment-klasse. Hier enkele voorbeelden (kijk zelf of er nog nuttige properties over je computer in staan):
```csharp
            bool is64bit = Environment.Is64BitOperatingSystem;
            string pcname = Environment.MachineName;
            int proccount = Environment.ProcessorCount;
            string username = Environment.UserName;
            long memory = Environment.WorkingSet; //bytes (hoeveelheid geheugen dat je programma krijgt van windows)
```

Zoals je ziet wordt het geheugen in bytes teruggegeven. Zorg ervoor dat het geheugen steeds in mega of gigabytes op het scherm wordt getoond.

**Formateer de informatie met behulp van de $-notatie  zodat deze  deftig getoond worden en de gebruiker snel de belangrijke informatie over z'n systeem te zien krijgt.**

## [PRO] Deel 2

Ook informatie over de harde schijven kan je verkrijgen (in bits). Dit vereist wel dat je bovenaan je programma volgende lijn bijschrijft: ``using System.IO``. Vervolgens kan je in je programma schrijven:

```csharp
            long cdriveinbytes = DriveInfo.GetDrives()[0].AvailableFreeSpace;  
            long totalsize = DriveInfo.GetDrives()[0].TotalSize;  
```
 De lijn met using is om aan te geven dat we iets uit de ``System.IO`` bibliotheek nodig hebben, namelijk ``DriveInfo``.
Schrijven we dat niet dan moeten we in onze code DriveInfo aanroepen met z'n volledige path: ``System.IO.DriveInfo....``

De 0 tussen rechte haakjes is de index van welke schijf je informatie wenst. 0 is de eerste harde schijf, 1 de tweede, enzovoort. (Ter info: dit zijn arrays, zie later)

Vraag aan de gebruiker het nummer van de harde schijf waar meer informatie over moet getoond worden. 

Opgelet: sta toe dat de gebruiker 1 voor de eerste harde schijf mag gebruiken, 2 voor de tweede, enzovoort. Je zal dus in code nog manueel 1 moeten aftrekken van de invoer van de gebruiken.
Bv:
```csharp
int invoer= Convert.ToInt(Console.ReadLine()) - 1 ;
 long totalsize = DriveInfo.GetDrives()[invoer].TotalSize;  
 ```

# Weerstandberekenaar
## Deel 1
Maak een programma dat de weerstandwaarde berekent gebaseerd op:
* Ring 1: die de tientallen voorstelt
* Ring 2: die de eenheden voorstel
* [ENKEL VOOR PRO] Ring 3: die de exponent (10 tot de macht) voorstelt. (tip:``Math.Pow(10,ring3``))

Gebruik twee variabelen van het type ``int`` waar je getal van 0 tot 9 telkens aan kan toewijzen.
Test dat je "formule/berekening" klopt om gebaseerd op 2 (of 3) ringen de weerstandswaarde te berekenen. 

## Deel 2
Plaats het geheel in een mooie UNICODE/Asci-tabel

Hier enkele nuttige tekens:
```
╔═══════════════╦═══════════════╗
║ 
╟───────────────╫───────────────╢
║ 
╚═══════════════╩═══════════════╝
```

Gebruik $-string interpolatie om de informatie in de tabel te tonen zodat je volgende uitvoer kunt genereren:
![](/assets/1_csharpbasics/tabel.png)

of:

![](/assets/1_csharpbasics/tabel2.png)

## [PRO²] Deel 3

Kan je afhankelijk van de ringwaarde het getal in de tabel in de juiste kleur zetten conform de weerstandskleuren (tip: je zal ``Write`` en ``if`` moeten leren gebruiken)