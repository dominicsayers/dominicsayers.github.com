---
title: In which I tell you my password for this website
date: 2012-08-21 16:22:19.000000000 +01:00
thumbnail: exponential-wall2.png
image: password.jpg
tags: featured
---
I exaggerate. I'm not really going to tell you my password but I am going to tell you roughly how I created it. You may find it useful when thinking about your own passwords.

Over the years I got into the habit of using the same weakish password for every website I registered on. This was OK for a while then one of the sites I use got its password hashes published and within a few days they were cracked and my password was there for all to see.

I decided to do the sensible thing and create a strong, unique password for each site I use. The two problems I had are the same as everyone else:
<ol>
	<li>I wanted the passwords to be easy for me to remember but hard to crack</li>
	<li>I wanted them to be easy to enter on my phone</li>
</ol>
The second design goal was the one which made my approach slightly different to other ones you see around.

Here's how I make my passwords:
<ul>
	<li>To make a password that's unique for every site you need to incorporate some attribute of that site into the password</li>
	<li>If you have multiple accounts on the site, each should have a different password. So your algorithm needs to take account of your identity too.</li>
	<li>The password must be long enough to be strong but short enough to enter on a phone keyboard</li>
	<li>The password should only use the characters available unmodified on your phone keyboard (it's too painful to keep changing the keyset for me)</li>
</ul>
The characters I have available on my Android phone are the lowercase letters a-z and the punctuation keys ",", "." and space. Your phone may be different.

Here are the components of my password:
<ol>
	<li>A word that's memorable to me, let's say "fart"</li>
	<li>Some letters from the website's domain name</li>
	<li>Some letters from my email address</li>
	<li>Some mandatory punctuation</li>
</ol>
An example. Let's say I'm signing up to Facebook with the email address dominic@sayers.cc

My password would be <code>fart fcbk ae.. ,,</code>

It's made up as follows
<ol>
	<li>My memorable word, "fart"</li>
	<li>A space</li>
	<li>The consonants from the web site's domain name, padded out to a length of 4 by full stops.</li>
	<li>A space</li>
	<li>The vowels from the domain name of my email address, padded out to a length of 4 by full stops</li>
	<li>Some punctuation; a space followed by two commas.</li>
</ol>
So my password is 17 characters long: not perfect but strong enough for today's brute force attacks. It uses all the keyspace available without fiddling around on my phone's keyboard. It's unique for every account on every website (barring coincidences). It's easy to remember.

You can obviously vary these elements considerably to suit yourself. For instance you could use the last four letters in the website's name, maybe reversed or something. Rearrange the elements I've used.

This isn't my actual algorithm, by the way. Just a little bit like it.

Notes:
<ol>
	<li>Please don't tell me about the <a href="https://www.explainxkcd.com/wiki/index.php/Password_Strength" target="_blank">XKCD cartoon</a>. I know about it. I'm not going to type in a 28-character password on my phone.</li>
	<li>A password using this algorithm doesn't lend itself to dictionary attacks or even rainbow table attacks. A brute force attack using today's hardware would take an inordinate amount of time according to this chart:</li>
</ol>
<p style="text-align: center;"><a href="https://arstechnica.com/security/2012/08/passwords-under-assault/4/"><img class="aligncenter" title="Brute force attack time by password length" src="https://cdn.arstechnica.net/wp-content/uploads/2012/08/exponential-wall2-640x398.png" alt="" width="480" height="299" /></a></p>
&nbsp;
