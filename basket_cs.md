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

## Code schrijven (deel 1): klasses, objecten en properties

In dit 1ste deel gaan een kleine basis applicatie bouwen

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
Geen hierbij een duidelijke boodschap zoals bijvoorbeeld "Setting up event-loop with basic menu"

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


##### En nog een commit...

Maak nu een commit waarin je deze code commit.  
Geen hierbij een duidelijke boodschap zoals bijvoorbeeld *"Feedback within event-loop for each item"*

### Code schrijven: programma/event-loop beëindigen

Tot nog toe moesten we ons eerste programma afsluiten met **ctrl+c**  
Het eerste event dat we al kunnen afwerken is **"3> Sluit af"** opdat we het programma op een elegante manier kunnen afwerken.

Hiervoor stoppen we het programma door uit de **main-functie** een **return** uit te voeren, dat zal er voor zorgen dat het programma wordt afgesloten.

~~~cs
    switch(menuChoice)
    {
        case("1"): Console.WriteLine("TODO: voeg item toe");break;
        case("2"): Console.WriteLine("TODO: print item toe");break;
        case("3"): Console.WriteLine("Applicatie sluit af");return;
        default: Console.WriteLine("Foutieve keuze");break;
    }
~~~

> Bemerk ook dat je hier de break door een return vervangt (gezien bij return de break niet veel zin meer heeft)

En vervolgens testen we:

~~~
1> Voeg item toe
2> Print items af
3> Sluit af
3
Het programma wordt beeindigd
~~~

##### En nog een commit...

Maak nu een commit waarin je deze code commit.  
Geen hierbij een duidelijke boodschap zoals bijvoorbeeld *"Implementing menu-item exit"*

### Git Historiek en Commit-id's

We we zien dat de **git-historiek** zich langzaam maar zeker begint **op te bouwen** ondertussen.  
In git spreken we dan ook van een **history**, letterlijk een historiek van commits

![](git-history.png)

Bemerk ook dat deze **commits** allen een **id** hebben dit is een unieke (hash-)code voor je commit
die je achter kan gebruiken om een specifieke commit te identifieren voor diverse operaties

### Code schrijven: Afdrukken van items

We hebben bij een vorige commit een **lijst** gemaakt die wordt gebruikt om de **items** bij te houden.  

In **deze wijziging/commit** gaan we deze **lijst afdrukken**, gezien we echter de invulling nog niet hebben we uitgewerkt maken we voorlopig een fake/hardcoded lijst aan:

> **Belangrijk:**  
> Het gebruik van deze fake data dient achteraf verwijderd te worden 
> maar het laat ons toe onze code-wijziging te testen.
> In een volgende les gaan we meer geavanceerde technieken zien om onze code te testen
> (en deze testen zelf te automatiseren)

We **voegen** deze **code** **toe** boven de **event-loop**

~~~cs
        items.Add(new BasketItem(10, "Patatten"));
        items.Add(new BasketItem(20, "Bloemkool"));

        while (true)
~~~

Onder **optie 2** voegen we vervolgens een **loop** toe die deze **items afdrukt**.  

~~~cs
        switch (menuChoice)
        {
            case ("1"): Console.WriteLine("TODO: voeg item toe"); break;
            case ("2"):
                foreach (BasketItem item in items)
                {
                    Console.WriteLine($"{item.Description} voor {item.Price} als prijs");
                }
                break;
            case ("3"): Console.WriteLine("Applicatie sluit af"); return;
            default: Console.WriteLine("Foutieve keuze"); break;
        }
~~~

Als we even testen

~~~
1> Voeg item toe
2> Print items af
3> Sluit af
2
Patatten voor 10 als prijs
Bloemkool voor 20 als prijs
1> Voeg item toe
2> Print items af
3> Sluit af
3
Applicatie sluit af
~~~

#### git: ... volgende commit

We voegen onze **wijzigingen** toe aan de git repo met een commit *"Printing the current menu-items"*

### Code schrijven: items toevoegen

Om er een **interactieve applicatie** van te maken moeten we **user-input** gebruiken om de het **winkelmandje** aan te vullen.  
We doen dit door **event 1** te **implementeren** door de 3 volgende taken te implementeren:

* Vraag **user-input** op (beschrijving en prijs)
* **Maak BasketItem-object** aan met input
* Voeg BasketItem-object toe aan **lijst**

* Stap 1: We **verwijderen** hierbij ook de eerder aangemaakte **hard-coded** lijst
* Stap 2: We **vragen** de **prijs** en **beschrijving** op en **voegen** deze als object **toe** aan de lijst

~~~cs
    case ("1"):
        Console.Write("Geef prijs: ");
        int price = int.Parse(Console.ReadLine());

        Console.Write("Geef omschrijving: ");
        string description = Console.ReadLine();

        items.Add(new BasketItem(price, description));

        break;
~~~

Als we dit **testen** zie we dat we nu dynamisch items kunnen toevoegen:

~~~
1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef prijs: 20
Geef omschrijving: Frieten
1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef prijs: 25
Geef omschrijving: Ijsjes
1> Voeg item toe
2> Print items af
3> Sluit af
2
Frieten voor 20 als prijs
Ijsjes voor 25 als prijs
1> Voeg item toe
2> Print items af
3> Sluit af
3
~~~

De test is uitgevoerd:

* We kunnen meerdere items **toevoegen**
* En deze nog altijd **afprinten**

#### git: ... volgende commit

We **voegen** onze wijzigingen **toe** aan de **git** repo met de commit-boodschap *"Adding new items"*

### Code schrijven: Voeg een attribuut quantity toe

#### Nieuwe property Quantity toevoegen

In een winkelmandje dien je soms **meerdere items** van **hetzelfde product** bij te houden.  
Om dit op te lossen voegen we aan onze klasse BasketItem een **attribute quantity** toe

Hiervoor **voegen** we aan de **constructor** een **attribuut toe**...

> *Nota:*  
> Net zoals we eerder bij functies hebben gezien kan je attributen optioneel maken 
> door er een default waarde bij te plaatsen.  
> Als men dan deze waarde zou weglaten (bij aanroep van de constructor) krijgt dit attribuut
> deze default waarde

Hiervoor breiden we onze constructor uit met een nieuw argument.  

~~~cs
namespace PRB.ShoppingBasket.Bart
{
    public class BasketItem
    {
        public BasketItem(int price, string description, int quantity = 1) 
        {
            Price = price;
            Description = description;
            Quantity = quantity;
        }

        public int Quantity { get; set; }

        public int Price { get; private set; }

        public string Description { get; private set; }
    }
}
~~~

Hiervoor gebruiken we een nieuw element in C#, namelijk **default arguments**.  
Als je geen quantity meegeeft aan je constructor zal deze op 1 worden gezet...

#### Nieuwe (afgeleide) property TotalPrice toevoegen

... daarnaast voegen we een extra property **TotalPrice** toe, hiermee bereken we de werkelijke prijs

~~~cs
    public int TotalPrice 
    {      
        get { return Price * Quantity; }
    }
~~~

Bemerk dat deze property **geen setter** heeft en volledig **afhankelijk** is van de 2 **andere properties**...

#### Opvragen van de hoeveelheid

We zorgen nu 1ste dat de hoeveelheid mee wordt opgevraagd:

~~~cs
case ("1"):
    Console.Write("Geef prijs: ");
    int price = int.Parse(Console.ReadLine());

    Console.Write("Geef omschrijving: ");
    string description = Console.ReadLine();

    Console.Write("Geef hoeveelheid: ");
    int quantity = int.Parse(Console.ReadLine());

    items.Add(new BasketItem(price, description, quantity));

    break;
~~~

#### Print wijzigen

Vervolgens passen we dan de weergave aan zodat die niet enkel de prijs van 1 stuk afdrukt maar ook de prijs van de totaal aantal items.

~~~cs
case ("2"):
    foreach (BasketItem item in items)
    {
        Console.WriteLine($"{item.Quantity} maal {item.Description} voor {item.Price} per item, totaal {item.TotalPrice}");
    }
    break;
~~~

Als we dit dan **testen** krijgen we volgende output

~~~
1> Voeg item toe
2> Print items af
3> Sluit af
1
Geef prijs: 10
Geef omschrijving: Patatten
Geef hoeveelheid: 20
1> Voeg item toe
2> Print items af
3> Sluit af
2
20 maal Patatten voor 10 per item, totaal 200
1> Voeg item toe
2> Print items af
3> Sluit af
3
Applicatie sluit af
~~~

Test OK, we kunnen vervolgen met onze commit...

#### git: commit

Als git-comment geef je dan iets zoals *"Adding Quantity to BasketItem"*

### Totaal van de items

Interessant om te weten als gebruiker is de **totaal waarde** van deze items.  
We voegen hier een nieuw event toe aan het menu

~~~cs
string menu = """
                1> Voeg item toe
                2> Print items af
                3> Totaalprijs
                4> Sluit af
                """;
~~~

Vervolgens voegen we een **case** voor **3** toe:

~~~cs
    case ("3"):
        int totalPrice = 0;
        foreach (BasketItem item in items)
        {
            totalPrice += item.TotalPrice;
        }
        Console.WriteLine($"De totale prijs van uw winkelmandje is {totalPrice}");
        break;
~~~

Vergeet niet de oude optie 3 (afsluiten) aan te passen naar optie 4 

~~~cs
    case ("4"):
        Console.WriteLine("Applicatie sluit af");
        return;
~~~

Vervolgens even testen

~~~
1> Voeg item toe
2> Print items af
3> Totaalprijs
4> Sluit af
1
Geef prijs: 10
Geef omschrijving: Bier
Geef hoeveelheid: 25
1> Voeg item toe
2> Print items af
3> Totaalprijs
4> Sluit af
1
Geef prijs: 5   
Geef omschrijving: Cola
Geef hoeveelheid: 15
1> Voeg item toe
2> Print items af
3> Totaalprijs
4> Sluit af
3
De totale prijs van uw winkelmandje is 325
1> Voeg item toe
2> Print items af
3> Totaalprijs
4> Sluit af
4
Applicatie sluit af
~~~

De test is geslaagd...


#### git: volgend commit...

...We kunnen dit **committen** met de boodschap "Adding a total price for the basket"

