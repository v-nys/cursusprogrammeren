# ASCII Art

```csharp
            string myname = @"▄▄▄█████▓ ██▓ ███▄ ▄███▓   ▓█████▄  ▄▄▄       ███▄ ▄███▓  ██████ 
▓  ██▒ ▓▒▓██▒▓██▒▀█▀ ██▒   ▒██▀ ██▌▒████▄    ▓██▒▀█▀ ██▒▒██    ▒ 
▒ ▓██░ ▒░▒██▒▓██    ▓██░   ░██   █▌▒██  ▀█▄  ▓██    ▓██░░ ▓██▄   
░ ▓██▓ ░ ░██░▒██    ▒██    ░▓█▄   ▌░██▄▄▄▄██ ▒██    ▒██   ▒   ██▒
  ▒██▒ ░ ░██░▒██▒   ░██▒   ░▒████▓  ▓█   ▓██▒▒██▒   ░██▒▒██████▒▒
  ▒ ░░   ░▓  ░ ▒░   ░  ░    ▒▒▓  ▒  ▒▒   ▓▒█░░ ▒░   ░  ░▒ ▒▓▒ ▒ ░
    ░     ▒ ░░  ░      ░    ░ ▒  ▒   ▒   ▒▒ ░░  ░      ░░ ░▒  ░ ░
  ░       ▒ ░░      ░       ░ ░  ░   ░   ▒   ░      ░   ░  ░  ░  
          ░         ░         ░          ░  ░       ░         ░  
                            ░                                    ";
            Console.WriteLine(myname);
```

# ASCI Art & Colors

```csharp

Console.Write("▄▄▄█████▓ ██▓ ███▄ ▄███▓   ");
Console.ForegroundColor = ConsoleColor.Red; 
Console.Write("▓█████▄"); 
Console.ResetColor(); 
Console.Write("  ▄▄▄       ███▄ ▄███▓  ██████ \n");
Console.Write("▓  ██▒ ▓▒▓██▒▓██▒▀█▀ ██▒   "); 
Console.ForegroundColor = ConsoleColor.Red; 
Console.Write("▒██▀ ██▌"); Console.ResetColor(); 
Console.Write("▒████▄    ▓██▒▀█▀ ██▒▒██    ▒ \n");
Console.Write("▒ ▓██░ ▒░▒██▒▓██    ▓██░   "); 
Console.ForegroundColor = ConsoleColor.Red; 
Console.Write("░██   █▌"); Console.ResetColor(); 
Console.Write("▒██  ▀█▄  ▓██    ▓██░░ ▓██▄   \n");
Console.Write("░ ▓██▓ ░ ░██░▒██    ▒██    "); 
Console.ForegroundColor = ConsoleColor.Red; 
Console.Write("░▓█▄   ▌"); Console.ResetColor(); 
Console.Write("░██▄▄▄▄██ ▒██    ▒██   ▒   ██▒\n");
Console.Write("  ▒██▒ ░ ░██░▒██▒   ░██▒   "); 
Console.ForegroundColor = ConsoleColor.Red; Console.Write("░▒████▓ "); 
Console.ResetColor(); Console.Write(" ▓█   ▓██▒▒██▒   ░██▒▒██████▒▒\n");
string blood = @"  ▒ ░░   ░▓  ░ ▒░   ░  ░    ▒▒▓  ▒  ▒▒   ▓▒█░░ ▒░   ░  ░▒ ▒▓▒ ▒ ░
░     ▒ ░░  ░      ░    ░ ▒  ▒   ▒   ▒▒ ░░  ░      ░░ ░▒  ░ ░
░       ▒ ░░      ░       ░ ░  ░   ░   ▒   ░      ░   ░  ░  ░  
░         ░         ░          ░  ░       ░         ░  
                ░ ";
Console.WriteLine(blood);
```