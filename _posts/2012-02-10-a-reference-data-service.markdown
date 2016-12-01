---
layout: post
title: A reference data service
date: 2012-02-10 11:26:05.000000000 +00:00
---
I just wanted to get this idea out of my head so I can think about something else.
<h3>Available domains</h3>
<ul>
	<li>
<pre>refdata.org</pre>
</li>
	<li>
<pre>referen.org</pre>
</li>
	<li>
<pre>referen.se</pre>
</li>
</ul>
<h3>Possible API structure</h3>
Let's take currency data as an example:
<pre style="padding-left: 30px;">http://referen.org/currency/antigua.json</pre>
which gives you the details of Antigua's currency in JSON format. This would be the latest version of the format, and the current currency used in Antigua. For a specific data format you can add a version number, and for a specific data in history you can add a date:
<pre style="padding-left: 30px;">http://referen.org/v1/2012/02/10/currency/antigua.json</pre>
As well as JSON, data would be available as XML or semantic HTML (the default), possibly as a microformat.

The API would try to be as smart as possible, like http://cricdata.org. So, you could specify <em>antigua</em> or <em>USD</em> or <em>renminbi</em> and it would try to give you an appropriate response. If ambiguous (e.g. <em>dollar</em>) then it would return a list of matching currencies.
<h3>Crowdsourcing</h3>
Some data, like the currency example, is available for free from an authoritative source (in this case <a href="http://www.currency-iso.org/dl_iso_table_a1.xml">http://www.currency-iso.org/dl_iso_table_a1.xml</a>).

Other data is available from a reliable source such as http://opencorporates.com

But some data might need to be mastered here. In which case a wiki approach could be taken. In this case a reputation-based system would be good so that vandalism could be countered algorithmically. In other words, if you spot some bad data then you can flag it up (possibly anonymously, although an identified person's flagging would be taken more seriously than an anonymous one). Somebody whose contributions are flagged as bad will have their reputation compromised. Data contributed by somebody that is not flagged as bad will increase their reputation depending on how often it is eyeballed.

As a consumer of data you can choose to have all data, regardless of the reputation of the contributor. Or only high-reputation data. Or only authoritative data.
<h3>Data types</h3>
<ul>
	<li>Currencies</li>
	<li>Currency pairs</li>
	<li>Countries</li>
	<li>TLDs</li>
	<li>Second-level domains</li>
	<li>SIC codes</li>
</ul>
Obvious things like ISBNs, stock tickers, ISINs are actually fraught with licensing issues and generally poor design. But some attempt could be made.
<h3>Monetization</h3>
Dream on.
