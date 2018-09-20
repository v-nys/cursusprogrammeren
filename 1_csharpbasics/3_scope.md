# Scope van variabelen

De locatie waar je een variabele aanmaakt bepaald de **scope**, oftewel de zichtbaarheid, van de variabele.
Eenvoudig gezegd zullen steeds de omliggende accolades de scope van de variabele bevatten. Indien je de variabele dus buiten die accolades nodig hebt dan heb je een probleem: de variabele is enkel bereikbaar binnen de accolades vanaf het punt in de code waarin het werd aangemaakt.

```csharp
{
    int getal =0 ;  //Start scope getal
} // einde scope getal
```

>> Scope van variabelen is soms wat verwarrend. Hopelijk kan volgende kennis je helpen:[Kennisclip "Scope van variabelen](https://ap.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=20538981-ceaf-4129-a54a-a91100c81b2f).


# Variabelen met zelfde naam
Zolang je in de scope van een variabele bent kan je geen nieuwe variabele met dezelfde naam aanmaken:

Volgende code is dus niet toegestaan:
```csharp
{
    int getal=0;
    {
        int getal =5; //Deze lijn is niet toegestaan
    }

}
```
Je krijgt de error:
`` A local variable named 'getal' cannot be declared in this scope because it would give a different meaning to 'getal', which is already used in a 'parent or current' scope to denote something else`` 

Enkel de tweede variabele een andere naam geven is toegestaan in voorgaande geval.

Dit is wel geldig, daar de scope van de eerste variabele afgesloten wordt door de accolades:
```csharp
{
    int getal =0 ;
    //....
}
//Verder in code
{
    int getal= 5;
}
```

``` 