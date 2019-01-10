# Oplossing opwarmers


## Opwarmers 
```csharp
//Maak een array gevuld met de getallen 0 tot 100
int[] getallen= new int[10];
for(int i = 0; i<10;i++)
{
    getallen[i]= i+1;
    Console.Write(getallen[i]+",");
}

//Maak een array gevuld met de getallen van 100 tot 0
int[] getallen= new int[100];
int counter = 100;
for(int i = 0; i<getallen.Length;i++)
{
    getallen[i]= counter; //zonder counter: getallen[i]=100-i;
    counter--;
    Console.Write(getallen[i]+",");
}

//Maak een array gevuld met de letters a tot z
char[] letters= new char[26];
int startascii=97;
for(int i = 0; i<letters.Length;i++)
{
    letters[i]= (char)(startascii+i);
    Console.Write(letters[i]+",");
}

//Maak een array gevuld met willekeurige getallen tussen 1 en 100 (array is 20 lang)
int[] getallen= new int[20];
Random r= new Random();
for(int i = 0; i<getallen.Length;i++)
{
    getallen[i]= r.Next(1,101);
    Console.Write(getallen[i]+",");
}

//Maak een array gevuld met afwisselen true en false(lengte is 30)
bool[] binary= new bool[30];
Random r= new Random();
for(int i = 0; i<binary.Length;i++)
{
    if(i%2==0) 
        binary[i]=true;
    else
        binary[i]=false;
    
    Console.Write(binary[i]+",");
}
```

## ArrayOefener1

```csharp
 int[] getallen = new int[10];
//Invoer
Console.WriteLine("Voer 10 gehele getallen in");
for (int i = 0; i < getallen.Length; i++)
{
    getallen[i] = Convert.ToInt32(Console.ReadLine());
}

//Verwerking (kan ook in lus hierboven ineens)
int som = 0;
double gemiddelde = 0;
int grootste = getallen[0];
for (int i = 0; i < getallen.Length; i++)
{
    som += getallen[i]; //som
    if (getallen[i] > grootste)
        grootste = getallen[i];
}
Console.WriteLine("******");
Console.WriteLine($"Som is {som}, Gemiddelde is {(double)som/getallen.Length}, Grootste getal is {grootste}");
Console.WriteLine("******");

Console.WriteLine("Geef minimum getal in?");
int keuze =Convert.ToInt32(Console.ReadLine());
if(keuze>grootste)
    Console.WriteLine("Niets is groter");
else
{
    for (int i = 0; i < getallen.Length; i++)
    {
        if (getallen[i] >= keuze)
            Console.Write($"{getallen[i]},");
        {

        }
    }
}
```

## ArrayOefener2

```csharp
static void Main(string[] args)
{
    int length = 5;
    int[] A = VraagVulArray(length);
    int[] B = VraagVulArray(length);
    int[] C = new int[length];

    Console.WriteLine("Array c bevat:");
    for (int i = 0; i < length; i++)
    {
        C[i] = A[i] + B[i];
        Console.Write($"{C[i]},");
    }
}

static int[] VraagVulArray(int lengte)
{
    int[] array = new int[lengte];
    Console.WriteLine("Voer 5 gehele getallen in");
    for (int i = 0; i < lengte; i++)
    {
        array[i] = Convert.ToInt32(Console.ReadLine());
    }
    return array;
}
```

## Vraag Array
```csharp
string[] vragen =
{
    "Hoe oud ben je?",
    "Wat is je postcode?",
    "Hoeveel broers heb je?",
    "Hoeveel zussen heb je?",
    "Wanneer ben je geboren?",
    "Hoeveel is 3+5?"
};
int[] antwoorden = new int[vragen.Length];

for (int i = 0; i < vragen.Length; i++)
{
    Console.WriteLine(vragen[i]);
    antwoorden[i] = Convert.ToInt32(Console.ReadLine());
}

Console.WriteLine("Je antwoorden:");
for (int i = 0; i < vragen.Length; i++)
{
    Console.WriteLine($"{vragen[i]}: {antwoorden[i]}");
}
```

## Array Zoeker
Om niet steeds 10 getallen tijdens testen te moeten invullen gebruik ik ``Random`` om snel 10 getallen willekeurig te genereren:

```csharp
int[] ar = new int[10];
Random rand = new Random();
for (int i = 0; i < ar.Length; i++)
{
    ar[i] = rand.Next(1, 100);
    Console.WriteLine(ar[i]);
}
Console.WriteLine("Welk getal moet verwijder worden?");
int todel = Convert.ToInt32(Console.ReadLine());

//index van te zoeken getal zoeken
int index = -1;
bool found = false;
for (int i = 0; i < ar.Length; i++)
{
    if(!found && ar[i]==todel)
    {
        found = true;
        index = i;
    }
}

//alle elementen vanaf index met 1 plekje vooruitschuiven
if(found)
{
    for (int i = index; i < ar.Length-1; i++)
    {
        ar[i] = ar[i + 1];
    }
    ar[ar.Length - 1] = -1; //laatste element op -1
}

//Array tonen
for (int i = 0; i < ar.Length; i++)
{
    Console.WriteLine(ar[i]);
}
```