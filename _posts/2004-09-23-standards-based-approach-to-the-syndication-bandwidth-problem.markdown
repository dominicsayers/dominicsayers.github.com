---
layout: post
title: Standards-based approach to the syndication bandwidth problem
date: 2004-09-23 11:26:32.000000000 +01:00
---
...that I have written about <a href="http://dominicsayers.blogspot.com/2004/09/push-syndication-again.html">before</a>. Here is a <a href="http://bobwyman.pubsub.com/main/2004/09/if_you_must_pol.html">post</a> about RFC3229 which attempts to reduce the bandwidth used by the constant polling of syndicated feeds. It does this by only transmitting the parts of the feed that the reader hasn't yet seen: something I'm surprised wasn't already in the base spec for RSS or Atom.

It's still a pull solution, but given the technical problems around push approaches it is worth adding this to our list of requirements for a corporate feed-reader: it should support this RFC.
