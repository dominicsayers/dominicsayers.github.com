---
layout: post
title: Domain name geekery
date: 2009-01-27 10:31:01.000000000 +00:00
---
If you're not technical, there's nothing to see here. Move along please.

OK, I'm writing an email address validation function. Why? Because everybody else has and why should I be different? The catch is, I'm trying to make it RFC-compliant rather than use the same noddy regular expressions everybody else does.

Ask me anything you like about RFCs <a href="http://tools.ietf.org/html/rfc1035#section-2.3.1" target="_blank">1035</a>, <a href="http://tools.ietf.org/html/rfc2396" target="_blank">2396</a>, <a href="http://tools.ietf.org/html/rfc3696#section-3" target="_blank">3696</a>, <a href="http://tools.ietf.org/html/rfc4291#section-2.2" target="_blank">4291</a>, <a href="http://tools.ietf.org/html/rfc4343#section-2.2" target="_blank">4343</a>, <a href="http://tools.ietf.org/html/rfc5321#section-4.1.2" target="_blank">5321 </a>&amp; <a href="http://tools.ietf.org/html/rfc5322#section-3.4.1" target="_blank">5322</a>. Go on.

Try this one: RFC 1035 says the following:
<blockquote>
<pre class="newpage">The labels must follow the rules for ARPANET host names.  They must
start with a letter, end with a letter or digit, and have as interior
characters only letters, digits, and hyphen.</pre>
</blockquote>
(A label is a component of a domain name, i.e. the "example" in example.com)

So is <a href="http://3com.com/" target="_blank">3com.com</a> a valid domain name? No? Somebody should tell them.
