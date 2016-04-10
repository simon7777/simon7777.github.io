---
layout: web_publishing
title: Transformácia vybraného dokumentu do formátu DocBook
author: Šimon Dekrét
date: 10.04.2016
project: 2
---

Predmetom 2. zadania je spracovanie vybraného dokumentu (ideálne bakalárskeho projektu) z pôvodného ľubovoľného (Word, OpenOffice, LaTeX, …) formátu do formátu DocBook a vygenerovanie cieľového tvaru v PDF. Výsledný dokument bude mať rozsah minimálne 10 a maximálne 15 strán. Do rozsahu sa nezapočítavajú úvodné strany (obsah, zoznamy obrázkov a tabuliek), použitá literatúra a prílohy.

Dokument je rozdelený na 3 kapitoly: Úvod, Pozícia diagramu kompozitnej štruktúry v UML, Záver. Na rozčlenenie do kapitol som použil klasický element <**chapter**>, ktoré sú následné členené na sekcie <**section**>.

V texte som použil element na zvýraznenie textu, resp. slov, ktoré boli pre danú časť dôležité: <**emphasis**>.

V nasledujúcej časti sa nachádza 

    <figure id="f:class1"><title>Štruktúra diagramu tried</title>
		<mediaobject>
			<imageobject>
				<imagedata fileref="fig/class1.png"/>
			</imageobject>
			<textobject><phrase>Štruktúra diagramu tried</phrase></textobject>
		</mediaobject>
	</figure>

