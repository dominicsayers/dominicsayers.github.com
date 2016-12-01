---
layout: post
title: confused@rfc5322.com
date: 2009-02-23 13:17:35.000000000 +00:00
---
<h4>Quick links: <a href="http://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="http://isemail.info/" target="_blank">Email address validation service</a></h4>
Do you think this is a valid email address?
<blockquote><em>""@example.com</em></blockquote>
No, me neither. In one sense it clearly isn't since there is no mailbox of that name at example.com's mail host. Send <a href="mailto:&quot;&quot;@example.com" target="_blank">mail</a> to that address and you won't find anybody reading it.

In another sense, however, it is a perfectly good email address. That is, if you believe the RFCs that define how email addresses should be constructed. Here's the <a href="http://en.wikipedia.org/wiki/Backus%E2%80%93Naur_form" target="_blank">BNF</a> from <a href="http://tools.ietf.org/html/rfc5322#section-3.4.1" target="_blank">RFC5322</a> for example:
<pre class="newpage">addr-spec       =       local-part "@" domain</pre>
<pre class="newpage">local-part      =       dot-atom / quoted-string / obs-local-part</pre>
<pre class="newpage">quoted-string   =       [<a href="http://tools.ietf.org/html/rfc2822#ref-CFWS">CFWS</a>]
                        DQUOTE *([<a href="http://tools.ietf.org/html/rfc2822#ref-FWS">FWS</a>] qcontent) [<a href="http://tools.ietf.org/html/rfc2822#ref-FWS">FWS</a>] DQUOTE
                        [<a href="http://tools.ietf.org/html/rfc2822#ref-CFWS">CFWS</a>]</pre>
Don't worry if you can't follow the BNF syntax - I couldn't either until this week. Focus on the asterisk before <em>([</em><a href="http://tools.ietf.org/html/rfc2822#ref-FWS"><em>FWS</em></a><em>] qcontent)</em>. That asterisk means the contents of that bracket can occur <strong>zero</strong> or more times.

So tracing it through the specification:
<ol>
	<li>An email address is a <em>local-part</em> followed by an <em>@</em> sign followed by a <em>domain</em></li>
	<li>A <em>local-part</em> can be a <em>quoted-string</em></li>
	<li>A <em>quoted-string</em> is a pair of double quotes surrounding <em><strong>zero or more characters</strong></em>.</li>
</ol>
""@example.com follows these rules perfectly. And yet common sense suggests this is a preposterous address. Where should the receiving host deliver it?

I have had some discussions about this with <a href="http://www.iamcal.com/help/cal/" target="_blank">Cal Henderson</a> and we are somewhat at a loss. Both of us have <a href="http://www.dominicsayers.com/isemail/" target="_blank">functions that validate email addresses</a> and we cannot decide whether to follow the RFCs or common sense.

I could suggest the <a href="http://en.wikipedia.org/wiki/IETF" target="_blank">IETF</a> add an <a href="http://www.rfc-editor.org/" target="_blank">erratum</a> to their RFC but this format is also documented in RFC <a href="http://tools.ietf.org/html/rfc5321#section-4.1.2" target="_blank">5321</a> as well. No amount of published errata will correct the impression given by two published RFCs.

Perhaps we are wrong - can you think of a valid purpose for an email address of this format?
<h4>Quick links: <a href="http://code.google.com/p/isemail/source/browse/#svn/trunk" target="_blank">Source code</a> | <a title="Email address validation" href="http://isemail.info/" target="_blank">Email address validation service</a></h4>
