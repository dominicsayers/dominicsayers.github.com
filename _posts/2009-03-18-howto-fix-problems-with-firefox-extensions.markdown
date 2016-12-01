---
layout: post
title: 'HOWTO: Fix problems with Firefox extensions'
date: 2009-03-18 10:51:35.000000000 +00:00
---
I have been having problems with a <a href="https://www.firefox.com/" target="_blank">Firefox</a> extension that disappeared whenever I upgraded either Firefox or the extension itself. My specific problem was with an extension called <a href="https://getfirebug.com/" target="_blank">Firebug</a>, but I'm betting this affects other add-ons too.

After extensive searching I eventually came up with an answer that worked for me. I'm posting it here so other people might avoid the hot tears of frustration that I cried trying to fix this.
<h3>The symptom</h3>
You choose a Firefox extension by clicking on the install link, the extension downloads and installs. You click the button to restart Firefox and the extension is simply not there. No error message, no indication why it failed. Just stubborn, passive-aggressive refusal to install. Arms folded, lips pursed, the extension just won't do what you want. Gah.
<h3>The solution</h3>
Yes, it's the old favourite - your virus checker. In my case all I had to do was open the <a href="https://free.avg.com/" target="_blank">AVG Anti-Virus</a> control panel, double-click Resident Shield and unclick the "Resident Shield active" checkbox. Click on Save Changes. Then if you repeat the Firefox estension install you should find it installs OK.

Don't forget to turn your virus checker back on afterwards.
