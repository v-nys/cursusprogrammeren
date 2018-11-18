# Zoek de fouten
Volgende bugs, fouten, minder goede oplossingen komen uit oplossingen van vaardigheidsproeven. Kan jij ontdekken wat er mis? De oplossingen staan achteraan dit document.
(de code is hier en daar ingeperkt om de focus op de fout te leggen)

## Opgaven
1.
```csharp
int keuze = Convert.ToInt16(Console.ReadLine());
```

2.
```csharp
switch (keuze) {
case 1:
    totaal += 5;
    int pType = Convert.ToInt16(Console.ReadLine()); // 

    switch (pType)
    {
        case 1:
            totaal += 10;
            topping = 1;
            break;
        case 2:
            totaal += 5.5;
            topping = 2;
            break;
        case 3:
            totaal += 0;
            break;
    }
    break;
case 2:
// enzovoort
```
3.
```csharp
 Console.WriteLine("Laten we starten met de bestelling. Druk op 1 voor de pizzabodem, daarna 2 voor de topping, vervolgens 3 voor de chefs extra en tot slot 4 voor het afleveradres.");
keuze = Convert.ToInt32(Console.ReadLine());
pizzabodem = Convert.ToString(Console.ReadLine());
CheesyCrust = Convert.ToString(Console.ReadLine());
MartianMeal = Convert.ToString(Console.ReadLine());
PegasusLime = Convert.ToString(Console.ReadLine());
EndraliPies = Convert.ToString(Console.ReadLine());


//Je moet een paar keer ENTER drukken alvorens je tot de vraag komt.
//Pizzabodem
if (keuze == 1)
{

```

 4. 
 ```csharp            
 int toegestaanleeftijd = 1;     //  0 is nee en 1 is ja.
 int toegestaanafstand = 1;      //  0 is nee en 1 is ja.
 ```

 5. 
 ```csharp
 if (ToppingsKeuzeBodem1 == 1)
{
    Console.WriteLine("Wat is de afstand van het afleveradres in lichtjaren?");
    int AfleverAdres = Convert.ToInt32(Console.ReadLine());
    if (AfleverAdres < 10)
    {
        int PizzaTotaal = bodem+topping;
        Console.WriteLine($"Het totaal is gelijk aan {PizzaTotaal} IC");
    }
    else if (AfleverAdres >= 10)
    {
        int PizzaTotaal = (int)Math.Sqrt(AfleverAdres / 15) + martian + topping;
        Console.WriteLine($"Het totaal is gelijk aan {PizzaTotaal} IC");
    }
    else { Console.ForegroundColor = ConsoleColor.Red; Console.WriteLine("ERROR"); }
}
else if (ToppingsKeuzeBodem1 == 2)
{
    Console.WriteLine("Wat is de afstand van het afleveradres in lichtjaren?");
    int AfleverAdres = Convert.ToInt32(Console.ReadLine());
    if (AfleverAdres < 10)
    {

```
6. 
```csharp
PizzaTotaal = 25 + 5 + 10;

//Verder:
PizzaTotaal = 25 + 5 + 6;

//Verder:
PizzaTotaal = 25 + 5;
```

7. 
Volgende commentaar, of een variant, kwam bij vele studenten voor. Hoe had dit voorkomen kunnen worden?
```csharp
// Eindbedrag -> Had de pizzabodem en toppingprijzen niet apart opgeslagen
// en kon het niet meer veranderen wegens tijdstekort.
```
8. 
```csharp
Console.WriteLine("Oei, hier ging iets mis.");
Console.Clear();
Console.WriteLine("ERROR");
```

9. 
```csharp
goto end;
```

10. 
```csharp
double tussenkomst = adres / 5;
int Tonnen = 0;

if (tussenkomst <= 1)
{
    Tonnen = 1;
}
else if (tussenkomst <= 2)
{
    Tonnen = 2;
}
else if (tussenkomst <= 3)
{
    Tonnen = 3;
}
else if (tussenkomst <= 4)
{
    Tonnen = 4;
}
else if (tussenkomst <= 5)
{
    Tonnen = 5;
}
//enz.
```

11. Onderaan de code van een oplossing stond volgende commentaar:
    ```csharp 
    // TE WEINIG TIJD AKA MISSCHIEN TE TRAAG GEWERKT SORRY
    ```
    Mogelijk heeft de student te traag gewerkt, maar kijken we eens naar de code in z'n geheel dan zien we volgende beeld:

    ![](/assets/2_beslissingen/bigcode.jpg)

    What went wrong?


## Oplossingen
1. ``Convert.ToIn16`` is conversie naar een ``short`` maar het resultaat wordt wel in een grotere ``int`` bewaard. Ofwel werk je met ``short`` ofwel converteer je naar ``.ToInt32``.

2. Het is onduidelijk wat de verschillende cases willen zeggen: 1,2,3 is nietszeggend. Verduidelijk code met commentaar of gebruik ``enum``.

3. Hier gebeuren 2 fouten:
    1. De opmerking laat duidelijk zien dat de programmeur niet goed weet wat er moet gebeuren. De eerste ``WriteLine`` verteld aan de gebruiker duidelijk wat er moet ingevoerd worden. De eerste twee lijnen zijn dan ook zoals het hoort. Vervolgens worden er echter 5 extra zaken van de gebruiker verwacht dit met ``ReadLine`` worden ingelezen. De gebruiker weet uiteraard niet wat er moet ingevoerd worden en dus geeft de programmeur aan in de commentaar dat je maar een paar keer op enter moet duwen. De juiste manier had geweest om ofwel:
        * Voor iedere ``ReadLine`` een woordje uitleg via ``WriteLine`` geven wat er verwacht wordt.
        * Ofwel de zinnen naar de juiste plekken verderop in de code verplaatsen waar deze informatie effectief moet gevraagd worden.
    2. ``ReadLine`` geeft **altijd** ``string`` terug. De output ervan dus vervolgens nog een manueel converteren naar ``string`` mbv ``Convert.ToString`` is nutteloos.


4. Was er maar een type dat maar 2 mogelijk waarden kon hebben...Juist ja ``bool`` was hier een veel beter type geweest. Het had je code leesbaarder én minder foutgevoelig gemaakt (want wat was er gebeurt als je ``toegestaanleeftijd`` de waarde -6 had gegeven?)

5. De programmeur heeft het concept van ``scope`` mogelijk nog niet helemaal door. Dezelfde variabele wordt in meerdere codeblocks telkens van scratch terug aangemaakt (``int AfleverAdres`` en ``int PizzaTotaal``). Mogelijk was dat bewust. Maar wat als je verderop aan de code aan 'hét pizzatotaal' moet geraken? Dat is dan onmogelijk daar de aangemaakte variabele telkens maar leeft (=scope) binnen de accolades van het desbetreffende codeblock.

6. Dit is uiteraard een perfect legale zin. Maar niet als deze op verschillende plaatsen in de code deze vorm zo terugkomt. Wat als later de prijs van het ding dat nu ``25`` kost moet veranderen. De programmeur moet dan op alle plekken in z'n code dit manueel gaan aanpassen. En wat zijn die verschillende getallen eigenlijk?
Veel beter is om bovenaan je code de nodige variabelen (met goede namen) aan te maken waarin je de prijzen bewaard. De code wordt ook ogenblikkelijk veel begrijpbaarder:

    ```csharp
    int hawai=25;
    int ketchup=5;
    int noedels=6;
    int cheesycrust=10; 

    PizzaTotaal = hawai + ketchup + cheesycrust;

    //Verder:
    PizzaTotaal = hawai + ketchup + noedels;

    //Verder:
    PizzaTotaal = hawai + ketchup;
    ```

7. Lees de opgave steeds eerst helemaal door. Bepaald dan een 'aanvalsplan' hoe je de opgave gaat oplossen. Begin daarna pas te programmeren. Vergelijk het met het bouwen van een brug: je begint niet gewoon aan de linkeroever en dan meter per meter naar de andere oever te bouwen. Om dan aan de overkant te ontdekken dat de oever daar 5 meter hoger ligt en daar geen rekening mee hebt gehouden.

8. De bovenste zin zal maar enkele nanoseconden op het scherm verschijnen (de gebruiker zal deze dus nooit kunnen lezen) voor het scherm wordt leegemaakt en de nieuwe zin met ``ERROR`` op het scherm komt.

9.  Goto hell! PS ``Environment.Exit(0);``en  ``return`` waren in deze opgave de makkelijkste manieren om het programma af te sluiten. 

10. De programmeur wil hier z'n komma-getal naar boven afronden. Dit is duidelijk géén goede oplossing (gaat de programmeur voor alle ints die er bestaan een if bijschrijven?). De juiste manier om dit op te lossen is gebruik maken van de ``Math.Ceiling()`` methode die een getal naar boven zal afronden. De code kan dan herschreven worden naar 1 lijn:
    ```csharp
    int Tonnen = (int)Math.Ceiling(adres / 5);
    ```

11. De student heeft véél te veel dezelfde code geschreven (niet zichtbaar op de screenshot) en dus niet goed nagedacht over de if/else structuur die moet gemaakt worden. Maak steeds eerst een flowchart om te bepalen welke delen wanneer moeten gebeuren en zet 'gemeenschappelijke' code verderop in het verhaal. Het heeft bijvoorbeeld geen nut om overaal de ticket-visualisatie code te tonen daar deze voor alle mogelijkheden dezelfde is en dan onderaan de code gemeenschappelijk kan uitgevoerd worden.  Ook hier dus de opmerking die we ook in puntje 7 aanhaalden: stel eerst een aanvalsplan op voor je aan je aanval begint.