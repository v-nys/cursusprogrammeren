## BMI Berekenaar
```csharp
Console.WriteLine("Geef je gewicht in kg");
double gewicht = Convert.ToDouble(Console.ReadLine());
Console.WriteLine("Geef je lengte in cm");
double lengte = Convert.ToDouble(Console.ReadLine())/100;

double bmi = gewicht / Math.Pow(lengte, 2);

Console.WriteLine($"Je BMI is {Math.Round(bmi,2)}");
```