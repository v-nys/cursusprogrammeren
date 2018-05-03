# Generieke methoden
Vaak schrijf je methoden die hetzelfde doen, maar waarvan enkel het type van de parameters en/of het returntype verschilt. Stel dat je een methode hebt die de elementen in een array onder mekaar toont. Je wil dit werkende hebben voor arays van ints, string, etc. Zonder generics moeten we dan per type een methode schrijven:

```csharp
public static void ToonArray(int[] array)
{
    foreach (var i in array)
    {
        Console.WriteLine(i);
    }
}
 
public static void ToonArray(string[] array)
{
    foreach (var i in array)
    {
        Console.WriteLine(i);
    }
}
```
Dankzij generics kunnen we nu het deel dat *generiek* moet zijn aanduiden (in dit geval met ``T``) en onze methode eenmalig definiëren:

```csharp
public static void ToonArray<T>(T[] array)
{
    foreach (T i in array)
    {
        Console.WriteLine(i);
    }
}
```