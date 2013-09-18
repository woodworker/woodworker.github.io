---
layout: post
title: "MySQL String Spickzettel"
date: 2008-11-17 11:58:09
comments: true
categories: MySQL
---

Neben dem Spickzettel für die [MySQL Integer Größe](/blog/2008/06/26/mysql-integer-spickzettel) habe ich mir nun noch ein für die MySQL 
TEXT/BLOB Größe gemacht.

#### CHAR / BINARY

Größe festgelegt durch die Anzahl der Zeichen, aber maximal 255 Zeichen.
Also immer ein Festwert, egal ob gefüllt, halb gefüllt oder leer.

#### VARCHAR / VARBINARY

Definierte Feldgröße:
 * von 0-255 Zeichen: Anzahl der Zeichen + 1 Byte
 * von 256-65532 Zeichen Anzahl der Zeichen + 2 Byte

Also ein VARCHAR (500) brauch für das abspeichern von "abcd" ein Byte mehr Platz als ein VARCHAR (200).

#### TINYTEXT / TINYBLOB

Größe: < 2 ^8^ Byte (+ 1 Byte MySQL)
daraus ergibt sich max. 255 (Ein-Byte[1] ) Zeichen

#### TEXT / BLOB

Größe: < 2 ^16^ Byte (+ 2 Byte MySQL )
daraus ergibt sich max. 65535 (Ein-Byte[1] ) Zeichen oder ungefähr 64 KByte

#### MEDIUMTEXT / MEDIUMBLOB

Größe: < 2 ^24^ Byte (+ 3 Byte MySQL)
daraus ergibt sich max. 16777216 (Ein-Byte[1] ) Zeichen oder ungefähr 16 MB

#### LONGTEXT / LONGBLOB

Größe: < 2 ^32^ Byte (+4 Byte MySQL)
daraus ergibt sich max. 4294967296 (Ein-Byte[1] ) Zeichen oder ungefähr 4 GB

----------------------

Ein Byte Zeichen deswegen weil sich die Anzahl der Zeichen bei Unicode-/Nicht ASCII-Zeichen entsprechend verringert.

* *1 Byte* je Zeichen benutzt das normale *Latin*
* *2 Byte* je Zeichen benutzen die meisten *Europäischen Sprachen mit Umlauten*, Akzenten usw.
* *3 Byte* je Zeichen werden nur von *chinesischen , koreanischen und japanischen Schriftzeichen* benutzt.

Daraus folgt in einem Normalen "TEXT" können "nur" 21845 Chinesische oder 32767 "Normale" Nicht ASCII Zeichen untergebracht werden. Deswegen nochmal die Angabe in Byte
