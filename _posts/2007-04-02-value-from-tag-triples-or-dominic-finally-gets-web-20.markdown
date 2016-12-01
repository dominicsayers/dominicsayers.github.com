---
layout: post
title: 'Value from tag triples (or: Dominic finally gets Web 2.0)'
date: 2007-04-02 17:12:31.000000000 +01:00
---
I had noticed that geo-tagging was quite a cool feature of Flickr these days - I found a <a target="_blank" href="http://flickr.com/photo.gne?id=433602252">photo of my back garden gate</a> that somebody had taken when I searched my own location. The sat nav that my wife just bought for her car has a camera built in so I guess we get automatic geo-tagging of those pictures from the GPS device. Nice, although I'll probably carry on using a proper camera for important stuff.

Until today I hadn't realised that Flickr was getting quite good at what it calls "machine tags" in general. For instance, if you <a target="_blank" href="http://flickr.com/photos/tags/lastfm%3Aevent%3D35911">tag a photo</a> with "lastfm:event=35911" then Flickr realises this isn't a straightforward human mnemonic tag and doesn't clutter up the tag list with it.

So why would you use such a tag? Well, look at last.fm: if you look up <a target="_blank" href="http://www.last.fm/event/35911">Glastonbury 2005</a> as an event you'll see a collection of photos. These are all the photos with the tag "lastfm:event=35911". That tag is a specific instruction to last.fm to include the photo against that event.

This particular tag syntax is driven by last.fm - they decided on the namespace (lasftm) and the predicate (event). The geo-tagging is slightly different - Google provide an API to their maps and satellite imagery and Flickr have enabled the link themselves by programatically encouraging people to use a particular geo-tagging syntax.

For last.fm I believe there is something important missing. last.fm chose Flickr. Flickr is a good choice for them because of the sophisticated way it deals with tags and the highly functional API. But not all last.fm users user Flickr to store their photos.

How can last.fm discover other sources of material about Glastonbury 2005? The obvious answer is to look for stuff on other sites that is tagged "lastfm:event=35911". But that doesn't solve the whole problem because there's no indication of what sites to look on and how to display this content.

Easy enough for del.icio.us links - last.fm could simply display them as a list like Google or del.icio.us themselves do. There were <a target="_blank" href="http://del.icio.us/tag/lastfm:event=35911">no links</a> on del.icio.us tagged with "lastfm:event=35911" when I looked a moment ago, but there could have been if last.fm encouraged del.icio.us users to use this syntax.

Other content is more difficult. Another photo site would have a different API to Flickr - how can last.fm keep track of all the photo sites? Clearly it can't do so at reasonable cost.

The solution might be a degree of indirection. It sould be easy enough to set up a site that mapped namespace:predicate pairs to a URI with a placeholder for the value part. Something like this:

<a href="http://www.tripleviewer.com/listviews.php?namespace=lastfm&amp;predicate=event">http://www.tripleviewer.com/listviews.php?namespace=lastfm&amp;predicate=event</a>

would return a list of URIs that knew how to display things on their site tagged with "lastfm:event=nnnnn". The list would consist of things like this:

<a href="http://last.fm/events/$1">http://last.fm/events/$1</a>
<a href="http://flickr.com/photos/tags/lastfm%3Aevent%3D$1/">http://flickr.com/photos/tags/lastfm%3Aevent%3D$1/</a>
<a href="http://del.icio.us/tag/lastfm%3Aevent%3D$1">http://del.icio.us/tag/lastfm<font color="#810081">%3A</font>event<font color="#810081">%3D</font>$1</a>
<a href="http://myphotos.tv/tags/lastfm%3Aevent%3D$1">http://myphotos.tv/tags/<u><font color="#0000ff">lastfm%3Aevent%3D$1</font></u></a>

...and last.fm would only need to enumerate this list, replace the placeholder with their event id and display the results on their page for that event. It replaces the need for last.fm to know how to manage every other site with a mechanism for any site to say 'I know how to include stuff on last.fm's page'.

I know things could get more complicated than this.  It would help if these views were named so that you could identify individual views. Also, I've deliberately chosen an example with a single unique identifier for the item (the last.fm event id) and very often there will be a number of elements to the unique identifier (geo-tagging has a latitude and a longitude for example).

But the idea remains the same - a site where you can register views of semantically tagged data. It's just a thought that sprung up when I read the post below and I haven't thought it through properly yet. Just blogging it as a memorandum to myself at this stage.

Thanks to <a target="_blank" href="http://www.clagnut.com/blog/1907/">Clagnut</a> for the germ of this post, and as always thanks to <a target="_blank" href="http://www.phildawes.net/blog/category/semantic-web/">Phil Dawes</a> for his ongoing primer on the semantic web.
