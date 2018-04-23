# Compositie
We spreken over compositie (**composition**) wanneer we een object in een ander object gebruiken. Denk bijvoorbeeld aan een object van het type motor dat je gebruikt in een object van het type auto.

## Heeft een-relatie
Wanneer twee objecten  een "heeft een"-relatie hebben dan spreken we over compositie:
* Een auto heeft een motor 
* Een computer heeft een harde schijf

Het lijdende voorwerp zal steeds het object zijn dat binnen het onderwerp zal geplaatst worden (motor in auto, schijf in computer).

## In de praktijk

We bekijken het voorbeeld van de computer en de harde schijf. We hebben twee klassen
```java
class PC
{
}

class Disk
{
}
```

Een PC heeft een Disk, dit wil zeggen dat we in de klasse PC een object van het type Disk zullen definieren:
```java
class PC
{
    private Disk cDisk;
}
```

Uiteraard moeten we deze Disk nog instantiaren, dit kan op verschillende mogelijkheden en is afhankelijk van wat je nodig hebt;-.

### Manier 1
Ogenblikkelijk:
```java
class PC
{
    private Disk cDisk=new Disk();
}
```

### Manier 2
Ogenblikkelijk, maar in constructor:
```java
class PC
{
    public PC()
    {
       cDisk= new Disk();
    } 
    private Disk cDisk;
}
```

### Manier 3
Door een extern object, bv via een property:
```java
class PC
{
    public Disk CDisk
    {
      get{return cDisk;}
      set{cDisk= value;}
    }
    private Disk cDisk;
}

// Elders dan:
myPC.CDisk= new Disk();
```

## Kortom
Kortom, comp
