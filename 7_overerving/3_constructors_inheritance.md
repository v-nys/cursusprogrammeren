# Constructors bij overerving

Wanneer je een object instantiëert van ee child-klasse dan gebeuren er meerdere zaken na elkaar, in volgende volgorde:

* Eerst wordt de constructor aangeroepen van de basis-klasse: dus steeds eerst die van ``System.Object``
* Gevolgd door de constructors van alle parent-klassen
* Finaal de constructor van de klasse zelf.

Volgende voorbeeld toont dit in actie:

```csharp
class Soldier
{
   public Soldier() {Console.WriteLine("Soldier reporting in");}
}

class Medic:Soldier
{
   public Medic(){Console.WriteLine("Who needs healing?");}
}
```

Indien je vervolgens een object aanmaakt van het type Medic:

```csharp
Medic RexGregor= new Medic();
```

Dan zal zien we de volgorde van constructor-aanroep op het scherm:

```text
Soldier reporting in
Who needs healing?
```

Er wordt dus verondersteld in dit geval dat er een default constructor in de basis-klasse aanwezig is. 

## Overloaded constructors

Indien je klasse Soldier een overloaded constructor heeft, dan geeft deze niet automatisch een default constructor. Volgende code zou dus een probleem geven indien je een Medic wilt aanmaken via ``new Medic()``:
```csharp
class Soldier
{
   public Soldier(bool canShoot) {//...Do stuff  }
}

class Medic:Soldier
{
   public Medic(){Console.WriteLine("Who needs healing?");}
}
```

Wat je namelijk niet ziet bij child-klassen en hun constructors is dat er eigenlijk een impliciete call naar de basis-constructor wordt gedaan. Bij alle constructors staat eigenlijk ``:base()`` wat je ook zelf kunt schrijven:
```csharp
class Medic:Soldier
{
   public Medic(): base()
   {Console.WriteLine("Who needs healing?");}
}
```
``base()`` achter de constructor zegt dus eigenlijk 'roep de constructor van de parent-klasse aan. Je mag hier echter ook parameters meegeven en de compiler zal dan zoeken naar een constructor in de basis-klasse die deze volgorde van parameters kan accepteren.

We zien hier dus hoe we ervoor moeten zorgen dat we terug Medics via ``new Medic()`` kunnen aanroepen zonder dat we de constructor(s) van Soldier moeten aanpassen:
```csharp
class Soldier
{
   public Soldier(bool canShoot) {//...Do stuff  }
}

class Medic:Soldier
{
   public Medic():base(true)
    {Console.WriteLine("Who needs healing?");}
}
```

De medics zullen de canShoot dus steeds op true zetten.
Uiteraard wil je misschien dit kunnen meegeven bij het aanmaken van een object zoals ``new Medic(false)``, dit vereist dat je dus een overloaded constructor in Medic aanmaakt, die op zijn beurt de overloaded constructor van Soldier aanroept. Je schrijft dan een overloaded constructor in Medic bij:

```csharp
class Soldier
{
   public Soldier(bool canShoot) {//...Do stuff  }
}

class Medic:Soldier
{
   public Medic(bool canSh): base(canSh)
   {} 

   public Medic():base(true)  //Default
    {Console.WriteLine("Who needs healing?");}
}
```

Uiteraard mag je ook de default constructor aanroepen vanuit de child-constructor, alle combinaties zijn mogelijk (zolang de constructor in kwestie maar bestaat in de parent-klasse).

# Ballspel met overerving

Volgende code toont hoe we nu een bestaande klasse  ``Ball`` kunnen overerven om een bestuurbare bal te maken:

## Basisklasse Ball

We maken een klasse ``Ball`` die via ``Update`` en ``Draw`` zichzelf over het consolescherm beweegt. Enkele opmerkingen:

* We maken sommige variabelen ``protected`` zodat later de overgeërfde klasse er aan kunnen
* Een ``static`` methode ``CheckHit`` laat ons toe te ontdekken of twee ``Ball``objecten mekaar raken

```csharp
class Ball
{
   public int X { get { return x; } }
   public int Y { get { return y; } }
   private int x = 0;
   private int y = 0;
   protected int vx = 0;
   protected int vy = 0;
   protected char drawChar = 'O';
   protected ConsoleColor drawColor = ConsoleColor.Red;

   public Ball(int xin, int yin, int vxin, int vyin)
   {
      x = xin;
      y = yin;
      vx = vxin;
      vy = vyin;
   }

   public void Update()
   {
      x += vx;
      y += vy;
      if (x >= Console.WindowWidth || x < 0)
      {
            vx *= -1;
            x += vx;
      }
      if (y >= Console.WindowHeight || y < 0)
      {
            vy *= -1;
            y += vy;
      }
   }
   public void Draw()
   {
      Console.SetCursorPosition(x, y);
      Console.ForegroundColor = drawColor;
      Console.Write(drawChar);
      Console.ResetColor();

   }

   static public bool CheckHit(Ball ball1, Ball ball2)
   {

      if (ball1.X == ball2.X && ball1.Y == ball2.Y)
            return true;

      return false;
   }
}
```

## Specialisatie klasse PlayerBall

De overgeërfde klasse ``PlayerBall`` is een ``Ball`` maar zal z'n ``vx`` en ``vy`` updaten gebaseerd op input via de ``ChangeVelocity`` methode:

```csharp
class PlayerBall : Ball
{
   public PlayerBall(int xin, int yin, int vxin, int vyin) : base(xin, yin, vxin, vyin)
   {
      drawChar = 'X';
      drawColor = ConsoleColor.Green;
   }

   public void ChangeVelocity(ConsoleKeyInfo richting)
   {
      switch (richting.Key)
      {
            case ConsoleKey.UpArrow:
               vy--;
               break;
            case ConsoleKey.DownArrow:
               vy++;
               break;
            case ConsoleKey.LeftArrow:
               vx--;
               break;
            case ConsoleKey.RightArrow:
               vx++;
               break;
            default:
               break;
      }
   }
}
```

## Eenvoudig spel

We maken nu een rudimentair spel waarin de gebruiker een bal moet proberen te raken. 

```csharp
static void Main(string[] args)
{
   Console.CursorVisible = false;
   Console.WindowHeight = 20;
   Console.WindowWidth = 30;
   Ball b1 = new Ball(4, 4, 1, 0);
   PlayerBall player = new PlayerBall(10, 10, 0, 0);
   while (true)
   {

         Console.Clear();

         //Ball
         b1.Update();
         b1.Draw();
         
         //SpelerBall
         if (Console.KeyAvailable)
         {
            var key = Console.ReadKey();
            player.ChangeVelocity(key);
         }

         player.Update();
         player.Draw();
         
         //Check collisions
         if (Ball.CheckHit(b1, player))
         {
            Console.Clear();
            Console.WriteLine("Gewonnen!");
            Console.ReadLine();
         }
         System.Threading.Thread.Sleep(100);
   }
}
```

Kan je dit uitbreiden met?

* Meerdere ballen die over het scherm vliegen (benodigdheden: array en collision check met alle ballen)
* Meerdere levels 
* Score gebaseerd op tijd die gebruiker nodig had om bal te raken (benodigdheden: teller die optelt na iedere ``Sleep``)