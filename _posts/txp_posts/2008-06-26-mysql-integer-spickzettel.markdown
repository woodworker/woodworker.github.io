---
layout: post
title: "MySQL Integer Spickzettel"
date: 2008-06-26 11:19:06
comments: true
categories: MySQL
---

So damit ich es mir endlich mal merke und nicht jedes mal nach schauen muss habe ich hier mal die 5 Integer Felder der MySQL Datenbank in einer Kurzzusammenfassung zusammengestellt mit Namen, dem Wertebereich für Vorzeichen behaftet (signed) und ohne Vorzeichen (unsigned).

#### TINYINT

Größe: 8 Bit
signed: von -128 bis 127
unsigned: von 0 bis 255

#### SMALLINT

Größe: 16 Bit
signed: von -32768 bis 32767
unsigned: von 0 bis 65535

#### MEDIUMINT

Größe: 24 Bit
signed: von -8388608 bis 8388607
unsigned: von 0 bis 16777215

#### INT oder INTEGER

Größe: 32 Bit
signed: von -2147483648 bis 2147483647
unsigned: von 0 bis 4294967295

#### BIGINT

Größe: 64 Bit
signed: von -9223372036854775808 bis 9223372036854775807
unsigned: von 0 bis 18446744073709551615

Arithmetische Funktionen sollte nicht auf BIGINTs die selbst größer 63 Bit (9223372036854775807) sind oder deren Ergebnisse größer der besagten 63 Bit sind angewendet werden, da sonst Rundungsfehler auftreten können ,da MySQL dann mit DOUBLE werten arbeitet
