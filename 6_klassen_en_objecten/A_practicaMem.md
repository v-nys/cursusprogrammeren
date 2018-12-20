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