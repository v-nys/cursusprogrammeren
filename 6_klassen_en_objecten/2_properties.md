# Properies
Private variabelen van een klasse zijn enkel bereikbaar binnenin de klasse. Soms wil je echter een gecontroleerde toegang van buitenaf tot deze private variabelen voorzien. Klassen voorzien dit door zogenaamde Get (lees/read) en Set (schrijf/write)-methoden. Deze methoden, die je zelf schrijft, zorgen ervoor dat je kan controleren wat er naar de private data wordt geschreven (Set) en welke informatie er naar buiten wordt gegeven (Get).

Het is een algemene afspraak om deze methoden met get of set vooraf te laten gaan zodat jijzelf, of een medeprogrammeur, duidelijk weet wat de methode doet. Als je dus een private variabele interestRate hebt dan zouden de respectievelijke getter  en setter getInterestRate en setInterestRate zijn.

Waarom niet gewoon de private variabele publiek maken? Stel dat je als bank hebt bepaald dat de interest nooit negatief kan zijn (het zou een slechte bank zijn) en nooit hoger dan 5% kan zijn. Met een publieke interestRate zou je dus telkens je deze wil aanpassen BUITEN de klasse moeten controleren of dit wel mag. Wat als de huidige programmeur dit niet weet? Hij zal gewoon de interestRate op -4 bijvoorbeeld instellen en rustig voortwerken (bijvoorbeeld een typefout).

Door met de setMethode te werken kan je in de methode eerst controleren of de ingegeven waarde wel kan. De code zou er bijvoorbeeld als volgt kunnen uitzien:
```java
            //In BankAccount-klasse
            private interestRate;
            public void setInterest(int waarde)
            {
                if(waarde >=0 && waarde <=5)
                    interestRate = waarde;
                else
                {
                    Console.WriteLine("Error occured: rate should be between 0 and 5");
                }
            }

            //Elders, bv in main
            
            timsAccount.setInterest(-4);
```
