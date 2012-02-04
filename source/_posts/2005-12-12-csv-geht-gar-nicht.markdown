---
layout: post
title: CSV geht gar nicht
wordpress_id: 27
wordpress_url: http://wp.codemo.de/?p=27
date: 2005-12-12 11:03:00.000000000 +01:00
---
<acronym title="Comma-separated Values">CSV</acronym> ist mit das schlimmste Format für Datenaustausch. Leider muß ich mich gerade damit auseinandersetzen, und lerne es immer mehr zu hassen. Denn wenn mal der Fall auftritt, das ein einem Feld Anführungszeichen **und** Trennzeichen vorkommen, dann kommt zumindest die <acronym title="Pfui,Hualp,Pfui">PHP</acronym>-Funktion &#8220;fgetcsv&#8221; so richtig durcheinander.

Kleines Beispiel:

    "1";"2";"3";"Ganz "toller" Text; heute mit Semikolon"

wird dann zu

    1
    2
    3
    Ganz "toller Text
    heute mit Semikolon"

An die Verwendung von explode() oder regulären Ausdrücken möchte ich gar nicht erst denken. In so einem Fall wäre XML mal wirklich angebracht.
