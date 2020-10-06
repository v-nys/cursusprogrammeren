# Oefeningen

## Uitbreiding Course en Student \(SchoolAdmin project\)

Breid je klasse `Course` uit met een \(full\) property Studiepunten. Deze ligt altijd tussen 1 en 30. Bij het gebruik andere waarden wordt er een ArgumentException gegooid.

Schrijf vervolgens een constructor voor Course die beginwaarden voor alle properties neemt en deze instelt.

Schrijf ook een constructor die geen aantal studiepunten neemt, maar dit wel instelt op 3, een vaak gebruikt aantal studiepunten. Doe dit door middel van constructor chaining.

Schrijf ook een constructor voor je bestaande klasse Student, met een parameter per property.

Refactor ten slotte al je bestaande code om Student objecten en Course objecten te initialiseren via de constructor en niet meer via de properties. "Refactoren" betekent: code systematisch herschrijven zodat ze net hetzelfde doet, maar beter gestructureerd is.

## StudyProgram \(SchoolAdmin project\)

Schrijf nu zelf een klasse, `StudyProgram`. Een studieprogramma heeft een aantal members:

* een naam die niet leeg mag zijn \(geïmplementeerd als full property `Name`\)
* een array van vijf `Course`s \(geïmplementeerd als full property `Courses`\)
* een constructor met twee parameters die deze twee properties initialiseert
* een read-only property, `TotalStudyPoints`, die het totaal aantal studiepunten berekent en teruggeeft als `int`
* een methode `ShowOverview` die een overzicht van het studieprogramma op het scherm toont in volgend formaat:

```text
Graduaat Programmeren

Programming principles: 9 studiepunten
Web Technology: 3 studiepunten
Databanken Intro: 3 studiepunten
Communicatie: 3 studiepunten
Projectwerk: 6 studiepunten

Totaal: 24 studiepunten
```

## Verbetering ShowOverview \(SchoolAdmin project\)

Overmatig gebruik van Console.WriteLine om rapporten af te printen beperkt de flexibiliteit van onze code. Refactor eerst de methode `ShowOverview` van Student en Course zodat ze beide een methode `GetOverview` oproepen en deze gewoonweg afprinten. De methode `GetOverview` produceert een string met net dezelfde inhoud die anders op het scherm verschijnt.

Refactor vervolgens de `GetOverview` methode, zodat de verschillende regels in elk overzicht aan elkaar geplakt worden via `String.Join`.

Pas ten slotte de `GetOverview` van zowel `Student` als `Course` aan zodat de naam, respectievelijk de titel, in hoofdletters getoond worden.

Gebruik dezelfde technieken om `ShowOverview` van `StudyProgram` te refactoren en te zorgen dat de titel van het studieprogramma in hoofdletters verschijnt.

## Gemeenschappelijke kenmerken \(h11-tombola\)

### Leerdoelen

* goed gebruik van `Random`
* `static`
* `constructoren`

### Functionele analyse

We schrijven een digitale tombola. Iedere keer een lotje wordt aangemaakt, wordt er een willekeurig getal aan toegekend.

### Technische analyse

Maak een klasse, `Ticket`. Deze is voorzien van één autoproperty: `Prize`. Dit is een `byte`. Bij aanmaak van een `Ticket` wordt deze property ingesteld op een waarde tussen 1 en 100. Schrijf je code zodat dezelfde `Random` gebruikt wordt voor alle tickets. Je kan dus geen `Random` aanmaken iedere keer je een `Ticket` aanmaakt! Maak \(in de klasse `CustomObjectExercises`\) ook een methode `Raffle` \(d.w.z. "tombola"\) om te demonstreren dat dit werkt. Deze methode maakt een rij met 10 lotjes aan en print de waarde van elk lotje in de rij. Het is niet erg dat twee lotjes dezelfde waarde kunnen krijgen.

Je moet `Raffle` kunnen oproepen uit je menu.

### Voorbeeldinteractie

```text
Waarde van het lotje: 77
Waarde van het lotje: 8
Waarde van het lotje: 12
Waarde van het lotje: 14
Waarde van het lotje: 51
Waarde van het lotje: 97
Waarde van het lotje: 20
Waarde van het lotje: 15
Waarde van het lotje: 32
Waarde van het lotje: 68
```

