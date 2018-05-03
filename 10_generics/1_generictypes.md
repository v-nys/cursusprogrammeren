# Generic types
In het volgende codevoorbeeld is te zien hoe een eigen generic struct in C# gedefinieerd en gebruikt kan worden. Merk het gebruik van de aanduiding T , deze geeft aan dat hier een type (zoals int, double, Student,etc.) zal worden ingevuld tijdens het compileren.

## <T>
De typeparameter T wordt pas voor de specifieke instantie van de generieke klass of type ingevuld bij het compileren. Hierdoor kan de compiler per instantie controleren of alle parameters en variabelen die in samenhang met het generieke type gebruikt worden wel kloppen.

De afspraak is om .NET een T te gebruiken indien het type nog dient bepaald te worden (dit is niet verplicht).
[Meer info](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/generics/introduction-to-generics)

## Voorbeeld generic type
We wensen een struct te maken die de locatie in X,Y,Z richting kan bewaren. We willen echter zowel floats, double als ints gebruiken:



```csharp
struct Location<T>
{
    public T X;
    public T Y;
    public T Z;
}
```
We kunnen deze struct nu als volgt gebruiken:

```csharp
static void Main(string[] args)
{
    Location<int> plaats;
    plaats.X = 34;
    plaats.Y = 22;
    plaats.Z = 56;
 
    Location<double> plaats2;
    plaats2.X = 34.5;
    plaats2.Y = 22.2;
    plaats2.Z = 56.7;
 
    Location<string> plaats3;
    plaats3.X = "naast de kerk";
    plaats3.X = "links van de bakker";
    plaats3.Z = "onder het hotel";
 
}
```