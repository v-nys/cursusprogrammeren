# Herhalingen
Herhalingen (**Loops**) creëer je wanneer bepaalde code een aantal keer moet herhaald worden. Hoe vaak de herhaling moet duren is afhankelijk van de conditie die je hebt bepaald. 

In het vorige hoofdstuk leerden we hoe we met behulp van beslissingen onze code konden *branchen**, aftakken zodat andere code werd uitgevoerd afhankelijk van de staat van bepaalde variabelen of invoer van de gebruiker. Wat we nog niet konden was **terug naar boven** vertakken. Soms willen we dat een heel stuk code 2 of meerdere keren moet uitgevoerd worden tot aan een bepaalde conditie wordt voldaan. "Voer volgende code uit tot dat de gebruiker 666 invoert."

Er zijn 3 basis manieren om zogenaamde loops te maken in C#:
* ``while``: zal 0 of meerdere keren uitgevoerd worden
* `` do while``: zal minimaal 1 keer uitgevoerd worden
* ``for``: een alternatieve iets compactere manier om loops te beschrijven

Voorts zullen we ook een speciale loop variant zien wanneer we arrays leren gebruiken:
* [``foreach``](../5_arrays/3_foreach.md)


## NEVER EVAH USE GOTO
![](/assets/attention.jpg)

Het moet hier alvast even uit m'n systeem. ``goto`` is weliswaar een officieel C# keyword, toch zal je het in deze cursus **nooit** zien terugkomen in code. Je kan alle problemen in je algoritmes oplossen zonder ooit ``goto`` nodig te hebben. Voel je toch de drang: don't! Simpelweg, don't. Het is het niet waard. Geloof me.
**NEVER USE GOTO**.

[Lees gerust hier waarom](https://stackoverflow.com/questions/3517726/what-is-wrong-with-using-goto).
