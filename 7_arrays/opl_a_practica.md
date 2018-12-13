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