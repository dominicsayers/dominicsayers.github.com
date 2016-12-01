---
layout: post
title: RFC-compliant email address validator
date: 2009-01-28 18:05:51.000000000 +00:00
---
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="https://isemail.info" target="_blank">Email address validation service</a></h4>
There's a gazillion regular expressions out there that claim to validate an email address. They don't. Doug Lovell explains why <a href="https://www.linuxjournal.com/article/9585" target="_blank">here</a>. The function that Doug made for his article is good, but it delegates the validation of the domain part of the address to the DNS servers of the world. This is a good approach but there are three issues with it:
<ol>
	<li>The RFCs reluctantly allow you to use an IP address rather than a domain name, so you need to check for that.</li>
	<li>The DNS may not be available to your function at the time it needs to check the address (maybe it's an intranet application)</li>
	<li>There's no need to add extra workload to the DNS servers of the world if the address is wrongly formatted in the first place.</li>
</ol>
So I've come up with a PHP function that validates all parts of a given email address, according to RFCs <a href="https://tools.ietf.org/html/rfc1123" target="_blank">1123</a>, <a href="https://tools.ietf.org/html/rfc2396" target="_blank">2396</a>, <a href="https://tools.ietf.org/html/rfc3696#section-3" target="_blank">3696</a>, <a href="https://tools.ietf.org/html/rfc4291#section-2.2" target="_blank">4291</a>, <a href="https://tools.ietf.org/html/rfc4343#section-2.2" target="_blank">4343</a>, <a href="https://tools.ietf.org/html/rfc5321#section-4.1.2" target="_blank">5321 </a>&amp; <a href="https://tools.ietf.org/html/rfc5322#section-3.4.1" target="_blank">5322</a>. I've released it under a license that allows you to use it royalty-free in commercial or non-commercial work, subject to a few conditions (Doug Lovell's function is All Rights Reserved by Linux Journal so you can't use it for anything).

It's almost certainly the first email address validator that correctly lets you put an IPv6 address in for the domain part...

I've also included a lot of unit tests, including all Doug Lovell's examples and all the examples of valid addresses in RFC 3696. You might try running these test past your current email address validator. Prepare for the same nasty surprise I got :-)

The source code is available <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">here</a>.
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="https://isemail.info" target="_blank">Email address validation service</a></h4>
