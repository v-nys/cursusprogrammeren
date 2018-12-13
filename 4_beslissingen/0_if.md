#If statements
> De flowchart afbeeldingen komen uit het handboek ["Microsoft Visual C# 2015: An Introduction to Object-Oriented Programming" van Joyce Farrell](https://books.google.be/books/about/Microsoft_Visual_C_2015_An_Introduction.html?id=Xy-dBAAAQBAJ&source=kp_cover&redir_esc=y). Op termijn zullen de illustraties door mezelf gemaakt worden.

In dit deel  zullen we bekijken hoe we ons programma dynamischer kunnen maken met behulp van het if-statement.

## If
De ``if`` uitdrukking is 1 van de elementairste uitdrukking in een programmeertaal. De syntax is als volgt:

```csharp
if (boolean expression) 
{
     // code hier moet uitgevoerd worden indien de booleaanse expressie waar is
}

```
Enkel indien de booleaanse expressie waar is, en dus ``true`` als resultaat heeft zal de code binnen de accolades van het if-blok uitgevoerd worden. Indien de expressie niet waar is (``false``) dan wordt het blok overgeslagen en gaat het programma verder met de code eronder.



Een voorbeeld:
```csharp
int number = 3;
 
if ( number < 5 )
        Console.WriteLine ("A");
Console.WriteLine("B");
```
De uitvoer van dit programma zal zijn:
```
A
B
```
Indien ``number`` groter of gelijk aan 5 was dan zou er enkel ``B`` op het scherm zijn verschenen. De lijn ``Console.WriteLine("B")`` zal sowieso uitgevoerd worden zoals je ook kan zijn aan de volgende flowchart:

![](/assets/2_beslissingen/ifflow.png)

## if met een block
Het is aangeraden om steeds na de if-expressie met accolades te werken. Dit zorgt ervoor dat alle code tussen het block (de accolades) zal uitgevoerd worden indien de booleanse expressie waar was. **Gebruik je geen accolades dan zal enkel de eerste lijn na de ``if`` uitgevoerd worden bij ``true``.

Een voorbeeld:
```csharp
if ( number < 5 )
{        
    Console.WriteLine ("C");
    Console.WriteLine ("D");
}

```

![](/assets/2_beslissingen/iffflowblock.png)

De booleaanse expressie die je tussen de ``if`` haakjes plaats moet een stuk code zijn dat altijd een ``bool`` als resultaat teruggeeft. 



## Veelgemaakte if-fouten
Er zijn enkele veelgemaakte fouten waar je op moet letten:

* **Appelen en peren vergelijken**: de types in je booleanse expressie moeten steeds vergelijkbaar zijn. Volgende code is dus fout: ``if( "4" > 3)`` daar we hier een ``string`` met een ``int``vergelijken.
* **Accolades vergeten** om een codeblock aan te duiden, maar je code toch zodanig outlinen (met tabs) dat het lijkt of je een heel codeblock hebt. Het gevolg zal zijn dat enkel de eerste lijn na de ``if`` zal uitgevoerd worden indien ``true```. De volgende lijn zal vervolgens altijd uitgevoerd worden:
  
  ![](/assets/2_beslissingen/ifflownobrace.png)

* **Een puntkomma plaatsen** na de booleanse expressie. Dit zal ervoor zorgen dat er eigenlijk geen codeblock bij de if hoort en je dus een nietszeggende ``if`` het geschreven. De code na het puntkomma zal uitgvoerd worden ongeacht de ``if``:

  ![](/assets/2_beslissingen/ifflowsemicolon.png)
  

## Gebruik relationele operators
Met de relationele operators (==, !=, <, >, <= en >=) kunnen we complexere expressies schrijven die als uitkomst waar (true) of niet waar (false) geven:

Een voorbeeld:
```csharp
int a, b, c;  
 
a = 2;  
b = 3;  
 
if(a < b) 
{
    Console.WriteLine("a is less than b"); 
}
 
if(a == b) 
{
    Console.WriteLine("you won't see this");  
}
 
Console.WriteLine(); 
 
c = a - b; // c contains -1 
 
Console.WriteLine("c contains -1"); 
if(c >= 0) 
{
    Console.WriteLine("c is non-negative"); 
}
if(c < 0) 
{
    Console.WriteLine("c is negative"); 
}
 
Console.WriteLine(); 
 
c = b - a; // c now contains 1 
Console.WriteLine("c contains 1"); 
if(c >= 0) 
{
    Console.WriteLine("c is non-negative"); 
}
if(c < 0)
{
     Console.WriteLine("c is negative"); 
}
```
Uitvoer van bovenstaande code zal zijn:
```
a is less than b

c contains -1
c is negative

c contains 1
c is non-negative
```

We kunnen ook meerdere expressie combineren zodat we complexere uitdrukkingen kunnen maken. Hierbij kan je gebruik maken van de logische operators (``&&``,``||``,``!``) 

Een voorbeeld:
```csharp
int a = 5, b = 5, c = 10;
 
if (a == b)
{
        Console.WriteLine(a);
}
 
if ((a > c) || (a == b))
{  
    Console.WriteLine(b);
}
 
if ((a >= c) && (b <= c))
{
    Console.WriteLine(c);
}
```
Uitvoer van dit programma zal zijn:
```
5
5
```

## If/else
Met if/else kunnen we niet enkel zeggen welke code moet uitgevoerd worden als de conditie waar is maar ook welke specifieke code indien de conditatie niet waar (false). Volgende voorbeeld geeft een typisch gebruik van een if/else structuur om 2 waarden met elkaar te vergelijken:

```csharp
int x = 10;
 
if ( x > 9 )
{
         Console.WriteLine ("x is greater than 9!");
}
else
{
         Console.WriteLine ("x is less than 9!");
}
```

  ![](/assets/2_beslissingen/ifelseflow.png)
## If/else if
Met een if/ else if constructie kunnen we meerdere criteria opgeven die waar/niet waar moeten zijn voor een bepaald stukje code kan uitgevoerd worden. Sowieso begint men steeds met een if. Als men vervolgens een else if plaats dan zal de code van deze else if uitgevoerd worden enkel en alleen als de eerste expressie (van de if) niet waar was en de expressie van deze else if wel waar is.

Een voorbeeld:

```csharp
int x = 9;
 
if (x == 10)
{
     System.Console.WriteLine ("x is 10");
}
else if (x == 9)
{
     System.Console.WriteLine ("x is 9");
}
else if (x == 8)
{
     System.Console.WriteLine ("x is 8");
}
```


## Nesting
We kunnen met behulp van nesting ook complexere programma flows maken. Hierbij gebruiken we de accolades om het blok code aan te duiden dat bij een if/else/if else hoort. Binnen dit blok kunnen nu echter opnieuw if/else/if else structuren worden aangemaakt.

Volgende voorbeeld toont dit aan (bekijk wat er gebeurt als je emergencyValve aan ``closed`` gelijkstelt) :

````csharp
int reactorTemp = 1500;
string emergencyValve = " ";
 
if (reactorTemp < 1000)
{
    System.Console.WriteLine("Reactor temperature normal");
}
else
{
    System.Console.WriteLine("Reactor temperature too high!");
    if (emergencyValve == "closed")
    {
        System.Console.WriteLine("Reactor meltdown in progress!");
    }
}
```