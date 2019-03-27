---
number: 2
deadline: 2019-03-24
---
### Transformácia vybraného dokumentu do formátu DocBook

Predmetom 2. zadania je spracovanie vybraného dokumentu (ideálne bakalárskeho projektu) z pôvodného ľubovoľného (Word, OpenOffice, LaTeX, …) formátu do formátu DocBook a vygenerovanie cieľového tvaru v PDF. Výsledný dokument bude mať rozsah minimálne 10 a maximálne 15 strán. Do rozsahu sa nezapočítavajú úvodné strany (obsah, zoznamy obrázkov a tabuliek), použitá literatúra a prílohy.

Požadované a kontrolné konštrukcie sú:

- štandardné členenie textu na kapitola, podkapitola, podpodkapitola, príloha, generovaný obsah,
- zvýraznenie slov, zvýraznenie členenia textu odrážkami alebo číslovaním,
- odkazy na iné časti vlastného dokumentu, prípadne odkazy na URL,
- poznámka pod čiarou,
- zoznam použitej literatúry a zdrojov vrátane ich citácie v texte,
- vloženie obrázku a tabuliek, odkazy na ne v texte; zoznam obrázkov a tabuliek v úvode alebo závere textu,
- vytvorenie registra pojmov (indexu) s pojmami hierarchicky usporiadanými do dvoch úrovni, napríklad „cykly, while“, „cykly, for“ (najmenej ako ukážku na 10-15 pojmoch na predvedenie práce s registrom).

### Dokumentácia

Na vypracovanie tohto zadania bola použitá verzia DocBook-u 4.5.

**Vykonané zmeny v súbore `thesis-tp-fo.xsl`:**
- slovo Vedoucí nahradené slovom Vedúci (slovenský preklad)
- odkaz na súbor `kizi.pdf` nahradený odkazom na súbor `fiit.png` (predstavuje logo školy)
- doplnený príkaz pre vygenerovanie zoznamu tabuliek a obrázkov (doplnené slová `table,figure`): `<xsl:param name="generate.toc">book title,toc,table,figure</xsl:param>`

Nasleduje zoznam použitých príkazov pre jednotlivé požadované a kontrolné konštrukcie.

**Štandardné členenie textu na kapitola, podkapitola, podpodkapitola, príloha, generovaný obsah:**
- `chapter` - pre kapitoly
- `section` - pre podkapitoly a podpodkapitoly
- `para` - pre odseky
- `appendix` - pre prílohy
- obsah je generovaný na začiatku dokumentu

**Zvýraznenie slov, zvýraznenie členenia textu odrážkami alebo číslovaním:**
- `orderedlist` - na vytvorenie číslovaného zoznamu
- `itemizedlist` - na vytvorenie nečíslovaného zoznamu
- `code` - na vloženie funkcie alebo inej časti zdrojového kódu do textu (inline)
- `emphasis` - na zvýraznenie slov
- `programlisting` - na vloženie zdrojového kódu

**Odkazy na iné časti vlastného dokumentu, prípadne odkazy na URL:**
- `xref` - v oddieli "Jednotkový test" (4.1) odkaz na kapitolu "Atrapy" (3) a v oddieli "Prostriedky na sledovanie volaní metód" (5.3) odkaz na oddiel "Profilovanie programu" (5.2)

**Poznámka pod čiarou:**
- `footnote` - nachádza sa v kapitole Lorem Ipsum

**Zoznam použitej literatúry a zdrojov vrátane ich citácie v texte:**
- `bibliography` - pre zoznam použitej literatúry
- `bibliomixed` - pre jednotlivé bibliografické záznamy
- `abbrev` - pre skratku jednotlivých bibliografických záznamov
- `citation` - na citovanie v texte

**Vloženie obrázku a tabuliek, odkazy na ne v texte; zoznam obrázkov a tabuliek v úvode alebo závere textu:**
- `table` - pre tabuľky, pričom jedna z tabuliek obsahuje horizontálny span vytvorený pomocou atribútov `namest` a `nameend` a iná tabuľka zas vertikálny span pomocou atribútu `morerows`
- `figure` - pre obrázky s popisom
- `xref` - odkazy na tabuľky a obrázky (v kapitole Lorem Ipsum)
- zoznam obrázkov a tabuliek je generovaný na začiatku dokumentu

**Vytvorenie registra pojmov (indexu) s pojmami hierarchicky usporiadanými do dvoch úrovni, napríklad „cykly, while“, „cykly, for“ (najmenej ako ukážku na 10-15 pojmoch na predvedenie práce s registrom):**
- `index` - na vytvorenie registra
- `primaryie`, `secondaryie` - usporiadanie  pojmov do 2 úrovní