# DateTime 

## Klokje

```csharp
while (true)
{
    Console.WriteLine(DateTime.Now.ToString("HH:mm:ss"));
    System.Threading.Thread.Sleep(1000);
    Console.Clear();
}
```

## Verjaardag

```csharp
Console.WriteLine("Geef je verjaardag (formaat: d/m . Bv 18/3)");
DateTime verj = DateTime.Parse(Console.ReadLine());


if (verj < DateTime.Now)
    verj = verj.AddYears(1);

TimeSpan dagenover = verj - DateTime.Now;

Console.WriteLine($"Je verjaart over {dagenover.Days} dagen");
```

