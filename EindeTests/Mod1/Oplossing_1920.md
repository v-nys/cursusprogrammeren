Oplossing hier met ``enum`` , maar dit had je uiteraard ook met een ``string`` (die dan de waarden "A","B","C" gaf) of een ``int`` (waarden 1,2,3) gewerkt.


```csharp
enum fases { A, B, C, Onbekend }

static void Main(string[] args)
{
    fases finalFase= fases.Onbekend;

    //Stap 1
    Console.WriteLine("Zet de computer aan");
    Console.WriteLine("Gaat de computer aan?");
    string invoer = Console.ReadLine();
    Console.Clear();
    if (invoer == "ja") //Veronderstelt dat er enkel ja/nee correct wordt ingevoerd
    {

        Console.WriteLine("Zijn er fout boodschappen?");
        invoer = Console.ReadLine();
        Console.Clear();
        if (invoer == "ja")
            finalFase = fases.A;
        else
            finalFase = fases.B;
    }
    else
    {
        Console.WriteLine("Gaat het power light aan?");
        invoer = Console.ReadLine();
        Console.Clear();
        if (invoer == "ja")
        {
            Console.WriteLine("Zet het computer scherm aan");
        }
        else
        {
            Console.WriteLine("Controleer de voedingskabel.");
        }
        Console.WriteLine("Probleem opgelost?");
        invoer = Console.ReadLine();
        Console.Clear();
        if (invoer == "ja")
            finalFase = fases.B;
        else finalFase = fases.C;
    }

    //Stap 2 - fase A

    if (finalFase == fases.A)
    {
        Console.WriteLine("Geef de foutcode tussen 0 en 9");
        int foutcode = Convert.ToInt32(Console.ReadLine());
        if (foutcode >= 0 && foutcode <= 9)
        {
            double X = Math.Sqrt(foutcode * 3);
            Console.ForegroundColor = ConsoleColor.Red;
            Console.WriteLine($"Gelieve je computer gedurende {X:F1} minuten af te zetten");
            Console.ResetColor();
        }
        else
        {
            Console.WriteLine("Loes het dan zelf op he!");
        }
    }

    //Stap 2 - fase B

    else if (finalFase == fases.B)
    {
        Console.WriteLine("Mooi zo, alles werkt.");
        Random dobbel = new Random();
        if (dobbel.Next(0, 4) == 0)
            Console.WriteLine("En u wint ook nog eens 1 jaar gratis IT support!");
    }

    //Stap 2 - fase C

    else if (finalFase == fases.C) //mag ook gewone else zijn
    {
        int proccount = Environment.ProcessorCount;
        bool bit64 = Environment.Is64BitOperatingSystem;

        if (proccount == 1)
        {
            Console.ForegroundColor = ConsoleColor.White;
            Console.BackgroundColor = ConsoleColor.Red;
            Console.WriteLine("1 processor");
            Console.ResetColor();
        }
        else 
        {
            Console.ForegroundColor = ConsoleColor.Blue;
            Console.BackgroundColor = ConsoleColor.Green;
            Console.WriteLine($"{proccount} processor");
            Console.ResetColor();
        }
        if (proccount >= 5)
            Console.WriteLine("200 euro");
        else
            Console.WriteLine($"{proccount * 50} euro");

        if (bit64)
        {
            Console.WriteLine("Hier een bon!");
        }
    }
}
```