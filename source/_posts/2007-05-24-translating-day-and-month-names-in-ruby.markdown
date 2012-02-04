---
layout: post
title: Translating day  and month names in Ruby
wordpress_id: 55
wordpress_url: http://wp.codemo.de/?p=55
date: 2007-05-24 08:26:00.000000000 +02:00
---
A few days ago, I ran into a problem translating the day and monthnames in the ruby &#8220;Date&#8221; class. The howtos I read recommended using replace to modify the array constants. That did not work, because these days, those arrays are frozen, making them immutable.

My first solution was to just comment out the part, where the arrays are frozen, but then everyone working on the code has to fiddle with the core ruby installation. Not a very clean solution.

Luckily, I found the [remove_const](http://www.ruby-doc.org/core/classes/Module.html#M001715) method. Using that, the constants in Date can be easily exchanged for the translated version:

``` ruby
Date.send(:remove_const, "ABBR_DAYNAMES")
Date.const_set("ABBR_DAYNAMES", [ _("sun"), _("mon"), _("tue"), _("wed"), _("thu"), _("fri"), _("sat") ])
Date.send(:remove_const, "DAYNAMES")
Date.const_set("DAYNAMES", [_("Sunday"), _("Monday"), _("Tuesday"), _("Wednesday"), _("Thursday"), _("Friday"), _("Saturday") ])
Date.send(:remove_const, "ABBR_MONTHNAMES")
Date.const_set("ABBR_MONTHNAMES", [nil, _("Jan"), _("Feb"), _("Mar"), _("Apr"), _("May"), _("Jun"), _("Jul"),_("Aug"),_("Sep"), _("Oct"), _("Nov"), _("Dec") ])
Date.send(:remove_const, "MONTHNAMES")
Date.const_set("MONTHNAMES", [nil, _("January"), _("February"), _("March"), _("April"), _("May"), _("June"), _("July"),_("August"),_("September"), _("October"), _("November"), _("December") ])
```