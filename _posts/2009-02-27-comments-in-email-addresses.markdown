---
layout: post
title: Comments in email addresses
date: 2009-02-27 10:28:17.000000000 +00:00
---
<h4>Quick links: <a href="http://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="http://isemail.info/" target="_blank">Email address validation service</a></h4>
[UPDATE 15 March 2011: see my comment below]

I was turning a blind eye to the part of <a href="http://tools.ietf.org/html/rfc5322" target="_blank">RFC5322</a> that allows you to put comments <em>within</em> an email address. But <a href="http://www.iamcal.com/help/cal/" target="_blank">Cal H</a> brought it up in an email so I had to bite the bullet.

On reflection I think this was worthwhile. The most common error in email address validators is that they reject valid addresses. This really annoys people who like to put a '+' in their address and find they can't because registration form won't allow it.

Why do they like putting a '+' in their address? Well it effectively tags the incoming email for you automatically. Mail sent to <em>first.last+hello@example.com</em> will go to the <em>first.last</em> mailbox, tagged with 'hello'. GMail will do this for you - try it.

So that's why I think it's worth allowing comments. The next GMail might be able to do the same thing or something even more useful with comments:

<em>first.last(notify IM)@example.com</em>

Version 1.6 of my validator now passes all 222 unit tests. So does Cal's. I see no reason why you wouldn't use one of these in your project: they are free and they work. Why reinvent the wheel?
<h4>RFC nerd notes</h4>
Comments can contain folding white space and can be nested. This is the final nail in the coffin for regular expressions that claim to validate email address. Show me a regex that says this is a valid address:

<em>first(Welcome to
the ("wonderful" (!)) world
of email)@example.com</em>

A thank-you also to Paul Gregg who allowed me to add his validator to the head-to-head (and added mine to <a href="http://www.pgregg.com/projects/php/code/showvalidemail.php" target="_blank">his page</a>). He also provided some more unit tests.
<h4><em><span style="font-style: normal;">Quick links: </span><a href="http://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank"><span style="font-style: normal;">Source code</span></a><span style="font-style: normal;"> | </span></em><a title="Email address validation" href="http://isemail.info/" target="_blank">Email address validation service</a></h4>
<h4><em>
</em></h4>
