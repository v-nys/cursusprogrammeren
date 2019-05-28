```csharp
    abstract class Card
    {
        public Card(string naamin)
        {
            Name = naamin;
        }
        public bool IsHidden { get; set; }
        public abstract void DrawCard();
        public abstract void UpdateCost();
        protected int cost;

        private string name;

        public string Name
        {
            get { return name; }
            private set { name = value; }
        }
    }

     class Centrale : Card, IPointGenerator
    {
        public Centrale() : base("Centrale")
        {

        }

        

        public override void DrawCard()
        {
            Console.ForegroundColor = ConsoleColor.Yellow;
            Console.WriteLine(Name);
            Console.ResetColor();
        }

        public int GeneratePoints(int payedmana)
        {
            return 1;
        }

        public override void UpdateCost()
        {
            //Do nothing
        }
    }

    class Deck
    {
        private List<Card> cards = new List<Card>();

        public List<Card> Cards
        {
            get { return cards; }
            private set { cards = value; }
        }

        public Deck()
        {
            for (int i = 0; i < 3; i++)
            {
                Centrale nieuweCentrale = new Centrale();
                Cards.Add(nieuweCentrale);
            }
            for (int i = 0; i < 2; i++)
            {
                Hero nieuweHero = new Hero();
                Cards.Add(nieuweHero);
            }
            for (int i = 0; i < 5; i++)
            {
                Land nieuwLand = new Land();
                Cards.Add(nieuwLand);
            }
        }

        internal int GenerateLandPoint(int keuzeland)
        {
            if (Cards[keuzeland] is Land)
                return (Cards[keuzeland] as Land).GenerateMana();
            return 0; //Dit is geen land!


        }

        internal int GenerateHeroPoint(int keuzehero, int mana)
        {
            if (Cards[keuzehero] is Hero)
                return (Cards[keuzehero] as Hero).GeneratePoints(mana);
            return 0; //Dit is geen hero!
        }

        public void DrawCards()
        {
            int teller = 1;
            foreach (var elem in Cards)
            {
                Console.Write(teller);
               elem.DrawCard();
                teller++;
            }
        }

        public void UpdateCost()
        {
            foreach (var elem in Cards)
            {
                if (elem is Land)
                {
                    Land temp = elem as Land;
                    if (temp.IsHidden)
                        temp.UpdateCost();
                }

                if (elem is Hero)
                {
                    Hero temp = elem as Hero;
                    if (temp.IsHidden)
                        temp.UpdateCost();
                }
            }
        }

        public void GenerateCentralePoints()
        {
            foreach (var elem in Cards)
            {
                if (elem is Centrale)
                {
                    if (!((Centrale)elem).IsHidden)
                    {
                        ((Centrale)elem).GeneratePoints(1);
                    }
                }
            }
        }
    }

        class Hero : Card, IPointGenerator
    {
        public Hero() : base("Hero")
        {

        }

        public override void DrawCard()
        {
            Console.ForegroundColor = ConsoleColor.Yellow;
            Console.WriteLine(Name + " " + cost);
            Console.ResetColor();
        }
        static Random generator = new Random();
        public int GeneratePoints(int payedmana)
        {
            if (payedmana == cost)
            {
                return generator.Next(1, cost);
            }
            return 0;
        }
        public override void UpdateCost()
        {
            if (cost - 1 > 0)
                cost--;
        }
    }

        class Land : Card
    {
        public Land() : base("Land")
        {
        }

        public override void DrawCard()
        {
          
                Console.ForegroundColor = ConsoleColor.Green;
            Console.WriteLine(Name + " " + cost);
            Console.ResetColor();
        
        }

        public int GenerateMana()
        {
            if (!IsHidden)
            {
                return cost;
            }
            else
            {
                return 0;
            }
        }

        public override void UpdateCost()
        {
            cost++;
        }
    }
```

```csharp
static void Main(string[] args)
{
    //deck genereren
    Deck deck = new Deck();
    int points = 0;
    int mana = 0;
    int tries = 0;
    while (points <= 10)
    {
        tries++;
        Console.WriteLine($"Mana:{mana} Points:{points} Tries:{tries}");
        deck.DrawCards();

        //Fase 0
        deck.UpdateCost();
        deck.GenerateCentralePoints();
        //Fase 1
        Console.WriteLine("Welke kaart omdraaien?");
        int keuze = Convert.ToInt32(Console.ReadLine());
        deck.Cards[keuze].IsHidden = false;

        //Fase 2
        Console.WriteLine("Welke land genereert punten?");
        int keuzeland = Convert.ToInt32(Console.ReadLine());
        mana += deck.GenerateLandPoint(keuzeland);

        //Fase 3
        Console.WriteLine("Welke hero genereert punten?");
        int keuzehero = Convert.ToInt32(Console.ReadLine());
        Console.WriteLine("Hoeveel mana ga je betalen?");
        int manac = Convert.ToInt32(Console.ReadLine());
        points += deck.GenerateHeroPoint(keuzehero,manac);
        mana -= manac;
        Console.ReadLine();
        Console.Clear();
    }
}
```