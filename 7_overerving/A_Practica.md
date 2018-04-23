# Book
## Deel 1
Maak een klasse ``Book``  en gebruik auto-properties voor de velden:
* ISBN (int)
* Title (string)
* Author (string)
Maak voorts een property voor Price, met bijhorende private price field.
* Price (double)
Maak een childklasse die van Book overerft genaamd ‘TextBook. Een textbook heeft één extra field:
* GradeLevel (int)
Maak een childklasse die van Book overerft genaamd ‘CoffeeTableBook’. Deze klasse heeft geen extra velden.

Voorts kunnen boeken "opgeteld" worden om als omnibus uitgebracht te worden. De titel wordt dan "Omnibus van [X]". waarbij X de Authors bevat, gescheiden met een komma. De prijs van een Omnibus is steeds de som van beide boeken gedeeld door 2.

In beide childklassen, override de Price-setter zodat 
a)	Bij Textbook de prijs enkel tu ssen 20 en 80 kan liggen
b)	Bij CoffeeTableBooks de prijs enkel tussen 35 en 100 kan liggen

## Deel 2
* Zorg ervoor dat boeken de ToString overriden zodat je boekobjecten eenvoudig via Console.WriteLine(myBoek) hun info op het scherm tonen. Ze tonen deze info als volgt: "Title - Auteur (ISBN) _ Price"  (bv The Shining - Stephen King (05848152) _ 50)
* Zorg ervoor dat de equals methode werkt op alle boeken. Boeken zijn gelijk indien ze hetzelfde ISBN nummer hebben

**Toon de werking aan van je 3 klassen:**
Maak boeken aan van de 3 klassen, toon dat de prijs niet altijd zomaar ingesteld kan worden en toon aan dat je Equals –methode werkt (ook wanneer je bijvoorbeeld een Book en TextBook wil vergelijken).

# Geometric figures

Maak een abstracte klasse ``GeometricFigure``. Iedere figuur heeft een hoogte, breedte en oppervlakte. Maak properties voor deze 3 fields. De oppervlakte is read-only want deze wordt berekend gebaseerd op de hoogte en breedte . 

Voorzie een abstracte methode “BerekenOppervlakte” die een int teruggeeft.
Maak 3 klassen:
* Rechthoek: erft over van GeometricFigure. Oppervlakte is gedefinieerd als breedte * hoogte.
* Vierkant: erft over van Rechthoek. Voorzie een constructor die lengte en breedte als parameter aanvaard: deze moeten gelijk zijn, indien niet zet je deze tijdens de constructie gelijk. Voorzie een 2e constructor die één parameter aanvaardt dat dan geldt als zowel de lengte als breedte. Deze klasse gebruikt de methode BerekenOppervlakte van de Rechthoek-klasse.
* Driehoek: erft over van GeometricFigure. Oppervlakte is gedefinieerd als breedte*hoogte/2.

Maak een applicatie waarin je de werking van deze klassen aantoont
