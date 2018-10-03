
# Handige Visual Studio code snippets

Bepaalde code zal je vaak opnieuw schrijven. Er zitten in VS tal van shortcuts om deze typische lijnen code sneller te schrijven. Schrijf een van volgende stukken code en druk dan 2x op de [tab]-toets
* cw: schrijft ``Console.WriteLine()``;
* for
* while
* dowhile
* switch
* propfull: full property
* prop: auto-property


# Bereik in code weten (Pro-kennis)
Het bereik van  datatypen is weliswaar opgegeven. Maar het is belangrijk om weten dat deze ook in de compiler gekend is. Het volgende voorbeeld toont dit aan:

```csharp
string zinnetje = "Het bereik van het type double is:";
Console.WriteLine(zinnetje + double.MinValue + " en " + double.MaxValue);
```

Je kan met andere woorden met `int.MaxValue` en `int.MinValue` het minimum- en maximumbereik van het type int verkrijgen. Wil je dit van een double, dan gebruik je `double.MaxValue` etc.




