# Layout van code
(grammatica)
# Keywords
C# bestaat zoals gezegd uit enkel grammaticale regels. Grammatica zonder vocabulair is nutteloos. Er ijn binnen C# dan ook 80 woorden, zogenaamde **keywords** gereserveerd die de woordenschat voorstellen.
In dze cursus zullen we stelselmatig deze keywords leren kennen en gebruiken op een correcte manier om zo werkende code te maken.

Deze keywords zijn:
|   |     |     |   |
|----|----|-----|----|
|*abstract*	|*as*	|*base*	|**bool**|
|**break**|	**byte**|	**case**|	catch|
|**char**|	checked|	*class*|	**const**|
|continue|	**decimal**|	*default*	|delegate|
|**do**|	**double**|	**else**|	**enum**|
|event|	explicit|	extern|	**false**|
|finally|	fixed|	**float**|	**for**|
|*foreach*|	goto|	**if**|	implicit|
|*in*|	**int**|	*interface*|	internal|
|*is*|	lock|	**long**|	**namespace**|
|*new*|	*null*|	*object*|	*operator*|
|**out**|	*override*|	params|	*private*|
|*protected*|	*public*|	readonly|	**ref**|
|**return**|	**sbyte**|	*sealed*|	**short**|
|sizeof|	stackalloc|	*static*|	**string**|
|*struct*|	**switch**|	*this*|	throw|
|**true**|	try|	typeof|	**uint**|
|**ulong**|	unchecked|	unsafe|	**ushort**|
|using	|using static|	*virtual*|	**void**|
|volatile	|**while**| |

> De keywords in vet zijn keywords die we dit semester zullen kennen. Die in cursief in het tweede semester.

# Identifiers en naamgeving
De code die we gaan schrijven moet voldoen aan een hoop regels. Wanneer we in onze code zelf namen (**identifiers**) moeten geven aan variabelen (en later ook methoden, objecten, etc) dan moeten we een aantal regels volgen:

* Hoofdlettergevoelig: de identifiers ``tim`` en ``Tim`` zijn verschillend. Je mag dus perfect twee verschillende variabelen aanmaken met deze name. 
* Geen keywords: identifiers mogen geen gereserveerd C# keyword zijn. De keywords van hierboven mogen dus niet. Varianten wel: denk maar aan ``goTO`` (``goto`` is een gereserveerd keyword, maar dankzij de hoofdlettergevoeligregel is dit dus toegelaten) en ``INT`` (tegenover keyword ``int``)
* Eerste karakter-regel: het eerste karakter van de identifier mag enkel zijn:
    * kleine of grote letter
    * liggend streepje ( ``_``)
* Alle andere karakters: de overige karakters moeten mogen enkel zijn:
    * kleine of groter| letter
    * liggend streepje
    * een cijfer (``1`` tot en met ``9`` en ``0``)
* Lengte: een legale identifier mag zo lang zijn als je wenst, maar hou het best leesbaar

# Commentaar
Soms wil je misschien extra commentaar bij je code zetten. Als je dat gewoon zou doen (bv ``Dit deel zal alles verwijderen``) dan zal je compiler niet begrijpen wat die zin doet. Hij verwacht namelijk C# syntax en niet een Nederlandstalige zin. Om dit op te lossen kan je in je code op twee manieren aangeven dat een stuk tekst gewoon commentaar is en mag genegeerd worden door de compiler:

## Enkele lijn commentaar  met //
Eén lijn commentaar geef je aan door de lijn te starten met twee voorwaartse slashes ``//``. Uiteraard mag je ook meerdere lijnen op deze manier in commentaar zetten. Zo wordt dit ook vaak gebruik om tijdelijk een stuk code "uit te schakelen". Ook mogen we commenaar *achter* een stuk C# code plaatsen (zie onderaan voorbeeld)
```csharp
//De start van het programma
int getal=3;
//Nu gaan we rekenen
int result = getal * 5;
// result= 5* 4;
Console.WriteLine(result); //We tonen resultaat op scherm
```
## Blok commentaar met /* en */
We kunnen een stuk tekst als commentaar aangeven door voor de tekst ``/*`` te plaatsen en achteraan de blok tekst ``*/``. Een voorbeeld:
```csharp
/*
    Veel commentaar.
    Een heel verhaal
    Mooi he.
    Is dit een haiku?
*/
int leeftijd= 0;
leeftijd++;
```