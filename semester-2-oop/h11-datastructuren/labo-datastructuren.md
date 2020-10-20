# Labo

## SchoolAdmin project

Als je alles eerder mee hebt kunnen volgen, werk dan vanaf je recentste commit. Anders is er een modeloplossing voorzien waarvan je kan verder werken.

### `StudyProgram.GetOverview` en `Course.GetOverview` met `foreach` en `var`

Pas je ShowOverview methodes aan zodat er geen gebruik wordt gemaakt van een klassieke `for`, maar wel van een foreach. Gebruik `var` voor je iteratieveriabele.

### Lijst van studenten

Vervang de property `Students` van StudyProgram \(met type `Student[]`\) door een property met type `List<Student>`.

### Lijst van studenten, zonder dubbels

Verbeter je nieuwe property `Students` zodat er geen dubbels meer in de lijst met alle studenten in een studieprogramma voorkomen. Maak hierbij gebruik van de methode `Contains` van de klasse `List<T>`.

### Flexibelere punten

### Puntenlijsten

### Studenten per vak tonen

### Sanity check op Courses

### OPTIONELE uitdaging: sanity check overbodig maken via SortedSet&lt;&gt;

Zelf sanity checks uitvoeren zoals hierboven omschreven is een vervelend karwei. Er bestaat een datastructuur die, net als `List<>`, elementen in volgorde bijhoudt, maar vanzelf dubbele elementen elimineert. Dit is `SortedSet<>`.  Je vindt de officiële documentatie [hier](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.sortedset-1?view=netcore-3.1). Niet alles zal op dit moment verstaanbaar zijn, maar kan je je `List<Course>` vervangen zodat je de code voor de sanity check kan schrappen?





