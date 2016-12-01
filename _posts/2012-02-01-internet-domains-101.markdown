---
layout: post
title: Internet domains 101
date: 2012-02-01 12:35:35.000000000 +00:00
tags: cname
---
Sometimes I help people out with web servers, email servers and other internet-related stuff. I often have to explain how we control what happens when you type in <em>www.example.com</em> or <em>whoever@example.com</em>.

Here's my simple guide to how internet domains work.
<h3>Name resolution</h3>
When you type <em>www.example.com</em> into a web browser, how does it know where to go to get the web page? As many people know, the answer is the <a href="https://en.wikipedia.org/wiki/Domain_Name_System" target="_blank">DNS</a> system. This translates <em>www.example.com</em> into the address of a web server. More mysterious stuff happens to connect your browser to that address, but we don't need to know about that today.

Your domain has a set of DNS records that say where on the internet your domain's resources (email servers, web servers etc.) actually live. You can change these records yourself, it's quite easy.
<h3>Resource records</h3>
Here are the DNS resource records you might need to change:

Address records (<strong>A</strong>): If your web server is at the internet address <em>192.0.43.10</em>, for example, then you need to create an A record for <em>www.example.com</em> that points to that address.

Synonyms (<strong>CNAME</strong>): If there's a resource on a server that already has a name then you can simply tell the DNS that your resource is on the same server. This is how Google Apps creates a webmail site at <em>mail.example.com</em>; you simply create a CNAME record that points <em>mail.example.com</em> at <em>ghs.google.com.</em>. That's all you have to know.

Mail servers (<strong>MX</strong>): Your email is transferred by mail servers. These are the servers that actually move mail around (not to be confused with your webmail site). For Google Apps mail, the settings for the MX records are specified in <a href="https://support.google.com/a/bin/answer.py?hl=en&amp;answer=174125" target="_blank">Google Apps help pages</a>.
<h3>Domain registration &amp; name servers</h3>
Where are <em>your</em> DNS records kept? This is determined by the domain's registration setup.

When you first registered the domain you will have used a registrar like GoDaddy or Network Solutions (or <a href="https://www.gandi.net/no-bullshit" target="_blank">Gandi</a>, the registrar I recommend). For an annual fee this company will maintain your domain's existence on the internet and one other thing: determine where the domain's name servers are (the name servers hold the DNS records).

When you first registered the domain, the registrar will have used their own name servers for your domain. This is to make it easy for you, but also because they are control freaks.

This is important. Many registrars try to hide the fact that <strong>you don't have to use their name servers</strong>. In fact there are advantages in using a separate DNS provider from your registrar:
<ol>
	<li>The domain registration should be managed by your organisation's legal or administrative department. This is the master key: in the event of a problem then the name servers can simply be changed to regain control of the domain.</li>
	<li>Management of the DNS records can be delegated to a technical person, but it's really not difficult to do this yourself.</li>
	<li>Specialist DNS service providers often add extra value: for instance <a href="http://www.cloudflare.com/">Cloudflare</a> will cache your web content and speed up web access for all your users.</li>
</ol>
<h3>Summary</h3>
So in a nutshell:
<ol>
	<li>Your domain is registered with a registrar. Your account at the registrar controls where the domain's name servers are.</li>
	<li>The name servers manage the DNS records for the domain. You should have a separate account with a DNS service provider to manage them.</li>
	<li>Your web server will be controlled by an A record in the DNS setup.</li>
	<li>Your webmail server will be controlled by a CNAME record in the DNS setup.</li>
	<li>Your mail servers will be specified by MX records in the DNS setup.</li>
</ol>
If this isn't clear please leave a comment.
