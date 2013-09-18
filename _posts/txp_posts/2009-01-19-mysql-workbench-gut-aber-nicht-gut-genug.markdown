---
layout: post
title: "MySQL Workbench - Gut, aber nicht gut genug."
date: 2009-01-19 21:21:56
comments: true
categories: Programmierung
---

Ich habe mich in letzer Zeit ziemlich viel mit dem [MySQL Workbench](http://dev.mysql.com/workbench/) beschäftigt. Vor allem für das Datenbank Design meines 
kleinen Privat Projektes, das ich hier wohl bald mal Vorstellen werde. Ich habe früher sehr gern mit dem [DBDesinger 4](http://www.fabforce.net/dbdesigner4/) 
gearbeitet und seine Features zu schätzen gelernt. Im OpenSource und Freeware Bereich gab es eigentlich keine Konkurrenz für ihn.

Bis dann die MySQL AB auf die Idee gekommen ist, den Entwickler anzustellen und eine eigene Software zur Datenmodellierung zu erstellen. Eigentlich keine 
Schlechte Idee, der Entwickler verdient nun sein Geld mit dem was er vorher in seiner Freizeit gemacht hat. Nur das Problem ist nun 
[MySQL](http://www.mysql.com), jetzt [SUN](http://www.sun.com), will ja auch Geld verdienen. Also gibt es eine Kommerzielle Lösung und eine OpenSource Lösung.
Und aus meiner Sicht sind ein Großteil der tollen Features des DBDesinger nur in die Kommerzielle Variante aufgenommen wurden. Wie z.B. die Synchronisation mittels Verbindung zum Datenbank Server. Außer dem ist mir noch aufgefallen, das die von mir relativ häufig genutzte Funktion, beim Exportieren des Schemas, das Ignorieren von "Foreign Keys" oder um genauer zu sein das nicht mit aufnehmen derer in die SQL Datei.

Viele Werden jetzt sagen, warum denn "Foreign Keys" nutzen aber nicht in das Schema einbauen. Ich nutze Foreign Keys im Design wirklich nur um die Verbindungen zwischen den Tabellen dazustellen und sichere dann über Programmierlogik die Integrität der Daten in der Datenbank. Das ist für mich persönlich die bessere Lösung im Bereich Webentwicklung.

Also MySQL Workbench ist schon mal ein guter Schritt in die Richtige Richtung, aber kann noch viele Schritte in diese Richtung vertragen. Wenn er wirklich an alle alten Features des DBDesinger herankommt werde ich evtl. sogar überlegen mir die Kommerzielle Variante zuzulegen.

Und für die die evtl. dem DBDesinger noch eine Chance geben wollen, auf Sourceforge hat sich eine Truppe rangemacht einen 
[Fork](http://sourceforge.net/projects/dbdesigner-fork) weiter zu führen, aber dort ist die Aktivität auch schon extrem gesunken.


