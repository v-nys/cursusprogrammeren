# Practica klassen

## Klassen objecten
### Sports
Kies je favoriete sport of game (voor zij die enkel pc/console-sporten :p  ). Maak een klasse aan die een speler uit deze sport kan voorstellen. Verzin een 4-tal datavelden die deze spelers hebben, alsook 2 methoden die de speler moet kunnen uitvoeren. Je mag deze datavelden en methoden voorlopig allemaal 'public' zetten (snap je properties al? Cool, ga dan ineens voor properties!) . 

Voorzie ook minstens 1 "Naam" (string) dataveld.

Bijvoorbeeld: 

klasse Waterpolospeler, 

datavelden: SpelerNaam(string), Mutsnummer (int), IsDoelman (bool), IsReserve(bool), Reeks (string, bv “Cadet”). 

Methoden: GooiBal, Watertrappen

Wanneer de methoden worden aangeroepen zal er een tekst (mbv console WriteLine in de methode) op het scherm verschijnen die bv zegt ``Ik (Jos) gooi de bal``. Waarbij de naam van de speler in kwestie uit het Naam dataveld wordt gebruikt om mee getoond te worden.

Maak vervolgens een console-applicatie aan waarin je de werking van de klasse aantoont. Maar in de applicatie een aantal speler-objecten aan, vervolgens stel je (via code) hun datavelden in. Vervolgens roep je enkele methoden van de spelers aan en toon je via (ConsoleWriteLine) ook de datavelden van de individuele spelerobjecten. 

Toon maw aan dat je:
* Een klasse kunt maken (in een aparte file!)
* Instanties (objecten) van deze klasse kunt maken
* Kunt werken met deze instanties (datavelden instellen én uitlezen, aanroepen van methoden)

Vervolgens:
Schrijf een methode genaamd:
``static void SimuleerSpeler(Waterpolospeler testspeler)``

(vervang Waterpolospeler door de klasse die je zelf hebt gemaakt)

De SimuleerSpeler-methode zal beide methoden van je klasse telkens 3x aanroepen m.b.v. een for-loop in de methode (dus in mijn geval 3x GooiBal en 3xWatertrappen)

Test je methode door 2 objecten aan te maken en telkens mee te geven als parameter.


### Alledaags
Zoek een foto naar keuze (nieuws, privé, etc) waarop meer dan één element opstaat (dus geen pasfoto of foto van blauwe lucht zonder wolken). Tracht de nodige klassen te verzinnen (met enkele datavelden en methoden)  en maak in een console-applicatie vervolgens objecten van deze klassen aan. Voeg de foto aan je solution-folder toe.

Bijvoorbeeld: een foto van een betoging. Je zou minstens 3 klassen kunnen verzinnen (gebouw, politie, betoger). Van ieder van deze klassen maak je dan objecten aan zoals je ze op de foto ziet (uiteraard gaan we geen 30 betoger-instanties maken, enkele zijn genoeg, als voorbeeld).

## RapportModule
Ontwerp een klasse Resultaat die je zal tonen wat je graad is gegeven een bepaalde behaald percentage. Het enige dat je aan een Resultaat-object moet kunnen geven is het behaalde percentage. Enkel het totaal behaalde % wordt bijgehouden via een auto-property. Via een methode PrintGraad kan de behaalde graad worden weergegeven. Dit zijn de mogelijkheden:

< 50: niet geslaagd;
tussen 50 en 68: voldoende;
tussen 68 en 75: onderscheiding;
tussen 75 en 85: grote onderscheiding;
> 85: grootste onderscheiding.

Schrijf een overloaded constructor die ervoor zorgt dat het behaalde percentage zo kan ingesteld worden (Resultaat r= new Resultaat (74);)
Test je klasse door enkele objecten in je main aan te maken en de verschillende properties waarden te geven en methoden aan te roepen.

## Methoden in klassen

### Nummers
Maak een eenvoudige klasse Nummers. Deze klasse bevat 2 getallen (type int). Er zijn 4 methoden:
* ``Som``: geeft som van beide getallen weer
* ``Verschil``: geeft verschil van beide getallen weer
* ``Product``: geeft product van beide getallen weer
* ``Quotient``: geeft deling van beide getallen door. Toon "Error" indien je zou moeten delen door 0. 

Toon in je main aan dat je code werkt.

Volgende code zou namelijk onderstaande output moeten geven:
```csharp
    Nummers paar1 = new Nummers();
    paar1.getal1 = 12;
    paar1.getal2 = 34;

    Console.WriteLine("Paar:" + paar1.getal1 + ", " + paar1.getal2);
    Console.WriteLine("Som = " + paar1.Som());
    Console.WriteLine("Verschil = " + paar1.Verschil());
    Console.WriteLine("Product = " + paar1.Product());
    Console.WriteLine("Quotient = " + paar1.Quotient());
```

Output:
```
Paar: 12, 34
Som = 46
Verschil = -22
Product = 408
Quotient = 0,352941176470588
```

### Figuren
Maak een eenvoudige klasse Rechthoek aan die een lengte en breedte als public fields heeft. 
Maak ook een klasse Driehoek die een basis en hoogte als fields heeft.

Beide klassen hebben een methode ``ToonOppervlakte`` die de oppervlakte van de figuur in kwestie op het scherm toont.

Toon de werking van het project aan door een aantal instanties van Driehoek en Rechthoek te maken, met verschillende groottes. Roep van iedere figuur de ToonOppervlakte-methode aan.



## Properties in klassen

### PizzaTime
Maak een klasse Pizza. Deze klasse heeft een aantal private fields:
* toppings (string): bevat beschrijving van wat er op ligt, bv. ananas, pepperoni, etc.
* diameter (integer): doorsnede van de pizza in cm
* price (double): prijs van de pizza in euro.
Zorg ervoor dat je met behulp van properties deze 3 velden kan uitlezen en aanpassen. Bouw controle in zodat de fields geen foute waarden kunnen gegeven worden (denk maar aan negatieve prijs en diameter, pizza zonder topping, etc.). Maak in je main een aantal pizza-instanties aan en toon de werking van de properties aan.

### Student Organizer Deluxe
Herschrijf de [Student-klasse](../6_klassen_en_objecten/A_practica.md#studentklasse) en zorg ervoor dat iedere public field private is. Vervolgens maak je bijhorende public properties aan die toegang tot deze private fields verzorgen. Controleer in de properties op illegale input zodat bijvoorbeeld geen  de punten enkel getallen tussen 0 en 20 mogen zijn.

Herschrijf de studentmanager zodat deze werkt met deze nieuwe klasse .

### BankManager

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
 
Voeg aan de Account-klasse een private field toe zijnde van het type accountState dat een enumeratie bevat. De account kan in volgende states zijn “Geldig”, “Geblokkeerd”). 
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

## Operator overloading
### Breuk
Maak een klasse ‘Breuk’ dat dus een breuk zal voorstellen met een noemer en teller.

Voorzie properties voor noemer en teller, waarbij de noemer niet 0 mag zijn (zet deze op 1 indien de gebruiker dit toch probeert).

Voeg 2 constructors toe:

* Default constructor: de breuk wordt ingesteld op 0/1
* Overloaded constructor: zowel de noemer als teller worden als parameter meegegeven

Voorts:
1. Voeg een + operator toe die het mogelijk maakt om 2 breuken bij elkaar op te tellen. Wanneer de +operatie is toegepast wordt ook automatisch de Vereenvoudig-methode aangeroepen (zie verder) voor het resultaat wordt teruggegeven. Belangrijk: je dient aan operator overloading te doen. We willen dus dat je bijvoorbeeld kan schrijven Breuk breuksom= breuk1 + breuk2;
2. Voeg voorts een * operator toe die breuken vermenigvuldigen mogelijk maakt (ook hier wordt het resultaat vereenvoudigd teruggegeven).
3. Voeg een methode ‘AlsString’ toe die de breuk als string teruggeeft, waarbij de breuklijn als slash wordt voorgesteld.

 
Maak een array van 4 breuken in je main en laat de gebruiker deze alle 4 invullen. Toon vervolgens de som en vermenigvuldiging van deze 4 breuken als strings op het scherm.

Pro: Voeg een methode ‘Vereenvoudig’ toe. Deze zal de breuk vereenvoudigen indien mogelijk. Als dus de breuk op 2/4 staat dan wordt deze na het uitvoeren van deze methode 1/2.