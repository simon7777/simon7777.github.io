---
layout: web_publishing
title: XML prezentácia
author: Šimon Dekrét
date: 12.05.2016
project: 3
---

## Zadanie

Analyzujte možnosti zápisu jednoduchej prezentácie v jazyku XML. Identifikujte základné súčasti prezentácie a navrhnite XML elementy pre ich označkovanie (metadátové, štrukturálne, inline). Dbajte na znovupoužiteľnosť a vyvarujte sa redundancií. Návrh elementov zrealizujte opísaním typu dokumentu pomocou vybraného jazyka (DTD, XSD, RELAX NG) spolu s vysvetlením účelu jednotlivých elementov. Vo vami navhrnutom jazyku vytvorte ukážkovú prezentáciu, ktorá bude demonštrovať možnosti tvorby prezentácií podľa definície typu dokumentu.

## Vypracovanie

### Opic typu dokumentu

Dokument som opísal pomocou DTD súboru 'presentation.dtd'. 

    <!ELEMENT presentation (title_slide, slide+)> 
    <!ELEMENT title_slide (topic, presented_by, date)>
    <!ELEMENT slide (title, (content|cols))>
    ....
    
### Ukazkova prezentacia

Prezentáciu som urobil o Slovensku. V nasledujúcej časti sú zobrazené dva slidy:

        <title_slide>
    		<topic>Slovakia</topic>
    		<presented_by>Simon Dekret</presented_by>
    		<date>May 10, 2016</date>
    	</title_slide>
    	<slide>
    		<title>Basic info</title>
    		<content>
    			<ul>
    				<li>Area: 49,035km2</li>
    				<li>Population: 5,415,949</li>
    				<li>GDP total: $158,428 billion</li>
    				<li>GDP per capita: $29,209</li>
    				<li>Currency: euro</li>
    				<li>HDI: 0.844(very high)</li>
    				<li>Official language: Slovak</li>
    			</ul>
    		</content>
    	</slide>
    	
### Transformácie do HTML

Na customizovanie výstupu HTML používateľom som vytvoril vlastný súbor. Jeho obsah je:

        <?xml version="1.0" encoding="UTF-8"?>
        <xsl:stylesheet version="1.0"
        xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
        
        <xsl:param name="color_title">#0000FF</xsl:param>
        <xsl:param name="topic_title_size">100</xsl:param>
        <xsl:param name="background-color">#D8D8D8 </xsl:param>
        <xsl:param name="normal_title_size">50</xsl:param>
        <xsl:param name="font-size">30</xsl:param>
        
        </xsl:stylesheet>

Tento dokument som importoval do súboru, v ktorom boli vytvorené transformácie.



