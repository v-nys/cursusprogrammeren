# Benodigheden

In alle lessen \(hoorcollege en practica\) hebben we 2 zaken nodig:

1. Deze cursus
2. Een laptop met daarop Visual Studio 2017 Enterpise edition geïnstalleerd. Enterprise \(aanbevolen\) kan je via [Dreamspark](https://dreamspark.ap.be) downloaden. Opgelet: VERGEET NIET DE KEY TE BEWAREN BIJ HET \(GRATIS\) BESTELLEN.

# Cheat sheet
Volgende document bevat een overzicht van de basis C# zaken van het eerste en (deel van het) tweede semester:


![/assets/0_intro/cheat-sheet.pdf](/assets/0_intro/cheatprev.jpg)


{% exercise %}
Define a variable `x` equal to 10.

{% initial %}
var x =

{% solution %}
var x = 10;

{% validation %}
assert(x == 10);

{% context %}
// This is context code available everywhere
// The user will be able to evaluate `exposedVar`
var exposedVar = 3;
// ... or call `exposedFunction`
function exposedFunction {
    return 3;
}
{% endexercise %}