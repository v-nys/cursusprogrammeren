> Bekijk volgende kennisclip waarin wordt uitgelegd hoe je meerdere projecten in 1 solution in VS kunt plaatsen:[Kennisclip link](https://ap.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=f2c322cd-7607-4624-b0cd-a969006f8b2a).
**Probeer vanaf nu per hoofdstuk 1 solution aan te maken met daarin meerdere projecten (1 project per oefening)**

# BMI met if

Pas je BMI-programma ([zie practica vorige hoofdstuk](../1_csharpbasics/A_practica.md)) aan zodat je programma feedback aan de gebruiker geeft naargelang de berekende BMI.

De kleur tussen haakjes geeft aan in welke kleur je deze tekst zet:

* Onder de 18,5 (rood): ondergewicht.
* Tussen de 18,5 en de 24,9 (groen): normaal gewicht. 
* Tussen de 25 en de 29,9 (oranje): overgewicht. Je loopt niet echt een risico, maar je mag niet dikker worden.
* Tussen de 30 en de 39,9 (rood): Zwaarlijvigheid (obesitas). Verhoogde kans op allerlei aandoeningen zoals diabetes, hartaandoeningen en rugklachten. Je zou 5 tot 10 kg moeten vermageren.
* Boven de 40 (paars): ernstige zwaarlijvigheid. Je moet dringend vermageren want je gezondheid is in gevaar (of je hebt je lengte of gewicht in verkeerde eenheid ingevoerd)

# Schoenverkoper
a) Maak een oefening die aan de gebruiker vraagt hoeveel paar schoenen hij wenst te kopen. Ieder paar schoenen kost steeds 20euro. Indien de gebruiker 10 paar koopt kosten ze maar 10euro. Toon aan de gebruiker de totale prijs.

b) Voeg nu toe dat het programma eerst aan de kassier vraagt vanaf hoeveel paar de klant korting zal krijgen. Als de gebruiker dus 5 indient zal reeds bij 5 paar de kost per paar 10euro zijn.

# Ohm-berekenaar
Vraag aan de gebruiker wat hij wenst te berekenen: Spanning, Weerstand of Stroomsterkte. Vraag vervolgens de 2 andere waarden (als dus de gebruiker "Spanning" kiest vraag je aan de gebruiker de stroomsterkte en de weerstand) en bereken m.b.v. de wet van Ohm de gewenste waarde.

# Kleurcode weerstand naar ohm
Vraag aan de gebruiker om de ringkleuren van de eerste 3 ringen in te voeren als tekst (bv ``groen``). Toon vervolgens de de waarde van deze weerstand.
Als dus de gebruiker na mekaar invoert:
```
rood
paars
rood
```
Dan zal het programma tonen:

``Deze weerstand heeft waarde van  2700 Ohm``

# Armstrong nummer
Een getal is een *narcistisch getal* of *armstronggetal* als het de som is van zijn eigen cijfers elk tot de macht verheven van het aantal cijfers.

* 9 is een Armstrong nummer, want 9 = 9^1 = 9
* 10 is geen Armstrong nummer, want 10 != 1^2 + 0^2 = 1
* 153 is een  Armstrong nummer, want: 153 = 1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153
* 154 is geen  Armstrong nummer, want: 154 != 1^3 + 5^3 + 4^3 = 1 + 125 + 64 = 190
Schrijf een programma dat aan de gebruiker een getal vraagt en vervolgens toont of het ingevoerde getal een Armstrong-nummer is of niet.

# Orakeltje van Delphi, part deux
Vul de oefening aan uit het vorige hoofdstuk. Voor het orakel je vertelt hoe lang je te leven hebt zal het eerste vragen of je een vrouw (``v``) of een man (``m``)bent. Dan vraagt ze je leeftijd.
Mannen leven maximum tot hun 120 jaar. Vrouwen tot 150 jaar. Laat het orakel een duur voorspellen die kan. Als een vrouw van 50 de vraag stelt dan zal het orakel dus een getal tussen 5 en 100 (``150-50``) genereren. Een man van 35 zal tussen de 5 en 85 (``120-35``) jaren langer kunnen leven. 


# Quiz
Maak een quiz. Maak gebruik van het switch-statement om de input van de gebruiker (a,b,c of d) te verwerken en bij iedere vraag aan te geven of dit juist/fout is. Voorzie 3 multiple choice vragen. Houdt bij hoe vaak de speler juist antwoordde en geef op het einde de eindscore (Juist is +2 , fout is -1)

 Zoek op hoe je de kleur van de letters en de achtergrond in een console-applicatie kunt aanpassen en pas dit toe op je quiz om deze er iets boeiender uit te laten zien. Toon iedere vraag op een nieuw scherm.

# Schrikkeljaar
De gebruiker voert een jaartal in en jouw programma toont of het wel of geen schrikkeljaar is. Een schrikkeljaar is deelbaar door 4, behalve als het ook deelbaar is dor 100, tenzij ht wél deelbaar is door 400.
Bijvoorbeeld: 
* 1997: geen schrikkeljaar
* 1996: wél schrikkeljaar
* 1900: geen schrikkeljaar
* 2000: wél schrikkeljaar
