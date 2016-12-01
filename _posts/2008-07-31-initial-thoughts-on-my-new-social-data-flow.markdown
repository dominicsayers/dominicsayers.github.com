---
layout: post
title: Initial thoughts on my new social data flow
date: 2008-07-31 10:38:10.000000000 +01:00
---
Firstly, apologies to anybody who couldn't see the social data flow diagram in my <a href="http://blog.dominicsayers.com/2008/07/28/my-social-data-flow/" target="_blank">earlier post</a> - I've now hosted it on my own server so it shouldn't disappear quite so often.

<a href="http://www.dominicsayers.com/socialdataflow/" target="_blank"><img style="margin-top:16px;margin-bottom:16px;border-width:0;" src="http://www.dominicsayers.com/socialdataflow/SocialDataFlowThumb.png" alt="" width="480" /></a>
<p style="font-size:x-small;">(Click on the image for a bigger version)</p>

The new data flow, using <a href="http://ping.fm" target="_blank">ping.fm</a> to syndicate my status updates and micro-blogs and <a href="http://friendfeed.com/dominicsayers" target="_blank">FriendFeed</a> to aggregate my other activity and consolidate everything into a coherent set of feeds, is working quite well. I would like to be able to have more control over the format of what both ping.fm and FriendFeed do for each target system, but the defaults are adequate for now.

Here are the issues I'm experiencing:

1. Using <a href="http://twitterfeed.com/" target="_blank">Twitterfeed</a> to take my <a href="http://friendfeed.com/dominicsayers?format=atom" target="_blank">FriendFeed RSS</a> and pipe it into <a href="http://twitter.com/dominicsayers" target="_blank">Twitter</a> introduces a degree of latency that's a bit inappropriate for Twitter. Twitter should be near real-time and conversational (whilst not being an instant messaging system), but Twitterfeed only reads my FriendFeed every half an hour. If I get ping.fm to update Twitter directly then I'm going to get some updates twice, which is exactly what I'm trying to avoid.

2. Some of the connected systems (<a href="http://identi.ca/dominicsayers" target="_blank">identi.ca</a> for example) are Twitter-like, and I'd like to treat them the same way as Twitter: as an output device for all my activity. But Twitterfeed is Twitter-specific and I haven't found an equivalent for identi.ca etc. yet. In any case I don't want a different Social ETL tool for each output system; I want Twitterfeed (or something) to do this for a number of target systems.

3. There's no class solution for location-based systems yet. Obviously I'd like to be able to update my location and travel plans in one place and have it propagate to <a href="http://www.tripit.com/people/dominicsayers" target="_blank">TripIt</a>, <a href="http://www.dopplr.com/traveller/DominicSayers" target="_blank">Dopplr</a>, <a href="http://brightkite.com/people/dominicsayers" target="_blank">BrightKite</a> etc. I think <a href="http://fireeagle.yahoo.net/" target="_blank">FireEagle</a> may be trying to do this but it's short of two things at the moment: co-operation from the other systems and an invitation for me. If anybody has access to FireEagle I would appreciate a way in.

4. Now I need to do the other thing - deduplicate my profligate friends' updates. When <a href="http://www.flickr.com/people/mlazopoulou/" target="_blank">Myrto</a> uploads a picture to Flickr, for instance, I get notified about it four times. I can rationalise this a bit but I can't ignore her FriendFeed or Twitter because I would miss some of her updates, so I'm condemned to hearing about her new pictures multiple times unless (a) she adopts a version of my social data flow or (b) I find a solution to deduplicating the same update coming through multiple channels. This duplicate filter is necessary until everybody adopts my architecture, i.e. for ever. Does anybody know of a solution out there?

This all seems quite difficult to manage and well beyond anybody who is either busy or technically challenged. There's no real way of developing a packaged solution until all the social systems adopt a single sign-on technology like <a href="http://openid.net/" target="_blank">OpenID</a>, and many of them have sound technical reasons for not doing so (OpenIDs can be created by anybody anywhere so it's a bit like expecting system owners to trust a digital certificate that has no trusted root certification authority).

Anyway, that's the state of play at the moment. More to come I'm sure.
