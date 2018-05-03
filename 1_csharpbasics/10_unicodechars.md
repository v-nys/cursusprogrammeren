# Vreemde tekens in console tonen

Niets is zo leuk als de vreemdste tekens op het scherm tonen. In oude console-games werden deze tekens vaak gebruikt om ‘complexe’ tekeningen op het scherm te tonen:

![](/assets/0_intro/kerosenethunder_mockup.png)

## Unicode karakters tonen

Zonder een uitleg te geven over het verschil tussen ASCII en Unicode is het vooral belangrijk te weten dat je best met Unicode werkt.

1. Zoek het teken\(s\) dat je nodig hebt in een Unicode-tabel \([Deze is handig](https://unicode-table.com/en/)\)
2. Plaats bovenaan je Main: `Console.OutputEncoding = System.Text.Encoding.UTF8;`
3. Je kan nu op 2 manieren dit teken in console plaatsen

### Manier 1: copy/paste

Kopieer het karakter zelf en plaats het in je code waar je het nodig hebt, bijvoorbeeld:

```rust
Console.WriteLine("˧");
```

### Manier 2: hexadecimale code casten naar char

Noteer de hexadecimale code van het karakter dat in de tabel staat.

![](/assets/0_intro/letter.jpg)

In dit geval is de code 0x02e7.

Om dit teken te tonen schrijf je dan:

```csharp
char blokje = (char)0x02e7;
Console.WriteLine(blokje);
```

In C\# schrijf je hexadecimale getallen als volgt als je ze rechstreeks in een string wilt plaatsen: \u02e7

Wil je dus bovenstaande teken schrijven dan kan dan ook als volgt:

```csharp
Console.WriteLine("\u02e7");
```





