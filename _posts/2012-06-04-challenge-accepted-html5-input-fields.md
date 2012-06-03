---
layout: post
title: Challenge Accepted
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_long_string  }} - Melbourne</p>

At Web Directions Code, [Tammy Butow](http://twitter.com/tammybutow)  set a challenge 
for all the developers in the room:

- Create a mobile web page
- Add a HTML5 form
- Share it, and
- Have fun :)

I personally found it a great reminder for me to keep being interested in the evolution 
of the web, and to make sure I share the things I learn with others around me.

So where to start?
------------------

I've been using the various input types for a while now, but given the speed that things change 
I though it probably wise to revisit both the [WHATWG spec](http://developers.whatwg.org/the-input-element.html#the-input-element) and some [compatibility test results](http://www.quirksmode.org/html5/inputs.html) 
from the Quirks Mode site.

Here's a couple of things I picked up, you can test them out on [this sample HTML page](/tests/htmlforms.html).


The `title` attribute on input fields
-------------------------------------

I've never been a fan of the standard *"Please fill in this field"* errors you get shown in
browsers for input fields with a `required` attribute. But it turns out you can customise these 
using the title attribute. For example:

{% highlight html %}
<input type="text" pattern="[a-z](2)" title="Enter two letters" required />
{% endhighlight %}

The code above will add an extra line below the standard error message, allowing more descriptive 
errors to be shown.

This goes some way to making the `pattern` attribute more user friendly, as the standard *"Please 
match the format requested"* assumes prior knowledge of the required format. The example above 
shows how you might approach this to provide a little more feedback to users.

Keep in mind [this advice from the WHATWG spec](http://developers.whatwg.org/common-input-element-attributes.html#the-pattern-attribute) however:

> UAs may still show the title in non-error situations 
> (for example, as a tool-tip when hovering over the control), so authors should be careful not to word 
> titles as if an error has necessarily occurred.


The `multiple` attribute
------------------------

I was aware the multiple attribute could be used on `file` inputs, but it turns out this is also valid
for `email` input types. When used in this context, browsers will accept a valid comma separated list 
of values for the field (optionally tied to a data list as shown in the example below)

{% highlight html %}
<input type="email" multiple="multiple" name="cc" list="contacts" />
<datalist id="contacts">
     <option value="hedral@damowmow.com" />
     <option value="pillar@example.com" />
     <option value="astrophy@cute.example" />
     <option value="astronomy@science.example.org" />
</datalist>
{% endhighlight %}

I tested this example in Firefox 12 and Chrome 20, but there still appears to be some inconsistency 
between the two. 

Firefox would allow me to use a data list for values, but it would only work for the first email address, 
Subsequent ones received no suggestions.

More worrying was the inconsistent behaviour when the form was submitted. Chrome would strip extra 
white-space from the submitted values, whereas Firefox would include the extra spaces.


Random stuff
------------

Support for the `date` input type is [now kicking around](https://plus.google.com/102860501900098846931/posts/hTcMLVNKnec), 
with my version of Chrome on Ubuntu (20.0.1132.21 beta) supporting both `date` and `color` input field types 
using native UI elements. Not sure how much traction these will get until you are able to manage the 
css for these, the date picker has plenty of well established alternatives that give the developer 
complete control over styling.


In conclusion
-------------

So it turns out there's lots I don't know, partly due to everything being implemented to varying 
degrees by the various browser vendors.

I'd started looking at all this stuff on the [Playbook](http://blackberry.com/playbook-tablet/) 
we received from Black Berry at WDC12 (more on that soon), but didn't want this to go on 
forever. I'll save that for Part Two :)

