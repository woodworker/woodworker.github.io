---
layout: post
title: "Reguläre Ausdrücke und Umlaute"
date: 2008-06-06 08:01:15
comments: true
categories: PHP
---

Keine Ahnung wem das schon alles auf die Füße gefallen ist, mir ist es gestern, Was macht man mit Umlauten wenn man mit Regulären Ausdrücken arbeitet?
Naja wenn man die PHP Manual liest, oder besser gesagt die meist viel interessanteren Komentare, findet man recht schnell eine Lösung.

*Lösungsansatz 1.*

{% highlight php %}
<?php
setlocale (LC_ALL, 'de_DE');
$match = preg_match("/^[[:alpha:]]+$/", $data);
?>
{% endhighlight %}

Was hier genau gemacht wird ist halt das System auf "Deutsch" umzustellen und somit wird auch der Inhalt der RegExp Zeichenklasse ":alpha:" mit den deutschen Umlauten gefüttert. Die Lösung ist eigentlich schon recht brauchbar.

Was macht man aber wenn auf irgend eine Weise ein Franzose oder ein Spanier sich auf die Webseite "verirrt" hat, oder sogar mit purer Absicht auf eure Seite gekommen ist. Da haben wir ja alle gelernt das UTF-8 so richtig dolle toll ist wenn es um Mehrsprachigkeit geht.
Und UTF-8 ist auch das Zauberwort für *Lösung Nummer 2.*

{% highlight php %}
<?php
$match = preg_match("/[\w\p{L}]/u",$data);
?>
{% endhighlight %}
 

Hier wird zum einen mit dem Modifier "u", Achtung kleines u ein Großes U hat wiederum eine andere bedeutung, die UTF-8 fähigkeit der Regulären Ausdrücke in PHP eingeschalten und zum anderen per "\p{L}" sagen wir das jede Unicode Sequenz die ein Buchstabe ist zutreffen soll.

Hier nochmal einige weiterführende Links:

* [Lösung 1 (setlocale)](http://de.php.net/manual/en/function.preg-match.php#49926)
* [Lösung 2 (Unicode)](http://de.php.net/manual/en/function.preg-match.php#68974)
* [RegExp Unicode Refernz in der PHP Manual](http://de.php.net/manual/en/regexp.reference.unicode.php)
