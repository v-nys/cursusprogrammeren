# Klassen
## Opwarmers

### Nummers
Maak een eenvoudige klasse Nummers. Deze klasse bevat 2 getallen (type int). Er zijn 4 methoden:
* Som: geeft som van beide getallen weer
* Verschil: geeft verschil van beide getallen weer
* Product: geeft product van beide getallen weer
* Quotient: geeft deling van beide getallen door. Toon "Error" indien je zou moeten delen door 0. 

Toon in je main aan dat je code werkt.

Volgende code zou namelijk onderstaande output moeten geven:
```java
    Nummers paar1 = new Nummers();
    paar1.getal1 = 12;
    paar1.getal2 = 34;

    Console.WriteLine("Paar:" + paar1.getal1 + ", " + paar1.getal2);
    Console.WriteLine("Som = " + paar1.Som());
    Console.WriteLine("Verschil = " + paar1.Verschil());
    Console.WriteLine("Product = " + paar1.Product());
    Console.WriteLine("Quotient = " + paar1.Quotient());
```

Output:
```
Paar: 12, 34
Som = 46
Verschil = -22
Product = 408
Quotient = 0,352941176470588
```

### Figuren
Maak een eenvoudige klasse Rechthoek aan die een lengte en breedte als public fields heeft. 
Maak ook een klasse Driehoek die een basis en hoogte als fields heeft.

Beide klassen hebben een methode “ToonOppervlakte” die de oppervlakte van de figuur in kwestie op het scherm toont.

Toon de werking van het project aan door een aantal instanties van Driehoek en Rechthoek te maken, met verschillende groottes. Roep van iedere figuur de ToonOppervlakte-methode aan.


