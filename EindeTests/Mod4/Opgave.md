# Heroes of AP
 
 *Volgende opgave komt uit een examen van augustus 2018 van deze cursus*

** Opgelet: deze opgave is erg brak en niet conform mijn gewoonlijke standaard.Waarvoor excuses**

## Inleiding
Heroes of AP is een single-player kaartspel dat we als consolespel spelenwaarbij de speler in zo weinig mogelijk beurten maximaal punten wil scoren. Het spel is een combinatie van geluk en strategie.
Spelregels
Heroes of AP bestaat uit een deck van tien kaarten met drie soorten kaarten:
* Landen: deze genereren mana 
  * Per beurt dat een kaart gedekt ligt verhoogt z’n mana-waarde (=COST)
* Centrales:
  * Per beurt genereert een centrale 1 punt indien deze zichtbaar is 
* Helden: deze gebruiken mana om punten te genereren
  * Per beurt dat een kaart gedekt ligt verlaagt z’n mana-waarde (=COST), maar nooit onder 1
  * Een held genereert een willekeurig aantal punten indien hij zichtbaar is afhankelijk van wat de gebruiker aan Mana betaald:
    * Om 1 punten te genereren moet de speler de Cost van de held in mana betalen
    * Het overschot aan mana dat de speler betaald zal ervoor zorgen dat de held mogelijk meer punten maakt, namelijk tussen 1 en het extra aan mana.

## Opzetten spel

* De speler krijgt 10 willekeurige kaarten  voor zich die gedekt blijven liggen. 
* Vijf kaarten zijn landkaarten,3 kaarten zijn centrales, 2 kaarten zijn helden
  * Iedere kaart heeft een willekeurige kost tussen 5 en 10

## Spelen spel

Zolang de speler geen 10 punten heeft zal de speler steeds een beurt spelen bestaande uit 4 fasen:
* **Fase 0 - Upkeep**: 
  *  alle landen die gedekt liggen zullen hun Cost met 1 verhogen (deze landen kunnen dus meer mana genereren van zodra de speler ze omdraait)
  *   alle helden die nog gedekt zijn hun Cost verlaagt met 1 (maar nooit lager dan 1)
  * alle centrale die zichtbaar zijn genereren 1 punt (hun Cost wordt niet gebruikt)
* **Fase 1 - FlipCard**: de speler kiest een kaart die moet omgekeerd worden.
  * Enkel kaarten die nog niet omgekeerd werden kunnen uiteraard omgekeerd worden.
* **Fase 2 - GenerateMana**: De speler kiest welke land mana genereert (enkel mogelijk indien er zichtbare landen zijn)
   * Een land genereert evenveel mana als de Cost van de kaart
* **Fase 3 - GeneratePoint**: De speler kiest welke held punten genereert (enkel mogelijk indien er zichtbare helden zijn)
  * De speler betaald hiervoor de cost van de held in mana. De held genereert vervolgens een willekeurig aantal punten tussen 1 en de cost van de held.

# Basisspel maken
## Deel 1 (8 punten)

**Gebruik de gegeven klassen (onderaan de opgave) in je project en pas ze aan waar nodig**

![](../../assets/Aallinone/heroap0.png) 
 
Vul de 3 klassen aan klassen om aan bovenstaand schema te voldoen:
* **``Land``:** 
  * Land is een ``Card``
  * Heeft een methode ``GenerateMana`` die mana zal returnen gelijk aan de ``Cost`` van het land, maar enkel indien het land zichtbaar is (``IsHidden==false``)
  * Heeft als ``Name`` altijd "Land"
  * Zal bij de ``DrawCard`` methode zichzelf in groene tekst op het scherm zetten, namelijk z’n ``Name``, gevolgd door z’n Cost (bv ``"Land 5"``)
  * Verhoogt z’n ``Cost`` met 1 wanneer ``UpdateCost`` wordt aangeroepen
* **``Centrale``:**
  * Centrale is een ``Card``
  * Heeft als Name altijd "Centrale"
  * Zal bij de ``DrawCard`` methode zichzelf in geel tekst op het scherm zetten, namelijk z’n Name (bv ``"Centrale"``)
  * Heeft de interface ``IPointGenerator``
  * Zal steeds 1 punt genereren bij ``GeneratePoints`` (de parameter die wordt meegegeven wordt niet gebruikt).
* **``Hero``:**
  * Hero is een ``Card``
  *	Heeft als ``Name`` altijd "Hero"
  * Heeft de interface ``IPointGenerator``
  * Zal bij de ``DrawCard`` methode zichzelf in gele tekst op het scherm zetten, namelijk z’n Name, gevolgd door z’n Cost (bv ``"Hero 6"``)
  * Heeft een methode ``GeneratePoints`` die 1 parameter aanvaardt van het type int. Indien de parameter gelijk is aan Cost zal de methode een willekeurig getal tussen 1 en Cost teruggeven als punten. 
 
* **``Deck``:**
  * Deck heeft een lijst van kaarten genaamd Kaarten, van het type ``List<Card>`` 
  * Deck heeft een default constructor: wanneer deze aangeroepen wordt zullen er 10 willekeurige kaarten (3 Centrale, 2 Hero, 5 Land) in de Kaarten-list geplaatst worden
  * Deck heeft een methode ``DrawCards``: deze zal de ``DrawCard`` van alle Kaarten aanroepen
  * Deck heeft een methode ``UpdateCosts``: deze zal de ``UpdateCost`` van alle Kaarten aanroepen die dat kunnen.
  * Deck heeft een methode ``GeneratePoints``: deze zal de ``GeneratePoints`` van alle Kaarten aanroepen die dat kunnen.
  * Kaarten-list is beschikbaar vanuit een readonly-property

## Deel 2: Basis game loop (8 punten)

Maak een basis-versie van het spel. 

1. Genereren van een Deck-object en de kaarten op het scherm tonen via DrawCards
2. Een loop die blijft herhalen tot de gebruiker 10 punten heeft
   * Alle interactie met de kaarten gebeurt uiteraard via het Deck-object
   * Bestaat uit de 4 fasen die al dan niet vragen aan de gebruiker wat er moet gebeuren
     * **Fase 0**: update costs van verborgen kaarten + Genereer punt per zichtbare Centrale
     * **Fase 1**: vraag aan gebruiker welke kaart moet omgekeerd worden
     * **Fase 2**: vraag aan gebruiker welk land mana moet genereren
     * **Fase 3**: vraag aan gebruiker welke held punten moet genereren
   * Na iedere fase ververs je het beeld (``Console.Clear()``) en herteken je de kaarten en toon je de volgende extra info aan de gebruiker, namelijk Mana, Punten en Beurt
   ![](../../assets/Aallinone/heroap1.png) 
3. Na de loop wordt getoond hoeveel beurten de gebruiker heeft nodig gehad


## Deel 3 Extras

* 1 punt: Gebruik een enum om bij te houden in welke fase van een beurt je bent.
* 2 punten: plaats alle spel-logica in deck zodat de gameloop enkel nog maar bestaat uit de aanroep van een ``SpeelBeurt()``-methode en een check of de loop moet gestopt worden.

# Voorbeeld spelverloop: 
 
![](../../assets/Aallinone/heroap.png) 

# Start klasen

## Card

```csharp
abstract class Card
{
    public Card(string naamin)
    {
        Name = naamin;
    }

    public abstract void DrawCard();
    protected int cost;

    private string name;

    public string Name
    {
        get { return name; }
        private set { name = value; }
    }
}
```

## IPointGenerator

```csharp
interface IPointGenerator
{
    int GeneratePoints(int payedmana);
}
```