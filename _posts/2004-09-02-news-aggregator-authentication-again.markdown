---
layout: post
title: Feed aggregator authentication (again)
date: 2004-09-02 10:08:51.000000000 +01:00
---
In my eternal quest to find a feed aggregator that supports a wide range of secure authentication methods I have so far drawn a blank. Some aggregators support SSL and some support HTTP Authentication. None will supply a digital certificate to the server.

In a forum on the Newz Crawler site a helpful but largely anonymous person calling herself Alice suggested trying stunnel (<a href="https://www.stunnel.org/">https://www.stunnel.org/</a>). Great! It claims to be able to wrap any TCP connection in an SSL layer <em>and</em> can supply a client-side digital certificate!

A pity for me that it is only configurable through the shibboleth of a unix-style config file. Oh, life is too short for me to get to grips with this. Help!

Anybody used stunnel before and would like to help me out?
