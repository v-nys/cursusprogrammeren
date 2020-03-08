# Maak een "voortplantings-simulator".

# Intro
Maak een klasse ``Mens`` met  eigenschappen:
* geslacht (enum)
* kleur ogen (enum)
* lengte (in cm)


Maak 12 willekeurige mensen aan en plaats deze in een List (). Zorg ervoor dat er 3 mannen en 3 vrouwen in de eerste helft staan, idem in de tweede helft van de lijst.

Laat nu de mensen voortplanten:
* De eerste helft mensen in de List zoeken een willekeurige partner van het andere geslacht in de andere helft lijst.
* Enkel de vrouwen kunnen nieuwe mensen maken. 
    * Iedere mens heeft een methode '`Plantvoort`' die als parameter een andere mens vereist.
    * Enkel bij vrouwen zal deze methode iets doen
    * De methode geeft een nieuw mens object terug. De nieuwe mens heeft als lengte de gemiddelde lengte van de man en vrouw. De oogkleur is willekeurig die van de man of van de vrouw. Het geslacht is willekeurig
    * Plaats deze nieuwe mens in de lijst achteraan.

# Simulatie
Herhaal bovenstaande voor 10 generaties (merk op dat ouders dus vermoedelijk kinderen zullen maken met hun eigen kinderen/kleinkinderen. Niet over nadenken) en bekijk wat de resultaten zijn. Plaats deze simulatie in een static methode ``Simuleer`` die een List van mensen als parameter aanvaardt, alsook een getal dat aangeeft hoeveel generaties moet getest worden.

Toon aan de gebruiker hoeveel de gemiddelde lengte is, hoeveel percent welke kleur ogen heeft, etc.

Maak een applicatie waarbij de gebruiker experimenten kan doen om te zien wat er gebeurt na x generaties.
Bijvoorbeeld:
* Wat als mannen erg klein zijn, vrouwen erg lang
* Wat als mensen met blauwe ogen steeds die kleur aan hun kinderen doorgeven, na hoeveel generaties heeft iedereen blauwe ogen

# Mutaties

Introduceer mutaties tijdens de voortplanting. Iedere keer als er een nieuwe mens wordt aangemaakt tijdens Plantvoort bestaat er 10% kans dat een van de "regels" overtreden wordt (bv i.p.v. gemiddelde lengte wordt lengte van de mama genomen, of i.p.v. kleur van een van ouder krijgt kind bij mutatie altijd groene ogen, etc). Verzin zelf enkele mutatie regels.

Test je mutaties en verzin extra regels en pas toe in de Simulatiemethode.

Voeg een "bool" parameter toe aan de simulatiemethode om aan te geven of mutaties zijn toegestaan of niet, aslsook een int parameter om de kans van mutatie mee te geven (bijvoorbeeld 10 = 10%)

# Extra properties

Voeg extra eigenschappen aan je ``Mens`` toe die je ook betrekt als genetische eigenschappen tijdens het voortplanten (denk aan haarkleur, allergieën of aantal armen).