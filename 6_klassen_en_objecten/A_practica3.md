
# Pokémons deel 2

## Constructors

Pas de kennis van constructors toe op je Pokémon-project uit het vorige hoofdstuk. Zorg ervoor dat je Pokémons op 3 kunt aanmaken als volgt:

* Via een default constructor: alle base stats worden daarbij op 10 standaard ingesteld via de constructor
* Via een overloaded constructor die de gebruiker toelaat om de 6 base stats als parameters mee te geven (bv ``new Pokemon(45,42,50,65,34,67)``)
* Via object initializer syntax waarbij je eender welke stat kunt instellen.

## Static methoden

Voeg volgende static methoden toe aan je klasse. Test ze in je main:

* ``WhoWillWin``: deze methode aanvaardt 2 objecten van het type pokemon. De methode geeft een int terug. 1 indien de eerste van de 2 pokemons wint, 2 indien de tweede. 0 indien gelijkstand. Verzin zelf hoe je aan de hand van de pokemon-properties kunt beslissen welke pokemon het sterkst is

* ``GeneratorRandom``: deze methode heeft geen methoden nodig. De methoden zal een nieuwe Pokemon aanmaken met random eigenschappen en deze vervolgens als resultaat teruggeven.

# Digitale kluis

Maak een klasse ``DigitaleKluis`` die we gaan gebruiken om een kluis voor te stellen.

De klasse heeft volgende elementen: 

* Een private variabele die de toegangscode van de kluis bewaard als geheel getal (naam: ``code``) 
* Een overloaded constructor die als parameter een geheel getal toelaat. Dit getal zal worden toegewezen aan de private variabele code.
* Een full property ``CanShowCode`` die kan ingesteld worden op true or false, om aan te geven of de code van buitenuit kan gezien worden.
* Een read-only property ``CodeLevel`` van type int. Deze property zal de ``level`` van de code teruggeven. Het level is eenvoudigweg de code gedeeld door 1000 als geheel getal (dus indien de code 500 is zal 0 worden teruggegeven, indien de code 2000 is wordt 2 teruggegeven, etc.) 
* Een fullproperty Code met private set. De get van deze property zal -666 teruggeven, tenzij CanShowcode op true staat, in dit geval zal de effectieve code worden terug gegeven. 
* Een methode ``TryCode`` die een geheel getal als parameter aanvaardt. De methode geeft een true terug indien de code correct was, anders false. Deze methode kan gebruikt worden om extern een code te testen , indien deze overeenkomt met de bewaarde code dan zal gemeld worden dat de code geldig is en wordt ook getoond hoeveel keer de gebruiker geprobeerd heeft. Indien de gebruiker -666 meegaf dan meldt de methode dat de gebruiker een cheater is . Indien de gebruiker een foute code meegaf dan meldt de methode dat dit een foute code was en wordt het aantal pogingen met 1 verhoogd.  
* Een private variabele ``aantalpogingen`` om bij te houden hoe vaak de gebruiker geprobeerd heeft de code te vinden. 
Maak enkele Digitale Kluis objecten aan in je main en test of je bovenstaande klasse correct is geïmplementeerd.

# APCenture-Job Agency

Maak een klasse ``Job``. Deze klasse heeft vier data fields:

* Description (``string``) bijvoorbeeld “ruiten wassen”
* Duration (``int``) , stelt tijd voor die nodig is om job uit te voeren
* RatePerHour (``int``), stelt kostprijs per uur voor van deze job
* TotalFee (``int``), stelt totale prijs voor zijnde  duration x rateperhour

Voorzie properties voor deze 4 velden, echter de TotalFee heeft geen ‘set’  daar deze een berekening van andere properties is.
Telkens de Duration of RatePerHour wordt aangepast (set) wordt de TotalFee herberekend (je zal dus een private totalFee nodig hebben waar de public property TotalFee z’n waarde van krijgt).

Voorzie 2 constructors:

* Default constructor: stelt de description in op "onbekend" en zet duration en rateperhour in op 0.
* Overloaded constructor: waarbij je de 3 velden (behalve TotalFee) kan aanpassen tijdens de constructie van een Job-object

Toon de werking van je klasse aan door enkele objecten aan te maken met zowel de default als de overloaded constructor. Toon vervolgens dat TotalFee correct werkt.

