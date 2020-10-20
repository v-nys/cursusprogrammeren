# Labo

## SchoolAdmin project

Als je alles eerder mee hebt kunnen volgen, werk dan vanaf je recentste commit. Anders is er een modeloplossing voorzien waarvan je kan verder werken.

### `StudyProgram.GetOverview` en `Course.GetOverview` met `foreach` en `var`

Pas je ShowOverview methodes aan zodat er geen gebruik wordt gemaakt van een klassieke `for`, maar wel van een foreach. Gebruik `var` voor je iteratieveriabele. Om het gebruik van een index te vermijden, zal je de array van `string` ook moeten vervangen door een `List<string>`.

### Alle studenten in het systeem bijhouden

Voorzie de klasse Student van een statische property `Students`. Deze is van het type `List<Student>` en bevat altijd elke student die in het systeem aanwezig is. Dit gebeurt door bij de constructie van elk `Student`-object de lijst uit te breiden.

### Lijst van studenten

Vervang alle properties van `StudyProgram`, `Course` en `Student` van een array type naar een `List` type.

### Lijst van studenten, zonder dubbels

Verbeter je vernieuwde property `Students` van `StudyProgram` zodat er geen dubbels meer in de lijst met alle studenten in een studieprogramma voorkomen. Maak hierbij gebruik van de methode `Contains` van de klasse `List<T>`.

### Flexibelere punten

Het is op termijn niet houdbaar om elke student een veld voor het cijfer per vak te geven \(bijvoorbeeld `MarkCommunication`\). Niet alle studenten volgen dezelfde vakken en puur technisch is het geen goed ontwerp dat je de `Student` klasse moet aanpassen omdat er rekening gehouden moet worden met een nieuw object van de `Course` klasse.

Een betere optie bestaat erin de cijfers van een student bij te houden als een `Dictionary<Course,byte>`. Geef `Student` een `private` attribuut `Grades` van dit type. Voorzie ook een methode `SetGrade(Course course, byte grade)` om het cijfer voor een bepaald vak in te stellen. Op deze manier kan je voorkomen dat een cijfer hoger dan 20 wordt ingesteld.

### Puntenlijsten

Studenten krijgen normaal niet één cijfer, maar meerdere cijfers per vak, omdat er tijdens het semester meerdere toetsen zijn. Het aantal cijfers is niet voor elk vak hetzelfde. Los dit op door `Grades` om te vormen naar een `Dictionary<Course,List<byte>>`. Ook hier moet je, wanneer een cijfer wordt ingesteld voor een vak, controleren dat alle cijfers in de lijst maximaal 20 zijn.

### OPTIONELE uitdaging: sanity check overbodig maken via `SortedSet<T>`

Zelf controleren op dubbels uitvoeren zoals hierboven omschreven is een vervelend karwei. Er bestaat een datastructuur die, net als `List<>`, elementen in volgorde bijhoudt, maar vanzelf dubbele elementen elimineert. Dit is `SortedSet<>`.  Je vindt de officiële documentatie [hier](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1?view=netcore-3.1). Niet alles zal op dit moment verstaanbaar zijn, maar kan je in de property `Students` van `StudyProgram` je `List<Student>` vervangen zodat je `Contains` kan negeren?





