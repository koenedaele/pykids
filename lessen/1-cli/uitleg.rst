Les 1: werken met de command line
=================================

Vandaag de dag werken de meeste mensen met een computer door middel van een GUI
(Graphical User Interface). Vroeger konden schermen nog niet zo veel en werk er
meer gewerkt met een CLI (Command Line Interface). In tegenstelling tot bij een
GUI doe je dan niet veel met een muis, maar doe je bijna alles met je
toetsenbord. Eigenlijk schrijf je kleine opdrachten of commando's naar je computer
die ze dan uitvoert. Je hebt telkens een regel om een opdracht in te tikken. Op
het einde van de regel druk je op de `enter` toets om het commando uit te voeren.

Om naar de CLI te gaan heb je een aantal mogelijkheden:

 * Druk tegelijk op `ctrl` + `alt` + `t`.
 * Klik links bovenaan op het Ubuntu icoon en tik daarin `terminal`. Selecteer
   het programma `terminalvenster`.
 * Je kunt het `terminalvenster` ook naar je linkerbalk slepen zodat je het
   altijd makkelijk kunt terug vinden.

Telkens als we een commando tonen dat je kunt intikken zetten we daar een `$`
teken voor. Dat is een veel voorkomend symbool om aan te geven dat je op de CLI
aan het werken bent. Een opdracht of commando bestaat uit een aantal woorden na
elkaar waartussen spaties staan. Het eerste woord is het eigenlijke commando, de
tweede en verdere woorden noemen we parameters of argumenten. Deze bepalen met
wat het commando wordt uitgevoerd.

Ga nu even naar de CLI zodat we een test kunnen doen. Kies één van de
bovenstaande methodes en open een CLI venster. Als je wil kan je dit wat groter
maken. Normaal heb je een blinkende cursor staan naast een `$`.

Om te beginnen testen we een commando waar geen argumenten voor nodig zijn. Voer
het commando `pwd` uit. Dit doe je door `pwd` in te tikken, gevolgd door de
`enter` toets.

```bash
$ pwd
```

Nu verschijnt er op je scherm waar op de harde schijf je staat. Normaal zal dit
beginnen met `/home/`, dan gevolgd door je gebruikersnaam. Bijvoorbeeld
`/home/mira`. Onder een Linux computer worden je bestanden georganiseerd in een
boomstructuur. Je kunt dit zien als een boom waarbij de stam het startpunt is,
daaraan zitten dan grote takken vast en aan die grote takken zijn dan kleinere
takken vast en zo voort. De stam noemen we in het Engels `root`. Deze stellen we
voor als `/`. Daaraan hangen de hoofdtakken vast. Je kunt er zelf aanmaken, maar
er zijn er een aantal die standaard aanwezig zijn. Eentje daar van is `/home`.
Dit is een tak waaronder iedereen zijn persoonlijke zaken kan opslaan. Een tak
van deze boom noemen we ook een map of folder. In de map `/home` heeft elke
gebruiker die de computer gebruikt een eigen map. Dus, er zijn mappen zoals
`/home/mira`, `/home/koen`, `/home/lena`, `/home/jef`, ... De computer is dus
een boom waaraan een grote tak hangt die we `home` noemen. Van hieruit ontstaan
er kleinere takken die we `mira`, `lena`, `koen`, ... noemen. En daarbinnen
kunnen we weer extra takken aanmaken.

Laten we dat nu eens doen. We maken een map `projecten` aan. Dit doen we met het
commando `mkdir`. Dit is een afkorting van `make directory`.

```bash
$ mkdir projecten
```

Als we nu willen zien welke mappen er al bestaan in onze map, gebruiken we het
commando `ls`. Dit is een afkorting van `list`.

```bash
$ ls
```

Nu zien we alle bestanden in onze eigen `home` directory. We zien zowel
bestanden als andere mappen. Afhankelijk van hoe je CLI is ingesteld kan het
zijn dat je de mappen in een ander kleur ziet dan de gewone bestanden. Je kunt
het ls commando ook toepassen op een andere map. Dit doe je door na het commando
de map op te geven. Dit noemen we ook wel een `argument` dat we aan het commando
doorgeven. Het commando zegt wat er moet gedaan worden, het argument waarmee.

```bash
$ ls projecten
```

Nu zie je alle bestanden in de map `projecten` die we net hebben aangemaakt.
Aangezien we daar nog niets gedaan hebben, is deze nog leeg. We gaan nu even een
bestandje in die map aanmaken.

```bash
$ touch projecten/test.txt
```

Dit wil zeggen: maak een leeg bestand met de naam test.txt aan in de map
projecten. Hier is het commando dus `touch` en het argument is
`projecten/test.txt`.

Je kunt een map of bestand op verschillende manieren opgeven. De simpelste
manier is om gewoon een naam van een bestand of map op te geven. Op dat moment
gaat de computer er van uit dat je het hebt over een map of bestand in de map
waar je op dit moment staat. Dus, als je in `/home/mira` staat en je voert het
commando `ls projecten` uit, dan wordt er gezocht naar een bestand of map
genaamd projecten in de map `/home/mira`.

Je kunt echter ook meteen hoger of lager in je boom op zoek gaan naar een
bestand. Je kunt bijvoorbeeld tikken `ls projecten/test.txt`. Dan zie je alle
bestanden genaamd `test.txt` in de map `projecten`. Als je dichter bij de stam
iets wil zien, kan je met `..` een niveau stijgen. Als je bv. doet `ls ..`
terwijl je in `/home/mira` staat, dan vraag je eigenlijk de inhoud van `/home`
op. Je kunt dit ook combineren. Zo kun je `ls ../..` intikken om de inhoud van
twee takken hoger te zien (dus van `/`). Of `ls projecten/..` om de inhoud van
je eigen map te zien.

Tenslotte is het soms makkelijker om niet te vertrekken van de plaats waar je nu
staat, maar vanaf de root van je boom. Zo kun je altijd doen `ls /home` om de
inhoud van de map `/home` te zien. Dit is hetzelfde als `ls ..` als je in
`/home/mira` staat, maar heeft het voordeel dat het altijd zal werken, zelfs al
sta je niet in `/home/mira`.

De weg die je moet afleggen om aan een bepaald bestand te geraken noemen we ook
wel een `pad`. Als het pad start vanaf de plaats waar je nu staat, dan noemen we
het een relatief pad. Dus, `projecten`, `projecten/test.txt`, `..` zijn allemaal
relatieve paden. Als het pad start vanaf de root, dan noemen we het een absoluut
pad. Je kunt zo'n pad herkennen aan het feit dat het start met `/`. Dus, `/`,
`/home`, `/home/mira`, .. zijn allemaal absolute paden.

Een speciaal pad is het pad `~`. Dit pad stelt altijd jouw eigen home folder
voor. Dus, afhankelijk van wie je bent zal dit steeds een andere map zijn. Voor
mij is dit `/home/koen`. Voor jou is dit `/home/mira` of `/home/lena`.

We hebben nu wel een map `projecten` aangemaakt en daar een bestand in gezet,
maar kunnen we er ook iets in gaan doen? Natuurlijk. Daarvoor gebruiken we het
commando `cd`. Dit is een afkorting van `change directory` (verander van map).
Zoals altijd combineer je het commando met een argument. Dit argument moet
wijzen naar de map waar je heen wil gaan. Zoals we gezien hebben kun je dat op
heel veel verschillende manieren doen.

Stel dat we in `/home/mira` beginnen.

Ten eerste kunnen we gewoon met de lokale mapnaam werken.

```bash
$ cd projecten
$ pwd
$ cd ~
```

Als je dit correct uitvoert, ga je eerst naar de map projecten die onder je huidige 
map hangt. Daarna vraag je aan de computer om het pad van de map af te drukken. 
Tenslotte ga je terug naar jouw home map.

Ten tweede kunnen we met een absoluut pad werken.

```bash
$ cd /home/<username>/projecten
$ pwd
$ cd ~
```

Hierbij moet je `<username>` vervangen door je eigen gebruikersnaam. Dus `koen`,
`jef`, `mira`, ... Je gaat dus rechtstreeks naar je projecten map. Waar het
commando `cd projecten` enkel werkt als je in de map boven `projecten` staat,
werkt dit commando waar je ook staat op de computer.

Test dit zelf eens uit.

```bash
$ cd /
$ cd projecten
$ pwd
$ cd /home/<username>/projecten
$ pwd
$ cd ~
```

De eerste `cd` werkt niet, de tweede wel. Een absoluut pad zal altijd werken,
maar is meer tikwerk. Een relatief pad zal niet altijd werken, maar is wel
sneller te tikken. Afhankelijk van waar je bent en wat je aan het doen bent is
het één beter of het ander.
