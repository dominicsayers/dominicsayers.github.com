---
layout: post
title: Buying tickets for Lord's cricket ground - don't do it online
date: 2012-01-09 10:47:15.000000000 +00:00
---
First of all, IANASC. That is, I Am Not A Security Consultant.

But I have used technology for a while. And I was surprised to see an e-commerce site for a serious commercial organisation presented to the public in the state that http://tickets.lords.org was in last week.

This is a site through which I am expected to buy tickets for international cricket matches in 2012. I bailed out before I got to the point where I entered my credit card details, for the following reasons:
<h3>Alarm #1</h3>
I created an account on the site. A short time later I received an email showing my password in plaintext
<h3>Alarm #2</h3>
When I was logged into the site, even in private areas such as my account details, I was connecting over HTTP not HTTPS.
<h3>Alarm #3</h3>
The site didn't work as intended: options weren't selectable. Click targets didn't respond. It transpired that the site just didn't work in any browser except Internet Explorer in Compatibility Mode. This was confirmed in an email I received from them later:
<blockquote>"If you are emailing with regard to a problem accessing the online general public ballot, the club are aware that some people may be experiencing difficulties. It appears currently that the problem is limited to those using smart phones (android ; blackberry ; i-phone), tablet devices and Mac computers using the safari and google chrome browser. At the moment the problem cannot be re-created when using a PC. Our website hosting team is aware of the problem and is investigating. We will update this message when we have further information."</blockquote>
This message seriously understated the problem. They could have recreated the problem quite easily on a PC just by using an up-to-date version of Internet Explorer (version 9).

So the tl;dr message is this: don't use this site to buy tickets for Lord's. You can use their ticket hotline or plain old snail mail instead.

If you want to know why these features alarmed me read on:
<h3>Concerns about alarm #1</h3>
For them to send me a copy of my password in an email means

1. My password was transmitted to them unencrypted, over an unencrypted connection.

2. They have stored it in a decryptable way

3. They are happy to send it back to me over another unencrypted channel (email).

None of these things are necessary. Most good sites will encrypt your password in the browser before transmitting it. It will be encrypted into a form that is not ever decryptable by them: they never need to know my password!

How does this work? They store the encrypted password when I create it. When I subsequently log in I enter my password and it is encrypted in the same way before sending. They compare the two encrypted passwords to ensure I am who I say I am. This means:

1. The only person who knows my password is me.

2. My password cannot be discovered by anyone else.

3. My password is never transmitted unencrypted, even over a secure channel.

Simples.
<h3>Concerns about alarm #2</h3>
[EDITED to add: I've had an email from the MCC's technology department. They point out that the credit card part of the site (but not the password part) does use SSL, so the following points are semi-mitigated]

It's not actually that difficult to get a digital certificate that authoritatively identifies who you are. Any serious technology organization should be very familiar with this process.

Once you've got a certificate and installed it on your server, you are ready to communicate with your users over SSL. They will see a URL beginning https:// instead of http:// and they will see a reassuring green padlock (or something similar) next to the URL in the address bar.

This communication will be encrypted.

Many websites are using SSL as their default channel. Certainly any serious website that expects you to enter confidential information (like a password or credit card number) will use SSL.

It is beyond belief that a competent technology organisation would make an e-commerce site without using SSL.
<h3>Concerns about alarm #3</h3>
Internet Explorer? Seriously?

I don't know what their stats show, but for my own sites I get about 15% of my visitors using Internet Explorer. Only about 10% of my visitors use the older versions of Internet Explorer that will render the Lord's ticketing site correctly.

But the developers of this site forgot to test their site in the browsers that 90% of my visitors use.

To me, this means they are living in a cocoon of unreality. They believe that the rest of the world is like them: developing websites using Microsoft technologies (the pages are .aspx) and using them with the browser provided by their corporate IT department. It is this cocoon that has led them to believe they are competent to deliver a commercial, public ticketing site.

They are not.

&nbsp;

&nbsp;

&nbsp;
