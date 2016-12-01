---
layout: post
title: My social data flow
date: 2008-07-28 18:42:32.000000000 +01:00
---
I got in a bit of a tangle with what Web 2.0 application was updating what so I've tried to rationalise the data flow like this:
<a href="https://www.dominicsayers.com/socialdataflow/" target="_blank"><img style="margin-top:16px;margin-bottom:16px;border-width:0;" src="https://www.dominicsayers.com/socialdataflow/SocialDataFlowThumb.png" alt="" width="480" /></a>
<p style="font-size:x-small;">(Click on the image for a bigger version)</p>

Having done this I'm fairly sure of three things:
<ol>
	<li>There are no feedback loops: no update is going to propagate to another site that feeds it back where it came from</li>
	<li>There is a specific feed for three appropriate levels of details that does not omit anything relevant.</li>
	<li>There is no need for any other feed unless you're interested in particular asset classes, e.g. photos.</li>
</ol>
There is one <strong>publisher</strong>, one <strong>syndicator</strong> and one <strong>aggregator</strong>. Each of them can be replaced at any time without affecting the principle of how this works.

So here is the guide to subscribing to updates about me:
<p style="padding-left:30px;"><strong>Give me everything!
</strong>I love hearing about what you say and do and I can't get enough of you
<a href="https://friendfeed.com/dominicsayers?format=atom" target="_blank">OK: subscribe to this feed</a>

</p><p style="padding-left:30px;"><strong>I</strong><strong> want to read what you write about
</strong>I'm not interested in where you are or what you're doing today but I am interested in your thoughts
<a href="https://blog.dominicsayers.com/feed" target="_blank">OK: subscribe to this feed</a>. And to <a href="https://blog.dominicsayers.com/comments/feed" target="_blank">this feed </a>for what people are saying about my writing

</p><p style="padding-left:30px;"><strong>I'm interested in keeping track of you but I don't want to read your boring writing
</strong>I'm a stalker not an bleeding intellectual
<a href="https://friendfeed.com/dominicsayers?service=internal&amp;format=atom" target="_blank">OK: subscribe to this feed.</a>

Hopefully that will cover everybody. If you're interested in specific stuff like photos then go to <a href="https://friendfeed.com/dominicsayers" target="_blank">my FriendFeed page </a>and choose the source you want.

<strong>Notes on how I rationalised this:
</strong>1. I now use <a href="https://twitterfeed.com/" target="_blank">Twitterfeed</a> simply as a mechanism for posting RSS to <a href="https://twitter.com/dominicsayers" target="_blank">Twitter</a>, specifically my FriendFeed stream. I've classed it as "Social ETL" in the diagram :-)

2. Twitter is now just an output device and a way of feeding my updates to mobile phones, for example.

3. I have tried to remove all <a href="https://www.facebook.com/profile.php?id=509253174" target="_blank">Facebook </a>apps that update my status except for ping.fm

4. Sorry for the multiple and egregious posts while I sorted this out today

5. Thanks to <a href="https://www.flickr.com/people/mlazopoulou/" target="_blank">Myrto </a>for the <a href="https://ping.fm" target="_blank">ping.fm </a>invite.</p>
