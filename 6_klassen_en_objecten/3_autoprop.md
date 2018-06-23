# Auto properties
Automatische eigenschappen (autoproperties) in C# staan toe om eigenschappen (properties) die enkel een waarde uit een private variabele lezen en schrijven verkort voor te stellen.

Zo kan je eenvoudige de klasse Person herschrijven met behulp van autoproperties. De originele klasse:

```csharp
public class Person
    {
 
        private string _firstName;
        private string _lastName;
        private int _age;
 
        public string FirstName
        {
            get
            {
                return _firstName;
            }
            set
            {
                _firstName = value;
            }
        }
 
        public string LastName
        {
            get
            {
                return _lastName;
            }
            set
            {
                _lastName = value;
            }
        }
 
        public int Age
        {
            get
            {
                return _age;
            }
            set
            {
                _age = value;
            }
        }
    }
```
De herschreven klasse met autoproperties (autoprops):
```csharp
public class Person
    {
 
        public string FirstName { get; set; }
        public string LastName { get; set; }
        public int Age { get; set; }
 
    }
```

Beide klassen hebben exact dezelfde functionaliteit, echter de klasse aan de rechterzijde is aanzienlijk eenvoudig om te lezen en te typen. 

## Beginwaarde van autoprops
Je mag autoproperties beginwaarden geven door de waarde achter de property te geven, als volgt:
```csharp
public int Age {get;set} = 45;
````

## Altijd auto-properties? 
Merk op dat je dit enkel kan doen indien er geen extra logica in de property aanwezig is.
Stel dat je bij de setter van age wil controleren op een negatieve waarde, dan zal je dit zoals voorheen moeten schrijven en kan dit niet met een automatic property:

```csharp
set
{
    if( value > 0)
        _age = value;
}
```
**Voorgaande property kan dus NIET herschreven worden met een automatic property.** 

## Alleen-lezen eigenschap
Je kan automatic properties ook gebruiken om bijvoorbeeld een read-only property te definiëren . Als volgt:

Originele klasse:
```csharp
public string FirstName
{
 
    get
    {
        return _firstName;
    }
}
```
Met autoprops:
```csharp
public string FirstName { get; private set;}
```

En andere manier die ook kan is als volgt:
```csharp
public string FirstName { get; }
```
De enige manier om FirstName een waarde te geven is via de constructor van de klasse. Alle andere manieren zal een error genereren.[Meer info.](https://docs.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-6#read-only-auto-properties)


## Snel autoproperties typen in Visual Studio:
Als je in Visual Studio in je code prop typt en vervolgens twee keer de tabtoets indrukt dan verschijnt al de nodige code voor een automatic property. Je hoeft dan enkel nog volgende zaken in orde te brengen:

* Het type van de property
* De naam van de property (identifier) 
* De toegankelijkheid van get/set (public, private, protected)
