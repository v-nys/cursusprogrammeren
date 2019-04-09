# Todo's

Deze cursus is nog volop in opbouw. Hier de lijst van de belangrijkste aspecten die nog moeten gebeuren:

* Titels in hoofding laten overeenstemmen met titels in inhoudsopgave
* Hoofdstuk debugging schrijven
* Zombie flowchart (ik heb geen flauw idee meer wat ik hier in godsnaam mee bedoel)
* Uitleg kleur veranderen uit oefening halen en naar "theorie" verplaatsen + Console.ResetColor() toevoegen
* Git
* Array opwarmers: [TODO](https://codeforwin.org/2015/07/array-programming-exercises-and.html)
* Generic methods: voorbeeld van rekenmachine methoden


* Bitwise operators
(bron:C#7 Quick Syntax Reference)
The bitwise operators can manipulate individual bits inside an integer. For example, the bitwise and (&) operator makes the resulting bit 1 if the corresponding bits on both sides of the operator are set.
int x = 5 & 4;  // and (0b101 & 0b100 = 0b100 = 4)
    x = 5 | 4;  // or (0b101 | 0b100 = 0b101 = 5)
    x = 5 ^ 4;  // xor (0b101 ^ 0b100 = 0b001 = 1)
    x = 4 << 1; // left shift (0b100 << 1 = 0b1000 = 8)
    x = 4 >> 1; // right shift (0b100 >> 1 = 0b10 = 2)
    x = ~4;     // invert (~0b00000100 = 0b11111011 = -5)
These bitwise operators have shorthand assignment operators, just like the arithmetic operators.
int x=5; x &= 4;  // and (0b101 & 0b100 = 0b100 = 4)
    x=5; x |= 4;  // or (0b101 | 0b100 = 0b101 = 5)
    x=5; x ^= 4;  // xor (0b101 ^ 0b100 = 0b001 = 1)
    x=5; x <<= 1; // left shift (0b101 << 1 = 0b1010 = 10)
    x=5; x >>= 1; // right shift (0b101 >> 1 = 0b10 = 2)