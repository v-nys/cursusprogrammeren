# Oefeningen

## Oefening: H2-string-interpolation

### Leerdoelen

* gebruik van string interpolation

### Functionele analyse

Oefening H1-maaltafels en H1-ruimte dienen we te herschrijven volgens de principes van string interpolation.

### Technische analyse

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

Zie oefening H1-maaltafels en H1-ruimte.

### Technische hulp

#### Programmaverloop

Pas string interpolatie mbv `$` \(manier 2\) toe.

#### Testscenario's

* Zie oefening H1-maaltafels en H1-ruimte.

### Ondersteunend materiaal

Hou het voorlopig op de cursus.

## 

> Volgende oefeningen zijn al iets stevigers.   
> Iedere oefening eindigt met een \[PRO\] gedeelte.



## Oefening: H2-systeem-informatie

### Leerdoelen

* gebruik van string interpolation
* gebruik van environment class

### Functionele analyse

Maak een applicatie die de belangrijkste computer-informatie \(geheugen, etc\) aan de gebruiker toont.

### Technische analyse

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```text
Uw computer heeft een 64-bit besturingssysteem: True
De naam van uw pc is: LAPTOP
Uw pc heeft 4 processorkernen.
ikke is uw gebruikersnaam.
Je gebruikt 12439552 bytes aan geheugen
```

### Technische hulp

#### Programmaverloop

Pas string interpolatie mbv `$` \(manier 2\) toe.  
De computerinformatie kan je verkrijgen mbv de Environment-klasse. Hier enkele voorbeelden \(kijk zelf of er nog nuttige properties over je computer in staan en voorzie deze ook binnen jouw code\):

```csharp
bool is64bit = Environment.Is64BitOperatingSystem;
string pcName = Environment.MachineName;
int procCount = Environment.ProcessorCount;
string userName = Environment.UserName;
long memory = Environment.WorkingSet; //zal ongeveer 10 Mb teruggeven.
```

> **WorkingSet** geeft terug hoeveel geheugen het programma van windows toegewezen krijgt. Als je dus op 'run' klikt om je code te runnen dan zal dit programma geheugen krijgen en via WorkingSet kan het programma dus zelf zien hoeveel het krijgt. \(wat een vreemde lange zin\).

Zoals je ziet wordt het geheugen in bytes teruggegeven. Zorg ervoor dat het geheugen steeds in mega of gigabytes op het scherm wordt getoond.

**Formateer de informatie met behulp van de $-notatie zodat deze deftig getoond worden en de gebruiker snel de belangrijke informatie over z'n systeem te zien krijgt.**

#### Testscenario's

* wat gebeurt er wanneer je het datatype string zou wijzigen in int?

### Ondersteunend materiaal

Hou het voorlopig op de cursus.

## Oefening: H2-systeem-informatie-pro

### Leerdoelen

* gebruik van string interpolation
* gebruik van system.io

### Functionele analyse

Informatie over de harde schijven van uw pc dienen te worden weergeven. 

### Technische analyse

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```text
Vrije ruimte op jouw c-schijf: 10803744768
Totale ruimte van jouw c-schijf: 159671906304

********************************************************************************
Geef met nummer 1 t/m ... aan over welke harde schijf van jouw pc je info wenst: 1
De vrije ruimte van C:\ is 108 Gb
```

### Technische hulp

#### Programmaverloop

Ook informatie over de harde schijven kan je verkrijgen \(in bits\). Dit vereist wel dat je bovenaan je programma volgende lijn bijschrijft: `using System.IO`.

Vervolgens kan je in je programma schrijven:

```csharp
long cDriveInBytes = DriveInfo.GetDrives()[0].AvailableFreeSpace;  
long totalSize = DriveInfo.GetDrives()[0].TotalSize;
```

De lijn met `using` is om aan te geven dat we iets uit de `System.IO` bibliotheek nodig hebben, namelijk `DriveInfo`. Schrijven we dat niet dan moeten we in onze code DriveInfo aanroepen met z'n volledige path: `System.IO.DriveInfo....`

De 0 tussen rechte haakjes is de index van welke schijf je informatie wenst. 0 is de eerste harde schijf, 1 de tweede, enzovoort. \(Ter info: dit zijn arrays, zie later\)

Vraag aan de gebruiker het nummer van de harde schijf waar meer informatie over moet getoond worden.

Opgelet: sta toe dat de gebruiker 1 voor de eerste harde schijf mag gebruiken, 2 voor de tweede, enzovoort. Je zal dus in code nog manueel 1 moeten aftrekken van de invoer van de gebruiken. Bv:

```csharp
int input= Convert.ToInt32(Console.ReadLine()) - 1 ;
long totalSize = DriveInfo.GetDrives()[input].TotalSize;
```

#### Testscenario's

* wat gebeurt er wanneer je het datatype int zou wijzigen in string?

### Ondersteunend materiaal

Hou het voorlopig op de cursus.

## Oefening: H2-weerstandberekenaar-deel1

### Leerdoelen

* gebruik van math class

### Functionele analyse

Stel dat je in het labo een weerstand vastneemt en je kent de kleurcodes van de streepjes wel, maar niet hoe je die kunt omzetten naar de effectieve weerstandswaarde. In dit programma kunnen we de gebruiker helpen.

![](../../.gitbook/assets/colors.jpg)

\(Bron afbeelding: [https://www.esdsite.nl](https://www.esdsite.nl)\)

### Technische analyse

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```text
Geef de waarde (uitgedrukt in een getal van 0 tot 9) van de eerste ring: 2
Geef de waarde (uitgedrukt in een getal van 0 tot 9) van de tweede ring: 2
Geef de waarde (uitgedrukt in een getal van 0 tot 9) van de derde ring (exponent): 2
Resultaat is 2200 Ohm, ofwel 22x100.
```

### Technische hulp

#### Programmaverloop

Maak een programma dat de weerstandwaarde berekent gebaseerd op:

* Ring 1: die de tientallen voorstelt
* Ring 2: die de eenheden voorstel
* Ring 3: die de exponent \(10 tot de macht\) voorstelt. \(tip:`Math.Pow(10,ring3`\)\)

Gebruik twee variabelen van het type `int` waar je getal van 0 tot 9 telkens aan kan toewijzen. \(we veronderstellen dus dat de gebruiker de kleurcode heeft omgezet naar een getal en dat toewijst aan de variabele\)

Test dat je "formule/berekening" klopt om gebaseerd op 2 \(of 3\) ringen de weerstandswaarde te berekenen.

## Oefening: H2-weerstandberekenaar-deel2

### Leerdoelen

* gebruik van UNICODE/Asci-tabel

### Functionele analyse

Zie deel 1.

### Technische hulp

#### Programmaverloop

Zie deel 1 en plaats het geheel in een mooie UNICODE/Asci-tabel

Hier enkele nuttige tekens:

```text
╔═══════════════╦═══════════════╗
║ 
╟───────────────╫───────────────╢
║ 
╚═══════════════╩═══════════════╝
```

Gebruik $-string interpolatie om de informatie in de tabel te tonen zodat je volgende uitvoer kunt genereren: ![](../../.gitbook/assets/tabel.png)

of:

![](../../.gitbook/assets/tabel2.png)

### \[PRO\] Deel 3

Kan je afhankelijk van de ringwaarde het getal in de tabel in de juiste kleur zetten conform de weerstandskleuren \(tip: je zal `Write` en `if` moeten leren gebruiken\)

## \[PRO\] Shell-starter

Je kan de output van een `Process.Start()` programma naar je console scherm sturen. Dit vereist wat meer code. Volgende voorbeeld zal de output van het commando `ipconfig /all` op het scherm tonen:

```csharp
System.Diagnostics.Process process = new System.Diagnostics.Process();
process.StartInfo.FileName = "ipconfig";
process.StartInfo.Arguments = "/all"; 
process.StartInfo.UseShellExecute = false;
process.StartInfo.RedirectStandardOutput = true;
process.StartInfo.RedirectStandardError = true;
process.Start(); //start process

// Read the output (or the error)
string output = process.StandardOutput.ReadToEnd(); //normal output
Console.WriteLine(output);
string err = process.StandardError.ReadToEnd(); //error output (if any)
Console.WriteLine(err);
process.WaitForExit();
//Continue
Console.WriteLine("Klaar");
```

> Let er op dat dit voorbeeld niet perfect werkt met een shell-commando dat even duurt. Denk bijvoorbeeld aan `ping`. De output komt namelijk pas op het scherm als het commando is afgelopen. Test zelf maar eens!

Maak enkele kleine C\# programma's die bepaalde shell-commando's zullen uitvoeren , eventueel na input van de gebruiker. Enkele nuttige shell-commando's in de netwerk-sfeer zijn bijvoorbeeld:

```text
hostname

arp -a

getmac 

nslookup google.com

netstat
```

Andere toffe commando's kunnen zijn:

```text
chrome.exe ap.be
notepad mytest.txt
```

Of de naam van een bestand dat je wilt openen, maar dan met het hele path:

```text
c:\Temp\mydocument.docx
```

