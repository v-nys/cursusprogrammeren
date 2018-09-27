# TODO
Math+berekeningen uitleggen


# Math-bibliotheek
De Math namespace bevat aardig wat handige methoden. Deze bibliotheek die deel uitmaak van het C# bevat methoden voor een groot aantal typische wiskundige methoden zowel Sinus, Cosinus, Vierkantswortel, Macht, Afronden, etc.

Type als code Math gevolgd door een . en je krijgt alle methoden van de Math-library te zien te zien, aangeduid met een paars blokje:

![](/assets/4_methoden/methoden3.png)

### PI 
Ook het getal Pi , 3.14159265358979323846, is beschikbaar in de Math-library. Het witte icoontje voor PI bij Intellisense toont aan dat het hier om en ‘field’ gaat; een eenvoudige variabele met een specifieke waarde. In dit geval gaat het zelfs om een const field, met de waarde van Pi van het type double.

```csharp
public const double PI;
```

Je kan deze gebruiken in berekeningen als volgt:
```csharp
double straal= 5.5;
double omtrek= Math.PI * 2 * straal;
```