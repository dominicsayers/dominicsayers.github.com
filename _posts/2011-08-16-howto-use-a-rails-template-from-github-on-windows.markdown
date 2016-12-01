---
layout: post
title: HOWTO use an application template from GitHub when you're developing in Rails
  on Windows
date: 2011-08-16 15:10:49.000000000 +01:00
---
Ruby has some tools for interacting with websites. I guess they are mainly wrappers around <code>cURL</code>. When the target website uses SSL (e.g. <code>https://github.com/...</code>) then the server will present a certificate to identify itself. The Ruby script needs to verify the Certificate Authority (CA) that issued this certificate, otherwise you might be downloading from an imposter site.

The list of CAs is maintained in one or more <code>.pem</code> files in a known place in your file system. At least that's true on Linux and OS X, but not Windows. Windows is different and CA verification in Ruby is broken. Windows is a minority platform for Rails developers so this isn't a big issue for them and it has remained unfixed through several version of Ruby and Rails. If you try to connect to an SSL site on Windows you'll get these sort of messages:
<pre>C:/Ruby1.9.2/lib/ruby/1.9.1/net/http.rb:678:in `connect':
SSL_connect returned=1 errno=0 state=SSLv3 read server certificate
B: certificate verify failed (OpenSSL::SSL::SSLError)</pre>
You can work around this in your code by downloading a <code>.pem</code> file containing CA certificates and putting it a known place, then setting <code>http.ca_path</code> to the folder containing the <code>.pem</code> file. Or you can turn off verification altogether by setting <code>http.verify_mode = OpenSSL::SSL::VERIFY_NONE</code>. Neither of these solutions is ideal but that's what you're stuck with if you insist on developing Rails apps on Windows.

But if it's not your app that's broken but Rails itself then you need to dig into the internals a bit to fix this. I came across the error when using a template from GitHub to create a new Rails app:
<pre>rails new myapp -m https://github.com/russfrisch/h5bp-rails/raw/master/h5bp.rb</pre>
I finally found a fix by hacking the <code>open-uri.rb</code> file in <code>C:/Ruby1.9.2/lib/ruby/1.9.1/</code> (of course your path might be different). I simply changed the default SSL verification mode to <code>OpenSSL::SSL::VERIFY_NONE</code> as described above. In my version it was line 288 and I changed it to read like this:
<pre>http.verify_mode = options[:ssl_verify_mode] || OpenSSL::SSL::VERIFY_NONE</pre>
There may be other approaches: the stack trace from the original error pointed at the Thor gem which is responsible for applying the template. This may give us a clue to why the problem hasn't been fixed: the Rails gem, the Thor gem and the core Ruby scripts <code>open-uri.rb</code> and <code>/net/http.rb</code> are all maintained by different developers. All their code probably works as intended in isolation - it's the combination that gives us a problem in one particular environment.

I'd raise a bug but I don't know which door to lay it at.
