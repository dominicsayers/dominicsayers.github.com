---
layout: post
title: HOWTO Install dig on Windows 7
date: 2011-03-03 15:41:43.000000000 +00:00
---
<script type="text/javascript">// <![CDATA[
// < ![CDATA[
// < ![CDATA[  google_ad_client = "ca-pub-2148551173170619"; /* Hotmail account compromised */ google_ad_slot = "7289443389"; google_ad_width = 468; google_ad_height = 60;
// ]]></script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js">// <![CDATA[
// < ![CDATA[
// ]]></script>

The short version:
<ol>
	<li>Create a folder for the dig application (I used <code>E:\apps\dig</code>)</li>
	<li>Download the latest version of BIND from the <a title="Internet Systems Consortium" href="http://www.isc.org/software/bind" target="_blank">Internet Systems Consortium</a> website.</li>
	<li>Open the <code>.zip</code> archive and extract <code>dig.*</code> and <code>*.dll</code> into your application folder</li>
	<li>Add the application folder to your path</li>
	<li>Double-click <code>vcredist_x86.exe</code> to install the Microsoft Visual C++ 2005 Redistributable (you may not need to do this if you're sure it's already installed)</li>
</ol>
All of these steps might need a little more explanation for an inexperienced person. But then if you're an inexperienced person, why do you need <code>dig</code>? Happy to expand on any of the above steps if you wish - just add a comment here.

<script type="text/javascript">// <![CDATA[
// < ![CDATA[
// < ![CDATA[  google_ad_client = "ca-pub-2148551173170619"; /* Hotmail account compromised */ google_ad_slot = "7289443389"; google_ad_width = 468; google_ad_height = 60;
// ]]></script>
<script type="text/javascript" src="http://pagead2.googlesyndication.com/pagead/show_ads.js">// <![CDATA[
// < ![CDATA[
// ]]></script>
