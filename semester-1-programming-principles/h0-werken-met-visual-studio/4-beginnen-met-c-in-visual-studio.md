---
description: >-
  In het vorige onderdeel Een C# project maken in Visual Studio, hebben we een
  nieuw project gemaakt met de naam BeginnenMetCharp.
---

# Beginnen met C\# in Visual Studio

In dit onderdeel:

1. analyseren we wat Visual Studio voor ons gemaakt heeft;
2. gebruiken we Visual Studio een C\# programma te uit te proberen;

## Doelstellingen

1. de basisonderdelen van de IDE leren kennen;
2. je leert hoe je de layout en het kleurenschema van IDE aanpast;
3. je schrijft de broncode in de editor;
4. je roept de compiler aan om de broncode om te zetten in programmabestand met de extensie .exe;
5. het programma wordt uitgevoerd en je kan het testen \(debuggen\);
6. als alles goed gaat, ben je klaar, Zo niet, dan terug naar de editor, de fout zoeken en verbeteren, opnieuw compileren en testen …
7. om wat hardnekkige fouten te zoeken kun je wel wat hulp gebruiken om de fouten te lokaliseren, zoals een debugger;
8. je kent het verschil tussen een debug versie van je programma en een release versie;

## Theorie

#### **1. IDE**

Het hele programmeerproces wordt een stuk aantrekkelijker met een handig gereedschap. En dat is het idee achter de geïntegreerde ontwikkelingsomgeving oftewel IDE \(Integrated Development Environment\). We gebruiken in deze lessen Visual Studio. Als Visual Studio het project BeginnenMetCSharp gemaakt heeft, wordt de editor van IDE geopend. We maken kennis met de essentiële onderdelen ervan:

![IDE basis onderdelen](../../.gitbook/assets/image%20%2835%29.png)

#### **2. Layout**

De layout van VS kan je volledig naar je hand zetten. Je kan ieder \(deel-\)venster en tab verzetten, verankeren en zelfs verplaatsen naar een ander bureaublad. Experimenteer hier gerust mee en besef dat je steeds alles kan herstellen:

![Reset Visual Studio Window Layout](../../.gitbook/assets/image%20%2832%29.png)

#### 3. Je kan ook het kleurenschema aanpassen

Open het Options dialoogvenster:

![Visual Studio Tools-Options](../../.gitbook/assets/image%20%2840%29.png)

En kies een ander kleurschema:

![Visual Studio Options dialoogvenster](../../.gitbook/assets/image%20%2841%29.png)

Met dit als resultaat:

![Visual Studio Dark kleurenschema](../../.gitbook/assets/image%20%2830%29.png)

#### **4. Het standaard programma in program.cs uitproberen**

Klik op het groene pijltje bovenaan, vlak voor de naam van het project BeginnenMetCSharp om het programma uit te proberen. 

![](../../.gitbook/assets/image%20%2834%29.png)

Je ziet dan het volgende:

![Het standaard programma in program.cs uitproberen](../../.gitbook/assets/image%20%2837%29.png)

#### 5. Opzettelijk een fout maken

We willen zien wat er gebeurt als er een fout in het programma staat. We verwijderen het puntkomma aan het einde van het statement in de Main functie. We vervangen

```csharp
Console.WriteLine("Hello World!");
```

door

```csharp
Console.WriteLine("Hello World!")
```

Het enige dat we hebben gewijzigd is de puntkomma op het einde.

#### 6. Opzettelijke fout testen

Klik op het groene pijltje bovenaan, vlak voor de naam van het project BeginnenMetCSharp om het programma opnieuw uit te proberen. De fout wordt in de editor onderlijnd met een rode golvende lijn. Je ziet het volgende:

![ Visual Studio Dialoogvenster met foutmelding](../../.gitbook/assets/image%20%2831%29.png)

#### 7. Fout detecteren 

We willen de laatste versie zonder fouten niet uitproberen en klikken dus op **No**. Dan wordt het **Error List** venster actief gemaakt:

1. we zien daarin uitleg over de fout;
2. dubbel klikken op de foutmelding en
3. de cursor verspringt in de editor naar de plaats waar de fout gevonden is en die wordt in de editor aangegeven met een rode golvende lijn onder de fout in de code:

![Visual Studio Zoeken waar de fout zit](../../.gitbook/assets/image%20%2836%29.png)

#### 8. Fout corrigeren

Plaats de puntkomma opnieuw op het einde van het statement op regel 9.

#### 9. Opnieuw testen

Voer het programma opnieuw uit door op het groene pijltje bovenaan te klikken, vlak voor de naam van het project BeginnenMetCSharp.

#### 10. Het **BeginnenMetCsharp.exe** bestand

10.1. De compiler zal je C\# code omzetten naar de IL-code zodat het programma uitgevoerd kan worden. Zolang de C\# niet exact voldoet aan de C\# syntax zal de compiler een foutmelding geven in het **Error List** venster.

![vereenvoudigd compiler overzicht](../../.gitbook/assets/image%20%2833%29.png)

10.2. Zolang we aan het uitproberen zijn \(debuggen\) wordt het exe bestand geplaatst in:

![Visual Studio Debug map](../../.gitbook/assets/image%20%2829%29.png)



#### **11. Release** versie van de app

11.1. Als we de applicatie in productie willen zetten moeten we een release versie maken;

11.2. Klik op het groene pijltje;

![Visual Studio Release versie van programma instellen](../../.gitbook/assets/image%20%2838%29.png)

11.3. De toepassing BeginnenMetCSharp.exe staat nu in de Release map:

![Visual Studio Release map](../../.gitbook/assets/image%20%2839%29.png)

## Oefening

Overloop samen wat we in de theorieles hebben gezien.

