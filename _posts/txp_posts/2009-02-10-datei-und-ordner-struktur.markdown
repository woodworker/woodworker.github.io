---
layout: post
title: "Datei und Ordner Struktur"
date: 2009-02-10 21:57:30
comments: true
categories: projektmanagement
---

Hier nun der zweite Artikel meiner Serie "Projektmanagement in kleinen Projekten".  Ich würde mich auch hier wieder über Feedback freuen.

Zu aller erst will ich erst einmal sagen das ich diese Ordnerstruktur für Web basierte Projekte mit PHP und Javascript erstellt habe und nutze. Ich weiß nicht in wie weit diese Struktur für andere Programmiersprachen/Verwendungszwecke tauglich ist, daher dieses kleine Vorwort.

Nun zur Struktur. Da jedes Projekt auch eine Dokumentation haben sollte sollte hier zu aller erst ein Ordner für die Dokumentation erstellt werden. Ja OK ein einfacher Ordner - man der muss mich für blöd halten. Nein, aber viele vergessen einfach das Dokumentation zum Projekt gehört und speichern ihre Dokumente dann einfach mal hier und mal dort, anstatt sie gleich mit in die Projektstruktur mit aufzunehmen. Das hat wiederum den Vorteil das die Dokumentation auch mit in der Versionskontrolle liegt und dadurch auch ältere Versionen wiederherstellbar sind, aber dazu mehr im Versionskontrolle Artikel.
Den Dokumentationsordner teile ich in meinen Projekten meist noch in einen Ordner für das Datenbankdesign und die eigentliche Dokumentation auf.

Nun zur Struktur für den Quelltextbaum des Projekte. In diesem erstelle ich meist einen Ordner, da ich ja hier von Webprojekten rede, der die eigentliche Webroot ist. Diesen nenne ich meist public oder htdocs je nach dem. Einen Ordner für Externe Bibliotheken wie PEAR, Zend Framework oder sonstige Frameworks. Einen Ordner für Selbstgeschriebene Klassen und Funktionen, einen für Konfigurationsdateien und zu guter letzt einen Ordner für Temporäre Dateien wie Cachedateien oder Uploads. Diese Grundstruktur halte ich für alle meine Projekte ein und habe bisher immer wieder mitbekommen das diese Variante für mich die beste ist.
Meist erstelle ich auch noch eine extra Struktur im Webroot Ordner für die Dateien die an den User garantiert ausgeliefert werden, wie Bilder, CSS, Javascript und evtl. auch Flash. So kommen neue Dateien immer da hin wo sie hingehören und mich muss nicht lange nach ihnen Suchen.

Neuerdings erstelle ich mir in dem Grundordner, in dem ja schon der Dokumentations und der Quelltext Ordner liegen, noch einen 3. Ordner für Sonstige Dateien die zum Projekt gehören, wie Vorlagen für ein Design, Stockfotos oder Screenshots die als Anregung dienen sollen.

Ordner Struktur</p><pre>\docs
  \db
  \doku
\src
  \extern
  \libs
  \temp
  \public
   \images
   \css
   \js
   \flash
\misc</pre><p>

Ich hoffe dieser kleine Artikel hilft euch ein wenig mit dem Aufbau einer eigenen Struktur für eure Projekte.
Und wie immer - Feedback erwünscht.
