---
number: 3
deadline: 2019-04-28
---

### XML prezentácia

Analyzujte možnosti zápisu jednoduchej prezentácie v jazyku XML. Identifikujte základné súčasti prezentácie a navrhnite XML elementy pre ich označkovanie (metadátové, štrukturálne, inline). Dbajte na znovupoužiteľnosť a vyvarujte sa redundancií. Návrh elementov zrealizujte opísaním typu dokumentu pomocou vybraného jazyka (DTD, XSD, RELAX NG) spolu s vysvetlením účelu jednotlivých elementov. Vo vami navhrnutom jazyku vytvorte ukážkovú prezentáciu, ktorá bude demonštrovať možnosti tvorby prezentácií podľa definície typu dokumentu.

Navrhnite a vytvorte XSLT šablóny pre konverziu prezentácie z XML do XHTML+CSS a pre konverziu prezentácie z XML do PDF. Klaďte dôraz na znovupoužitie jednotlivých šablon pre viaceré výstupné formáty. Umožnite zadávanie parametrov transformácií.

Súčasťou požiadaviek na zadanie je vytvorenie správy o zadaní 3, v ktorej zdokumentujete splenie jednotlivých bodov zadania. Správa bude súčasťou vašej stránky o Webovom publikovaní na GitHube.

### Dokumentácia

**Opis typu dokumentu + opis účelu navrhnutých elementov**
- typ dokumentu je opísaný pomocou **DTD**
- dokument s interným DTD bol validovaný použitím online validátora a následne bolo DTD presunuté do súboru `presentation.dtd`

*Opis elementov* (v zátvorke je uvedené, aké podelementy môže element obsahovať)
- `presentation` - koreňový element (meta, pages)
- `meta` - meta informácie (author, email, date)
- `author` - meno autora
- `email` - kontaktný email
- `date` - dátum prezentácie
- `pages` - strany prezentácie (titlepage, page)
- `titlepage` - titulná strana (title, subtitle)
- `page` - obyčajná strana (title, content, refs)
- `title` - názov titulnej alebo obyčajnej strany
- `subtitle` - podnadpis titulnej strany
- `content` - obsah obyčajnej strany (p, ul, ol, image, t)
- `p` - paragraf
- `ul` - nečíslovaný zoznam (li)
- `ol` - číslovaný zoznam (li)
- `li` - položka číslovaného alebo nečíslovaného zoznamu; má atribút `color` pre farbu textu
- `image` - obrázok; má atribút `src` pre zdroj obrázka a `title` pre názov obrázka
- `t` - tabuľka (r); má atribút `title` pre názov tabuľky
- `r` - riadok tabuľky (c)
- `c` - bunka riadku tabuľky; má atribút `color` pre farbu textu
- `refs` - referencie (ref)
- `ref` - referencia
- `e` - zvýraznenie textu kurzívou; možné v elementoch p, li alebo c
- `b` - nastavenie väčšej hrúbky textu; možné v elementoch p, li alebo c

**Vytvorenie ukážkovej XML prezentácie demonštrujúcej možnosti definície typu dokumentu**
- vytvorený súbor `presentation.xml`

**Základný návrh XSL transformácií, ich vhodnosť, parametrizácia**
- vytvorené šablóny pre:
   - jednotlivé elementy
   - nastavenie číslovania
   - vytvorenie odkazov prepájajúcich po sebe idúce strany
- používateľ si môže nastaviť nasledovné **parametre**:
   - číslovanie - n-0 (vypnúť číslovanie) / n-1 (zapnúť číslovanie)
   - typ textu - f-cursive / f-monospace / f-sans-serif / f-serif
   - pozadie strán - b-light (svetlé) / b-dark (tmavé)
- defaultne je číslovanie zapnuté, text nastavený na monospace a pozadie svetlé

**Vytvorenie XSLT pre konverziu prezentácie z XML -> XHTML+CSS**
- každá strana je v osobitnom html súbore
- po sebe idúce strany sú prepojené odkazmi (klikateľné šípky na spodnej časti strany)
- vytvorený súbor `style.css` pre nastavenie štýlov, ktorý je pripojený k html súboru pomocou elementu `link`
- pre zobrazenie prezentácie vo formáte html odporúčam použiť prehliadač Google Chrome

**Vytvorenie XSLT pre konverziu prezentácie XML -> PDF**
- nie je vytvorený