---
layout: post
title: light@the.end.of.the.tunnel
date: 2009-02-24 12:10:29.000000000 +00:00
---
<h4>Quick links: <a href="http://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="http://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
The amazingly helpful Cal Henderson has nearly caught up in the arms race that is email address validation. After our latest round of discussions we disagree about only one of the 161 test cases in the test suite. Cal's validator successfully validates all the test cases except that one (and he may be right about it -we'll see).

I've released version 1.3 of my validator and you can <a href="http://code.google.com/p/isemail/source/browse/trunk" target="_blank">download</a> it with the test cases from Google Code.
<h4>RFC nerd notes</h4>
I had a lesson from Cal on Folding White Space. Who knew that you could have an email address that was split over several lines? Please don't run out and try this - it's strictly for completeness.

Secondly, all those validators out there that use <a href="http://tools.ietf.org/html/rfc2822" target="_blank">RFC2822</a> as their authority: those are <em>yesterday's</em> validators. All the cool kids are validating using <a href="http://tools.ietf.org/html/rfc5322" target="_blank">RFC5322</a>. It's the latest thing.
<h4>Quick links: <a href="http://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="http://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
