---
layout: post
title: Getting online
date: 2012-04-11 13:48:44.000000000 +01:00
tags: featured
---
<em>I've been asked a few times recently for general advice about getting a new business or project online. Here's the skinny.</em>

<strong>Any new business or project is going to need an online presence. So you just need to go and register a domain with GoDaddy, right? Stop! First read this handy guide to how to get it right.</strong>

You need three basic things
<ol>
	<li>A registered name</li>
	<li>A way of telling the internet where your services are hosted</li>
	<li>Hosting for your services (web site and email at least)</li>
</ol>
When you register a domain name, the registrar will want to do <em>all</em> these things for you. That way they get to keep all your money. But there are good reasons for keeping everything separate. Now read on...
<h1>Choosing a name</h1>
It's fun choosing your name, but it's not easy these days because all the good ones have already been taken. Here's some things to consider that you might not have thought of:
<ol>
	<li><strong>A .com domain name.</strong>
D'oh!  Of course you thought of that. But if you didn't then you should. Plenty of people will try the .com version of your name even if you register it somewhere else.</li>
	<li><strong>A domain name in another top level domain.</strong>
If you plan to allow users to make comments on your web site or even to upload files then consider having an alternate domain name that is not subject to US laws.</li>
	<li><strong>A Twitter handle.</strong>
Twitter is pretty crowded these days and getting your name as a Twitter handle will not be easy. And Twitter doesn't have a secondary market in handles so you can't make someone else an offer for theirs..</li>
</ol>
<h1>Registering your name</h1>
You need to tell the gods of the internet that you have chosen your name. You do this through a <em>registrar</em>. Many companies will act as a registrar for you because it's money for old rope. They will also offer you other services like hosting and email. Here's why you shouldn't use the same company for everything.

Your domain names are your branding (and your trademark if you register it). It's your identity and you should keep tight control of it. If you were a big company then your domain names would be under the control of your legal or marketing department, not your techies. If you outsource your web development, for example, you don't want the developers owning your brand - what if you fall out with them?

So register the domain names yourself, but don't buy any other services from the registrar. <strong>Keep the credentials for your account at the registrar very safe. Nobody else needs to know them except you.</strong> Ever. If they say they do then they are trying to rip you off.

My recommended registrar: <a href="https://www.gandi.net/no-bullshit" target="_blank">Gandi</a>. Many countries have appalling internet legislation that compels internet service providers to pull your domain on the say-so of law enforcement agencies. France, where Gandi are domiciled, is no exception. But Gandi at least have a policy of <a href="https://www.gandibar.net/post/2010/12/20/US-Data-Center-Open-for-Business#c179053" target="_blank">pushing back</a> when asked to do something that is not in the customer's interest. GoDaddy, on the other hand, are happy to hand over your data and your domain to the US security services at the request of a junior officer.

You'll also need to register a <strong>Twitter handle</strong>. To do this you'll need an email address, so let's defer this until we've got our domain email services working. Registering a Twitter handle is easy: you're just creating a Twitter account in the normal way.
<h1>Hosting your services</h1>
It's no good having a domain name unless you use it for something. Here's some of the services you might use it for:
<ol>
	<li><strong>Email</strong>
You'll probably want email addresses at your domain (you@yourdomain.com). The easiest way to do this is <a href="https://www.google.com/apps/intl/en-GB/group/index.html" target="_blank">Google Apps</a>. To complete the setup of Google Apps you'll need to verify that the domain is yours - we'll cover this in the following section about the Domain Name System. When you've got your email accounts set up, don't forget to go and register your Twitter handle.</li>
	<li><strong>Website or web application</strong>
Traditionally your website would be hosted by a provider that gave you access to a virtual machine. On this machine would be a web server and you could simply upload HTML or PHP pages to create your site. The problem with this way of doing things is that it's fiddly to keep track of what you uploaded and when. This model has been replaced somewhat by the idea of an application server. Providers like <a href="https://www.heroku.com/" target="_blank">Heroku</a> or <a href="https://appfog.com/" target="_blank">AppFog</a> will link to your web developer's source code control systems to create more effective release control system.</li>
	<li><strong>Blog</strong>
Your blog is just another application, hosted by an application server. There are many companies that will do this for you. I happen to use <a href="https://wordpress.org/" target="_blank">Wordpress software</a> hosted on my own old-fashioned virtual server. But <a href="https://en.wordpress.com/signup/" target="_blank">Wordpress</a> as a company will host your blog for you if you want.</li>
</ol>
<h1>Tying the bits together</h1>
As it stands we've got a domain name (good) and email addresses like phil@yourdomain.com.test-google-a.com (bleugh!) and maybe a website at https://yourdomain.herokuapp.com (yuk!)

This isn't what we want. We want emails like phil@yourdomain.com and our website to be at https://yourdomain.com - how do we do this?

The thing we need is the Domain Name System (DNS). Your domain has name servers. These servers tell the internet where your own services are located. It's a bit of internet plumbing that we need to use to tie it all together. Bear with me, it's not that hard.

I recommend using <a href="https://www.cloudflare.com/" target="_blank">Cloudflare</a> for your name servers. They are specialists at this and they do a free account that gives you all your basic needs, plus a lot of extra value on top. The Cloudflare account setup gives you all the help you need to get your services running on the right domain names.

When you've been through the Cloudflare setup you'll understand it a lot more. But the basic steps are:
<ol>
	<li>Tell the DNS where your web hosts are</li>
	<li>Tell the DNS where your mail servers are</li>
	<li>Tell your registrar who is running your name servers</li>
</ol>
The last step is what achieves the important separation of responsibility between your registrar and your other service providers. It gives you the freedom to choose the best-of-breed hosting provider, email provider and DNS provider. You don't have to be tied to your registrar for these services any more.

If you're using Google Apps, the final step is to verify to Google that you own the domain. Google Apps setup will help you through this, but it's very easy with Cloudflare to set up a TXT record containing information provided by Google. You'll see what I mean when you try it.

Comments and suggestions appreciated.

&nbsp;
