---
layout: post
title: What does a double colon mean in IPv6 addresses?
date: 2010-08-24 13:42:46.000000000 +01:00
---
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="https://isemail.info" target="_blank">Email address validation service</a></h4>
This is a post for IPv6 geeks and people who care about email address validation. That's probably not you, so I'm warning you that it gets a bit nerdy below. YHBW.

People keep saying the IPv4 address space is going to run out Real Soon Now but it's still the protocol you are using right now to connect to the internet. It's still working. When I was at school many years ago, I was told that oil would probably run out before the year 2000. People who believed this started investing in Alternative Energy such as solar power, wind power and, least successful of all, wave power. Most of the early investors lost their money, I guess.

The Alternative Energy of the internet is IPv6. This is the solution that people designed when they first thought the IPv4 address space was in danger of running out. It's still a minority sport even though your Windows PC has it installed and running. It's talking this language to nobody though. Even if you have a few computers at your house, the router you use to network them together is still only talking IPv4.

IPv6 is there and it's real. One day we might start using it. Until then it remains a laboratory curiosity.

But it's a valid part of an email address. So if you want to validate somebody's email address in your registration form you shouldn't go rejecting <em>jon.postel@[IPv6:1234::cdef]</em> just because it doesn't match the usual <em>first.last@domain.com</em> format. It's a valid address. Check out <a href="https://tools.ietf.org/html/rfc5321" target="_blank">RFC 5321</a> if you don't believe me.

OK, let's assume you actually clicked that link and read the RFC (I won't tell if you don't).

Now tell me whether this is a valid address: <em>jon.postel@[IPv6:1111:2222:3333:4444:5555::7777:8888]</em>

The answer according to the bible of SMTP is <strong>no</strong>. I quote the comments to the definition of ipv6-comp: "<span style="font-family: Consolas, Monaco, 'Courier New', Courier, monospace; line-height: 18px; font-size: 12px;">The "::" represents at least 2 16-bit groups of zeros.  No more than 6 groups in addition to the "::" may be present.</span>"

But let's look at the bible of <strong>IPv6</strong>, <a href="https://tools.ietf.org/html/rfc4291" target="_blank">RFC 4291</a>: "<span style="font-family: Consolas, Monaco, 'Courier New', Courier, monospace; line-height: 18px; font-size: 12px;">The use of "::" indicates one or more groups of 16 bits of zeros.</span>"

So RFC 4291 appears to disagree with RFC 5321. Thanks, IETF. Which should we use as our authority when validating email addresses? Perhaps RFC 5321 is documenting a <em>special case</em> of IPv6 that only applies to SMTP transactions. Hmmm.

Fortunately just when we feel like banging John Klensin's head against RFC 4291 or (frankly) anything solid, along come Seiichi Kawamura and Masanobu Kawashima to our rescue. The brand-new <a href="https://tools.ietf.org/html/rfc5952" target="_blank">RFC 5952</a> gives us clear guidelines about the use of the double colon in IPv6 addresses:
<blockquote><em>The symbol "::" MUST NOT be used to shorten just one 16-bit 0 field.</em></blockquote>
Phew. We have clarity at last.

Or do we?

Remember Jon Postel's <a href="https://en.wikipedia.org/wiki/Robustness_principle" target="_blank">Robustness Principle</a>? "Be conservative in what you do, be liberal in what you accept from others". How might we apply that here? RFC 5952 still accepts the authority of RFC 4291. It is a <em>recommendation</em> for how IPv6 addresses might be standardised when written as text. The robustness principle would suggest we should ensure our own addresses conform to RFC 5952, but we should accept any addresses that conform to RFC 4291.

My conclusion is this: my own validator <em><a href="https://code.google.com/p/isemail/source/browse/trunk" target="_blank">is_email()</a></em> will accept as valid any address that conforms to RFC 4291 (even though that is contradicted by RFC 5321). It will raise a warning if the double colon elides only one zero group.

As a final personal note, I would say that an address of the format <em>::1111:2222:3333:4444:5555:6666:7777</em> is nonsense. It's valid according to RFC 4291 but it contains 8 colons. That's just silly. I think it's clear that the only sensible use of the double colon is to elide two or more zero groups and I certainly agree with RFC 5952 that that should be the standard.
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="https://isemail.info" target="_blank">Email address validation service</a></h4>
Thanks to my correspondent <a href="mailto:michael@squiloople.com">Michael Rushton</a> for bringing my attention to this issue.
