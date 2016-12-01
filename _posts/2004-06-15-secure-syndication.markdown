---
layout: post
title: Secure syndication
date: 2004-06-15 19:57:00.000000000 +01:00
---
Two contradictory thoughts.

If companies wish to disseminate commercial information using a syndication
protocol then they need a news aggregator that can supply authentication
credentials to the server. Some already can, but, depending on their
compatibility with the authentication methods available on the server, it is
possible they will be transmitting usernames and passwords unencrypted over
the internet. This is clearly a Bad Thing. If Digest Authentication were
reliably available then this would mitigate the problem. This would be an
appropriate solution for a company wishing to set up a public, but paid-for,
service.

For the type of information my company wants to disseminate, we would prefer
to issue our customers with a digital certificate. I am not enough of a
security guru to comment on the relative merits of this technology compared
to username/password, but I know it is the norm in my industry (financial
services) to operate like this.

Here (at last) is my point: the first news aggregator to offer digital
certificate authentication is in a unique position. Not only is it likely to
be widely adopted in the financial services industry, to the complete
exclusion of its competitors, but it will also generate a good deal of
publicity among some very influential consumers, for syndication
technologies in general. Blogging will have grown up all of a sudden.

What is the downside? Well although financial services is a large and
influential industry, it isn't mass market. If, as a news aggregator product
owner, your business model is to make $0.02 from everybody on the planet
then it's probably not worth building this. On the other hand you would like
to sell to an industry that doesn't mind paying top dollar for the right
technology then go right ahead and add this feature.
