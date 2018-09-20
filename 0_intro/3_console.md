# First program verbeteren
We nemen terug ons eerste programma erbij en gaan hier aan verder werken:
```csharp
namespace Demo1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hoi, ik ben het!");
            Console.WriteLine("Wie ben jij?!");
            Console.ReadKey(); //Zie opmerking hieronder

        }
    }
}
```

# IMPORTANT: ReadLine en Visual Studio code
## Stap 1: console veranderen
![](/assets/attention.jpg)
`ReadLine` dat we zo meteen gaan bespreken is momenteel niet zo'n goede vriend van Visual Studio code.
Om ReadLine te kunnen gebruiken dienen we in ons project een aanpassing te maken. **Dit moet je bij ieder nieuw project doen dat je in de toekomst gaat aanmaken waar ReadLine vereist is**

* Ga naar de ``.vscode`` folder in je project en open de file ``launch.json``  (indien deze file en/of folder nog niet bestaat moet je eerst je project builden)
* In het bestand, vervang volgende lijn ``"console": "internalConsole",`` door **``"console": "externalTerminal",``**

Vanaf nu zal je programma in een aparte terminal runnen en kan je ReadLine toepassen.
## Stap 2: programma 'pauzeren' voor afsluiten
Je zal merken dat programma's die in de externe console runnen ogenblikkelijk afsluiten. Je kan dit oplossen door als laatste lijn  ``Console.ReadKey()`` of ``Console.ReadLine()`` te plaatsen. We hebben dit in de code hierboven reeds gedaan. Zorg er voor dat dus de lijn ``Console.ReadKey()`` steeds de laatste lijn is!

Dit is een goede gewoonte als je console-applicaties aan het schrijven bent.
 

## ReadLine: Input van de gebruiker verwerken

Met de console kan je met een handvol methoden reeds een aantal interessante dingen doen. 

Zo kan je bijvoorbeeld input van de gebruiker inlezen en bewaren in een variabele als volgt:
```csharp
string result;
result = Console.ReadLine();
```
Bespreking van deze code:

``string result;`` 
* Concreet zeggen we hiermee aan de compiler: maak in het geheugen een plekje vrij waar enkel data van het type string in mag bewaard worden; 
* Noem deze geheugenplek ``result``  zodat we deze later makkelijk kunnen in en uitlezen.

``result = Console.ReadLine();`` 

* Vervolgens roepen we de ``ReadLine`` methode aan. Deze methode zal de invoer van de gebruiker uitlezen tot de gebruiker op enter drukt.
* Het resultaat van de ingevoerde tekst wordt bewaarde in de variabele result (denk eraan dat de toekening van rechts naar links gebeurt).


Je programma zou nu moeten zijn:

```csharp
namespace Demo1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hoi, ik ben het!");
            Console.WriteLine("Wie ben jij?!");
            string result;
            result = Console.ReadLine();

            Console.ReadKey();  //Prevent program from finishing
        }
    }
}
```





Start nogmaals je programma. Je zal merken dat je programma nu een cursor toont en wacht op invoer. Als je eender welke karakters op het toetsenbord intypt en drukt op enter dan zal je programma stoppen met ‘``Druk op een toets om door te gaan. . .`` (dit zal in de taal staan waarin je computer op is ingesteld).



## Input gebruiker verwerken en gebruiken
We kunnen nu invoer van de gebruiker, die we hebben bewaard in de variabele `` result``  gebruiken en tonen op het scherm. 
```csharp     
Console.WriteLine("Dag ");
Console.WriteLine(result);
Console.WriteLine(" hoe gaat het met je?");
```

In de tweede lijn hier gebruiken we de variabele ``result´´(waar de invoer van de gebruiker in bewaard wordt) als parameter in de ``WriteLine``-methode. Met andere woorden: de ``WriteLine`` methode zal op het scherm tonen wat de gebruiker even daarvoor heeft ingevoerd.

Je volledige programma ziet er dus nu zo uit:
```csharp
using System;

namespace Demo1
{
    class Program
    {
        static void Main(string[] args)
        {

            Console.WriteLine("Hoi, ik ben het!");
            Console.WriteLine("Wie ben jij?!");

            string result;
            result = Console.ReadLine();

            Console.WriteLine("Dag");
            Console.WriteLine(result);
            Console.WriteLine("hoe gaat het met je?");

            Console.ReadKey();  //Prevent program from finishing
        }
    }
}
```
 
Test het programma en voer je naam in wanneer de cursor knippert.

Voorbeelduitvoer (lijn 3 is wat de gebruiker heeft ingetypt)
```csharp
Hoi, ik ben het!
Wie ben jij?!
tim [enter]
Dag
tim
hoe gaat het met je?
```


### Aanhalingsteken of niet?
Wanneer je de inhoud van een variabele wil gebruiken in een methode zoals  ``WriteLine()`` dan plaats je deze zonder aanhalingsteken!
Bekijk zelf eens wat het verschil wordt wanneer je volgende lijn code `` Console.Write(result);`` vervangt door ``Console.Write("result");`` .

De uitvoer wordt dan:
```csharp
Hoi, ik ben het!
Wie ben jij?!
tim [enter]
Dag
result
hoe gaat het met je?
```

## Write en WriteLine
De ``WriteLine``-methode zal steeds een line break ([enter] zeg maar) aan het einde van de lijn zetten zodat de cursor naar de volgende lijn springt. 

De ``Write``-methode zal geen enter aan het einde van de lijn toevoegen. Als je dus vervolgens iets toevoegt (met een volgende ``Write`` of ``WriteLine``) **dan zal dit aan dezelfde lijn toegevoegd worden.** 

Vervang daarom eens de laatste 3 lijnen code in je project door:
```csharp
Console.Write("Dag");
Console.Write(result);
Console.Write("hoe gaat het met je?");
```

Voer je programma uit en test het resultaat. Je krijgt nu:
```csharp
Hoi, ik ben het!
Wie ben jij?!
tim [enter]
Dagtimhoe gaat het met je?
```

Wat is er verkeerd gelopen? Al je tekst van de laatste lijn plakt zo dicht bij mekaar? Inderdaad, we zijn spaties vergeten toe te voegen! Spaties zijn ook tekens die op scherm moeten komen (ook al zien we ze niet) en je dient dus binnen de aanhalingstekens spaties toe  te voegen. Namelijk:
```csharp
Console.Write("Dag ");
Console.Write(result);
Console.Write(" hoe gaat het met je?");
```
Je uitvoer wordt nu:
```csharp
Hoi, ik ben het!
Wie ben jij?!
tim [enter]
Dag tim hoe gaat het met je?
```

### Opletten met spaties

Spaties zijn ook tekens die op scherm moeten komen (ook al zien we ze niet) en je dient dus binnen de aanhalingstekens spaties toe  te voegen. Indien je deze erbuiten plaats dan heeft dit geen effect (je wist al uit het eerste hoofdstuk dat C# alle witregels negeert die niet tussen aanhalingstekens staan). *In volgend voorbeeld zijn de spaties aangegeven als liggende streepjes ( _ )*.

Fout (de code zal werken maar je spaties worden genegeerd):
```csharp
Console.Write("Dag"_);
Console.Write(result_);
Console.Write("hoe gaat het met je?");
```
Correct:
```csharp
Console.Write("Dag_");
.Console.Write(result);
Console.Write("_hoe gaat het met je?");
```

## Zinnen aan mekaar plakken
We kunnen dit hele verhaal een pak korter tonen. De plus-operator (``+``) in C# kan je namelijk gebruiken om variabelen van het type string aan mekaar te plakken. De laatste 3 lijnen code kunnen korter geschreven worden  als volgt:

```csharp
Console.WriteLine("Dag " + result + " hoe gaat het met je?");
```

Merk op dat result dus NIET tussen aanhalingstekens staat, in tegenstelling de andere stukken zin. Waarom is dit? Aanhalingstekens in C# duiden aan dat een stuk tekst moet beschouwd worden als tekst van het type string. Als je geen aanhalingsteken gebruikt dan zal C# de tekst beschouwen als een variabele met die naam.

Bekijk zelf eens wat het verschil wanneer je volgende lijn code vervangt door de lijn er onder:
```csharp
Console.WriteLine("Dag "+ result + " hoe gaat het met je?");
Console.Write("Dag "+ "result" + " hoe gaat het met je?");
```

### Meer input vragen
Als je  meerdere inputs van de gebruiker tegelijkertijd wenst te bewaren dan zal je meerdere geheugenplekken nodig hebben om de invoer te bewaren. Bijvoorbeeld:
```csharp
string leeftijd;
Console.WriteLine("Geef leeftijd");
leeftijd = Console.ReadLine();
Console.WriteLine("Geef adres");
string adres;
adres = Console.ReadLine(); 
```