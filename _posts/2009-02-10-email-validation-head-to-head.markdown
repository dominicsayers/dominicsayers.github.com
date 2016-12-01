---
layout: post
title: Email validation head-to-head
date: 2009-02-10 12:42:05.000000000 +00:00
---
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="https://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
I've discovered a number of other public-domain functions that attempt to validate the format of an email address. I tried to validate my 124 test cases against these functions with the results below:

<a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Dominic Sayers</a>: 100% correctly validated
<a href="https://simonslick.com/VEAF/" target="_blank">Simon Slick</a>: 88% 
<a href="https://code.google.com/p/php-email-address-validation" target="_blank">Dave Child</a>: 80%
<a href="https://code.iamcal.com/php/rfc822/" target="_blank">Cal Henderson</a>: 72%

Interestingly, all the other functions failed correctly to validate the example addresses given in <a href="https://www.apps.ietf.org/rfc/rfc3696.html#sec-3" target="_blank">RFC3696</a> (Section 3: Restrictions on email addresses).

I couldn't include Doug Lovell's <a href="https://www.linuxjournal.com/article/9585" target="_blank">function</a> in my tests because the code is copyright All Rights Reserved by Linux Journal (ironically).

Some of the other functions also supply test cases; I've added these to my test suite. More analysis and commentary here: <a href="https://www.dominicsayers.com/isemail/" target="_blank">RFC-compliant email address validator</a>.

In summary, I recommend you use my function if you want totally RFC-compliant address validation.
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="https://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
