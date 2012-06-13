---
layout: post
title: HTML5 Input Fields - The BlackBerry Playbook
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_long_string  }} - Melbourne</p>

One perk of Web Directions Code was the PlayBooks Blackberry handed out to all the 
developers. I've got plenty to say about it both as a device in general, and as a
target for app development, but for now lets stick to some details of it's HTML5 form support.

An outline of the basic form types can be found on the [blackberry site](http://docs.blackberry.com/en/developers/deliverables/26991/HTML_input_types_1247751_11.jsp), 
however there were a few differences I noticed in testing out the [different input field types](/tests/htmlforms.html).

URLs
----

The `url` input type gets .com and forward slash keys.

<img src="/img/2012-06-14_01.jpg" />

Passwords
---------

The `password` input types include a full keyset of numbers and letters, along with the addition 
of an asterisk key.

<img src="/img/2012-06-14_02.jpg" />


Phone Numbers
-------------

The `tel` input type gets a custom number pad input field.

<img src="/img/2012-06-14_03.jpg" />


Colour Picker
-------------

The `color` field type uses a system styled color picker, however it still returns and displays 
a hex color value (unlike Chrome which will show a color swatch).

<img src="/img/2012-06-14_04.jpg" />


Validation Message
------------------

One annoying thing I noticed was the title of validation messages. The example below shows the 
"pattern mismatch" title returned when the `pattern` attribute does not validate - not the most 
user friendly error message. Personally I'd prefer it just displayed the title specified on the 
input field. 

<img src="/img/2012-06-14_05.jpg" />


I think I'll have to play with this some more, perhaps dig into the shadow DOM some to see how 
much (if at all) these can be styled. 