# Methoden

**Instantiemethoden**, ook **objectmethoden** genoemd, weerspiegelen staan toe om functionaliteit toe te voegen aan objecten van een bepaalde klasse. Soms wordt ook gezegd dat ze "gedrag" van de objecten voorzien. Ze verschillen van statische methoden omdat ze niet alleen gebruik kunnen maken van statische onderdelen van klassen, maar ook van het object waar ze zelf bij horen.

## Basisvoorbeelden

We gaan verder met de klasse `Auto`. Er zijn verschillende soorten functionaliteit die je kan koppelen aan één auto:

* voltanken
* rijden
* op onderhoud gaan
* verkoopsprijs bepalen

{% hint style="info" %}
Is het de auto die deze zaken doet, of is het een persoon? In werkelijkheid is het natuurlijk dat laatste. Maar de functionaliteit is wel veel sterker gelinkt aan auto's dan aan personen en misschien interesseert de persoon die de handeling uitvoert ons niet eens. Het hangt opnieuw af van welk programma we schrijven.
{% endhint %}

Je doet dit met objectmethoden. Deze lijken erg op `static` methoden, maar ze hebben toegang tot het woordje `this`. Daarmee stellen ze het object voor waarop ze worden toegepast.

Een simpele implementatie van dit gedraag zie je hier:

```csharp
class Auto {

    // objectvariabelen van eerder zijn er nog

    public void Voltanken()
    {
        this.benzine = 50.0; // we veronderstellen even dat dat het maximum is
    }

    public void Rijden(int aantalKilometers)
    {
        this.kilometers += aantalKilometers
        this.benzine -= 5.0 * (aantalKilometers/100);
    }

    public void Onderhouden()
    {
        this.laatsteOnderhoud = DateTime.Now;
    }

    public float VerkoopsprijsBepalen()
    {
        return Math.Max(10000 * (1 - this.kilometers / 200000.0),1000);
    }
}
```

{% hint style="warning" %}
Bovenstaande code is kort om didactische redenen. Er wordt niet gecontroleerd dat je benzinepeil altijd minstens 0l is, er wordt verondersteld dat de capaciteit van je tank 50l is,...
{% endhint %}

{% hint style="warning" %}
Eigenlijk kan je het woordje `this` weglaten. Maar de code is duidelijker als je het wel schrijft, dus maak er een gewoonte van.
{% endhint %}

## Gebruik

Om een objectmethode te gebruiken, hebben we een object nodig. We schrijven dan de naam van het object, gevolgd door een punt en een methodeoproep.

```csharp
public void DemonstreerAttributen() {
    Auto auto1 = new Auto();
    Auto auto2 = new Auto();
    auto1.Voltanken();
    auto1.Rijden(5);
    auto1.Rijden(10);
    auto1.Rijden(20);
    Console.WriteLine(auto1.kilometers);
    Console.WriteLine(auto2.kilometers);
}
```

Het gedrag van een object kan afhangen van de waarde van de instantievariabelen. Zo zal de verkoopswaarde van `auto1` iets lager liggen dan die van `auto2`. Dat komt omdat `this.kilometers` deel uitmaakt van de berekening van de verkoopsprijs. Ook dit valt onder het principe van **encapsulatie**: er vindt een berekening plaats "onder de motorkap". We hoeven niet te weten hoe de prijs berekend wordt, elk object weet van zichzelf hoe het de prijs berekent.
