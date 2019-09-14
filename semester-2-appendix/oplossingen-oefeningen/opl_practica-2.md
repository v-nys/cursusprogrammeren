# H16 - Interfaces

```csharp
class Rechthoek: IComparable
{
    //Alle vorige zaken
    //...

    public int CompareTo(object obj)
    {
        Rechthoek temp = (Rechthoek)obj;
        if (temp.Breedte * temp.Lengte > Breedte * Lengte)
            return -1;
        else if (temp.Breedte * temp.Lengte < Breedte * Lengte)
            return 1;
        return 0;
    }
}
```

