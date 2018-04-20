# System.Object 
**Alle** klassen C# zijn afstammelingen van de ``System.Object`` klasse. Indien je een klasse schrijft zonder een expliciete parent dan zal deze steeds System.Object als rechtstreekse parent hebben. Ook afgeleide klassen stammen dus af van System.Object. Concreet wil dit zeggen dat alle klassen System.Object-klassen zijn en dus ook de bijhorende functionaliteit ervan hebben.
>Because every class descends from ``Object``, every object "is an" ``Object``.

# Hoe ziet System.Object er uit?
Wanneer je een lege klasse maakt dan zal je zien dat instanties van deze klasse reeds 4 methoden ingebouwd hebben, dit zijn uiteraard de methoden die in de ``System.Object`` klasse staan gedefinieerd:

|Methode| Beschrijving|
|-------| ------------|
|``Equals()``| Gebruikt om te ontdekken of twee instanties gelijk zijn. |
|``GetHashCode()``| Geeft een unieke code (hash) terug van het object; nuttig om o.a. te sorteren.|
|``GetType()``| Geeft het type (of klasse) van het object terug.|
|``ToPrint()``| Geeft een string terug die het object voorstel.|
