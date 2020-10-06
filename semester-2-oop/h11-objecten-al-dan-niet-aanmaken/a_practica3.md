# Oefeningen

## Uitbreiding Course \(SchoolAdmin project\)

Breid je klasse `Course` uit met een \(full\) property Studiepunten. Deze ligt altijd tussen 1 en 30. Bij het gebruik andere waarden wordt er een ArgumentException gegooid.

Schrijf vervolgens een constructor voor Course die beginwaarden voor alle properties neemt en deze instelt.

Schrijf ook een constructor die geen aantal studiepunten neemt, maar dit wel instelt op 3, een vaak gebruikt aantal studiepunten. Doe dit door middel van constructor chaining.

## StudyProgram \(SchoolAdmin project\)

Schrijf nu zelf een klasse, `StudyProgram`. Een studieprogramma heeft een aantal members:

* een naam die niet leeg mag zijn \(geïmplementeerd als full property `Name`\)
* een array van vijf `Course`s \(geïmplementeerd als full property `Courses`\)
* een constructor die deze twee properties initialiseert
* een read-only property, `TotalStudyPoints`, die het totaal aantal studiepunten berekent en teruggeeft als `int`
* een methode `GetOverview` die een overzicht van het studieprogramma produceert, als string, in volgend formaat:

```text
Graduaat Programmeren

Programming principles: 9 studiepunten
Web Technology: 3 studiepunten
Databanken Intro: 3 studiepunten
Communicatie: 3 studiepunten
Projectwerk: 6 studiepunten

Totaal: 24 studiepunten
```

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

