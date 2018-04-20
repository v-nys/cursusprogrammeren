# Constructors bij overerving
Wanneer je een object instantieert van ee child-klasse dan gebeuren er meerdere zaken na mekaar, in volgende volgorde:
* Eerst wordt de constructor aangeroepen van de basis-klasse: dus steeds eerst die van ``System.Object``
* Gevolgd door de constructors van alle parent-klassen
* Finaal de constructor van de klasse zelf.

Volgende voorbeeld toont dit in actie:
```java
class Soldier
{
   public Soldier() {Console.WriteLine("Soldier reporting in");}
}

class Medic:Soldier

