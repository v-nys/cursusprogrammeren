# Oefeningen

## H4-BMI-if

### Leerdoelen

* conditionele boodschappen

### Functionele analyse

Deze opgave bouwt verder op H3-BMI-berekenaar. Meerbepaald moet je de gebruiker niet alleen zijn of haar BMI tonen, maar moet je ook een gekleurde boodschap tonen die laat weten of de BMI goed zit of niet.

Voor een BMI lager dan 18,5 toon je de boodschap "ondergewicht" in rode tekst. Voor een BMI die hoger ligt dan 18,5 maar lager dan 25, toon je de boodschap "normaal gewicht" in groene tekst. Voor een hogere BMI, maar lager dan 30, toon je in gele tekst "overgewicht". Voor een hogere BMI, maar lager dan 40, toon je "zwaarlijvig" in rode tekst. Voor een hogere BMI toon je "ernstige obesitas" in magenta.

### Technische analyse
Via `if` en `else` (en dus ook `else if`) kan je gevallen onderscheiden. Gebruik `ConsoleColor.Red`, `ConsoleColor.Green`, `ConsoleColor.Yellow` en `ConsoleColor.Magenta`.


#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```text
Hoe veel weeg je in kg?
> 69.0
Hoe groot ben je in m?
> 1.78
Je BMI bedraagt 21.78.
normaal gewicht
```

{% hint style="info" %}
De tekst zou in het groen moeten verschijnen maar Gitbook staat dit niet meteen toe.
{% endhint %}

## Schoenverkoper

a\) Maak een oefening die aan de gebruiker vraagt hoeveel paar schoenen hij wenst te kopen. Ieder paar schoenen kost steeds 20euro. Indien de gebruiker 10 paar koopt kosten ze maar 10euro. Toon aan de gebruiker de totale prijs.

b\) Voeg nu toe dat het programma eerst aan de kassier vraagt vanaf hoeveel paar de klant korting zal krijgen. Als de gebruiker dus 5 indient zal reeds bij 5 paar de kost per paar 10euro zijn.

## Ohm-berekenaar

Vraag aan de gebruiker wat hij wenst te berekenen: Spanning, Weerstand of Stroomsterkte. Vraag vervolgens de 2 andere waarden \(als dus de gebruiker "Spanning" kiest vraag je aan de gebruiker de stroomsterkte en de weerstand\) en bereken m.b.v. de wet van Ohm de gewenste waarde.

## Kleurcode weerstand naar ohm

Vraag aan de gebruiker om de ringkleuren van de eerste 3 ringen in te voeren als tekst \(bv `groen`\). Toon vervolgens de de waarde van deze weerstand. Als dus de gebruiker na elkaar invoert:

```text
rood
paars
rood
```

Dan zal het programma tonen:

`Deze weerstand heeft waarde van 2700 Ohm`

Indien je deze oefening maakt nadat je reeds `switch` hebt leren gebruiken, los deze oefening dan met `switch` op. Nog niet gezien? Ga voor `if`-`if else` code.

## Orakeltje van Delphi, part deux

Vul de oefening aan uit het vorige hoofdstuk \(zie [hier](../h3-werken-met-data/a_practica.md#het-orakeltje-van-delphi)\). Voor het orakel je vertelt hoe lang je te leven hebt zal het eerste vragen of je een vrouw \(`v`\) of een man \(`m`\)bent. Dan vraagt ze je leeftijd. Mannen leven maximum tot hun 120 jaar. Vrouwen tot 150 jaar. Laat het orakel een duur voorspellen die kan. Als een vrouw van 50 de vraag stelt dan zal het orakel dus een getal tussen 5 en 100 \(`150-50`\) genereren. Een man van 35 zal tussen de 5 en 85 \(`120-35`\) jaren langer kunnen leven.

## Quiz

Maak een quiz. Maak gebruik van het `switch`-statement om de input van de gebruiker \(a,b,c of d\) te verwerken en bij iedere vraag aan te geven of dit juist/fout is. Voorzie 3 multiple choice vragen. Houd bij hoe vaak de speler juist antwoordde en geef op het einde de eindscore \(Juist is +2 , fout is -1\)

Zoek op hoe je de kleur van de letters en de achtergrond in een console-applicatie kunt aanpassen en pas dit toe op je quiz om deze er iets boeiender uit te laten zien. Toon iedere vraag op een nieuw scherm.

## Schrikkeljaar

De gebruiker voert een jaartal in en jouw programma toont of het wel of geen schrikkeljaar is. Een schrikkeljaar is deelbaar door 4, behalve als het ook deelbaar is door 100, tenzij het wél deelbaar is door 400. Bijvoorbeeld:

* 1997: geen schrikkeljaar
* 1996: wél schrikkeljaar
* 1900: geen schrikkeljaar
* 2000: wél schrikkeljaar

## H4-ruimte-specifiek

{% hint style="danger" %}
Dit is een complexere oefening dan de vorige! Pak het stapje voor stapje aan en gebruik indien nodig de debugger.
{% endhint %}

### Leerdoelen

* werken met `enum`s
* conversie van enums van en naar getallen
* werken met `switch`

### Functionele analyse

Deze opgave bouwt verder op H1-ruimte. Eerst vraag je de gebruiker om zijn of haar gewicht in te voeren. Daarna geef je een lijst van de planeten in ons zonnestelsel (Pluto inbegrepen, ook al is dat officieel geen planeet). Iedere planeet wordt voorafgegaan door een nummer. Dan selecteert de gebruiker het nummer van een van deze planeten en ten slotte toont het programma hoe veel de persoon weegt op de planeet in kwestie.

### Technische analyse
Je hebt hier verschillende zaken nodig:

* conversie naar een `double` om een gewicht in te lezen
* een `enum` om de planeten voor te stellen
* conversie van de planeten naar getallen om de gebruiker een nummer voor elke planeet te tonen
* conversie in de omgekeerde richting om de keuze van de gebruiker te verstaan
* een `switch` om de juiste vermenigvuldigingsfactor te bepalen

#### UI

console applicatie

#### voorbeeldinteractie\(s\)

```text
Hoe veel weeg je?
> 69.0
Voor welke planeet wil je je gewicht kennen?
1. Mercurius
2. Venus
3. Aarde
4. Mars
5. Jupiter
6. Saturnus
7. Uranus
8. Neptunus
9. Pluto
> 2
Daar weeg je 62.79kg.
```
