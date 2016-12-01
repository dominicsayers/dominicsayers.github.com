---
layout: post
title: Revised social data flow
date: 2008-08-05 16:27:53.000000000 +01:00
---
In an attempt to remove the latency problem from my social data flow, I've rearchitected it a bit. Unfortunately the reworked flow is not quite as elegant as the original but then it had more sophisticated design goals so that's not terribly surprising.

Here's the revised flow with notes below:
<a href="http://www.dominicsayers.com/socialdataflow/" target="_blank"><img style="margin-top:16px;margin-bottom:16px;border-width:0;" src="http://www.dominicsayers.com/socialdataflow/SocialDataFlowThumb.png" alt="" width="480" /></a>
<p style="font-size:x-small;">(Click on the image for a bigger version)</p>

<strong>Notes:</strong>
<ol>
	<li>Now I can allow <a href="http://ping.fm" target="_blank">ping.fm</a> to update <a href="http://twitter.com/dominicsayers" target="_blank">Twitter</a> and <a href="http://identi.ca/dominicsayers" target="_blank">identi.ca</a> immediately so I have removed the latency problem from the previous configuration. Once again I can use Twitter in a conversational way instead of it being a mere receptacle for RSS updates every half hour.</li>
	<li>You'll note also that <a href="http://twitterfeed.com/" target="_blank">Twitterfeed</a> can now update identi.ca and other <a href="http://en.wikipedia.org/wiki/Laconica" target="_blank">Laconica</a>-based micro-blogging sites. Thanks, <a href="http://twitter.com/mario" target="_blank">Mario</a>. This means I can promote identi.ca to be a peer with Twitter and receive all my updates including real-time micro-blogs (tweets).</li>
	<li>The three subscription points are the same: <a href="http://blog.dominicsayers.com/feed" target="_blank">Writing</a>, <a href="http://friendfeed.com/dominicsayers?service=internal&amp;format=atom" target="_blank">Status Updates</a> and <a href="http://friendfeed.com/dominicsayers?format=atom" target="_blank">All Activity</a>. The URIs for those resources have not changed.</li>
	<li>I have distinguished between blog posts such as this and the notification of those posts. To subscribe to the full post stream use the Writing feed. If you subscribe to the All Activity feed you will be notified about posts but only see the title not the whole article. Unfortunately if you subscribe to both you will see both the blog post and a separate notification of its existence - I can't do anything about this yet.</li>
</ol>
So there's an emerging gap between those select sites that I use to do stuff and those sites that merely receive notification of that activity. My strategy will be to keep to a minimum the sites I use for doing things, and maximise the number of sites that are notified about it. This way I can keep all my pictures, links, writing etc. in one place but all my disparate multiple friend communities will get equal notification of new activity in one of those upstream sites.

I think the new slightly less elegant social data flow is functionally better and I'll try to stick with it for a while to see how it performs in practice.
