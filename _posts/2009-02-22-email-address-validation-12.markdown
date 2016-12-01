---
layout: post
title: Email address validation 1.2
date: 2009-02-22 15:25:24.000000000 +00:00
---
<h4>Quick links: <a href="http://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="http://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
I had some very helpful input from Cal Henderson on interpreting RFC 2822. I've included his latest validator in my head-to-head comparison and updated the test suite to reflect the consensus from our discussion.

I've also updated my own routine so that it still passes all the tests, of which there are now 158. As always, the <a href="http://www.dominicsayers.com/isemail/" target="_blank">full analysis</a> is on my website and the <a href="http://code.google.com/p/isemail/source/browse/trunk" target="_blank">latest version of the source code</a> will always be in Google Code.

I would really appreciate it if you find a valid address that fails my validator, or an invalid one that passes, if you would get in touch with me and let me know.

Here are the latest scores:

Dominic Sayers: <strong>100% validated correctly
<span style="font-weight:normal;">Simon Slick: <strong>91</strong><strong>%</strong>
Cal Henderson: <strong>84</strong><strong>%
</strong></span></strong>Phil Haack: <strong>80</strong><strong>%
<span style="font-weight:normal;">Dave Child</span><span style="font-weight:normal;">: </span>79</strong><strong>%</strong>

<strong><span style="font-weight:normal;">I know Cal is working on IPv6 validation so this may change soon.</span></strong>
<h4><strong></strong>RFC nerd notes</h4>
There are two principle changes in this version.

Firstly, I now accept Dave Child and Cal Henderson's opinion that a backslash can escape <em>anything</em> in a quoted string local element. However, it must escape something - it can't be at the end of the string.

Secondly, if the string is <em>not</em> quoted then the local element must be a vanilla atom. You can't escape individual characters unless the element is surrounded by double quotes.

By "local element" I mean a single component of a dot-delimited local part.

I've extracted the raw specification of a valid email address in BNF (<a href="http://en.wiktionary.org/wiki/Backus-Naur_form">Backus-Naur form</a>) from RFC 5322 and put it here: <a href="http://www.dominicsayers.com/isemail/isemail/RFC5322BNF.html">The BNF from RFC 5322 defining parts of a valid email address</a>. If you try to follow this in the RFC you end up going backwards and forwards and getting confused - it's much easier to understand in the way I've laid it out.
<h4>Quick links: <a href="http://code.google.com/p/isemail/source/browse/trunk" target="_blank">Source code</a> | <a href="http://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
