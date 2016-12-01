---
layout: post
title: HOWTO install Ruby on Rails on Windows and deploy to Heroku
date: 2011-01-21 15:30:14.000000000 +00:00
---
<h2>Why I'm writing this</h2>
I tried for over two days to install <a href="https://guides.rubyonrails.org/getting_started.html" target="_blank">Ruby on Rails</a> on my Windows 7 machine so that I could deploy an app to <a href="https://docs.heroku.com/quickstart" target="_blank">Heroku</a>. Eventually I did it - it wasn't hard but I needed to collate information that wasn't easily to be found in one place. So I'm collating it here.

This is the record of an installation at a particular moment in time: January 2011. By the time you read this, the situation may have changed. If so, please let me know and I'll update this page.

My principle stumbling blocks were these:
<ol>
	<li>The default install of Ruby (1.9.2) is not compatible with the Heroku deployment widget.</li>
	<li>Heroku does not like apps that use the Rails default database (sqlite3).</li>
</ol>
Problem 1 will probably go away quite soon when Heroku update their widget. Problem 2 is easy to fix but it took me long time to find out how to fix it.
<h2>What I did</h2>
What follows is the step-by-step guide to how I got a working install. If you're too impatient to follow this the executive summary is: (1) Install stuff using RailsInstaller, (2) edit the Gemfile before deployment to let Heroku use its own database. Here's the detail:
<ol>
	<li>You need compatible versions of Ruby, Rails and Git. If you have any of these currently installed then I suggest you uninstall them before you go on.</li>
	<li><a href="https://railsinstaller.org/" target="_blank">Download</a> and run the RailsInstaller kit. Follow the defaults unless you want to install it elsewhere. I installed mine to <code>E:AppsRailsInstaller</code> and it works fine.</li>
	<li>From a command window, enter <code><strong>ruby -v</strong></code>
You should see something like this <code>ruby 1.8.7 (2010-12-23 patchlevel 330) [i386-mingw32]</code></li>
	<li>Enter <code><strong>gem -v</strong></code>
You should see something like this <code>1.3.7</code></li>
	<li>Enter <code><strong>rails -v</strong></code>
You should see something like this <code>Rails 3.0.3</code></li>
	<li>Enter <code><strong>git version</strong></code>
You should see something like this <code>git version 1.7.3.1.msysgit.0</code></li>
	<li>Enter <code><strong>sqlite3 --version</strong></code>
You should see something like this <code>3.7.3</code></li>
	<li>OK, we have a basic platform. Now to install the Heroku gem. This is described <a href="https://docs.heroku.com/heroku-command" target="_blank">here</a>: please look at this if you have problems with public keys etc. Hopefully you will just have to enter <code><strong>gem install heroku</strong></code>
With a little luck you will see something like this:
<code>Successfully installed rest-client-1.6.1
Successfully installed configuration-1.2.0
Successfully installed launchy-0.3.7
Successfully installed heroku-1.17.8
4 gems installed
Installing ri documentation for rest-client-1.6.1...
Installing ri documentation for configuration-1.2.0...
Installing ri documentation for launchy-0.3.7...
Installing ri documentation for heroku-1.17.8...
Installing RDoc documentation for rest-client-1.6.1...
Installing RDoc documentation for configuration-1.2.0...
Installing RDoc documentation for launchy-0.3.7...
Installing RDoc documentation for heroku-1.17.8...
</code></li>
	<li>Now you should be able to enter <code><strong>heroku version</strong></code> and see something like <code>heroku-gem/1.17.8</code></li>
	<li>Change directory to where you want to put the application's files. They will go in a new folder you are about to create.</li>
	<li>Enter <code><strong>rails new tutorialapp</strong></code>and you will see this kind of thing:
<pre>      create
      create  README
      create  Rakefile
      create  config.ru
      create  .gitignore
      create  Gemfile
      create  app
      create  app/controllers/application_controller
      create  app/helpers/application_helper.rb
      create  app/mailers
      create  app/models
      create  app/views/layouts/application.html.erb
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/backtrace_silencer
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/secret_token.rb
      create  config/initializers/session_store.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  doc
      create  doc/README_FOR_APP
      create  lib
      create  lib/tasks
      create  lib/tasks/.gitkeep
      create  log
      create  log/server.log
      create  log/production.log
      create  log/development.log
      create  log/test.log
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/favicon.ico
      create  public/index.html
      create  public/robots.txt
      create  public/images
      create  public/images/rails.png
      create  public/stylesheets
      create  public/stylesheets/.gitkeep
      create  public/javascripts
      create  public/javascripts/application.js
      create  public/javascripts/controls.js
      create  public/javascripts/dragdrop.js
      create  public/javascripts/effects.js
      create  public/javascripts/prototype.js
      create  public/javascripts/rails.js
      create  script
      create  script/rails
      create  test
      create  test/fixtures
      create  test/functional
      create  test/integration
      create  test/performance/browsing_test.rb
      create  test/test_helper.rb
      create  test/unit
      create  tmp
      create  tmp/sessions
      create  tmp/sockets
      create  tmp/cache
      create  tmp/pids
      create  vendor/plugins
      create  vendor/plugins/.gitkeep</pre>
</li>
	<li>Enter <code><strong>cd tutorialapp</strong></code> to move to your app's folder</li>
	<li>Enter <code><strong>bundle install</strong></code>and gem will install anything your app needs
<pre>Fetching source index for https://rubygems.org/
Using rake (0.8.7)
Using abstract (1.0.0)
Using activesupport (3.0.3)
Using builder (2.1.2)
Using i18n (0.5.0)
Using activemodel (3.0.3)
Using erubis (2.6.6)
Using rack (1.2.1)
Using rack-mount (0.6.13)
Using rack-test (0.5.7)
Using tzinfo (0.3.24)
Using actionpack (3.0.3)
Using mime-types (1.16)
Using polyglot (0.3.1)
Using treetop (1.4.9)
Using mail (2.2.14)
Using actionmailer (3.0.3)
Using arel (2.0.7)
Using activerecord (3.0.3)
Using activeresource (3.0.3)
Using bundler (1.0.9)
Using thor (0.14.6)
Using railties (3.0.3)
Using rails (3.0.3)
Using sqlite3 (1.3.3)
Installing sqlite3-ruby (1.3.3)
Your bundle is complete! Use `bundle show [gemname]` to see where a bundled gem is installed.</pre>
</li>
	<li>Enter <code><strong>rails server</strong></code> and the mini web server will start your application on port 3000.
You should see this in the command window
<code>=&gt; Booting WEBrick
=&gt; Rails 3.0.3 application starting in development on https://0.0.0.0:3000
=&gt; Call with -d to detach
=&gt; Ctrl-C to shutdown server
[2011-01-21 14:33:22] INFO WEBrick 1.3.1
[2011-01-21 14:33:22] INFO ruby 1.8.7 (2010-12-23) [i386-mingw32]
[2011-01-21 14:33:22] INFO WEBrick::HTTPServer#start: pid=8932 port=3000</code>
and this in a web browser when you navigate to <em>https://localhost:3000</em>
<a href="https://blog-dominicsayers.rhcloud.com/wp-content/uploads/2011/01/webpagelocal.png"><img class="aligncenter  wp-image-551" title="Rails new app" src="https://res.cloudinary.com/dominicsayers/image/upload/v1399584839/webpagelocal_xakuln.png" alt="" /></a></li>
	<li>Enter <strong>Ctrl-C</strong> in the command window to terminate the local web server</li>
	<li>Enter <code><strong>git init</strong></code> and git will initialize a repository in the current folder.
<code>Initialized empty Git repository in C:/Path/to/your/dev/folder/tutorialapp/.git/</code></li>
	<li>Enter <code><strong>git add .</strong></code></li>
	<li>Enter <code><strong>git commit -m "first commit"</strong></code>
<pre>[master (root-commit) fd8c17d] first commit
 40 files changed, 10287 insertions(+), 0 deletions(-)
 create mode 100644 .gitignore
 create mode 100644 Gemfile
 create mode 100644 Gemfile.lock
 create mode 100644 README
 create mode 100644 Rakefile
 create mode 100644 app/controllers/application_controller.rb
 create mode 100644 app/helpers/application_helper.rb
 create mode 100644 app/views/layouts/application.html.erb
 create mode 100644 config.ru
 create mode 100644 config/application.rb
 create mode 100644 config/boot.rb
 create mode 100644 config/database.yml
 create mode 100644 config/environment.rb
 create mode 100644 config/environments/development.rb
 create mode 100644 config/environments/production.rb
 create mode 100644 config/environments/test.rb
 create mode 100644 config/initializers/backtrace_silencers.rb
 create mode 100644 config/initializers/inflections.rb
 create mode 100644 config/initializers/mime_types.rb
 create mode 100644 config/initializers/secret_token.rb
 create mode 100644 config/initializers/session_store.rb
 create mode 100644 config/locales/en.yml
 create mode 100644 config/routes.rb
 create mode 100644 db/seeds.rb
 create mode 100644 doc/README_FOR_APP
 create mode 100644 lib/tasks/.gitkeep
 create mode 100644 public/404.html
 create mode 100644 public/422.html
 create mode 100644 public/500.html
 create mode 100644 public/favicon.ico
 create mode 100644 public/images/rails.png
 create mode 100644 public/index.html
 create mode 100644 public/javascripts/application.js
 create mode 100644 public/javascripts/controls.js
 create mode 100644 public/javascripts/dragdrop.js
 create mode 100644 public/javascripts/effects.js
 create mode 100644 public/javascripts/prototype.js
 create mode 100644 public/javascripts/rails.js
 create mode 100644 public/robots.txt
 create mode 100644 public/stylesheets/.gitkeep
 create mode 100644 script/rails
 create mode 100644 test/performance/browsing_test.rb
 create mode 100644 test/test_helper.rb
 create mode 100644 vendor/plugins/.gitkeep</pre>
</li>
	<li>Enter <code><strong>heroku create</strong></code>
<code>Enter your Heroku credentials.
Email: joe@example.com
Password:
Uploading ssh public key /Users/joe/.ssh/id_rsa.pub
Creating blooming-wind-752..... done
https://blooming-wind-752.heroku.com/ | git@heroku.com:blooming-wind-752.git
Git remote heroku added</code></li>
	<li>This is the only time Heroku will ask for your credentials. If you have an existing <code>id_rsa.pub</code> file in the <code>.ssh</code> folder in your home directory then Heroku will use it. Otherwise it will create one for you (if I remember correctly).</li>
	<li>There is now a Heroku app ready for your code. We just need to upload the code we commited to git. To do this enter <code><strong>git push heroku master</strong></code>and you will see this
<pre>Warning: Permanently added the RSA host key for IP address '75.101.145.87' to the list of known hosts.
Counting objects: 63, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (48/48), done.
Writing objects: 100% (63/63), 85.99 KiB, done.
Total 63 (delta 3), reused 0 (delta 0)

-----&gt; Heroku receiving push
-----&gt; Rails app detected
-----&gt; Detected Rails is not set to serve static_assets
       Installing rails3_serve_static_assets... done
-----&gt; Gemfile detected, running Bundler version 1.0.3
       Unresolved dependencies detected; Installing...
       Fetching source index for https://rubygems.org/
       Installing rake (0.8.7)
       Installing abstract (1.0.0)
       Installing activesupport (3.0.3)
       Installing builder (2.1.2)
       Installing i18n (0.5.0)
       Installing activemodel (3.0.3)
       Installing erubis (2.6.6)
       Installing rack (1.2.1)
       Installing rack-mount (0.6.13)
       Installing rack-test (0.5.7)
       Installing tzinfo (0.3.24)
       Installing actionpack (3.0.3)
       Installing mime-types (1.16)
       Installing polyglot (0.3.1)
       Installing treetop (1.4.9)
       Installing mail (2.2.14)
       Installing actionmailer (3.0.3)
       Installing arel (2.0.7)
       Installing activerecord (3.0.3)
       Installing activeresource (3.0.3)
       Using bundler (1.0.3)
       Installing thor (0.14.6)
       Installing railties (3.0.3)
       Installing rails (3.0.3)
       Installing sqlite3-ruby (1.3.3)
       Your bundle is complete! It was installed into ./.bundle/gems/
       Compiled slug size is 3.7MB
-----&gt; Launching... done
       https://blooming-wind-752.heroku.com deployed to Heroku

To git@heroku.com:blooming-wind-752.git
 * [new branch]      master -&gt; master</pre>
</li>
	<li>Now enter <code>h<strong>eroku open</strong></code>and the app will open in your browser. Unfortunately you will get the dreaded App Crashed message:

[caption id="attachment_552" align="aligncenter" width="300" caption="App crashed. Please check your Heroku logs for the backtrace."]<a href="https://blog-dominicsayers.rhcloud.com/wp-content/uploads/2011/01/webpageherokubad.png"><img class="size-medium wp-image-552" title="Heroku app crashed. Heroku sad." src="https://res.cloudinary.com/dominicsayers/image/upload/h_93,w_300/v1399584838/webpageherokubad_fzkvw2.png" alt="" width="300" height="93" /></a>[/caption]</li>
	<li>To fix this, edit the file <code>Gemfile</code>in the root folder of your app. Change the following line
<pre>gem 'sqlite3-ruby', :require =&gt; 'sqlite3'</pre>
to look like this
<pre><strong>group :development, :test do gem 'sqlite3-ruby', :require =&gt; 'sqlite3' end</strong></pre>
What this does is tell Rails you want to use the sqlite3 database in your development and test environments, and you don't specify what Heroku will use in the production environment. This make Heroku happy. Heroku no like sqlite3.</li>
	<li><code><strong>git add .</strong></code></li>
	<li><code><strong>git commit -m "second commit"</strong></code>
<pre>[master d0bfbc5] second commit
 1 files changed, 3 insertions(+), 1 deletions(-)</pre>
</li>
	<li><code><strong>git push heroku</strong></code>
<pre>Counting objects: 5, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 318 bytes, done.
Total 3 (delta 2), reused 0 (delta 0)

-----&gt; Heroku receiving push
-----&gt; Rails app detected
-----&gt; Detected Rails is not set to serve static_assets
       Installing rails3_serve_static_assets... done
-----&gt; Gemfile detected, running Bundler version 1.0.3
       Unresolved dependencies detected; Installing...
       Fetching source index for https://rubygems.org/
       Installing rake (0.8.7)
       Installing abstract (1.0.0)
       Installing activesupport (3.0.3)
       Installing builder (2.1.2)
       Installing i18n (0.5.0)
       Installing activemodel (3.0.3)
       Installing erubis (2.6.6)
       Installing rack (1.2.1)
       Installing rack-mount (0.6.13)
       Installing rack-test (0.5.7)
       Installing tzinfo (0.3.24)
       Installing actionpack (3.0.3)
       Installing mime-types (1.16)
       Installing polyglot (0.3.1)
       Installing treetop (1.4.9)
       Installing mail (2.2.14)
       Installing actionmailer (3.0.3)
       Installing arel (2.0.7)
       Installing activerecord (3.0.3)
       Installing activeresource (3.0.3)
       Using bundler (1.0.3)
       Installing thor (0.14.6)
       Installing railties (3.0.3)
       Installing rails (3.0.3)
       Installing sqlite3-ruby (1.3.3)
       Your bundle is complete! It was installed into ./.bundle/gems/
       Compiled slug size is 3.7MB
-----&gt; Launching... done
       https://blooming-wind-752.heroku.com deployed to Heroku

To git@heroku.com:blooming-wind-752.git
   fd8c17d..d0bfbc5  master -&gt; master</pre>
</li>
	<li>With luck and a following wind, when you now try <code><strong>heroku open</strong></code> your Heroku-hosted app will now look like this:
<a href="https://blog-dominicsayers.rhcloud.com/wp-content/uploads/2011/01/webpagelocal.png"><img class="aligncenter  wp-image-551" title="Rails new app" src="https://res.cloudinary.com/dominicsayers/image/upload/v1399584839/webpagelocal_xakuln.png" alt="" /></a></li>
	<li>That's it from me. You're now on your own making the app do something useful...</li>
</ol>
There are plenty of other tutorials on Getting Started with Ruby on Rails and Heroku. This is just to get you over a hurdle that I faced and which took me a lot of effort to get over. Hopefully I've saved you some time.
Thanks to <a href="https://www.oozou.com/" target="_blank">Jan Jones</a> for the RailsInstaller tip.
