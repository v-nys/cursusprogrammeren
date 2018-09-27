# Strings samenvoegen
Je kan strings en variabelen samenvoegen tot een nieuwe string op verschillende manieren:
* +-operator 
* $ string interpolation 
* Of de oude manier:  ``String.Format()`` 

> We prefereren **manier 2** , de string interpolatie, in deze cursus. Dit is de meest moderne aanpak.


## In dit hoofdstuk
We gaan van volgende informatie uit:

Stel dat je 2 variabelen hebt ``int age=13`` en ``string name="Finkelstein"``.
We willen de inhoud van deze variabelen samenvoegen in een nieuwe ``string result`` die zal bestaan uit de tekst:
```Ik ben Finkelstein en ik ben 13 jaar oud``` **

Volgende 3 manieren tonen hoe je steeds tot voorgaande string zal komen.

## Manier 1: String samenvoegen met de +-operator
Je kan string en variabelen eenvoudig 'bij mekaar' optellen. Ze worden dan achter mekaar geplakt als het waren. 
```csharp
string result= "Ik ben "+ name + "en ik ben "+ age+ " jaar oud";
```
Let er op dat je tussen de aanhalingsteken (binnen de strings) spaties zet indien je het volgende deel niet 'tegen het vorige stringstuk' wilt plakken.

## Manier 2: String interpolation met $
In de oude dagen van C# gebruiken we ``String.Format()`` (zie hieronder) om meerdere string(s) en variabelen samen te voegen tot een string. Nu kan dat met string interpolation waarbij we het $-teken gebruiken.

Door het $-teken **VOOR** de string te plaatsen geef je aan dat alle delen in de string die tussen accolades staan { } als code mogen beschouwd worden. Een voorbeeld maakt dit duidelijk:
```csharp
string result= $"Ik ben {name} en ik ben {age} jaar oud";
```
In dit geval zal dus de inhoud van de variabele ``name`` tussen de string op de plek waar nu ``{name}`` staat vervangen worden. Idem voor ``age``.
Zoals je kan zien is dit veel meer leesbare code dan de eerste manier.

### Berekeningen doen bij string interpolatie
Je mag eender welke *expressie* tussen de accolades zetten bij string interpolation, denk maar aan:
```csharp
string result= $"Ik ben {name} en ik ben {age+4} jaar oud";
```

Alle expressies tussen de accolades zullen eerst uitgevoerd worden voor ze tussen de string worden geplaatst. De uitvoer wordt dus nu:  ```Ik ben Finkelstein en ik ben 17 jaar oud```

Eender welke expressie is toegelaten, dus je kan ook complexe berekeningen of zelfs andere methoden aanroepen:
```csharp
string result= $"Ik ben {age*age+(3%2)} jaar oud";
```


## Manier 3: String.Format()
String interpolatie met het $-teken is een nieuwe C# aanwinst. Je zal echter nog veel documentatie en online code tegenkomen die nog met ``String.Format`` werkt (ook zijn er nog zaken waar het te prefereren is om ``String.Format`` te gebruiken i.p.v. 1 van vorige manieren). Om die reden bespreken we dit nog in deze cursus.

``String.Format`` is een ingebouwde methode die string-interpolatie toe laat op een iets minder intuïtieve manier:
```csharp
string result= String.Format("Ik ben {0} en ik ben {1} jaar oud",name,age);
```
Het getal tussen de accolades geeft aan de hoeveelste parameter na de string hier in de plaats moet gezet worden (0= de eerste, 1= de tweede, enz).

Volgende code een ander resultaat geven:
```csharp
string result= String.Format("Ik ben {1} en ik ben {1} jaar oud",name,age);
```
Namelijk:  ``Ik ben 13 en ik ben 13 jaar oud``


Wens je meer informatie over ``string.Format``, kijk dan [hier](https://codevan1001nacht.wordpress.com/2013/11/05/placeholders-aka-string-formatters/).
