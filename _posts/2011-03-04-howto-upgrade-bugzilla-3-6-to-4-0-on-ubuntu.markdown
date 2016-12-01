---
layout: post
title: HOWTO Upgrade Bugzilla 3.6 to 4.0 on Ubuntu
date: 2011-03-04 12:44:42.000000000 +00:00
---
If I had known what a 1337 exercise this was going to be I would have ignored the  seductive message that appeared on my Bugzilla home page.

WARNING: If Bugzilla tries to tempt you into upgrading from 3.6 to 4.0 then you should know this is not very well automated.

My server was running Bugzilla 3.6 on Ubuntu 10.04.2 LTS with Apache 2.2.14 and MySQL 5.1.41

Here's what I had to do (from memory - sorry).
<ol>
	<li><code>apt-get install libapache2-mod-perl2 apache2-dev</code></li>
	<li>Create a file called <code>/etc/apache2/mods-enabled/perl.conf</code> with the following lines (check the path is correct for your installation)
<pre>PerlSwitches -w -T
PerlConfigRequire /var/www/bugzilla/mod_perl.pl</pre>
</li>
	<li>Edit the Apache conf file for the Bugzilla site (on my server it was <code>/etc/apache/sites-enabled/000-default</code>). Make sure there is a <code>&lt;Directory&gt;</code> entry for your Bugzilla installation. Make sure the <code>AllowOverride</code> line is correct according to the <a href="http://www.bugzilla.org/releases/4.0/release-notes.html#v40_upgrading" target="_blank">Bugzilla installation instructions</a>. Mine looked like this after:
<pre>&lt;Directory /var/www/bugzilla&gt;
        AllowOverride Limit FileInfo Indexes
&lt;/Directory&gt;</pre>
</li>
	<li>Enable the following Apache modules (I use Webmin to do this; if you want to do this the man's way then ask a nerd):
<ul>
	<li><code>mod_headers</code></li>
	<li><code>mod_expires</code></li>
	<li><code>mod_env</code></li>
</ul>
</li>
	<li>Restart Apache. There may be a clever way to do this, but I used <code>/etc/init.d/apache2 restart</code></li>
	<li>Follow the instructions in the tempting message on the home page, then do the following additional steps</li>
	<li><code>cd /var/www/bugzilla</code></li>
	<li><code>./checksetup.pl</code></li>
	<li>Whoa! It's all broken. Never mind - if you look carefully you'll see the magic command to fix everything is there. It looks something like <code>/usr/bin/perl install-module.pl all</code> (copy it from the output of <code>checksetup.pl</code>, not from here)</li>
	<li>If you're getting error messages at the bottom of the output from <code>checksetup.pl</code> then try this<pre>/usr/bin/perl install-module.pl DateTime:Locale</pre></li>
</ol>
That's pretty much it. If it still doesn't work then try restarting Apache again. If you have to do anything else then let me know and I'll add it here. Also if I've made any mistakes then I'm happy to correct them.
