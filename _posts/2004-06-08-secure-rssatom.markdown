---
layout: post
title: Secure RSS/Atom
date: 2004-06-08 16:54:19.000000000 +01:00
---
I have been thinking about RSS/Atom in the context of compliance-sensitive information and wondering how to restrict the flow of information to those who are supposed to see it. Having got myself into horrible logical tangle over this I now realise I was missing the point all along.

You don't need to add permissions to the RSS at all, you just need to generate it on the fly after you have identified the user. You can use server-side code to filter the records that the user is permissioned to see, then form them into a standard RSS document.

Bingo.
