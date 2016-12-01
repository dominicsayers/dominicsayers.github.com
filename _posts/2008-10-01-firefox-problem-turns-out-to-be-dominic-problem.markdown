---
layout: post
title: Firefox "problem" turns out to be Dominic problem
date: 2008-10-01 12:11:22.000000000 +01:00
---
Big thanks to <a href="https://thingamy.typepad.com/" target="_blank">Sig</a> for helping me out with my Firefox CSS issue. He was dead right - it was a MIME issue that was easily fixed by setting the MIME type to text/css in the header of the dynamic CSS.
<p style="text-align:left;">More details here: <a href="https://www.digital-web.com/articles/generating_dynamic_css_with_php/"><em>Generating Dynamic CSS with PHP</em></a></p>

I've left the demonstration in place here: <a href="https://www.dominicsayers.com/cssmime"><em>Dynamic CSS MIME demonstration</em></a> but adjusted the text to make it clear I was at fault, not the browser.

Why do the other browsers behave differently? Well the CSS was returned to the page within an element of the page's header that declared the contents to be text/css so it was fairly easy for a "smart" browser to guess my intention. And also quite easy for me to make the fatal assumption that that was enough.

We live and learn. And Firefox is a strict mistress.
