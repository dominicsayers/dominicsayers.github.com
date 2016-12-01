---
layout: post
title: Email address validation 1.0
date: 2009-02-20 10:39:14.000000000 +00:00
---
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="https://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
OK, after some correspondence with <a href="https://www.addedbytes.com/blog/email-address-validation-v2/" target="_blank">Dave Child</a> and <a href="https://code.iamcal.com/php/rfc822/" target="_blank">Cal Henderson</a> I have now released version 1.0 of my PHP email address validator.

This version passes all 139 unit tests in the suite - tests I have collated from <a href="https://www.apps.ietf.org/rfc/rfc3696.html" target="_blank">RFC 3696</a> and from articles by Dave Child, <a href="https://www.linuxjournal.com/article/9585" target="_blank">Doug Lovell</a> and <a href="https://haacked.com/archive/2007/08/21/i-knew-how-to-validate-an-email-address-until-i.aspx" target="_blank">Phil Haack</a> plus some of my own to test the IPv6 address format. The <a href="https://www.dominicsayers.com/isemail/" target="_blank">full analysis</a> is on my website and the <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">latest version of the source code</a> will always be in Google Code.

I would really appreciate it if you find a valid address that fails my validator, or an invalid one that passes, if you would get in touch with me and let me know.

Here are the scores on the doors:

Dominic Sayers: <strong>100% validated correctly</strong>
Simon Slick: <strong>86%</strong>
Dave Child: <strong>81%</strong>
Phil Haack: <strong>79%</strong>
Cal Henderson: <strong>71%</strong>

For the RFC nerds, this version now correctly validates the obsolete local form of <em>word *("." word)</em>. In other words you can regard the local part of the address as a dot-delimited series of elements each of which can be separately quoted. This means that <em>first."last"@example.com</em> is now recognised as a valid address.
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="https://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
