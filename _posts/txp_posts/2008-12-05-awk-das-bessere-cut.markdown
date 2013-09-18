---
layout: post
title: "AWK, das bessere CUT "
date: 2008-12-05 15:51:39
comments: true
categories: Linux
---

Falls ihr euch immer geärgert habt das [cut](http://de.wikipedia.org/wiki/Cut_(Unix)) immer nur ein und nicht mehrere Zeichen zum auseinander schneiden 
unterstützt, dann nehmt doch awk.
[Awk](http://de.wikipedia.org/wiki/Awk) unterstüzt dieses udn noch viel mehr.

Awk hat den Konsolenschalter "-F" dem eine beliebige Zeichenkette übergeben werden kann. Nach dieser Zeichenkette splittet awk dann den String auf.
Dann müsst ihr nur noch die gewollten Teile ausgeben mit "print".

Beispiel:

```awk -F"delim" '{print $1; print $2; print $3}' testfile```
