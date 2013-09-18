---
layout: post
title: "Webservice - SOAP vs. REST"
date: 2008-11-24 13:09:47
comments: true
categories: Programmierung
---

Da ich mich schon selber gerne mit Webservices/Webdiensten beschäftige und ich auch immer wieder die Diskussion zum Thema "SOAP ist Tot, es lebe REST" mitverfolgt habe, möchte ich das Thema einmal aus meiner Blickweise aufzeigen.

Zu erst einmal eine Auflistung von Vor- und Nachteilen der Beiden Webservice Varianten.

### SOAP

#### Vorteile

* fest definierter Standard
* In vielen Programmiersprachen implementiert

#### Nachteile

* bei einigen Sprachen müssen WSDL Dateien selber erzeugt werden (XML!=Menschenlesbar)

### REST

#### Vorteil

* Einfach und schnell zu implementieren (Client und Server)

#### Nachteil

* Keine Standards für Parameterübergabe und Rückgabe


### Mein Blick auf SOAP

Ich sehe SOAP für die größeren Business-Anwendungen klar im Vorteil, wegen dem hohen Grad an Standardisierung und der bereits hohen Durchdringung in diesem Marktsegment. Geschäftslogik lässt sich mittels SOAP aus meiner Sicht viel einfacher umsetzen.

&rArr; Also wenn schon eine Große Anwendung vorhanden ist und diese in einem Intranet/Extranet genutzt werden soll ist die Umsetzung als SOAP Webdienst aus meiner Sicht das einzig richtige.

### Mein Blick auf REST

Wegen der einfachen Implementierbarkeit von REST Anwendungen sehe ich das Hauptgebiet von REST in der Webfrontend Entwicklung und den Bereichen in denen viele "Enduser" eine API eines Dienstanbieters nutzen wollen.

&rArr; Wenn also viele Benutzer (im Internet) auf Daten zugreifen sollen, finde ich die Umsetzung als REST Webservice ein bedeutend Besseren Schritt.

### Mein Abschlusssenf

Ich persönlich sehe weder SOAP noch REST tot, noch sonst irgendwie auf einem absterbenden Ast. SOAP und REST haben beide ihre Berechtigung zu existieren. 
Und nein ich will nicht sagen das REST nicht für den Unternehmenseinsatz geeignet ist, sondern einfach das SOAP besser geeignet ist für das Abbilden von Geschäftsprozessen und nein SOAP ist nicht schlecht für eine Große Benutzeranzahl aber REST hat hier klare Vorteile in der Skalierbarkeit.
