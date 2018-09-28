# Wiskunde en de Math-bibliotheek

De Math bibliotheek bevat aardig wat handige methoden. Deze bibliotheek bevat methoden voor een groot aantal typische wiskundige methoden zowel Sinus, Cosinus, Vierkantswortel, Macht, Afronden, etc. en kan je dus helpen om leesbaardere expressies te schrijven.

Stel dat je de derde macht van een variabele ``getal`` wenst te berekenen. ZONDER de Math-bibliotheek zou dat er zou uitzien:
```csharp
double result= getal*getal*getal;
```

MET de bibliotheek kunnen we schrijven:
```csharp
double result= Math.Pow(getal,3);
```

# De Math bibliotheek ontdekken

Als je in Visual Studio ``Math```schrijft, gevolgd door een punt ``.`` krijg je alles te zien wat de Math-bibliotheek kan doen:

![](/assets/4_methoden/methoden3.png)

Een doosje voor een naam wil zeggen dat het om een **Methode** gaat (zoals Console.ReadLine()). Een vierkantje met twee streepjes in zijn constanten (zoals Pi en E).

# Methoden gebruiken
De meeste methoden zijn zeer makkelijk in gebruik en werken op dezelfde manier. Meestal moet je 1 of meerdere "argumenten" tussen de haken meegeven en het resultaat moet je altijd in een nieuwe variabele opvangen. Enkele voorbeelden:
```csharp
double sineHoekA= Math.Sin(345); //IN RADIALEN!
double DerdeMachtVan20= Math.Pow(20, 3);
double complex= 3+ DerdeMachtVan20 * Math.Round(sineHoekA)
```

Twijfel je over de werking van een methode, gebruik dan de help als volgt:
1) schrijf de Methode zonder argumenten. Bijvoorbeeld ``Math.Pow()`` (je mag de rode error negeren)
![](/assets/4_methoden/math.png)
2) plaats je cursos op Pow
3) druk op F1 op je toetsenbord. 
4) Je krijgt nu de help-files te zien van deze methode op MDSDN

## PI 
Ook het getal Pi , 3.14159265358979323846, is beschikbaar in de Math-library. Het witte icoontje voor PI bij Intellisense toont aan dat het hier om en ‘field’ gaat; een eenvoudige variabele met een specifieke waarde. In dit geval gaat het zelfs om een const field, met de waarde van Pi van het type double.

```csharp
public const double PI;
```

Je kan deze gebruiken in berekeningen als volgt:
```csharp
double straal= 5.5;
double omtrek= Math.PI * 2 * straal;
```