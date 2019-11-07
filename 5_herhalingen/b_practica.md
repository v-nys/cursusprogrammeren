> Begin pas aan deze oefeningen in week 2 van deze module. Doe eerst de practica deel 1!

##  Grootste getal
Vervolledig deze code zodat ook getoond wordt welke de grootste waarde is die werd ingevoerd.
```csharp
int x=0;
int y=0;
do
{
    y=y+x;
    Console.WriteLine("Voer gehele waarden in (32767=stop)");
    string instring= Console.ReadLine();
    x= Convert.ToInt32(instring);
    //....

}while (x != 32767)
Console.WriteLine($"Som is{y}");
```

## Boekhouder
1° Maak een 'boekhoud-programma': de gebruiker kan continu positieve en negatieve getallen invoeren. Telkens hij op enter duwt wordt de huidige invoer aan de balans bijgevoegd.
Je houdt volgende zaken bij:

* De balans van alle ingevoerde getallen: dit is gewoon de som van de getallen. Als de gebruiker dus de getallen 4,-10, 8 invoerde dan zal de balans op +2 staan  (4 -10 + 8)
* De som van alle negatieve invoeren. Als de gebruiker dus 4,-10,8,-6 invoerde dan zal dit getal op -16 staan (= -10 -6) .
* De som van alle positieve invoeren. Als de gebruiker dus 4,-10,8,-6 invoerde dan zal dit getal op +12 staan (= 4+8) . 
* Het gemiddelde van alle ingevoerde getallen 

Deze 4 getallen worden steeds geüpdate en getoond wanneer de gebruiker een nieuw getal invoert en op enter duwt.


## Raad het getal

**Deel 1:** Teken de flowchart van het volgende programma. 
```csharp
int getal;
int poging = 0;
string pogingString;
bool gevonden= false;
Random rand= new Random();
getal= rand.Next(0,10);

while(!gevonden)
{
    Console.WriteLine("Geef een getal tussen 0 en 10");
    pogingString= Console.ReadLine();
    poging = int.Parse(pogingString);

    if(getal>poging)
    {
        Console.WriteLine("Het gezochte getal is groter, probeer opnieuw.");
    }
    else if(getal<poging)
    {
        Console.WriteLine("Het gezochte getal is kleiner, probeer opnieuw.");
    }
    else 
        gevonden=true;
}
Console.WriteLine($"Gevonden! Het te zoeken getal was inderdaad {getal} je had er {poging} pogingen voor nodig.");
```

**Deel 2:** Pas het programma zo aan dat de tekst die verschijnt bij het inlezen van de volgende poging het resterende interval aangeeft. Gebruik hiervoor twee extra variabelen "ondergrens" en "bovengrens" die als beginwaarden respectievelijk 0 en 100 krijgen. Bij het inlezen van de volgende waarde voor poging zal deze toegekend worden aan ondergrens of bovengrens naargelang ze groter dan wel kleiner dan het te zoeken getal is. 

Zie hieronder een voorbeeldoutput:
 ![](../assets/3_loops/raadgetaloutput.png)

**Deel 3:**
Bouw in het programma een controle in die er voor zorgt dat je geen waarde meer kan ingeven die buiten het opgegeven interval ligt (dus ook indien de grenzen aangepast worden moet deze controle blijven werken!)
**Deel 4:**
Pas het programma aan zodat er een maximum aantal pogingen is toegestaan. Om dit maximum te bepalen moet je uitgaan van de beginwaarden van "ondergrens" en "bovengrens". Ga dus na hoeveel pogingen er in het ideale geval (bij het zoeken telkens de middelste waarde als nieuwe poging ingeven) maximaal nodig zijn om een interval te doorzoeken.


## Steen schaar papier
Maak een applicatie waarbij de gebruiker steen-schaar-papier met de computer kan spelen. De gebruiker kiest telkens steen, schaar of papier en drukt op enter. Vervolgens kiest de computer willekeurig steen, schaar of papier (gebruik de Random.Next() methode, waarbij je deze tussen 1 en 3 laat varieren). 
Vervolgens krijgt de winnaar 1 punt:
* Steen wint van schaar, verliest van papier
* Papier wint van steen, verliest van schaar
* Schaar wint van papier, verliest van steen
* Indien beide hetzelfde hebben wint niemand een punt.

Op het scherm wordt telkens getoond wie de huidige ronde heeft gewonnen en hoeveel de tussenscore is. De eerste (pc of gebruiker) die 10 punten haalt wint.

Teken een flowchart van je applicatie.





# Become Neo
Volgende code genereert een beeld zoals dat ook in de cultfilm The Matrix plaatsvindt. 
```csharp
Random rangen = new Random();
Console.ForegroundColor = ConsoleColor.Green;
while (true)
{
    //Genereer nieuw random teken:
    char teken = Convert.ToChar(rangen.Next(62, 400));
    //Zet teken op scherm
    Console.Write(teken);
    
    //Ietwat vertragen
    System.Threading.Thread.Sleep(10); //dit getal is in milliseconden. Speel er gerust mee.
    
    //Af en toe donker kleurtje
    if(rangen.Next(0,3)==0)
    {
        Console.ForegroundColor = ConsoleColor.DarkGreen;
    }
    else
    {
        Console.ForegroundColor = ConsoleColor.Green;
    }
}
```

Vul de code aan zodat de karakters random kleuren krijgen. Kan je het nog cooler maken?

# [PRO]  Password generator
Ontwerp een consoletoepassing waarmee je een wachtwoord genereert voor een gebruiker. Het wachtwoord is opgebouwd uit:

de 2 eerste letters van de familienaam: de 1ste letter is een hoofdletter, de 2de letter is een kleine letter. 
Daarna worden de 2 letters gewisseld;
het zonenummer van het telefoonnummer zonder de 0;
het eerste cijfer van de postcode in het kwadraat.

# BeerSong
Schrijf een BeerSong-generator zoals onderstaande output. Merk op dat de laatste 6 zinnen anders zijn:

```
99 bottles of beer on the wall, 99 bottles of beer.
Take one down and pass it around, 98 bottles of beer on the wall.

98 bottles of beer on the wall, 98 bottles of beer.
Take one down and pass it around, 97 bottles of beer on the wall.

97 bottles of beer on the wall, 97 bottles of beer.
Take one down and pass it around, 96 bottles of beer on the wall.

96 bottles of beer on the wall, 96 bottles of beer.
Take one down and pass it around, 95 bottles of beer on the wall.

95 bottles of beer on the wall, 95 bottles of beer.
Take one down and pass it around, 94 bottles of beer on the wall.
....

4 bottles of beer on the wall, 4 bottles of beer.
Take one down and pass it around, 3 bottles of beer on the wall.

3 bottles of beer on the wall, 3 bottles of beer.
Take one down and pass it around, 2 bottles of beer on the wall.

2 bottles of beer on the wall, 2 bottles of beer.
Take one down and pass it around, 1 bottle of beer on the wall.

1 bottle of beer on the wall, 1 bottle of beer.
Take it down and pass it around, no more bottles of beer on the wall.

No more bottles of beer on the wall, no more bottles of beer.
Go to the store and buy some more, 99 bottles of beer on the wall.
```

## BankManager

Ontwerp een klasse Account die minstens een Naamveld, bedrag en rekeningnummer bevat. Voorzie 3 methoden:

1. WithdrawFunds: bepaald bedrag wordt van rekening verwijderd
2. PayInFunds: bepaald bedrag (als parameter) wordt op de rekening gezet
3. GetBalance: het totale bedrag op de rekening wordt teruggegeven

Pas de WithdrawFunds methode aan zodat als returntype het bedrag (int) wordt teruggegeven. Indien het gevraagde bedrag meer dan de balance is dan geef je al het geld terug dat nog op de rekening staat en toon je in de console dat niet al het geld kon worden gegeven.

Maak 2 instanties van het type Account aan en toon aan dat je geld van de ene account aan de andere kunt geven, als volgt:

```csharp
BankAccount rekening1=new BankAccount();
BankAccount rekening2=new BankAccount();
```

Voeg aan de Account-klasse een private field toe zijnde van het type accountState dat een enumeratie bevat. De account kan in volgende states zijn "Geldig", "Geblokkeerd"). 
Maak een bijhorende publieke Methode  waarmee je de account van state kunt veranderen. Deze methode (noem ze ChangeState) vereist één parameter van het type accountState natuurlijk.

Indien een persoon geld van of naar een Geblokkeerde rekening wil sturen dan zal er een error op het scherm verschijnen.
Maak een array aan van 10 klanten. Wanneer je met klassen werkt moet je bij de initialisatie van de array ook ieder element afzonderlijk initialiseren, als volgt:

```csharp
BankAccount[] lijst = new BankAccount[10];
//Init
for(int i=O; i<lijst.Length;i++)
{ 
 lijst[i]= new BankAccount();
}
```

Schrijf nu een BankManager systeem. Voorzie  een console- menu waarbij de gebruiker volgende zaken kan doen:

1. Nieuwe klant aanmaken (max 10) 
2. Status van bestaande klant tonen 
3. Geld op  bepaalde account zetten 
4. Geld van bepaalde account afhalen 
5. Geld tussen 2 accounts overschrijven.
6. Een totaaloverzicht van alle accounts tonen (Allerlei statistieken zoals de totale som op alle rekeningen samen, rijkste account, etc worden in een tabel getoond)

Voorzie extra functionaliteit naar keuze.