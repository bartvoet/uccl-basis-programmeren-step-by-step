# Synthese-oefening

## Inleiding

Op dit moment van de cursus zijn we toegekomen aan het werken met:

* **Klassen** en **objecten**
* **Collecties** en arrays

### Step-by-step

Deze **nieuwe elementen** laten ons toe om **grotere programma's** te maken (met veel meer functionaliteit).  

Om zulke **grotere programma's** - die in het beroepsveld worden gebouwd - schrijven vereist echter een zekere **discipline** en **aanpak** nodig met onder andere:

* **Step-by-step**-aanpak
* **Opbouw** en **design**
* Gebruik van **tooling** om je **code-base** te **beheersen**

### Mini-projectje

We bouwen hier voor een **éénvoudige commandline** applicatie - een **Winkelmandje** - op basis van een **event-loop**
die we **stelselmatig** **uitbreiden**.

Dit hoofdstukje is dus **enerzijds** een **herhalings**-oefening maken rond het werken met **klassen en objecten** gecombineerd met het gebruik van **lijsten**.  

Naast het herhalen van het OO-principe willen we hier ook aantonen dat eender welk wat grotere applicatie **step-by-step** moet worden opgebouwd.

### Step-by-step met Git

Dit doe je door de volgende stappen constant te herhalen:

* **Coderen:** Een heel **kleine subset** van de **applicatie** opbouwen/toevoegen
* **Testen:**
  * Werkt je nieuwe functionaliteit?  
    Testen van je functie/code die je hebt gebouwd, ook soms **unit-testing**
  * Werkt de functionaliteit die je hebt toe nog altijd even goed?  
    Dit noemen ze ook **testen op regressie**
* **Revisioneren**
  * Een maal getest **slagen** we onze **wijziging** (step) **op**
  * We voegen een **duidelijke** **commentaar** toe
* ...en we starten opnieuw...

De laatste actie - **revisioneren** - is iets wat we nu voor de **eerste maal** introduceren.  
Het komt er op neer van (met behulp van een tool) de evolutie en verschillende versies bij te houden, waardoor dat je:

* Een **historiek** kan behouden van de wijzigingen van je code
* Kan **terugkoppelen** naar een **vroegere** specifieke **revisie**
* Code **delen** tussen **verschillende** **personen** (en zelfs organisaties)
* ...

De tool die we hiervoor gebruiken is **Git**, en quasi **standaard** op **gebied** van **code-beheer**.  

## Opzetten van het project

In dit voorbeeld gaan we Git gebruiken om de **wijzigingen** van onze **applicatie** bij te houden.  

### Met Visual Studio (Windows)

We starten met:

* We **maken** een **Visual Studio-project** aan (we noemen deze **basket**)
* **Navigeren** (in de command-line-prompt) naar deze folder
* We voeren in het commando **"git init"** uit binnen deze folder

#### Stap 1: Aanmaak project

We starten met een nieuw project aan:

![](new_console_project_1.png)

We noemen we dit **PRB.ShoppingBasket.Bart** waar je **Bart** **vervangt** door je **eigen naam**...

![](new_console_project_2.png)

Tenslotte maak je het project aan met de optie "Do not use top-level statements"

![](new_console_project_3.png)

Als resultaat zou je een project moeten krijgen zoals hieronder...

![](new_console_project_4.png)

#### Stap 2: Git toevoegen aan dit project

We selecteren in het menu Git/Create Repository

![](git_new_repo_1.png)

Binnen dat menu kiezen we:

* Local Only (linkerkant)
* Optioneel mag je ook nog "Add README.md" toevoegen (komen we later nog op terug)

![](git_new_repo_2.png)

#### Resultaat

Wat is er nu gebeurd?  
Op in het menu "Git/Open in File Explorer", dit opent een file explorer met je project.  

> Zie wel dat je in je file explorer aanduidt dat je "hidden files" kan zien

Binnen deze folder zie je dat er aantal nieuwe hidden files zijn:

* Een **.git-folder** deze bevat de database-objecten die je code-wijzigingen bijhoudt
* Een **.gitignore** die aanduidt welke files (extensies) er moeten genegeerd worden door git
* **.gitattributes** die configuratie bevat hoe om te gaan met files

![](git_new_repo_3.png)

Die .git-folder noemen we ook een **lokale** **git-repository**, dit is 

* Een soort van database waar je **code-wijzigingen** kan **bijhouden/traceren**
* Als een soort van **snapshot** (zoals je bijvoorbeeld een snapshot van een harde schijf zou nemen)
* Het stelt je in staat een historiek bij te houden en zelfs terug te keren naar een vorige **revisie**

De files die deze database omvatten bevinden zich in een verborgen folder **.git** .

#### Git Commits

Deze repository houdt dus code-wijzigingen bij, we noemen dit **commits**.  

Deze **commits** zijn eigenlijk **incrementele wijzigingen** aan je code die **samengebundeld** zitten in een **historiek** (fysiek zijn deze geregistreerd in de .git-folder die we eerder vermeldden).  
Vanuit Visual Studio kan je deze **history** van deze commits zien door in het *menu "Git/View Branch History"* te selecteren.

![](git_new_repo_4.png)

Hier zie je dat Visual Studio voor jou reeds 2 commits heeft aangemaakt.  
Hoe je **zelf** code-**wijzigingen** moeten **registreren** gaan we zo dadelijk in deze **oefening** in de praktijk brengen...

Je kan ook deze commits bekijken door hier met de rechtermuisknop op te klikken "View Commit Details" te selecteren

![](git_new_repo_4.png)

Vervolgens zie je dan de files die gewijzigd zijn met de inhoud daarbij gelinkt:

![](git_new_repo_4.png)

In dit geval zie je dat er 3 files zijn toegevoegd, de **A** opzij aan de files staat voor **APPEND**.  
Daarnaast zie je ook in **groen** de inhoud die is **toegevoegd** op de geselecteerde file

### Met VS Code (Linux, Mac, ...)

#### Stap 1: Aanmaken project

Start met het aanmaken van een folder met de naam *PRB.ShoppingBasket.Bart* aan waar je Bart **wijzigt** door je **eigen naam**.  

![](new_console_project_vs_0.png)

Vervolgens **open** je deze **folder** met **VS Code**.  
Hier gebruik je het command palette (ctrl+shift+p of command+shift+p voor Mac) om een **nieuw project** aan te maken.

![](new_console_project_vs_1.png)

Nadat u de opdracht hebt geselecteerd, moet u de **project template** kiezen. Kies **Console-app**.  
(gemakkelijkste is Console te typen om de selectie te versnellen)

![](new_console_project_vs_2.png)

Geef uw nieuwe project dezelfde naam als de solution (folder) "PRB.ShoppingBasket.Bart" waar je Bart
wijzigt door je eigen naam..

![](new_console_project_vs_3.png)

Selecteer vervolgens de locatie van nieuwe project (kies hier de default zijnde deze folder).

![](new_console_project_vs_4.png)

Alvorens je het project "aanmaakt" zorg er eerst voor dat je de top-level statements uitschakelt.   Selecteer "Show all template options." zoals je hieronder ziet:

![](new_console_project_vs_5.png)

Stel "Do not use top-level statements" in op "true".  

![](new_console_project_vs_6.png)

![](new_console_project_vs_7.png)

Selecteer tot slot "Create Project".  
Nadien is het project aangemaakt bestaande uit een solution met 1 project (beiden zelfde naam)

![](new_console_project_vs_8.png)

1 klasse is aangemaakt als gevolg, als je de top-level-statements hebt uitgeschakeld zal 
deze als volgt eruit zien:

~~~cs
namespace PRB.ShoppingBasket.Bart
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }
    }
}
~~~

#### Stap 2: git-repo aanmaken

Om met git te werken in VS Code heb je iets meer setup werk nodig vergeleken tot Visual Studio.  

Visual Studio maakt namelijk automatisch reeds een .gitignore file aan, dit is een file die er voor zorgt dat git niet-source-code elementen negeert (zoals de eigenlijke executable)

Je maakt hiervoor een nieuwe file aan in de root van je solution met de naam .gitignore.

![](git_new_repo_vs_1.png)

Vervolgens copieer je onderstaande inhoud in deze file

~~~.gitignore
[Dd]ebug/
[Rr]elease/
x64/
[Bb]in/
[Oo]bj/
~~~

![](git_new_repo_vs_2.png)

Vervolgens maken we een nieuwe git-repository aan door te navigeren naar het "Source Code"-gedeelte.  
Hier druk je op de knop "Create repository".

![](git_new_repo_vs_3.png)

Dit command zal een lokale git-repository aan:

~~~bash
bart@linuxcomputers:~/Demo/PRB.ShoppingBasket.Bart$ ls -la
total 28
drwxrwxr-x  5 bart bart 4096 nov 23 21:48 .
drwxrwxrwx 17 bart bart 4096 nov 23 20:44 ..
drwxrwxr-x  8 bart bart 4096 nov 23 21:49 .git
-rw-rw-r--  1 bart bart   42 nov 23 21:48 .gitignore
drwxrwxr-x  4 bart bart 4096 nov 23 21:47 PRB.ShoppingBasket.Bart
-rw-rw-r--  1 bart bart 1045 nov 23 21:00 PRB.ShoppingBasket.sln
drwxrwxr-x  2 bart bart 4096 nov 23 21:00 .vscode
bart@linuxcomputers:~/Demo/PRB.ShoppingBasket.Bart$ 
~~~

Die .git-folder noemen we ook een **lokale** **git-repository**, dit is 

* Een soort van database waar je **code-wijzigingen** kan **bijhouden/traceren**
* Als een soort van **snapshot** (zoals je bijvoorbeeld een snapshot van een harde schijf zou nemen)
* Het stelt je in staat een historiek bij te houden en zelfs terug te keren naar een vorige **revisie**

De files die deze database omvatten bevinden zich in een verborgen folder **.git**.  
In VS Code ga je dan onderstaande view zien met de files die klaar staan om te **committen**

![](git_new_repo_vs_4.png)

#### Git Repo en Commits

Deze repository houdt dus code-wijzigingen bij, we noemen dit **commits**.  

Deze **commits** zijn eigenlijk **incrementele wijzigingen** aan je code die **samengebundeld** zitten in een **historiek** (fysiek zijn deze geregistreerd in de .git-folder die we eerder vermeldden).  

Momenteel zijn er nog geen commits aanwezig, we gaan echter al onze 1ste commit aanmaken
om het initiele project te registreren.  
Om dit te doen moet je files aanduiden om te committen door op het plusje te klikken naast elke file die je wil toevoegen (in dit geval all files die je ziet)

![](git_new_repo_vs_5.png)

Vervolgens zal je zien dat al deze files zijn verhuisd naar een "Staging Area".  
Van de files die daar staan zullen de wijzigingen mee worden opgenomen in de commit:

![](git_new_repo_vs_6.png)

Vervolgens geeft je een comment in het tekstvenstertje "Setting up project" en druk je op de knop "Commit"

#### Git commits en Historiek

Na deze commit zal je - onderaan - zien dat er een 1ste commit is toegevoegd aan je historiek van de 

![](git_new_repo_vs_7.png)

Als je op deze commit klikt kan je dan ook zien welke files en wijzigingen zijn toegevoegd...

![](git_new_repo_vs_8.png)

In dit geval zie je dat er 3 files zijn toegevoegd, de **A** opzij aan de files staat voor **APPEND**.  

## Code schrijven

### Basket-item-class

Alvorens met git verder te gaan starten we met **code te schrijven**.  
Bedoeling is dat we een **applicatie** gaan maken die een **winkelmandje** (of **winkellijstje**) gaat beheren.

Zo'n winkelmandje bestaat uit verschillende **items** die je in dat **mandje** mag droppen.  
Laten we starten met er van uit te gaan dat zo'n **item** een **beschrijving** en een **prijs** bevat...

We hebben in het studenten-voorbeeld gezien hoe je zulke gestructureerde data kan **bijhouden/groeperen** in een **klasse**.

We starten met een file **BasketItem.cs** aan te maken en voorzien daarin een klasse **BasketItem** voorzien:

![](new_class.png)

In VS Code gebruik je het command palet, selecteer je "New File" zoals hieronder

![](vs_code_new_class.png)

De klasse zou er als volgt moeten uit zien:

~~~cs
namespace PRB.ShoppingBasket.Bart
{
    public class BasketItem
    {

    }
}
~~~

Deze zou je ook moeten zien in je explorer:

![](new_class_file.png)

Voorzie vervolgens in de klasse **2 properties**:

* Price
* Description

en **initialiseer** deze via een **constructor**, het resultaat zou er als
volgt moeten uitzien:

~~~cs
namespace PRB.ShoppingBasket.Bart
{
    public class BasketItem
    {
        public BasketItem(int price, string description)
        {
            Price = price;
            Description = description;
        }

        public int Price { get;private set; }

        public string Description { get;private set; }
    }
}
~~~

Bemerk ook dat we de **setter private** hebben gezet, dit doen we ter encapsulatie.  
We willen bijvoorbeeld dat logica gerelateerd aan het beheer in de BasketItem-klasse
zelf zit (en dat je die niet zo maar kan wijzigen)

Om zeker te zijn van correctheid passen we Program.cs aan om zeker te zijn dat deze geen code-fouten bevat, maw we **testen** bij elke **stap**.

~~~cs
using PRB.ShoppingBasket.Bart.Model;

namespace PRB.ShoppingBasket.Bart
{
    internal class Program
    {
        static void Main(string[] args)
        {
            BasketItem item = new BasketItem(10, "Patatten");
            Console.WriteLine($"Item {item.Description} met prijs {item.Price}");
        }
    }
}
~~~

Vanzelfsprekend doet deze nog **niet** erg **veel**, maar het is een 1ste stap...  
Eerst gaan we echter onze eerste **code-wijzigen registereren/revisioneren** in git.

#### Git: Je 1ste (echte) code-commit

We hebben ons **eerste stuk code** geschreven.  
De volgende stap is dat we deze files gaan toevoegen aan een **nieuwe commit**.

Als je nu in het menu "Git/Commit" selecteert zie je de wijzigingen die klaarstaan

![](first_commit_1.png)

**Merk** ook dat naast de **files** ook nog letters staan, deze tonen aan wat er met de file is gebeurd:

* **A** staat voor toevoegen (**A**ppend)
* **M** staat voor wijzigen (**M**odify)

##### Files naar staging-area

Voor dat je deze commit gaat maken moet je 1st nog de files selecteren die je aan deze commit wil
binden.  Als je dit doet ga je deze brengen naar een staging-omgeving (maw ze staan dan klaar om te committen).

Als je **"hoovert"** over het item zie je dat er een **+** verschijnt:

![](first_commit_2.png)

Als je daar op die **+ klikt** komt de specifiek file terecht in de staged area:

![](first_commit_3.png)

Doe dit vervolgens ook voor de andere file en dan zouden beide wijzigingen moeten klaarstaan:

![](first_commit_4.png)

##### Committen...

De volgende stap is nog een **boodschap** te **selecteren** die je wijzigingen documenteert.  
Het is extreem belangrijk dat je deze **boodschap** **duidelijk** (maar wel beknopt) houdt.

Hoe **duidelijker** deze is hoe **gemakkelijker achteraf** om te consulteren wat je wijziging waren.  
Je vult gewoon het tekstveldje met een duidelijk maar korte zin...

![](first_commit_5.png)

Vervolgens druk je op de button "Commit Staged" en is deze commit geregistreerd in je history.  
Om naar deze history te gaan kies je in het Git-menu "View Branch History" of klik je op de "View all commits"-link.

![](first_commit_6.png)

en krijg je een overzicht van de commits die zijn gemaakt met je laatste commit 1st in de rij

![](first_commit_7.png)

##### Stelselmatig verder werken en committen

Bedoeling nu is dat je dit proces stelselmatig verder werkt:

* **Kleine** maar **significante** wijziging maken
* Dit **testen** op 
  * **regressie** -> werkt je wijziging nog altijd, niets gebroken?
  * werkt de nieuwe **functionaliteit** die je hebt toegevoegd
* Een **commit** samenstellen met je **wijzigingen**

> Het testen gaat na een tijdje veel werk zien, we gaan hievoor later nog 
> de techniek van unit-testen zien die je in staat stelt je testen te automatiseren...

### Code schrijven: event-loop

We hebben nu echter **nog geen applicatie** daarvoor zijn er nog **2** belangrijke **elementen** nodig:

* Een **lijst** van BasketItem-objecten die kan worden bijgewerkt
* Een **event-loop** waar we de nodige acties implementeren

#### Lijst van BasketItem-objecten

De **eerste stap** is een **lijst** aan te maken als globale variable waarin we BasketItems kunnen toevoegen en bewerken.

~~~cs
using PRB.ShoppingBasket.Bart.Model;

namespace PRB.ShoppingBasket.Bart
{
    internal class Program
    {
        static void Main(string[] args)
        {
            List<BasketItem> items = new List<BasketItem>();
        }
    }
}
~~~

#### Event-loop (loop)

De applicatie moet natuurlijk nog wel iets doen, dus om deze lijst aan te vullen
zetten als **eerste stap** zetten we de **interactie met de gebruiker** op.  

Om met de gebruiker te praten voegen we:

* Een **oneindige lus** toe
* Waar we telkens **input** gaan vragen aan de gebruiker
* Als deze gebruiker antwoordt (**event**)
* Voeren we een **actie** uit 
* En geven we **feedback** aan de gebruiker

Zo'n loop is wat we noemen een **event-loop**, telkens als de gebruiker een ingave doet zal deze event-loop een reactie geven.

Een eerste versie van de loop...

~~~cs
using PRB.ShoppingBasket.Bart.Model;

namespace PRB.ShoppingBasket.Bart
{
    internal class Program
    {
        static void Main(string[] args)
        {
            List<BasketItem> items = new List<BasketItem>();

            while(true)
            {
                Console.Write("Geef een item-naam: ");
                string name = Console.ReadLine();

                Console.Write("Geef een prijs");
                int price = int.Parse(Console.ReadLine());

                items.Add(new BasketItem(price, name));
            }
        }
    }
}
~~~

Hier ontbreekt nog een stuk om van een event-loop te spreken maar we hebben reeds de basisstructuur
opgezet die 

#### Event-loop (menu)

Een **oneindige loop** is natuurlijk **niet voldoende**, de gebruiker moet een **menu** hebben (afgeprint).  
We printen hier het menu telkens af en vangen gebruikers-input op via de functie **input()**

> Voor het menu gebruiken we een **multiline string** die start en eindigt met 3 dubbele quotes

~~~cs
using PRB.ShoppingBasket.Bart.Model;

namespace PRB.ShoppingBasket.Bart
{
    internal class Program
    {
        static void Main(string[] args)
        {
            List<BasketItem> items = new List<BasketItem>();

            string menu = """
                            1> Voeg item toe
                            2> Print items af
                            3> Sluit af
                            """;

            while(true)
            {
                Console.WriteLine(menu);
                string menuChoice = Console.ReadLine();
                Console.WriteLine(menuChoice);
            }
        }
    }
}
~~~

De **user-input** wordt gevraagd en **opgevangen**, maar er is nog **meer nodig**...

##### En nog een commit...

Maak nu een commit waarin je deze code commit.  
Geen hierbij een duidelijke boodschap zoals bijvoorbeeld "Opzetten van event-loop met menu"

#### Event-loop (if-else)

We moeten er natuurlijk voor zorgen dat deze **user-input verwerkt** wordt.  
Hiervoor plaatsen we een **if/elif-clausule** voor elke **menu-optie**.

~~~cs
    while(true)
    {
        Console.WriteLine(menu);
        string menuChoice = Console.ReadLine();
        
        switch(menuChoice)
        {
            case("1"): Console.WriteLine("TODO: voeg item toe");break;
            case("2"): Console.WriteLine("TODO: print item toe");break;
            case("3"): Console.WriteLine("TODO: sluit de applicatie af");break;
            default: Console.WriteLine("Foutieve keuze");break;
        }
    }
~~~

Voorlopig printen we een **tijdelijke TODO-boodschap** waarmee we kunnen **testen** of onze event-loop correct werkt.   
We voeren even een **korte test** uit zoals hieronder...

~~~
1> Voeg item toe
2> Print items af
3> Sluit af
1
TODO: voeg item toe
1> Voeg item toe
2> Print items af
3> Sluit af
2
TODO: print item toe
1> Voeg item toe
2> Print items af
3> Sluit af
5
Foutieve keuze
1> Voeg item toe
2> Print items af
3> Sluit af
~~~

...en zien dat de boodschappen worden afgeprint overeenkomstig de keuzes.  
Het **basis-skelet** van onze **event-loop** lijkt **ok** te zijn.  

> **Belangrijk:**  
> Voer deze code uit met **Python 3**, met Python 2 zal deze code niet correct runnen.  
> Later in de cursus komen we nog terug op deze verschillen.

##### En nog een commit...

Een nieuwe fase van onze ontwikkeling is **ontwikkeld** en **getest**, we gaan nu deze **code-wijziging** toevoegen aan onze **git-repo**.

Als we de status opvragen geeft git aan dat er een nieuwe wijziging is.  

~~~
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   basket.py

no changes added to commit (use "git add" and/or "git commit -a")
~~~

Wij hebben deze **wijziging** echter **nog niet klaargezet** voor de commit.  
Hier voor gebruiken we opnieuw het commando **"git add"**

~~~
$ git add basket.py
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   basket.py
~~~

De status geeft nu aan dat deze kan **gecommit** worden.  
We doen dit opnieuw met een korte maar duidelijke boodschap.

~~~
$ git commit -m "Setup of basic event-loop and -menu"
[master ecc9bc7] Setup of basic event-loop and -menu
 1 file changed, 20 insertions(+), 1 deletion(-)
~~~

Merk op dat onze **git-historiek** nu ook **2** commits bevat

~~~
$ git log
commit ecc9bc7dea83661149a7c5bd9942f1b36c8d6e54
Author: Bart Voet <bart_voet@telenet.be>
Date:   Sun Jan 10 21:20:20 2021 +0100

    Setup of basic event-loop and -menu

commit 6e8de9336064b7c7b7ff1c5e3ebff40a068efb7b
Author: Bart Voet <bart_voet@telenet.be>
Date:   Sun Jan 10 19:43:15 2021 +0100

    Creating class BasketItem.py
~~~

> **Opdracht voor de student:**  
> Probeer nu even de **wijzigingen** te **bestuderen** van elke commit via git show <commit-id>  
> Normaal gezien is het voldoende van enkel de eerste 4/5 letter van je commit-id te typen.

### Code schrijven: programma/event-loop beëindigen

Tot nog toe moesten we ons eerste programma afsluiten met **ctrl+c**  
Het eerste event dat we al kunnen afwerken is **"3> Sluit af"** opdat we het programma op een elegante manier kunnen afwerken.

Hiervoor gebruiken we de **python-functie exit()** die er zal voor zorgen dat het programma wordt afgesloten.

~~~python
    switch(menuChoice)
    {
        case("1"): Console.WriteLine("TODO: voeg item toe");break;
        case("2"): Console.WriteLine("TODO: print item toe");break;
        case("3"): Console.WriteLine("Het programma wordt beeindigd"); return;
        default: Console.WriteLine("Foutieve keuze");break;
    }
~~~

~~~
1> Voeg item toe
2> Print items af
3> Sluit af
3
Het programma wordt beeindigd
~~~


#### git: diff en nog commit's

We gaan deze wijziging/progress ook **bewaren** in de git-repo.  
Alvorens dit te doen, gebruiken we het **"git diff"**-commando om te inspecteren wat we hebben gewijzigd tov de vorige commit.

~~~
$ git diff
diff --git a/basket.py b/basket.py
index fa85624..c923bc3 100644
--- a/basket.py
+++ b/basket.py
@@ -17,6 +17,7 @@ while True:
     elif menu_input == "2":
         print("TODO: Print item af")
     elif menu_input == "3":
-        print("TODO: Sluit de applicatie af")
+        print("Programma wordt beeindigd")
+        exit()
     else:
         print("Foutieve keuze")
\ No newline at end of file
~~~

Dit geeft een vergelijkbaar rapport zoals we dit eerder hebben gezien voor **"git show"**.  
Het toont ons dat tov de vorige commit:

* **1 lijn** is **verwijderd** (aangeduid met **-**)

~~~
-        print("TODO: Sluit de applicatie af")
~~~

* **2 lijnen** zijn **toegevoegd** (aangeduid met **+**)

~~~
+        print("Programma wordt beeindigd")
+        exit()
~~~

* Ook wordt er aangeduid **waar** in de code dat **deze wijzigingen** kunnen gevonden worden
    * de file basket.py
    * ergens vanaf op lijn 17

~~~
--- a/basket.py
+++ b/basket.py
@@ -17,6 +17,7 @@
~~~

We **voegen** deze **commit toe**...

~~~
$ git add basket.py 
$ git commit -m "Implementing exit-event"
[master a29a73a] Implementing exit-event
 1 file changed, 2 insertions(+), 1 deletion(-)
$ git log
commit a29a73a734df309ea2a221c778729c74d99d63a5
Author: Bart Voet <bart_voet@telenet.be>
Date:   Sun Jan 10 22:09:05 2021 +0100

    Implementing exit-event
:...skipping...
commit a29a73a734df309ea2a221c778729c74d99d63a5
Author: Bart Voet <bart_voet@telenet.be>
Date:   Sun Jan 10 22:09:05 2021 +0100

    Implementing exit-event

commit ecc9bc7dea83661149a7c5bd9942f1b36c8d6e54
Author: Bart Voet <bart_voet@telenet.be>
Date:   Sun Jan 10 21:20:20 2021 +0100

    Setup of basic event-loop and -menu

commit 6e8de9336064b7c7b7ff1c5e3ebff40a068efb7b
Author: Bart Voet <bart_voet@telenet.be>
Date:   Sun Jan 10 19:43:15 2021 +0100

    Creating class BasketItem.py
~~~

...en we zien dat de **git-historiek** zich langzaam maar zeker begint **op te bouwen**

### Code schrijven: Afdrukken van items

We hebben bij een vorige commit een **lijst** gemaakt die wordt gebruikt om de **items** bij te houden.  

In **deze wijziging/commit** gaan we deze **lijst afdrukken**, gezien we echter de invulling nog niet hebben we uitgewerkt maken we voorlopig een fake/hardcoded lijst aan:

> **Belangrijk:**  
> Het gebruik van deze fake data dient achteraf verwijderd te worden 
> maar het laat ons toe onze code-wijziging te testen.
> In een volgende les gaan we meer geavanceerde technieken zien om onze code te testen
> (en deze testen zelf te automatiseren)

~~~python
class BasketItem:
    description = ""
    itemPrice = 0

menu = """
1> Voeg item toe
2> Print items af
3> Sluit af
"""

items = []
# Temporary list/will be removed later on
an_item = BasketItem()
an_item.description = "Laptop"
an_item.itemPrice = 1000
items.append(an_item)

an_item = BasketItem()
an_item.description = "USB-stick"
an_item.itemPrice = 10
items.append(an_item)

while True:
    menu_input = input(menu)
    if menu_input == "1":
        print("TODO: Voeg item toe")
    elif menu_input == "2":
        for item in items:
            print(item.description, "voor prijs", item.itemPrice)
    elif menu_input == "3":
        print("Programma wordt beeindigd")
        exit()
    else:
        print("Foutieve keuze")
~~~

Onder **optie 2** voegen we vervolgens een **loop** toe die deze **items afdrukt**.  

~~~
$ python basket.py 

1> Voeg item toe
2> Print items af
3> Sluit af
2
Laptop voor prijs 1000
USB-stick voor prijs 10

1> Voeg item toe
2> Print items af
3> Sluit af
3
Programma wordt beeindigd
$
~~~

Als we deze testen zien we dat de **hardcoded lijst** wordt **afgedrukt**, dus onze test is uitgevoerd dus we kunnen **revisioneren**


#### git: ... volgende commit

We voegen onze **wijzigingen** toe aan de git repo met een commit:

~~~
$ git add basket.py
$ git commit -m "Printing the available items"
[master 07d49e9] Printing the available items
 1 file changed, 12 insertions(+), 1 deletion(-)
~~~ 

### Code schrijven: items toevoegen

Om er een **interactieve applicatie** van te maken moeten we **user-input** gebruiken om de het **winkelmandje** aan te vullen.  
We doen dit door **event 1** te **implementeren** door de 3 volgende taken te implementeren:

* Vraag **user-input** op (beschrijving en prijs)
* **Maak BasketItem-object** aan met input
* Voeg BasketItem-object toe aan **lijst**

> We verwijderen hierbij ook de eerder aangemaakte **hard-coded** lijst

~~~python
class BasketItem:
    description = ""
    itemPrice = 0

menu = """
1> Voeg item toe
2> Print items af
3> Sluit af
"""

items = []

while True:
    menu_input = input(menu)
    if menu_input == "1":
        # Request input from user
        description = input("Geef beschrijving: ")
        price = int(input("Geef prijs: "))
        # Create item
        item = BasketItem()
        item.description = description
        item.itemPrice = price
        # Append new item
        items.append(item)
    elif menu_input == "2":
        for item in items:
            print(item.description, "voor prijs", item.itemPrice)
    elif menu_input == "3":
        print("Programma wordt beeindigd")
        exit()
    else:
        print("Foutieve keuze")
~~~

Als we dit uittesten:

~~~
$ python basket.py 

1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef beschrijving: Laptop
Geef prijs: 1000

1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef beschrijving: Harde schijf
Geef prijs: 200

1> Voeg item toe
2> Print items af
3> Sluit af
2
Laptop voor prijs 1000
Harde schijf voor prijs 200

1> Voeg item toe
2> Print items af
3> Sluit af
~~~

De test is uitgevoerd:

* We kunnen meerdere items **toevoegen**
* En deze nog altijd **afprinten**

#### git: ... volgende commit

We **voegen** onze wijzigingen **toe** aan de **git** repo:

~~~
$ git add basket.py
$ git commit -m "Adding items to the basket"
[master 94df14f] Adding items to the basket
 1 file changed, 9 insertions(+), 11 deletions(-)
~~~ 

### Code schrijven: constructor toevoegen

We voegen een **refactoring/code-optimalisatie** toe, we maken een **constructor**.  
Zoals we eerder hebben gezien kunnen we deze **constructor** gebruiken om deze attributen **in 1 maal** volledig te initialiseren.

> Dit verkort het aantal lijnen in optie 1 gevoelig

~~~python
class BasketItem:
    def __init__(self, description, itemPrice):
        self.description = description
        self.itemPrice = itemPrice

menu = """
1> Voeg item toe
2> Print items af
3> Sluit af
"""

items = []

while True:
    menu_input = input(menu)
    if menu_input == "1":
        # Request input from user
        description = input("Geef beschrijving: ")
        price = int(input("Geef prijs: "))
        # Append new item
        items.append(BasketItem(description, price))
    elif menu_input == "2":
        for item in items:
            print(item.description, "voor prijs", item.itemPrice)
    elif menu_input == "3":
        print("Programma wordt beeindigd")
        exit()
    else:
        print("Foutieve keuze")
~~~

> De code wordt hierdoor gecondenseerd zonder aan leesbaarheid in te winnen.  

We voeren opnieuw dezelfde test uit die we bij de vorige commit hadden uitgevoerd en zien dat onze code nog altijd naar behoren werkt (geen regressie).


#### git: ...volgende commit

We kunnen dus opnieuw een  commit toevoegen hiervoor met een korte duidelijke boodschap:

~~~
$ git add basket.py
$ git commit -m "Provide constructor for BasketItem"
[master 5d7122b] Provide constructor for BasketItem
 1 file changed, 4 insertions(+), 8 deletions(-)
~~~

### Code schrijven: Voeg een attribuut quantity toe

In een winkelmandje dien je soms **meerdere items** van **hetzelfde product** bij te houden.  
Om dit op te lossen voegen we aan onze klasse BasketItem een **attribute quantity** toe

Hiervoor **voegen** we aan de **constructor** een **attribuut toe**...

> *Nota:*  
> Net zoals we eerder bij functies hebben gezien kan je attributen optioneel maken 
> door er een default waarde bij te plaatsen.  
> Als men dan deze waarde zou weglaten (bij aanroep van de constructor) krijgt dit attribuut
> deze default waarde

~~~python
class BasketItem:
    def __init__(self, description, itemPrice, quantity = 1):
        self.description = description
        self.itemPrice = itemPrice
        self.quantity = quantity
    
    def totalPrice(self):
        return self.itemPrice * self.quantity
~~~

... daarnaast voegen we een functie **totalPrice()** toe, hiermee bereken we de werkelijke prijs

Binnen de event-loop passen we dan de print aan zodat die niet de prijs van 1 item afdrukt maar de prijs van de totaal aantal items.

~~~python
class BasketItem:
    def __init__(self, description, itemPrice, quantity = 1):
        self.description = description
        self.itemPrice = itemPrice
        self.quantity = quantity
    
    def totalPrice(self):
        return self.itemPrice * self.quantity

menu = """
1> Voeg item toe
2> Print items af
3> Sluit af
"""

items = []

while True:
    menu_input = input(menu)
    if menu_input == "1":
        # Request input from user
        description = input("Geef beschrijving: ")
        price = int(input("Geef prijs: "))
        quantity = int(input("Geef hoeveelheid: "))
        # Append new item
        items.append(BasketItem(description, price, quantity))
    elif menu_input == "2":
        for item in items:
            print(item.quantity, "*", item.description, " = ", item.totalPrice())
    elif menu_input == "3":
        print("Programma wordt beeindigd")
        exit()
    else:
        print("Foutieve keuze")
~~~

Als we dit dan **uittesten** krijgen we volgende output

~~~
1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef beschrijving: Laptop
Geef prijs: 1000
Geef hoeveelheid: 2

1> Voeg item toe
2> Print items af
3> Sluit af
2
2 * Laptop  =  2000

1> Voeg item toe
2> Print items af
3> Sluit af
3
Programma wordt beeindigd
~~~

Test OK, we kunnen vervolgen met onze commit...

#### git: commit

~~~
$ git commit -m "Adding a quantity to BasketItem"
[master c4a19e5] Adding a quantity to BasketItem
1 file changed, 8 insertions(+), 3 deletions(-)
~~~

### Totaal van de items

Interessant om te weten als gebruiker is de **totaal waarde** van deze items.  
Hiervoor voegen we een loop toe binnen **event 2**

~~~python
class BasketItem:
    def __init__(self, description, itemPrice, quantity = 1):
        self.description = description
        self.itemPrice = itemPrice
        self.quantity = quantity
    
    def totalPrice(self):
        return self.itemPrice * self.quantity

menu = """
1> Voeg item toe
2> Print items af
3> Sluit af
"""

items = []

while True:
    menu_input = input(menu)
    if menu_input == "1":
        # Request input from user
        description = input("Geef beschrijving: ")
        price = int(input("Geef prijs: "))
        quantity = int(input("Geef hoeveelheid: "))
        # Append new item
        items.append(BasketItem(description, price, quantity))
    elif menu_input == "2":
        sumOfItems = 0
        for item in items:
            print(item.quantity, "*", item.description, " = ", item.totalPrice())
            sumOfItems = sumOfItems + item.totalPrice()
        print("Totale waarde:", sumOfItems)
    elif menu_input == "3":
        print("Programma wordt beeindigd")
        exit()
    else:
        print("Foutieve keuze")
~~~

~~~
1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef beschrijving: Laptop
Geef prijs: 1000
Geef hoeveelheid: 2

1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef beschrijving: Harde schijf
Geef prijs: 250
Geef hoeveelheid: 3

1> Voeg item toe
2> Print items af
3> Sluit af
2
2 * Laptop  =  2000
3 * Harde schijf = 750
Totaal: 2750

1> Voeg item toe
2> Print items af
3> Sluit af
3
Programma wordt beeindigd
~~~

De test is geslaagd...

#### git: volgend commit...

...We kunnen dit **committen**

~~~
$ git commit -m "Adding total-value"
[master 88f498e] Adding total-value
 1 file changed, 3 insertions(+)
~~~

### Aparte Basket-klasse bouwen

Een kleine **optimalisatie** is het isoleren van het beheer van verschillende items in een binnen een aparte klasse.  We noemen deze klasse **Basket**

Dit laat ons toe van de logica rond het beheer van items te isoleren op 1 plek (namelijk in de klasse Basket)
Dit zou ook interessant zijn voor de toekomst als we binnen een applicatie meerdere winkelmandjes will bijhouden (bijvoorbeeld voor verschillende gebruikers).

Deze klasse bevat:

* Een **lijst** met **items**
* Een functie om een **item toe te voegen**
* Een functie om de **totale prijs** te berekenen

~~~python
class BasketItem:
    def __init__(self, description, itemPrice, quantity = 1):
        self.description = description
        self.itemPrice = itemPrice
        self.quantity = quantity
    
    def totalPrice(self):
        return self.itemPrice * self.quantity

class Basket:
    items = []

    def addItem(self, item):
        self.items.append(item)

    def getItems(self):
        return self.items

    def totalValueOfItems(self):
        totalValue = 0
        for item in self.items:
            totalValue = totalValue + item.totalPrice()
        return totalValue

basket = Basket()

menu = """
1> Voeg item toe
2> Print items af
3> Sluit af
"""

while True:
    menu_input = input(menu)
    if menu_input == "1":
        # Request input from user
        description = input("Geef beschrijving: ")
        price = int(input("Geef prijs: "))
        quantity = int(input("Geef hoeveelheid: "))
        # Append new item
        basket.addItem(BasketItem(description, price, quantity))
    elif menu_input == "2":
        for item in basket.getItems():
            print(item.quantity, "*", item.description, " = ", item.totalPrice())
        print("Totale waarde:", basket.totalValueOfItems())
    elif menu_input == "3":
        print("Programma wordt beeindigd")
        exit()
    else:
        print("Foutieve keuze")
~~~

We **herhalen** de **test** van het voorgaande deel en zien dat de code nog altijd werkt (geen regressie)

~~~
...
1> Voeg item toe
2> Print items af
3> Sluit af
2
2 * Laptop  =  2000
3 * Harde schijf = 750
Totaal: 2750
...
~~~

#### git: committen maar...

~~~
git commit -m "Adding Basket-class to manage group of items"
[master 943f10f] Adding Basket-class to manage group of items
 1 file changed, 20 insertions(+), 7 deletions(-)
~~~

### Error-handling: Vermijden van negatieve ingaves

Tot nog toe hebben we geen controles uitgevoerd op negatieve waardes.  
We passen de volgende regels toe:

* Enkel een hoeveelheid toelaten > 0
* Enkel een prijs toelaten >= 0

We gaan deze controles toevoegen in de klasse Basket.  

Het idee is om vanuit de constructor een exceptie op te werpen om te vermijden dat er een item kan aangemaakt met de verkeerde data.

Om deze excepties op type te kunnen opvangen maken we 2 specifieke exceptie-klasses aan
 (1tje voor elke fout).  
Deze excepties worden dan opgevangen binnen de eventloop en een boodschap wordt afgedrukt bij fout.

~~~python
class InvalidQuantityException(Exception):
    pass

class InvalidItemPriceException(Exception):
    pass

class BasketItem:
    def __init__(self, description, itemPrice, quantity = 1):
        if quantity <= 0:
            raise InvalidQuantityException()

        if itemPrice < 0:
            raise InvalidQuantityException()
        
        self.description = description
        self.itemPrice = itemPrice
        self.quantity = quantity
    
    def totalPrice(self):
        return self.itemPrice * self.quantity

class Basket:
    items = []

    def addItem(self, item):
        self.items.append(item)

    def getItems(self):
        return self.items

    def totalValueOfItems(self):
        totalValue = 0
        for item in self.items:
            totalValue = totalValue + item.totalPrice()
        return totalValue

basket = Basket()

menu = """
1> Voeg item toe
2> Print items af
3> Sluit af
"""

while True:
    menu_input = input(menu)
    if menu_input == "1":
        try:
            # Request input from user
            description = input("Geef beschrijving: ")
            price = int(input("Geef prijs: "))
            quantity = int(input("Geef hoeveelheid: "))
            # Append new item
            basket.addItem(BasketItem(description, price, quantity))
        except InvalidQuantityException:
            print(quantity, "is geen geldige hoeveelheid")
        except InvalidItemPriceException:
            print(price, "is geen geldige prijs")
    elif menu_input == "2":
        for item in basket.getItems():
            print(item.quantity, "*", item.description, " = ", item.totalPrice())
        print("Totale waarde:", basket.totalValueOfItems())
    elif menu_input == "3":
        print("Programma wordt beeindigd")
        exit()
    else:
        print("Foutieve keuze")
~~~

~~~
...
1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef beschrijving: Laptop 
Geef prijs: -1000
Geef hoeveelheid: 10 
10 is geen geldige prijs

1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef beschrijving: Laptop
Geef prijs: 1000
Geef hoeveelheid: -10
-10 is geen geldige hoeveelheid
...
~~~

#### Git commit...

~~~
$ git commit -m "Exception handling, avoid negative values"
[master 8176859] Exception handling, avoid negative values
 1 file changed, 27 insertions(+), 6 deletions(-)
~~~

### Error-handling: Opvangen van niet int-getallen

Als we momenteel geen getal in voeren voor hoeveelheid of prijs zal de applicatie crashen.  
We zullen dit opvangen door ook ValueError-exceptie op te vangen binnen de event-loop.

~~~python
class InvalidQuantityException(Exception):
    def QuantityException():
        pass

class InvalidItemPriceException(Exception):
    def InvalidQuantityException():
        pass

class BasketItem:
    def __init__(self, description, itemPrice, quantity = 1):
        if quantity <= 0:
            raise InvalidQuantityException()

        if itemPrice < 0:
            raise InvalidQuantityException()
        
        self.description = description
        self.itemPrice = itemPrice
        self.quantity = quantity
    
    def totalPrice(self):
        return self.itemPrice * self.quantity

class Basket:
    items = []

    def addItem(self, item):
        self.items.append(item)

    def getItems(self):
        return self.items

    def totalValueOfItems(self):
        totalValue = 0
        for item in self.items:
            totalValue = totalValue + item.totalPrice()
        return totalValue

basket = Basket()

menu = """
1> Voeg item toe
2> Print items af
3> Sluit af
"""

while True:
    menu_input = input(menu)
    if menu_input == "1":
        try:
            # Request input from user
            description = input("Geef beschrijving: ")
            price = int(input("Geef prijs: "))
            quantity = int(input("Geef hoeveelheid: "))
            # Append new item
            basket.addItem(BasketItem(description, price, quantity))
        except InvalidQuantityException:
            print(quantity, "is geen geldige hoeveelheid")
        except InvalidItemPriceException:
            print(price, "is geen geldige prijs")
        except ValueError:
            print("Gelieve een geldige waarde ingeven")
    elif menu_input == "2":
        for item in basket.getItems():
            print(item.quantity, "*", item.description, " = ", item.totalPrice())
        print("Totale waarde:", basket.totalValueOfItems())
    elif menu_input == "3":
        print("Programma wordt beeindigd")
        exit()
    else:
        print("Foutieve keuze")
~~~

#### git: ...nog een commit...

Vanzelfsprekend voeren we een nieuwe commit uit:

~~~
>git commit -m "Intercepting non-numeric values for user input"
[master 9eedf57] Intercepting non-numeric values for user input
 1 file changed, 2 insertions(+), 2 deletions(-)
~~~

### En verder... voor de student

We gaan deze oefening in latere hoofdstukken verderzetten al leidraad:

* Aanmaken van modules
* Werken met test-frameworks
* GUI met TKInter
* Webinteface
* Persistentie in een database
* ...

#### Git

Dit voorbeeld is als zip downloadbaar in de cursus.  
Download deze en probeer via de commando's **"git log"** en "git show <commit-id>" dit voorbeeld te bestuderen en wat handigheid op te bouwen met Git zelf.

#### Uitbreidingsoefeningen

Daarnaast kunnen er nog veel verbeteringen worden toegevoegd:

* Verwijderen van een item
* Wijzigen van de hoeveelheid
* Meerdere baskets aanmaken
* Toevoegen van klant-data
* ...

Probeer deze stap-gewijs toe te voegen
