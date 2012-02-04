---
layout: post
title: Rails regelt
wordpress_id: 20
wordpress_url: http://wp.codemo.de/?p=20
date: 2005-10-29 14:15:48.000000000 +02:00
---
Heute bin ich endlich mal dazu gekommen, mich ausgiebig mit [Ruby on Rails](http://www.rubyonrails.org) auseinanderzusetzen.

Ich hab zwar schon das [Rails-Buch](http://www.pragmaticprogrammer.com/titles/rails/index.html) und jede Menge How-Tos gelesen, aber heute hab ich zum ersten Mal eine komplett neue Applikation in Rails angefangen. Zwar nur eine sehr simple Sache mit 2 Datenbanktabellen, aber schon da merkt man, was man an Rails hat.

Am meisten hat mich beindruckt, was ich alles **nicht** programmieren mußte. Die Inhalte der Tabellen sollen vom Benutzer sortierbar sein, daher gibt es eine Spalte &#8220;position&#8221;, nach der sortiert wird. Während ich mir noch überlege, wie man das Verschieben am besten programmiert, finde ich den Abschnitt über &#8220;acts_as_list&#8221;. Wenn man das in einem Modell benutzt, daß eine Spalte &#8220;position&#8221; hat, bekommt man automatisch ein paar nützliche Funktionen dazu, unter anderem first?, last?, move_higher und move_lower.</p>

Dadurch ist die Verschiebe-Funktion im Controller gerade mal 3 Zeilen lang, wovon eine Zeile der Redirect auf die Übersichtsseite ist.

Mit Rails zu programmieren ist echt eine Freude. So viel Spaß am coden hatte ich schon lange nicht mehr.
