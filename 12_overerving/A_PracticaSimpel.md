# Overerven a la carte

Selecteer twee oefeningen met klassen die je in het verleden hebt gemaakt. Probeer zelf een "is een" relatie te ontdekken voor een van je bestaande klasse. Maak een nieuwe klasse die deze "is een" relatie via overerving aantoont. Voeg extra properties en methoden toe en test deze klasse.

Voorbeeld: De ``Student`` klasse zou je kunnen overerven naar een ``WerkStudent`` : "Een werkstudent **is een** student", maar heeft ook een methode "MoetgaanWerken" (bijvoorbeeld) en een property ``IsSteenDood`` (``bool``) die op true wordt gezet als deze student meer dan 10uur is moeten gaan werken.

# HiddenBookmark

 Voeg een ``HiddenBookmark`` klasse toe aan je bestaande Bookmark Manager applicatie van vorige hoofdstuk.

 De ``HiddenBookmark`` is een ``Bookmark`` klasse die de browser in Incognito-modus zal opstarten bij het openen van de bookmark. Dit kan je bewerkstelligen door ``-incognito`` achter ``chrome.exe`` te plaatsen. Maak de ``OpenSite`` methode ``virtual``  in ``BookMark`` om vervolgens via ``override`` in ``HiddenBookmark`` dit op te lossen.

 Test wat er gebeurt als je al je bookmarks vervangt door ``HiddenBookmarks``.

Afhankelijk van de browser die je wilt aanroepen moet je de incognito parameter iets anders doorgeven:
**Let op de spatie na "-private ", deze moet er staan anders plak je je url aan de parameter:**

```csharp
Process.Start("iexplore.exe", "-private " + url);
Process.Start("chrome.exe", "-incognito " + url);
Process.Start("firefox.exe", "-private-window " + url);
Process.Start("iexplore.exe", "-private " + url);
```




## Oefening: H12-ziekenhuis
### Leerdoelen
* werken met methodes
* methodes overschrijfbaar maken
* code specifieker maken met behulp van subklassen

### Functionele analyse
Dit programma berekent de doktersrekening van een patiënt, op basis van een basisbedrag (€50) en een extra kost (€20/uur). In het geval van een verzekerde patiënt worden de kosten met 10% verlaagd.

### Technische analyse
#### UI
console applicatie
#### voorbeeldinteractie(s)
```
Vincent, een gewone patiënt die 12 uur in het ziekenhuis gelegen heeft, betaalt €290.
Tim, een verzekerde patiënt die 12 uur in het ziekenhuis gelegen heeft, betaalt €261.
```

### Technische hulp
#### Programmaverloop
Per patiënt worden een naam en een verblijfsduur in het ziekenhuis bijgehouden (als velden van een klasse). Per patiënt wordt de uitvoer getoond door middel van een methode `ShowInfo`. De berekening van de kost wordt uitgevoerd door een methode `CmputeCost`. In het geval van een verzekerde patiënt is dit een verfijnde versie van de methode voor niet-verzekerde patiënten.

#### Testscenario's
* Test uit met een verblijf van 1 uur.
* Test uit met een verblijf van 0 uur.
* Test uit met de patiënten beschreven in de voorbeeldinteractie.

### Ondersteunend materiaal
Hou het voorlopig op de cursus.

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
