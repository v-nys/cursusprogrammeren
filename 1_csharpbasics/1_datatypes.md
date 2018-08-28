>Een variabele is een soort container in een C# programma waarin we een data waarde kunnen opslaan in het computergeheugen. The bewaarde waarde kan aangeroepen worden via de naam van de variabele

Een essentieel onderdeel van C# is kennis van datatypes. Binnen C# zijn een aantal types gedefinieerd die je kan gebruiken om data in op te slaan. Wanneer je data wenst te bewaren in je applicatie dan zal je je moeten afvragen wat voor soort data het is. Gaat het om een getal, een geheel getal, een kommagetal, een stuk tekst of misschien een binaire reeks? Ieder datatype in C# kan één welbepaald soort data bewaren, en dit zal telkens een bepaalde hoeveelheid computergeheugen vereisen. 

De data zelf bewaren we in **variabelen** van een **bepaald type**. Een variabele is een plekje in het geheugen dat in je programma zal gereserveerd worden om daarin data te bewaren van het type dat je aan de variabele hebt toegekend. Een variabele zal intern een geheugenadres hebben (waar de data in het geheugen staat) maar dat zou lastig programmeren meer, daarom moeten we ook steeds een naam oftewel **identifier** aan de variabele geven. 
>De naam (identifier) van de variabele moet voldoen aan de identifier regels uit het vorige hoofdstuk.


Dit alles bespreken we in de komende secties.

# Datatypes
Er zijn tal basistypes in C# gedeclareerd (zogenaamde **primitieve datatypes**). Dit semester leren we werken met datatypes voor:
* Gehele getallen: `sbyte, byte, short, ushort, int, uint, long`
* Kommagetallen: `double , float, decimal`
* Tekst: `char`,`string`
* Booleans: `bool`

# Basistypen voor getallen
Alhoewel een computer digitaal werkt en enkel 0'n en 1'n bewaard zou dat voor ons niet erg handig werken. C# heeft daarom een hoop datatypes gedefinieerd om te werken met getallen zoals wij ze kennen, gehele en kommagetallen. Intern zullen deze getallen nog steeds binair bewaard worden, maar dat is tijdens het programmeren zelden een probleem.
> Onthoudt echter dat onderaan je programma steeds hardware zal draaien die binair werkt. 

De basistypen van C\# om getallen in op te slaan zijn:

* Voor gehele getallen: `sbyte, byte, short, ushort, int, uint, long`
* Voor kommagetallen: `double , float, decimal`

> Ieder type hierboven heeft een bepaald bereik en hoeveelheid geheugen nodig. Je zal dus steeds moeten afwegen wat je wenst. Op een high-end pc met ettelijke gigabytes aan werkgeheugen (RAM) is geheugen zelden een probleem waar je rekening mee moet houden...Of toch: wat met real-time shooters die miljoenen berekeningen (3D) per seconde moeten uitvoeren. Daar zal iedere byte tellen. En op andere apparaten (smartphone, arduino, smart fridges, etc) is iedere byte geheugen nog kostbaarder. **Kortom: kies steeds bewust het datatype dat het beste 'past' voor je probleem qua bereik, precisie en geheugengebruik.**

## Eigenschappen van datatypes

Deze datatypes hebben allemaal een bepaald bereik, wat een rechtstreeks gevolg is van de hoeveelheid geheugen die ze innemen.

### Gehele getallen
Voor de gehele getallen:

| **Type** | **Geheugen** | **Bereik** | **Meer info**|
| :--- | :--- | :--- | :--|
| `sbyte` | 8 bits | -128 tot 127 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/sbyte)|
| `byte` | 8 bits | 0 tot 255 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/byte)|
| `short` | 16 bits | -32768 tot 32767 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/short)|
| `ushort` | 16 bits | 0 tot 65535 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/ushort)|
| `int` | 32 bits | -2 147 483 658 tot +2 147 483 657 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/int)|
| `uint` | 32 bits | 0 tot 4294967295 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/uint)|
| `long` | 64 bits | -9 223 372 036 854 775 808 tot 9 223 372 036,854 775 807 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/long)|
| `ulong` | 64 bits | 0 tot 18 446 744 073 709 551 615 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/long)|
| `char` | 16 bits | 0 tot 65535 | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/char)|

**We raden aan dat je de 'info' urls bekijkt om te ontdekken hoe je de literals van data datatypes moet schrijven in C#.**

Enkele opmerkingen bij deze tabel:
* De `s` vooraan `sbyte` types staat voor ``signed``: m.a.w. 1 bit wordt gebruikt om het + of - teken te bewaren. 
* De `u` vooraan `ushort`en `uint` staat voor `unsigned`. Het omgekeerde van signed dus. Kwestie van het ingewikkeld te maken dus. Deze twee datatypes hebben dus geen teken en zijn **altijd positief**.
* `char`bewaard karakters. We zullen verderop dit datatype uitspitten en ontdekken dat karakters (alle tekens op het toetsenbord, inclusief getallen, leesteken, etc.) als gehele, binaire getallen worden bewaard. Daarom staat `char` in deze lijst.
* Het grootste getal bij `long` is 2 tot de 63ste (
negen triljoen tweehonderddrieëntwintig biljoen driehonderd tweeënzeventig biljoen zesendertig miljard achthonderdvierenvijftig miljoen zevenhonderdvijfenzeventigduizend achthonderd zeven) . Dit zijn maar 63 bits?! Inderaad, de laatste bit wordt gebruikt om het teken te bewaren.

### Kommagetallen
Voor de kommagetallen zijn er maar 3 mogelijkeden. Ieder datatype heeft een 'voordeel' tegenover de 2 andere, dit voordeel staat vet in de tabel:

| **Type** | **Geheugen** | **Bereik** | **Precisie** |
| :--- | :--- | :--- | :--- |
| `float` | **32 bits** | 1,5\*10-45tot 3,4\*1048 | 7 digits |  [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/float)|
| `double` | 64 bits | **5\*10-324tot 1,7\*10308** | 15 digits |  [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/double)|
| `decimal` | 128 bits | 1\*10-28tot 7,9\*1028 | **28-29 digits** | [info](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/decimal)|

  Zoals je ziet moet je bij kommagetallen een afweging maken tussen 3 even belangrijke criteria.  Heb je ongelooflijk grote precisie nodig dan ga je voor een ``decimal``. Wil je vooral erg grote of erg kleine getallen kies je voor ``double``. De precisie van een getal is het aantal beduidende of significante cijfers. Het getal 12,45 heeft een precisie van 4. Zoals je merkt zal je dus zelden ``decimal`` nodig hebben , deze zal vooral nuttig zijn in wetenschappelijke programma's waar met erg exacte cijfers moet gewerkt worden. 
  
  > Bij twijfel opteren we meestal voor kommagetallen om het ``double`` datatype te gebruiken. Bij gehele getallen kiezen we meestal voor  ``int`` .

## Variabelen aanmaken en gebruiken

Om een variabele te maken moeten we deze **declareren**, door een type en naam te geven. Vanaf dan zal de computer een hoeveelheid geheugen voor je reserveren waar de inhoud van deze variabele in kan bewaard worden. 
Hiervoor dien je minstens op te geven:

1. Het datatype \(bv ``int`` ,  ``double``\)
2. Een identifier zodat de variabele uniek kan geïdentificeerd worden ([volgens de naamgevingsregel van C#](0_csharpessentials.md))
3. \(optioneel\) Een beginwaarde die de variabele krijgt bij het aanmaken ervan


Een variabele declaratie heeft als syntax:
```csharp
datatype identifier;
```
Bijvoorbeeld: ``int leeftijd;``

Je mag ook meerdere variabelen van het zelfde datatype in 1 enkele declaratie aanmaken door deze met komma's te scheiden:

```csharp
datatype identifier1, identifier2, identifier3;
```
Bijvoorbeeld ``string voornaam,achternaam,adres;``

Indien je reeds weet wat de beginwaarde moet zijn van de variabele dan mag je de variabele ook reeds deze waarde toekennen bij het aanmaken:

```csharp
int mijnLeeftijd = 37;
```

## Waarden toekennen aan variabelen

Vanaf dit punt kunnen we dus ten allen tijde deze variabele gebruiken om een waarde aan toe te kennen, de bestaande waarde te overschrijven, of de waarde te gebruiken, zoals:

* Waarde toekennen: `mijnGetal= 15;`. **Toekening gebeurt steeds van rechts naar links: het deel rechts van het gelijkheidsteken wordt toegewezen aan het deel links er van.**
* Waarde tonen op scherm: `Console.WriteLine(mijnGetal);`

Met de** toekennings-operator \(=\)** kan je een waarde toekennen aan een variabele. Hierbij kan je zowel een literal toekennen oftewel het resultaat van een expressie.

Je kan natuurlijk ook een waarde uit een variabele uitlezen en toewijzen aan een andere variabele:

```csharp
int eenAndereLeeftijd = mijnLeeftijd;
```


## Literal toewijzen

Literals zijn expliciet ingevoerde waarden in je code. Als je in je code expliciet de waarde 4 wilt toekennen aan een variabele dan is het getal 4 in je code een zogenaamde literal. Wanneer we echter data bijvoorbeeld eerst uitlezen of berekenen \(via bijvoorbeeld invoer van de gebruiker of als resultaat van een berekening\) en het resultaat hiervan toekennen aan een variabele dan is dit geen literal.

Voorbeelden van een literal toekennen:

```csharp
int temperatuurGisteren = 20;
int temperatuurVandaag = 25;
```

Het is belangrijk dat het type van de literal overeenstemt met dat van de variabele waaraan je deze zal toewijzen. Een string-literal (zie verder) stel je voor door aanhalingstekens. Volgende code zal dan ook een compiler-fout generen, daar je een string-literal aan een int-variabele wil toewijzen, en vice versa.

```csharp
string eenTekst;
int eenGetal;

eenTekst = 4;
eenGetal = "4";
```

Als je bovenstaande probeert te compileren dan krijg je volgende error-boodschappen:

![](/assets/0_intro/errorliteraltoekenning.png)

### Literal bepaald het datatype
De manier waarop je een literal schrijft in je code zal bepalen wat het datatype van de literal is:

* Gehele getallen worden standaard als ``int`` beschouwd. Bijvoorbeeld: ``125``.
* Kommagetallen (met punt ``.``) worden standaard als ``double`` beschouwd, vb: ``12.5``.
* Via een suffix na het getal kan je aangeven als het om andere types gaat:
    * ``U`` of ``u`` voor ``uint`` . Vb.: ``125U``.
    * ``L`` of ``l`` voor ``long`` . Vb.: ``125L``.
    * ``UL`` of ``ul`` voor ``ulong`` . Vb.: ``125ul``.
    * ``F`` of ``f`` voor ``float`` . Vb.: ``12.5f``.
    * ``M`` of ``m`` voor ``float`` . Vb.: ``12.5M``.
* Voor ``bool`` (zie verder) is dit enkel ``true``  of ``false``
* Voor ``char`` (zie verder) wordt dit aangeduid met een enkele apostrof voor en na de literal. Vb: ``'q'``.
* Voor ``string`` (zie verder) wordt dit aangeduid met  aanhalingsteken voor en na de literal. Vb: ``"pikachu"``.
  
De overige types ``sbyte``,``short`` en ``ushort`` hebben geen literal aanduiding. Er wordt vanuit gegaan wanneer je een literal probeert toe te wijzen aan een van deze types dat dit zonder problemen zal gaan (ze worden impliciet geconverteerd).

#### Hexadecimale en binaire notatie

Je kan ook hexadecimale notatie (starten met ``0x`` of ``0X``) gebruiken wanneer je bijvoorbeeld met ``int`` of ``byte`` werkt:
```csharp
int myAge= 0x0024;
byte myByteValue = 0x00C9;
``` 

Ook binaire notatie (starten met ``0b`` of ``0B``) kan:
```csharp
int myAge= 0b00010110001101000010‬; //Vanaf C# 7.2 mag je ook schrijven: 0b0001_0110_0011_0100_0010
byte myByteValue =  0b‭00100100‬9;
``` 


## Nieuwe waarden overschrijven oude waarden

Wanneer je een reeds gedeclareerde variabele een **nieuwe waarde toekent **dan zak de oude waarde in die variabele onherroepelijk verloren zijn. Probeer dus altijd goed op te letten of je de oude waarde nog nodig hebt of niet. Wil je de oude waarde ook nog bewaren dan zal je een nieuwe, extra variabele moeten aanmaken en daarin de nieuwe waarde moeten bewaren:

```csharp
int temperatuurGisteren = 20;
temperatuurGisteren = 25;
```

In dit voorbeeld zal er dus voor gezorgd worden dat de oude waarde van temperatuurGisteren, ``20``, zal worden overschreven met ``25``.

Volgende code toont hoe je bijvoorbeeld eerst de vorige waarde kunt bewaren en dan overschrijven:

```csharp
int temperatuurGisteren= 20;
//Doe vanalles
//...
//1 dag later
int temperatuurEerGisteren= temperatuurGisteren; //Vorige temperatuur in eergisteren bewaren
temperatuurGisteren = 25; //temperatuur nu overschrijven
```
We hebben dus aan het einde van het programma zowel de temperatuur van eergisteren ``20`` als die van vandaag ``25``.