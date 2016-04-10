---
layout: web_publishing
title: Transformácia vybraného dokumentu do formátu DocBook
author: Šimon Dekrét
date: 10.04.2016
project: 2
---

Predmetom 2. zadania je spracovanie vybraného dokumentu (ideálne bakalárskeho projektu) z pôvodného ľubovoľného (Word, OpenOffice, LaTeX, …) formátu do formátu DocBook a vygenerovanie cieľového tvaru v PDF. Výsledný dokument bude mať rozsah minimálne 10 a maximálne 15 strán. Do rozsahu sa nezapočítavajú úvodné strany (obsah, zoznamy obrázkov a tabuliek), použitá literatúra a prílohy.

##Vypracovanie

Dokument je rozdelený na 3 kapitoly: Úvod, Pozícia diagramu kompozitnej štruktúry v UML, Záver. Na rozčlenenie do kapitol som použil klasický element <**chapter**>, ktoré sú následné členené na sekcie <**section**>.

V texte som použil element na zvýraznenie textu, resp. slov, ktoré boli pre danú časť dôležité: <**emphasis**>.

V nasledujúcej časti sa nachádzú elementy s príslušnými atribútmi, ktoré som použil na vloženie diagramu do textu:

    <figure id="f:class1"><title>Štruktúra diagramu tried</title>
		<mediaobject>
			<imageobject>
				<imagedata fileref="fig/class1.png"/>
			</imageobject>
			<textobject><phrase>Štruktúra diagramu tried</phrase></textobject>
		</mediaobject>
	</figure>

V texte som sa na takýto obrázok odvolával elementom <**xref**/> s atribútom **linkend="f:class1"**. Tento istý element a atribút som použil aj pri citovaní z použitej literatúry.

Tabuľka obsahuje diagramy použité v dokumente a je vytvorená elementami tvoriacimi nasledujúcu štruktúru:

    <table><title>Tabuľka diagramov UML, použitých v dokumente </title>
			<tgroup cols='2' align='center'>
				<thead>
					<row>
					  <entry>Štrukturálne</entry>
					  <entry>Behaviorálne</entry>
					</row>
				</thead>
				<tbody>
					<row>
					  <entry>Diagram tried</entry>
					  <entry>Sekvenčný diagram</entry>
					</row>
					<row>
					  <entry>Diagram objektov</entry>
					  <entry>Diagram prípadov použitia</entry>
					</row>
					<row> 
					  <entry>Diagram kompozitnej štruktúry</entry>
					</row>
					<row>
					  <entry>Diagram komponentov</entry>
					</row>
				</tbody>
			</tgroup>
		</table>


V dokumente je použitý aj ústrižok kódu v C++, ktorý som vložil elementom <**programlisting**>

Register pojmov som vytváral pomocou elementu <**indexterm**>. Na konci dokumentu sa tento register automaticky vygeneroval použitím elementu <**index**>.

    <indexterm>
    	<primary>štruktúra</primary>
    	<secondary>kolaborácia</secondary>
    </indexterm>
    
V xsl súbore **thesis-tp-fo** som pridal atribút **hyphenate=”false** do šablóny **book.titlepage.before.recto** a taktiež som zmenšil písmo book.titlepage.before.recto na 18pt, kvôli tomu, aby sa názov Bratislavy zmestil do jedného riadku.
