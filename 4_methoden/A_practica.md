# Geavanceerde methode concepten

## Film Default
Maak een methode FilmRuntime() die 3 parameters accepteert:
1. Een string die de naam van de film bevat
2. Een integer die duur in minuten van de film bevat
3. Een enumtype die het genre van de film bevat (Drama, Actie, etc.)
Indien de duur van de film niet wordt meegeven wordt een standaard  lengte van 90 minuten ingesteld. Indien het genre niet wordt meegeven dan wordt deze default op Onbekend ingesteld.

De methode geeft niets terug maar toont eenvoudigweg de film op het scherm, gevolgd door z’n duur.
Toon aan in je main dat de methode werkt met zowel 1, 2 als 3 parameters. Toon ook aan dat je met ‘named arguments’ de methode kan aanroepen.

## Grote Som
Maak een methode Som() die eender welke hoeveelheid paramaters van het type int aanvaardt en vervolgens de som van al deze parameters teruggeeft (als int).

Toon in je main aan dat de methode werkt door onder andere 1, 3,5 en 10 gehele getalen mee te geven.

Toon ook aan dat je een array van 50 ints als parameter kan meegeven aan de methode. (hint:je moet het ``params``  keyword gebruiken).
