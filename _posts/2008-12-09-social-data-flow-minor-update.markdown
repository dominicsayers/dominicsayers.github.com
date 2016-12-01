---
layout: post
title: Social Data Flow minor update
date: 2008-12-09 11:50:46.000000000 +00:00
---
I'll probably write some more about Social Data Flow shortly, but for now I just wanted to talk about extending the canonical data flow with bespoke updates flowing through my own site.

In a perfect world, my syndicator (which happens to be <a href="https://ping.fm" target="_blank">ping.fm</a>) would take care of all my syndication needs. It would take my micro-blogs and status updates and send them to all known social sites where I have an account. Unfortunately while ping.fm appears to have the best coverage, it's not complete. Posterous, for example, is a significant omission (any site where <a href="https://stephenfry.posterous.com/" target="_blank">Stephen Fry</a> is active has to be considered a significant site, or anyway it soon will be).

As it happens, it's very easy for me to update Posterous with my ping.fm outpourings since I've already implemented a ping.fm Custom URL for my own site - it updates the dynamic sections in the left-hand column.

All I had to do was arrange for the PHP page that receives the ping.fm updates to then mail the same update to Posterous. Job done.

Not sure why ping.fm haven't done it themselves, except that pressure of other feature request probably prevents them doing everything they want to straight away.

More to come on my struggle to get an acceptable flow of <em>location data</em> in place.
