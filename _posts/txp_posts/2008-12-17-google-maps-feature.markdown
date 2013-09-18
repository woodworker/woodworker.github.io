---
layout: post
title: "Google Maps Feature"
date: 2008-12-17 08:35:46
comments: true
categories: JavaScript
---

<p>Falls ihr vor habt Google Maps auf eurer Seite einzusetzen, und dem Besucher eurer Seite evtl. ersparen wollt, das er immer erst sein Gebiet auf der Karte heraussuchen und groß Zoomen muss macht euch doch ein neues Feature der <span class="caps">AJAX API</span> von Google zunutze.</p>

<blockquote>When an application makes use of the <span class="caps">AJAX API</span> loader, the loader attempts to geo locate the client based on it's IP address. If this process succeeds, the client's location, scoped to the metro level, is made available in the google.loader.ClientLocation property. If the process fails to find a match, this property is set to null.<br />
<a href="http://code.google.com/intl/de/apis/ajax/documentation/#ClientLocation">Quelle</a>
</blockquote>

<p><strong>Beispiel</strong></p>
<pre><code>/**
 * Set the currentState_ and currentCountry_ properties based on the client's
 * current location (when available and in the US), or to the defaults.
 */
InTheNews.prototype.setDefaultLocation_ = function() {
  this.currentState_ = this.options_.startingState;
  if (google.loader.ClientLocation &amp;&amp;
      google.loader.ClientLocation.address.country_code == "US" &amp;&amp;
      google.loader.ClientLocation.address.region) {
    // geo locate was successful and user is in the United States. range
    // check the region so that we can safely use it when selecting a
    // state level polygon overlay
    var state = google.loader.ClientLocation.address.region.toUpperCase();
    if (InTheNews.stateNames[state]) {
      this.currentState_ = state;
    }
  }
  this.currentCountry_ = "US";
}</code></pre>

<p>Das heißt soviel, das wenn ihr die Karten API ladet, übernimmt Google für euch die Positionsbestimmung der Client. Ihr könnt diese Daten dann z.B. für das zentrieren eurer Karte, oder das Vorausfüllen von Eingabefeldern nutzen.</p>

<p>Ganz neben bei kann die AJAX API von Google noch einiges mehr. Ihr könnt euch euer jQuery oder moo Tools von dort laden, ja und auch die YUI Libary der "Konkurenz"</p>

<p><a href="http://code.google.com/intl/de/apis/ajax/documentation/">Google AJAX API</a><br />
<a href="http://code.google.com/intl/de/apis/ajaxlibs/documentation/">Google AJAXLibs API</a></p>
