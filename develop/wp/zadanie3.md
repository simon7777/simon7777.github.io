---
layout: web_publishing
title: Transformácia vybraného dokumentu do formátu DocBook
author: Šimon Dekrét
date: 10.04.2016
project: 2
---

## Zadanie

Analyzujte možnosti zápisu jednoduchej prezentácie v jazyku XML. Identifikujte základné súčasti prezentácie a navrhnite XML elementy pre ich označkovanie (metadátové, štrukturálne, inline). Dbajte na znovupoužiteľnosť a vyvarujte sa redundancií. Návrh elementov zrealizujte opísaním typu dokumentu pomocou vybraného jazyka (DTD, XSD, RELAX NG) spolu s vysvetlením účelu jednotlivých elementov. Vo vami navhrnutom jazyku vytvorte ukážkovú prezentáciu, ktorá bude demonštrovať možnosti tvorby prezentácií podľa definície typu dokumentu.

## Vypracovanie

Dokument som opísal pomocou DTD súboru 'presentation.dtd'. 

    <!ELEMENT presentation (title_slide, slide+)> 
<!ELEMENT title_slide (topic, presented_by, date)>
<!ELEMENT slide (title, (content|cols))>
<!ELEMENT topic (#PCDATA)>
<!ELEMENT presented_by (#PCDATA)>
<!ELEMENT date (#PCDATA)>
<!ELEMENT title (#PCDATA)>
<!ELEMENT content (ul|text|cols|table)>
<!ELEMENT cols (col1, col2)>
<!ELEMENT ul (li+)>
<!ELEMENT text (#PCDATA)> 
<!ELEMENT col1 (ul|text|image)> 
<!ELEMENT col2 (ul|text|image)>
<!ELEMENT li (#PCDATA)>
<!ELEMENT image (#PCDATA)>
<!ELEMENT table (tr+)>
<!ELEMENT tr (th|td)+>
<!ELEMENT th (#PCDATA)>
    <!ELEMENT td (#PCDATA)>
