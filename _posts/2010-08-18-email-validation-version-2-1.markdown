---
layout: post
title: Email validation version 2.1
date: 2010-08-18 15:46:49.000000000 +01:00
---
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="https://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
I've had a lot of correspondence about <em><a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">is_email()</a></em>, the free PHP email address validation software that I maintain. The principle topics of debate were the edge cases where an email address is technically valid but extremely unlikely in the real world.

Examples of this sort of address would be <em>""@example.com</em> or <em>benedictXIII@va</em> - the first because it doesn't contain any text to identify the mailbox and the second because it's at a Top Level Domain.

Both these addresses could exist but neither is likely to. If a user entered one of these addresses into your registration page it is much more likely to be a typo than a real address.

So in the first versions of <em>is_email()</em> I made the decision to call these address invalid because they were unlikely. It was this decision that generated most of the correspondence.

My learned correspondents were right. The purpose of <em>is_email()</em> is to determine whether an address is valid or not. It should not be rejecting valid addresses - this is the most common fault of other ways of validating email addresses.

But I wanted to identify unlikely addresses without declaring them invalid. For this reason I added a Warning feature to <em>is_email()</em>. Without losing any backward compatibility, I have enabled it to return a diagnostic code that identifies either the fault (if it's invalid) or the reason it's unlikely to be a real address (despite being valid).

This has allowed me to make it a true validator - it follows the RFCs as precisely as I can make it - without losing real-world usefulness.

<a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank"><em>is_email()</em> version 2.1</a> was released yesterday. Try it. Let me know if it works for you.
<h4>Quick links: <a href="https://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a href="https://www.dominicsayers.com/isemail/" target="_blank">Email address validators head-to-head</a></h4>
