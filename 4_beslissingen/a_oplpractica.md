
![](../assets/movie.png)

* [Bespreking BMI met if](https://ap.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=8d5602e2-ef82-486c-ba60-a981009b3a61)
* [Bespreking Schoenverkoper](https://ap.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=8ccac527-2386-4393-b9bb-a981009c71a1)
* [Bespreking Ohmberekenaar](https://ap.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=3d9dcd19-a130-4287-8ef2-a981009dc942)
* [Bespreking Orakeltje van delphi, part Deux](https://ap.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=d0ff5c46-9839-483f-97dd-a98100a28b9d)
* [Bespreking Kleurcode weerstand naar Ohm](https://ap.cloud.panopto.eu/Panopto/Pages/Viewer.aspx?id=a272f856-78cd-44a6-afbd-a981009f7253)


# Code

## BMI met if

Voeg volgende code toe aan het bestaande BMI programma:
```csharp
if(bmi<18.5)
{
    Console.ForegroundColor = ConsoleColor.Red;
    Console.WriteLine("Ondergewicht");
}
else if(bmi<24.9)
{
    Console.ForegroundColor = ConsoleColor.Green;
    Console.WriteLine("Normaal gewicht");
}
else if (bmi < 29.9)
{
    Console.ForegroundColor = ConsoleColor.DarkYellow;
    Console.WriteLine("Overgewicht");
}
else if (bmi < 39.9)
{
    Console.ForegroundColor = ConsoleColor.Red;
    Console.WriteLine("Zwaarlijvigheid");
}
else
{
    Console.ForegroundColor = ConsoleColor.Magenta;
    Console.WriteLine("Ernstige zwaarlijvigheid");
}
            ```