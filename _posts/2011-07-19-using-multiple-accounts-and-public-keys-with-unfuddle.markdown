---
layout: post
title: Using multiple accounts (and public keys) with Unfuddle
date: 2011-07-19 14:37:51.000000000 +01:00
tags: ssh-keygen
---
If you develop on more than one Unfuddle account you'll probably need separate identities for each account. Unfortunately git by default will only offer a single public key to authenticate you, and each Unfuddle account needs its own public key.

Here's how to configure your SSH client to offer more than one public key to Unfuddle when you come to authenticate:
<ol>
	<li>Make sure you have a key pair for each Unfuddle account you will be using. To generate a new key pair, use <code>ssh-keygen</code> and give each key pair a unique name</li>
	<li>Create a file called <code>config</code> in your <code>~/.ssh</code> folder</li>
	<li>Edit it to look something like this:</li>
</ol>
<pre># Tell SSH to different key pairs for different hosts
# Useful for e.g. Unfuddle when using several accounts
# because you can only use your default public key
# for one of the accounts
Host other.unfuddle.com
IdentityFile ~/.ssh/other_id_rsa

Host other2.unfuddle.com
IdentityFile ~/.ssh/other2_id_rsa

Host *
IdentityFile ~/.ssh/id_rsa</pre>

There should be a <code>Host</code> entry for each Unfuddle account for which you have used a different key pair. The final <code>*</code> section tells SSH to use your default key pair for all other connections.
