---
layout: post
title: "RDFa oder wie die Semantik in die Seite kommt."
date: 2009-01-14 13:44:43
comments: true
categories: Programmierung
---

Wir alle kennen ja die [Microformats](http://microformats.org/). Dort werden ja über die Verwendung von genormten HTML Tags und CSS-Klassennamen ja Inhalte einer Seite einigermaßen maschinenlesbar gemacht. Dies ist nun aber nicht wirklich eine schöne Sache wenn man Inhalte Semantisch hinterlegen will und für den Menschen auch noch angenehm und gut lesbar machen möchte/muss.
Ausserdem gibt es da noch [RDF](http://de.wikipedia.org/wiki/Resource_Description_Framework), das [Resource Description Framework](http://de.wikipedia.org/wiki/Resource_Description_Framework), das sich zur aufgabe gemacht hat über XML Inhalte komplett maschinenlesbar zu gestalten. Und da RDF ein XML Dialekt ist nicht wirklich für menschliche Endkunden geeignet.
Nun hat sich das [W3C](http://w3c.org) gedacht das die "normale" Benutzerschnittstelle im Web, die Webseite, auch mit maschienenlesbaren Metadaten zu versehen, ohne dem Webseiten eigentümer HTML Konstrukte aufzuzwingen wie es bei den Microformats ist.
Herausgekommen ist mit [RDFa](http://www.w3.org/TR/xhtml-rdfa-primer/). Eine RDF Version für XHTML die dort mit Annotationen arbeitet die in einem externen Namespace definiert werden. So können einfache Beschreibungstexte mittels Tags versehen werden die wiederum die Metadaten enthalten. Diese Tags müssen nichteinmal einen gewissen Inhalt haben sondern können auch für den Menschen "verborgen" in der Seite liegen.
So kann z.B. aus dem Satz "Ich lese gerade das tolle Buch, Die Zwerge, von
meinem Lieblingsautor Markus Heitz." mittels RDFa wunderbar einfach die Informationen für das Buch und den Author hinterlegt werden.

{% highlight xml %}
<p xmlns:dc="http://purl.org/dc/elements/1.1/"
   about="http://www.mahet.de/site/13.0.html">
Ich lese gerade ein tolles Buch, <cite property="dc:title">Die Zwerge</cite>, von
meinem Lieblingsautor <span property="dc:creator">Markus Heitz</span>
</p>
{% endhighlight %}

Keine Einschränkungen an die verwendeten HTML Tags oder CSS Klassen. Das war jetzt mal ein einfaches Beispiel mit der Verwendung des Dublin Core. Über RDFa lässt sich alles was für RDF erdacht wurde auch in "normalen" Webseiten verweden.
Ein weiteres Beispiel wäre hier das [Friend of a Friend Projekt](http://www.foaf-project.org/). Hier lassen sich mittels RDF Daten Beziehungen zwischen Personen anzeigen und veröffetnlichen. Eine Art dezentrales XING, wenn man so will.

Also meine Empfehlung, beim nächsten Projekt mal ein kleinen Blick auf RDFa werfen und überlegen ob man nicht ein wenig mehr Semantik in das Web bringen kann. Schaden kann es nicht.

_Edit:_
Als Anmerkung muss ich jetzt leider noch machen, das RDFa nur mit XHTML Funktioniert

*Links:*
[Microformats](http://microformats.org/)
[RDF](http://de.wikipedia.org/wiki/Resource_Description_Framework)
[RDFa](http://www.w3.org/TR/xhtml-rdfa-primer/)
[Friend of a Friend](http://www.foaf-project.org/)
