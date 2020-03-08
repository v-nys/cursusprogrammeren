---
marp: true
---
<style>
section {
  padding: 100px;
  background-image: url('background.png');
  background-size: cover;
}
h1 {
    color: rgb(153,35,36)
}
</style>

# OO Programmeren
<style scoped>
section {
  padding-left: 400px;
  color: white;
}
h1 {
  font-size: 60px;
  color: white;
}
a {
  color: white ;
}
h3 {
  font-size: 40px;
  color: white
}
</style>
![bg](background_cover.png)
### Geavanceerde klassen en objecten

https://apwt.gitbook.io/cursus-pro-oo

---

# Werking new operator

```c#
Student FrankVermeulen = new Student();
```

De new operator doet 2 dingen:
- Het maakt een object aan in het geheugen.
- Het roept de **constructor** van het object aan voor  e
ventuele extra initialisatie
---

# Constructor
- Bevat code die uitgevoerd moet worden bij instantie aanmaken.
- Speciale methode die wordt aangeroepen bij het aanmaken van een object. 
    - Daarom ronde haakjes bij new Student()



---

# Soorten constructors

Als programmeur van eigen klassen zijn er 3 opties voor je:

- Je gebruikt geen constructors
- Je hebt enkel de default constructor nodig. 
    - Je beschrijft zelf wat er moet gebeuren
- Gebruik van meerdere overloaded constructoren
    - bv: ```new Student(24, "Jos")```

---

# Gratis default constructor: Wel of niet?

- Je krijgt standaard voor elke klasse een lege default constructor
    - Deze is onzichtbaar en kan niet aangepast worden.
- Schrijf je zelf een constructor?
    - Je moet zelf ook de default constructor schrijven.

---
# Gratis default constructor: Wel of niet?

```
public class Student
    {
        public Student(int age)
        {
            ...
        }
    }
```
werkt de volgende code?

```c#
    Student student = new Student();
```

---

# Default constructor

- De default constructor is een constructor die geen extra parameters aanvaardt. 
- Een constructor bestaat altijd uit volgende vorm:
    - public **(enkel in deze cursus, kan ook anders zijn)**
    - Heeft geen returntype, ook niet void.
    - Heeft als naam de naam van de klasse zelf.

    ```
    class Student
    {
        public Student()
        {
            
        }
    }
    ```
