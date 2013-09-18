---
layout: post
title: "Die Qual der Wahl"
date: 2010-04-09 20:25:10
comments: true
categories: Programmierung
---

Für ein kleines Projekt das ich gerade dabei bin "hochzuziehen" bin ich gerade am überlegen wie ich meine Klassen Strukturieren. Früher war ich ein wirklicher Verfechter und Anhänger des PEAR Naming Schemas. Problem ist nur die wundervolle Aussicht auf viele, viele, Dateien nur für ein Modul mit ein paar Klassen, Exceptions und Interfaces.

Doch jetzt dachte ich mir, da ich eh alles in einzelne Pakete verpacke und ich PHP 5.3 nutze - JAY - hau ich mir wie es die ezComponents machen eine Hauptdatei die dann die Klassen, Exceptions und Interfaces lädt. Dann kann ich schauen ob ich alle Interfaces oder nur die jeweils Logisch zusammengehörenden zusammen in eine Datei packe. Wobei alle Interfaces in einer Datei wohl eher nur bei kleineren Modulen geschehen wird. Meine Exceptions werden ebenso alle zusammen gepackt und die Klassen bekommen nach wie vor ihre eigenen Dateien.

Soviel zu meinen Gedankengängen und kurz gesagt, ich lerne doch noch dazu und eine Lösung/Standard ist nicht immer der beste weg.
