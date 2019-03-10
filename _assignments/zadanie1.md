---
number: 1
deadline: 2019-03-10
---
### Osobná webová prezentácia na GitHub pages

Vytvorte webovú prezentáciu (webové sídlo) o sebe. Zamerajte sa jednak na vaše profesné záujmy (napr. projekty, ktoré riešite/riešili ste, čo vás v informatike najviac baví, fascinuje = váš developerský profil) a jednak vaše osobné záujmy, hobby.

V rámci developerského profilu vytvorte sekciu Webové publikovanie, kde budete publikovať všetky tri vaše vypracované zadania z predmetu.

Využite pritom technológie Git + GitHub Pages + Jekyll + Markdown. Využite potenciál statického generátora Jekyll a jeho templatovacích možností.

Podrobné požiadavky na vypracovanie a odovzdanie zadania (priemerná úroveň kvality):

- Sídlo musí obsahovať aspoň 5 podstránok, pri využití aspoň 3 rôznych rozložení (layout-ov)
- V rámci šablon musí byť použité:
    - aspoň 5 premenných
    - kolekcie alebo dátové súbory
    - aspoň 5 filtrov alebo tagov
    - aspoň 1 plugin (okrem pagination)
	

### Dokumentácia

**Toto webové sídlo obsahuje nasledovné podstránky:**
- Domov
- O mne
- Blog
- Fotogaléria
- Developerský profil
- Webové publikovanie
    - Zadanie 1
	- Zadanie 2
    - Zadanie 3
	
**Rozloženia:**
- `default.html`
    - defaultné rozloženie
	- ostatné rozloženia rozširujú toto rozloženie
- `home.html`
    - pre úvodnú stránku
	- dole na stránke sa zobrazujú 3 najnovšie príspevky v blogu
- `post.html`
    - pre príspevok
	- na začiatku príspevku je uvedené, koľko má slov
- `photo-gallery.html`
    - pre fotky
	- pri fotkách sa zobrazujú ďalšie informácie o nich
- `skills.html`
    - pre zoznam jazykov, ktoré ovládam
	- pri jazykoch sa zobrazuje ikonka, úroveň a popis
- `wpub.html`
    - pre dokumentáciu k zadaniam
	- obsahuje 3 podstránky
- `assignment.html`
    - pre konkrétne zadanie
	- obsahuje číslo zadania, deadline a jeho znenie s dokumentáciou

**Premenné:**
- `site.email` 
- `site.my-name`
- `site.github`
- `site.school-web`
- `site.school-name`
- okrem týchto premenných sú ďalšie definované v jednotlivých kolekciách - ich názvy sú uvedené nižšie v zozname kolekcií v zátvorkách 

**Kolekcie:**
- `photos` - fotky (`title`, `image_path`, `date`, `place`)
- `skills` - zručnosti (`title`, `icon`, `level`)
- `assignments` - zadania (`number`, `deadline`)
- `interests` - záujmy (`title`)

**Filtre:**
- `date_to_string` - na formátovanie dátumu pri príspevkoch a fotkách
- `sort` - na zoradenie fotiek podľa dátumu
- `number_of_words` - na zobrazenie počtu slov príspevku
- `truncatewords` - na zobrazenie náhľadu príspevku

**Tagy:**
- `include` - na includovanie navigácie a footeru v defaultnom rozložení
- `if`, `endif` - na zobrazenie zadaní na podstránkach (zadanie 1 sa zobrazí na stránke 1, zadanie 2 na stránke 2 ...), použité v rozložení `assignment.html` 
- `for`, `endfor` - na prechádzanie položkami kolekcie

**Pluginy:**
- `jekyll-sitemap` - na vygenerovanie mapy webového sídla (odkaz na sitemap je umiestnený dole vpravo)
- `jekyll-email-protect` - na ochranu zverejnenej emailovej adresy pred spam botmi

**Štýly**
- externý štýl pre Font Awesome (ikonky vo footeri a niektoré ikonky programovacích jazykov)
- pridané vlastné CSS štýly do súboru `main.css`, ide hlavne o štýly definujúce zobrazenie:
    - najnovších príspevkoch na úvodnej stránke
	- textu na stránke WPUB a jej podstránkach - pre prehľadnosť bolo potrebné nastaviť menšie písmo
	- fotiek vo fotogalérii (nastavenie ich šírky)
	- zručností v developerskom profile (rozmiestnenie ikoniek, názvu a popisu)
	