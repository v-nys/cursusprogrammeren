> Welkom terug. Goed te zien dat je de missie zo serieus neemt. Allereerst willen we testen hoe vaardig je C# skills nog zijn. Van zodra je deze opdracht begint door te nemen gelieve een timer te starten. Je mag maximum 120 minuten over deze opdracht doen. Deze tijd is inclusief het lezen van de opdracht en het starten van VS. Je start je timer vanaf de eerste titel hierna leest.

# Start de klok

## Maak een Vaccin klasse

Deze klasse heeft:
* Een Naam (``string``) als autoproperty met private setter. 
* Enkel een overloaded constructor, waarbij je de naam van het vaccin kunt instellen
* Een methode ``TryKillCode`` die geen parameters aanvaardt en steeds een random getal tussen 1 en 100 teruggeeft 
* Een autoproperty ``Oplossing`` van het type ``int`` deze staat standaard op -1.
* Een methode ``ToonInfo`` die de naam van het vaccin en de huidige opl op het scherm zet.

## Maak een Virus klasse

Deze klasse heeft:
* Een Naam als autopoperty met private setter
* Een DoomCountdown (``int``) full property met private setter:
  * Indien doomcountdown 0 of lager wordt gezet zal er "Game over [Naam virus]" op het scherm verschijnen. Dit gebeurt in de setter van de property.
* Een private ``int killcode``
* Enkel een default constructor die:
  * DoomCountdown op een getal tussen 10 en 20 instelt.
  * killcode op een getallen tussen 0 en 99 instelt
* Een methode ``TryVaccin`` die:
  * Eén parameter van het type ``Vaccin`` aanvaardt
  * Een bool teruggeeft. Deze zal true zijn indien het meegegeven Vaccin werkt:
    * De methode zal de ``TryKillcode`` aanroepen op het Vaccin. Indien het resultaat van TryKillcode overeenkomt met de killcode van het Virus zal er een true teruggestuurd worden. Ook zal vervolgens de property Oplossing van het Vaccin op de geteste én werkende killcode ingesteld worden in het meegegeven Vaccin.
    * Indien de kill code verkeerd is wordt er false terugestuurd , maar niet voordat eerst de doomcountdown met 1 werd verlaagd.

## Lijst van Vaccin

Maak een virus aan.
Maak een programma waarin je 5 vaccins aanmaakt en in een lijst plaatst. Vervolgens ga je deze  vaccins blijven testen op een aangemaakt virus en toon je aan de gebruiker welke Vaccin werkten. 
Indien de countdown van het virus op 0 komt te staan ben je gameover en heb je geen vaccin gevonden.

# Vaccinatietester

Maak een klasse ``VaccinatieCentrum`` aan.

Deze klasse heeft een ``static`` methode ``BewaarVaccin``. Aan deze methode kan je een int als parameter meegeven. Deze parameter wordt in een ``static`` autoproperty bewaard en bevat de killcode voor het virus.

Maan een ``static`` methode 