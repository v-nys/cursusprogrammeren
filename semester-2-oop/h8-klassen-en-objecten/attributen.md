# Attributen

**Attributen**, ook **velden** of **instantievariabelen** genoemd, zijn stukjes data die je bijhoudt in objecten. Ze stellen informatie voor die deel uitmaakt van een \(object van een\) klasse. Ze werken zoals de variabelen die je al kent, maar hun scope is een klasse of een object van een klasse, afhankelijk van de vraag of ze `static` zijn of niet.

## Basisvoorbeelden

Een typisch voorbeeld van een klasse is `Auto`. Er zijn verschillende stukjes data die deel kunnen uitmaken van één auto: de kilometerstand, het benzinepeil, de datum van het laatste onderhoud,...

{% hint style="info" %}
Dit is een zinvolle manier om een auto voor te stellen in code, maar er is niet echt een "perfecte" manier. Alles hangt af van wat relevant is voor de programma's die je wil schrijven.
{% endhint %}

Deze zaken kunnen we bijhouden in een object van klasse `Auto` als volgt:

```csharp
class Auto {
    public int Kilometers;
    public float Benzine;
    public DateTime LaatsteOnderhoud;
}
```

Al deze velden zijn voorlopig `public`. Dat hoeft niet absoluut, maar het vergemakkelijkt de presentatie. Verdere opties volgen snel. Het is ook een afspraak om publieke velden met een hoofdletter te schrijven.

## Uitproberen: auto's met eigen attributen

We kunnen nu vaststellen dat elke auto zijn eigen kilometerstand,... heeft met volgende \(gedeeltelijke\) code, die je in `Program` plaatst:

```csharp
public static void DemonstreerAttributen() {
    Auto auto1 = new Auto();
    Auto auto2 = new Auto();
    auto1.Kilometers = 10000;
    auto2.Kilometers = 50000;
    auto1.Benzine = 10.0;
    auto2.Benzine = 30.0;
    auto1.LaatsteOnderhoud = DateTime.Now;
    auto2.LaatsteOnderhoud = DateTime.Now.AddMonths(-3);
    Console.WriteLine(auto1.Kilometers);
    Console.WriteLine(auto2.Kilometers);
    // de kilometerstand is verschillend voor beide
    // idem voor de andere attributen
}
```

## Beginwaarden

Een veld krijgt normaal de defaultwaarde voor zijn type. Voor `int` is dat bijvoorbeeld `0`. Het is mogelijk dit aan te passen met de syntax voor een toekenning:

```csharp
class Auto {
    public int Kilometers = 5; // in de fabriek vinden bv. een aantal testen plaats
    public float Benzine = 10; // nieuwe auto's moeten kunnen rijden
    public DateTime LaatsteOnderhoud = DateTime.Now;
}
```

Nu hebben nieuwe auto's standaard 5km op de teller staan, enzovoort.

## Voordelen en nadelen

Door attributen te gebruiken, kunnen we met objecten grotere gehelen vormen om over na te denken. We hoeven geen aparte variabelen bij te houden zoals `auto1Kilometers` en `auto2Kilometers`. We hebben alleen variabelen voor `auto1` en `auto2`. De onderdelen zijn netjes verpakt in de objecten. Dit draagt bij tot het objectgeoriënteerd principe van **encapsulatie**, dat je kan onthouden als "onder de motorkap steken".

Een nadeel van dit gebruik van attributen is dat we niet echt controle hebben over de waarde: niets verhindert dat we \(al dan niet per ongeluk\) schrijven: `auto1.kilometers = -20000;`. Om dat soort fouten te voorkomen, hebben we meer concepten nodig.

## `static` attributen

Iets dat `static` is, hoort niet bij de objecten, maar wel bij de hele klasse. Bijvoorbeeld: voor auto's worden de milieunormen na een paar jaar strenger. Er is een vaste set milieunormen en de te halen milieunorm wordt vastgelegd voor **alle** auto's. Daarom zouden we de milieunorm als volgt kunnen bijhouden:

```csharp
enum MilieuNormen {
Euro1, Euro2, Euro3, Euro4, Euro5, Euro6
}

class Auto {
    public static MilieuNormen HuidigeNorm;
    // rest van de code voor Auto
}
```

{% hint style="warning" %}
Herhaal: `static` betekent niet "onveranderlijk" of "vast". Het betekent dat iets op niveau van de klasse werkt en niet op niveau van de objecten van die klasse.
{% endhint %}

