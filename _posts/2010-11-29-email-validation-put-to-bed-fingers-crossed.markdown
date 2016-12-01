---
layout: post
title: Email validation put to bed (fingers crossed)
date: 2010-11-29 19:30:47.000000000 +00:00
---
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="https://isemail.info" target="_blank">Email address validation service</a></h4>
[UPDATED 15 March 2011]

In an attempt to draw a line under my efforts to validate email addresses properly, I've rewritten <em>is_email()</em> from scratch. It's now ready for public inspection <del>although not quite ready for release</del>.

<del>The beta version can be downloaded from here: <a href="https://code.google.com/p/isemail/source/browse/PHP/beta">https://code.google.com/p/isemail/source/browse/PHP/beta</a></del>

<del>More interestingly, there's a test page here <a href="https://www.dominicsayers.com/source/beta/is_email/test">https://www.dominicsayers.com/source/beta/is_email/test</a> where you can try your own favourite edge and corner cases. Click on <a href="https://www.dominicsayers.com/source/beta/is_email/test/?all" target="_blank">Run All Tests</a> to see the tests cases compiled by me and Michael Rushton.</del>

The version 3.0 code has now been released <a href="https://isemail.googlecode.com/" target="_blank">here</a>. You can validate email addresses <a href="https://isemail.info" target="_blank">here</a>. And you can see the test cases run against the validator <a href="https://isemail.info/_system/is_email/test/?all" target="_blank">here</a>.

What you can now see is
<ul>
	<li>Exactly what's wrong with the address (if anything)</li>
	<li>Is it valid for a normal use case (e.g. validating a registration form)</li>
	<li>Under what circumstances you can use it</li>
	<li>The appropriate ABNF code from the RFCs that define acceptable email addresses</li>
</ul>
Much of the code is now data driven so I can add new test cases and enhance the analysis without rewriting it.

It's all free.
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="https://isemail.info" target="_blank">Email address validation service</a></h4>
