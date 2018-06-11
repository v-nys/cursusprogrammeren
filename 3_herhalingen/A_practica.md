
## Prijzen met foreach
Maak een array die tot 20 prijzen (double) kan bewaren. Vraag aan de gebruiker om 20 prijzen in te voeren en bewaar deze in de array. Doorloop vervolgens m.b.v. een foreach-lus de volledige array en toon enkel de elementen op het scherm wiens prijs hoger of gelijk is aan €5.00. Toon op het einde van het programma het gemiddelde van alle prijzen (dus inclusief de lagere prijzen).

## For doordenker
Schrijf een programma dat de volgende output geeft , gegeven dat de gebruiker een maximum waarde invoert , dus als hij 4 ingeeft dan zal de driehoek maximum 4 breed worden. Gebruik enkel forloops!
```
*
**
***
****
***
**
*
```

## For doordenker extra
Schrijf een programma dat de volgende output geeft  (zie ook WhileDoordenker van vorige labo), gegeven dat de gebruiker een maximum waarde invoert die opgeeft uit hoeveel lijnen de boom bestaat. Maak enkel gebruik van for-loops.
```
     *
    ***
   *****
  *******
 *********
***********
```

# Euler project
Maak volgende opdracht van [projecteuler.net](projecteuler.net):
>Indien we alle natuurlijke getallen van 0 tot en met 10 oplijsten die een meervoud van 3 of 5 zijn, dan krijgen we de getallen 3,5,6 en 9. De som van deze 4 getallen is 23.
Maak nu een programma dat de som van alle veelvouden van 3 of 5 weergeeft onder van 0 tot 1000.

# Grootste getal
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
Console.WriteLine(y);
```
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
    else if(getal>poging)
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
 ![](/assets/3_loops/raadgetaloutput.png)

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

