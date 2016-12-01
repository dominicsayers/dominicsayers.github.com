---
layout: post
title: Email address validation
date: 2011-03-14 16:27:22.000000000 +00:00
---
I've made an <a href="https://isemail.info" target="_blank">email address validation service</a> powered by the free PHP function <em><a href="https://code.google.com/p/isemail/" target="_blank">is_email()</a></em>.
<h1>What is a valid email address?</h1>
There's only one real answer to this: a valid email address is one that you can send emails to.

There are acknowledged standards for what constitutes a valid email address. These are defined in the <a href="https://en.wikipedia.org/wiki/Request_for_comments" target="_blank">Request For Comments</a> documents (RFCs) written by the lords of the internet. These documents are not rules but simply statements of what some people feel is appropriate behaviour.

Consequently, the people who make email software have often ignored the RFCs and done their own thing. Thus it is perfectly possible for you to have been issued an email address by your <a href="https://en.wikipedia.org/wiki/Internet_Service_Provider" target="_blank">internet service provider</a> (ISP) that flouts the RFC conventions and is in that sense <em>invalid</em>.

But if your address works then why does it matter if it's invalid?

That brings us onto the most important principle in distributed software.
<h2>The Robustness Principle</h2>
A <a href="https://en.wikipedia.org/wiki/Jon_Postel" target="_blank">very great man</a>, now sadly dead, once <a href="https://en.wikipedia.org/wiki/Robustness_principle" target="_blank">said</a>
<blockquote>be conservative in what you do, be liberal in what you accept from others</blockquote>
We take this to mean that all messages you send out should conform carefully to the accepted standards. Messages you receive should be interpreted as the sender intended so long as the meaning is clear.

This is a very valuable principle that allows networked software written by different people at different times to work together. If we are picky about the standards conformance of other people's work then we will lose useful functions and services.
<h2>How does this apply to validating email addresses?</h2>
Look, if a friend says to you “this is my email address” then there's no point saying to her “Ah, but it violates RFC 5321”. That's not her fault. Her ISP has given her that address and it works and she's committed to it.

If you've got an online business that she wants to register for, she will enter her email address into the registration page. If you then refuse to create her account on the grounds that her email address is non-conformant then you've lost a customer. More fool you.

But if she says her address is <code>sally.@herisp.com</code> the chances are she's typed it in wrong. Maybe she missed off her surname. So there is a point in validating the address – you can ask her if she's sure it's right before you lose her attention and your only mean of communicating with a potential customer. Most likely she'll say “Oh yes, silly me” and correct it.

Occasionally a user might say “Damn right that's my email address. Quit bugging me and register my account”. Better register the account before you lose a customer, even if it's not a <em>valid</em> email address.
<h2>Getting it right</h2>
If you're going to validate an email address you should get it right. Hardly anybody does.

The worst error is to reject email addresses that are perfectly valid. If you have a Gmail account (e.g. <code>sally.phillips@gmail.com</code>) then you can send emails to<code>sally.phillips+anything@gmail.com</code>. It will arrive in your inbox perfectly. This is great for registering with websites because you can see if they've passed your address on to somebody else when email starts arriving addressed to the unique address you gave to the website (e.g. <code>sally.phillips+unique_reference@gmail.com</code>).

But.

Sadly, many websites won't let you register an address with a plus sign in it. Not because they are trying to defeat your tracking strategy but just because they are crap. They've copied a broken regular expression from a dodgy website and they are using it to validate email addresses. And losing customers as a result.

How long can an email address be? A lot of people say 320 characters. A lot of people are wrong. <a href="https://www.rfc-editor.org/errata_search.php?rfc=3696&amp;eid=1690" target="_blank">It's 254 characters</a>.

What RFC is the authority for mailbox formats? <a href="https://tools.ietf.org/html/rfc822" target="_blank">RFC 822</a>? <a href="https://tools.ietf.org/html/rfc2822" target="_blank">RFC 2822</a>? Nope, it's <a href="https://tools.ietf.org/html/rfc5321" target="_blank">RFC 5321</a>.

Getting it right is hard because the RFCs that define the conventions are trying to serve many masters and they document conventions that grew up in the early wild west days of email.

My recommendation is: don't try this yourself. There's free code out there in many languages that will do this better than anybody's first attempt. My own first attempt was particularly laughable.
<h2>Test cases</h2>
If you do try to write validation code yourself then you should at least test it. Even if you're adopting somebody else's validator you should test it.

To do this you're going to have to write a series of unit tests that explore all the nooks and crannies of what is allowed by the RFCs.

Oh wait. You don't have to do that because I've done it for you.

Packaged along with the free <em>is_email()</em> code is an XML file of 164 unit tests. If you can write a validator that passes all of them: congratulations, you've done something hard.

See the tests and the results for <em>is_email()</em> <a href="https://isemail.info/_system/is_email/test/?all" target="_blank">here</a>.

If you think any of the test cases is wrong please leave a comment here.
<h2>Downloading <em>is_email()</em></h2>
I've written <em>is_email()</em> as a simple PHP function so it's easy to include in your project. <a href="https://code.google.com/p/isemail/downloads/list" target="_blank">Just download the package here</a>. The tests are included in the package.

&nbsp;
