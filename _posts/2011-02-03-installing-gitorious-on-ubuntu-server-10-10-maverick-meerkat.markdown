---
layout: post
title: Installing Gitorious on Ubuntu Server 10.10 (Maverick Meerkat)
date: 2011-02-03 15:26:20.000000000 +00:00
---
Thanks to Christian Johansen for the excellent detailed instructions on setting up Gitorious <a href="https://cjohansen.no/en/ruby/setting_up_gitorious_on_your_own_server" target="_blank">here</a>. I eventually got it working, which I would not have done without this help. Here are some notes from setting it up on the following versions:
<pre>Ubuntu Server 10.10 as a VMware VM
ruby 1.8.7 (2010-06-23 patchlevel 299) [i686-linux]
RubyGems 1.5.0
Rails 3.0.3
ActiveMQ 5.4.2</pre>
<ol>
	<li>I got as far as
<pre>sudo rake gems:install</pre>
and got the following error:
<pre>rake aborted!
Your config/gitorious.yml does not have an entry for your current Rails environment. Please consult config/gitorious.sample.yml for instructions.</pre>
which I fixed by doing
<pre>sudo rake gems:install RAILS_ENV=production</pre>
</li>
	<li>Then I got an error "<code>undefined local variable or method `version_requirements'</code>" which had me stuck for a while (being a Rails n00b). Google eventually led me to this: <a href="https://www.redmine.org/issues/7516" target="_blank">https://www.redmine.org/issues/7516</a> and the <code>environment.rb</code> hack from Phillip Koebbe fixed it for me.</li>
	<li>When adding the first user, the command
<pre>script/console</pre>
gave me the following messages
<pre>Loading development environment (Rails 2.3.5)
/var/www/git.moo.li/gitorious/config/environment.rb:26:RuntimeError: Your config/gitorious.yml does not have an entry for your current Rails environment. Please consult config/gitorious.sample.yml for instructions.
/var/www/git.moo.li/gitorious/vendor/rails/railties/lib/rails/backtrace_cleaner.rb:2:NameError: uninitialized constant ActiveSupport::BacktraceCleaner
/var/www/git.moo.li/gitorious/vendor/rails/railties/lib/console_with_helpers.rb:5:NameError: uninitialized constant ApplicationController</pre>
so I tried
<pre>env RAILS_ENV=production ruby script/console</pre>
which worked fine. Presumably I could <code>export $RAILS_ENV=production</code> to fix both these?</li>
	<li>I couldn't login until I'd enabled Passenger and Apache because the mongrel server on port 3000 didn't like the fact that the Gitorious login page had an <code>https://</code> URL. In other words, I had to defer the user setup until I had the Passenger server working.</li>
	<li>The Passenger install only instructed me to create a <code>passenger.load</code> file. A <code>passenger.conf</code> wasn't needed.</li>
	<li>In the section on enabling some Apache modules, <code>rewrite</code> is enabled twice, which is unnecessary.</li>
	<li>I couldn't run the login page at first until I installed the i18n gem v0.1 - it didn't like the v0.5 version.</li>
	<li>At first I couldn't upload my public key. This seemed to be a problem with ActiveMQ. I added the following line to <code>activemq.xml</code>
<pre>&lt;transportConnector name="stomp" uri="stomp://0.0.0.0:61613"/&gt;</pre>
(there wasn't a stomp connector in there before). By the way, there were no <code>networkConnectors</code> lines in my <code>activemq.xml</code> so I didn't change the multicasting setup.</li>
	<li>I also did <code>update-rc.d activemq defaults</code> so that ActiveMQ starts at boot time.</li>
	<li>[EDITED to add:]
I also found that the Sphinx cron job was causing errors. Here's what I did to fix it. Firstly, the cron job couldn't find the <code>indexer</code> command, so I did a <code>crontab -e</code> and added the following lines to the crontab.
<pre>SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin</pre>
</li>
	<li>Also, the cron rob running every minute was creating a lot of unecessary mail, so I appended <code>&nbsp;&gt; /dev/null</code> to the end of the line defining the job.</li>
	<li>Next the Sphinx configuration file was using the deprecated Sphinx <code>searchd</code> options <code>address</code> and <code>port</code> so I commented them out and added the <code>listen</code> option instead. I did this in both the <code>production.conf</code> and <code>default.base</code> files within the <code>config/ultrasphinx</code> folder of the Gitorious app. Here's what those lines in the <code>searchd</code> section looked like afterwards:
<pre>#  address = 0.0.0.0
#  port = 3312
  listen = 0.0.0.0:3312</pre>
</li>
</ol>
