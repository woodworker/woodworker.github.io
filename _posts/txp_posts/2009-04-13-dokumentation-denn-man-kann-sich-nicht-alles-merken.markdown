---
layout: post
title: "Dokumentation, denn man kann sich nicht alles Merken."
date: 2009-04-13 18:48:01
comments: true
categories: projektmanagement
---

Hier nun der dritte Artikel meiner Serie "Projektmanagement in kleinen Projekten".  Ich würde mich auch hier wieder über Feedback freuen.

In diesem Artikel geht es wie ihr evtl schon am Titel gesehen haben und das wahnsinnige Interessante und total von allen geliebte Thema Dokumentation. OK, dem einen oder anderen ist der Hauch Sarkasmus aufgefallen. 
Jetzt werden sich einige Programmierer denken, ja ich Dokumentiere doch mit PHPDoc, JavaDoc, SonstwasDoc. Ja das ist auch Dokumentieren, aber diese Dokumentation ist nur für euch oder wenn ihr für Kunden arbeitet, deren Programmierer hilfreich. Ich möchte diese Dokumentation auf keinen Fall runterspielen, ich sage nur es ist nur einer von vielen Punkten wo in einem Projekt dokumentiert wird. Dokumentation übersteigt nunmal die einfache Quelltext-Dokumentation bei weitem. In einem guten Projekt kann man alle wichtigen und interessanten Dinge in einer Projektdokumentation nachschlagen.
Denn alle einfachen Handlungen und vorallem auch komplexere Aufgaben in einer Software sollten Dokumentiert sein, so das später sich neue Benutzer sehr einfach in das Stück Software einlesen können. Bei kleinen Projekten macht das meist sogar noch einen größeren Ausschlag. Denn wollt ihr jedem neuen User der Software erklären wie man dies, das oder jenes bewerkstelligt?
Hier würde eine gute und vorallem auch aktuelle Dokumentation für den End-User oder den Admin viel Probleme vereinfachen oder sogar lösen. Und aktuell kann ich nicht oft genug sagen und nicht weit genug hervorheben. Denn nichts ist so schlecht wie eine veraltete und dadurch falsche Dokumentation. Sogar keine Dokumentation wäre in diesem Fall besser als eine Falsche, was wir aber natürlich garnicht erst anfangen wollen. Eine veraltete Dokumentation kann zu Fehlbedienungen des Programms und im Extremfall sogar zu Problemen mit dem Programm führen. Nicht nur einfache "Es geht nicht"-Probleme sondern auch "Upps, warum ist das jetzt abgestürzt"-Probleme. Deshalb Dokumentation immer aktuell halten.

So genug zum warum wir Dokumentieren sollten jetzt zum Praktischen Teil, wie wir Dokumentieren wollen. Wie ich bereits erwähnt habe ist die Quelltextdokumentation nur ein Punkt unter vielen in der kompletten Dokumentation. Und da dieser Punkt einer der unter Programmierern bekannteste und auch am besten ausgebaute im Internet ist werde ich mich hier auf einen kurzen Satz dazu beschränken. Macht es, dokumentiert euren Quelltext! So das soll es dazu gewesen sein.
Nun erstmal eine kleine Übersicht was man so alles in einem Projekt dokumentieren kann: Installation, Konfiguration, Updaten, Benutzung als Admin, Benutzung als User, Information für Anpassungen usw. Je nach Projekt kommen dann noch einzelne Handbücher für die einzelnen Benutzerebenen wie Moderatoren oder Redakteure.
Ihr solltet beim Dokumentieren darauf achten das ihr immer schon für die in Entwicklung befindliche Version schreit, so das ihr mit jeder herausgegebenen Version auch gleich die Fertige Dokumentation ausliefern könnt. Und die Dokumentation am besten auch in einem relativ einfachen Format schreiben, so das es auch in der Versionsverwaltung mit aufgenommen werden kann und dort auch gedifft werden kann.
Für das schreiben lohnt sich meist LaTeX oder wenn man den Overkill des lernen von LaTeX nicht haben will gibt es auch noch eine einfache Variante: [reStructuredText](http://docutils.sourceforge.net/rst.html)

So da wir nun wissen was wir wie dokumentieren können gibt es nun noch ein paar Tipps zum Strukturieren der Dokumentation. Die Struktur sollte immer so gehandhabt werden, das alles in Logische Einheiten aufgespalten wird. Klingt logisch aber es sollte erwähnt werden. Wenn sich Themen in der Dokumentation überschneiden, immer auf den entsprechenden Abschnitt in der Dokumentation verweisen und nicht doppelten Text verfassen. Doppelte Text führen beim Updaten der Dokumentation nur dazu das sie im schlimmsten Fall ein und den selben Sachverhalt grundverschieden erklären. Daher wie im Netz, immer verlinken.
Die logischen Bereiche sind nach meiner Erfahrung am besten so kurz wie möglich zu halten und sich wirklich auf die Aufgabe konzentrieren die man gerade beschreibt. Denn derjenige der die Dokumentation liest will nichts davon wissen was man denn noch so alles in Menü X anstellen kann sondern er liest den Abschnitt weil er genau das wissen will was die Überschrift verspricht. Und genau deswegen sollten Überschriften in der Dokumentation, wie eigentlich auch sonst überall, gut gewählt und treffend sein. Denn wenn jemand eine Dokumentation liest, ist es meine Erfahrung, das er etwas ganz spezielles wissen will. Ich persönlich habe noch nie jemanden erlebt der gesagt hat: So ich lese mir mal die Komplette Dokumentation für Ding X durch.
Ein weiterer Tipp ist, wenn ihr ein Grafisches Programm habt, bebildert die Dokumentation denn nach wie vor gilt: Ein Bild sagt mehr als tausend Worte. Und vorallem im Bereich der Softwaredokumentation ist eine bebilderung hilfreich. Aber auch hier gilt wieder sie müssen IMMER Aktuell sein und das wirkliche Abbild des Programms zeigen, den auch hier kann wieder extrem viel Frust entstehen wenn die Bilder in der Dokumentation nicht mit denen die man als Benutzer selber sieht übereinstimmen.

Also nun zu guter letzt eine Zusammenfassung für alle die, die es nicht ertragen können meine schreklichen Schachtelsätze zu lesen.

1. Für alle Benutzergruppen (einzeln) Dokumentieren
2. Dokumentation IMMER aktuell halten
3. Screenshots und Bilder sind immer gut
4. Wie alles, auch die Dokumentation Versionieren
5. Dokumentation immer kurz und treffend halten
und der wichtigste Punkt: Dokumentiert, tut es einfach

