---
layout: post
title: Lobster Hatstand
date: 2011-03-23 14:21:29.000000000 +00:00
tags: justhost
---
I've had a few minor outages of this blog and other sites hosted by JustHost. I'm not particularly worried so long as they get to the bottom of it and stop it happening again.

My uptime over the last 12 months has been 99.97%, which I'm perfectly happy with.

But I'm a bit bemused by the attitude of their support people, who seem to be satisfied that the server is up when they look at it. No attempt to check if it has an internet connection, no intention to do root cause analysis, not even an admission that there is a problem.

I reproduce here my entire conversation with them over the last few days: there are some masterpieces of surreal logic. I sort of suspect they are all native English speakers who are trying to wind me up deliberately. If so, they succeeded.
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/21/2011 10:29:11AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">Domain: noo.gs

Pingdom and Altertra are reporting that my websites on cx52.justhost.com are
unavailable.</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/21/2011 10:32:13AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">OK, they're back.

Would appreciate an explanation.</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/21/2011 12:33:07PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">Hi Dominic,

I've just checked and the website noo.gs works fine. Our server has been up for
66 days already. The causes could be different. If you still have the problem,
please, provide us with the screen shot of the error.
<a href="http://www.wikihow.com/Take-a-Screenshot-in-Microsoft-Windows" target="_blank">http://www.wikihow.com/Take-a-Screenshot-in-Microsoft-Windows</a>

Let us know if you need any help.

--
Kind regards,
Marcus Gervaise
Just Host</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/21/2011 12:57:58PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">Hi Marcus,

As I said in my update several hours ago, I know the service is working
again now.

Two separate monitoring services (Pingdom and Alertra) notified me of
the interruption from monitoring points worldwide. Attached is the
detailed Pingdom log for the error.

I'm looking for two things from you:

(1) An acknowledgement of the service interruption.
(2) An indication of your intention to do root cause analysis and inform
me of the results

I'm aware of your terms of service, but I'd like you to take this
seriously. Your uptime figure is not a proof that connectivity has been
continuously maintained.

What does "The causes could be different" mean, please? The causes of
what? Different from what?

Regards,

Dominic Sayers</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/21/2011 2:01:56PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">Hi Dominic,

There was no interruption on the server. One of the possible causes could be
blocking of your WAN IP, because of to many parallel connections. I can't tell
you for sure what causes the problem, because I don't see any error and you
don't too, because as far as I understand you don't have any problem with the
accessing your website. We can check only your current connection to our
server.
You may  check the hosting of your website via the following link:

<a href="http://host-tracker.com/" target="_blank">http://host-tracker.com/</a>

Let us know if you need any help.

--
Kind regards,
Marcus Gervaise
Just Host</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/21/2011 5:19:40PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">Hello Marcus,

"To [sic] many parallel connections" - what is the limit on parallel
connections? Could you also point me to the clause in your Ts &amp; Cs that
limits the parallel connections I am allowed? Which of your Cpanel
monitoring tools allows me to track the peaks in parallel connections?

By the way, I am not unhappy with your service in general, just with
your response to this incident. You do not seem to be taking seriously
the demonstrable failure in the service I pay for.

Looking at the total traffic across all my sites, this was another very
low volume day. I think it unlikely that any parallel connections limit
was breached.

Sorry Marcus but you have so far come up with two possible explanations
based on no evidence. Do I understand from this that the 24/7 network
monitoring that is promised on your sales pages
&lt;<a href="http://www.justhost.com/guarantees#ic&gt;" target="_blank">http://www.justhost.com/guarantees#ic&gt;</a> amounts to nothing that is
useful for diagnosing the root cause of my problem?

Regards,

Dominic Sayers</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/21/2011 7:02:59PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">Dear  Dominic,

Please take my apologies but, the maximum allowed quota of the connection to
the server is 50. We use a couple of monitoring systems that use this limit as
rule and if it is overloaded they just send warning messages. That action
allows us to discover DDoS attacks. As you probably understand it would be too
hard to block those IPs manually so we use our custom scripts and scripts that
cPanel offers by default. Some of that IPs are blocked temporary. ( from 1 to
30 min)
Each of those scripts monitor its own part of our system moreover they
contacting each other in order to block the problematic part in the system and
in the end they make the entire firewall system.
As for this incident: I can confirm that cx52 was not down. Current uptime of
your server is: 18:00:15 up 66 days, 11:56,  1 user,  load average: 2.76, 2.00,
1.94

Let me know if you have more questions.
- - - - - - -
Kind regards,
Yates Stebljanko
Just Host</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/21/2011 7:06:35PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">Thanks for the quick reply.

If the cause of the outage was not (1) connection quota or (2) server
downtime then what do you think it was?

Will it happen again?

Regards,

Dominic</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/21/2011 8:11:10PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">Dear  Dominic,

Unfortunately I can't say what the real problem was.
I hope this never happen again.
Sorry for caused inconveniences.
Thank you
- - - - - - -
Kind regards,
Yates Stebljanko</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/22/2011 5:27:26AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">I hoped so too. Unfortunately the sites were unavailable again this
morning from 04:33 to 05:44. Attached is the log from my monitoring
service Pingdom.

Can you say what the reason for this extended outage was?</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/22/2011 6:06:43AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">HI Dominic,

Sorry, but we were forced to restart our server that time
(as it was a necessary kernel update there)
thank you for the understanding.
Please let me know if you need more help.
--
Kind regards,
Max Pinner

Just Host</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/22/2011 7:38:33AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">Why was it down for over an hour?</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/22/2011 8:16:14AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">HI Dominic,

It was not for an hour , it was just for 20-30 min from our end.
It would be better to provide us with the traceroute result from your end.
traceroute noo.gs
It would be helpful to investigate this issue for that moment.
As it might be the connect brake down from your end also.
--
Kind regards,
Max Pinner

Just Host</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/22/2011 8:25:28AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">Sorry, I don't understand your English.

I provided you with a log of monitoring from many different cities that
shows the web sites were unavailable for 1 hour 11 minutes. I do not pay
just for the server to be up, I pay for it to be on the internet.

Here are traceroutes from Madrid and Washington DC during the outage
(03/22/2011 04:34:50AM)

[traceroutes omitted for brevity (!)]</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/22/2011 10:32:43AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">Dear Dominic Sayers,

Please also show me your WAN IP address:
<a href="http://mywanip.com/" target="_blank">http://mywanip.com/</a>
It's necessary to check if your IP address wasn't blocked on the server.

--
Kind regards,
Vadim Dodds
Just Host</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/22/2011 10:37:27AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">In my last two messages I explained that the service was unavailable
from multiple locations. I provided 2 kinds of evidence that this was
the case.

Why would the IP address from another location help?

It's 217.144.158.42 here but that's irrelevant: the service is available
to everyone now, including here.</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/22/2011 12:04:44PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">Dear Dominic Sayers,

1) I have added your IP to white list of our server - please check your access
to site now and inform me about results.

2) FSCK process was completed and now your site is working well. We apologize
for the inconveniences caused to you.

--
Kind regards,
Vadim Dodds
Just Host</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/22/2011 12:29:35PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">This IP address was already on the whitelist.

What was the cause of the 1 hour outage this morning?</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/22/2011 9:22:47PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">Hi Dominic

Thank you for your email.

I am sorry to hear of the recent experience you have had with Just Host, I can
assure you was an isolated event and we pride ourselves on exceptional uptime.


Just Host is committed to providing a secure and reliable hosting environment.
Customer websites are hosted on high performance quad processor servers, and
our data center is equipped with a UPS power back-up generator. We perform 24/7
network monitoring, so if an issue does arise, we can address it immediately.

Thank you in advance for your patience and understanding and apologies for any
inconvenience caused.

Kind regards,
Aiden

--
Aiden Pilcher</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/23/2011 6:29:09AM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">Hi Aidan,

The ironic thing is that you sent this during another period of
downtime. There have now been four incidents, starting on Monday after a
long period of uptime (several months). This is no longer an isolated
incident.

I'm disappointed in the technical staff's ability to read the
information I am giving them, often asking me to supply information that
was in a previous email. Each shift seems to start the process from
scratch as if it was a new incident.

Several times they have assured me that the server is up and I must be
mistaken. My point is that I am buying an internet-connected service and
it is the connectivity that appears to be the issue. The monitoring
attached is from Pingdom, which checks uptime from many cities around
the world. All their monitoring locations found my sites unavailable at
the times you can see.

I do not understand why it takes up to 71 minutes to restore
connectivity when it is lost. I do not understand why no root cause
analysis has been done on what is clearly a systematic problem.

I have had 99.97% uptime in the last 12 months. That is very good and I
am happy with that level of service. Please don't let yourselves down now.

Regards,

Dominic Sayers</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#f1f1fe"><strong>Sent</strong> to <a title="Dominic Sayers &lt;dominic@sayers.cc&gt;" href="mailto:Dominic Sayers &lt;dominic@sayers.cc&gt;">Dominic Sayers</a> on <strong>Mar/23/2011 12:24:47PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#f1f1fe">
<pre>Hi Dominic,

Thank you for your reply.

The Just Host team are always happy to help out, please do not hesitate to contact us if you have any other questions or queries in the future. As always, feedback is greatly appreciated.

This ticket will now be closed.

Kind regards,
<div>--
Izzy

Izzy Sturgess</div></pre>
</td>
</tr>
</tbody>
</table>
<table border="0" cellspacing="1" cellpadding="4" width="100%" bgcolor="#CCCCCC">
<tbody>
<tr height="10">
<td bgcolor="#ffffff"><strong>Received</strong> on <strong>Mar/23/2011 12:31:35PM</strong></td>
</tr>
<tr>
<td valign="top" bgcolor="#ffffff">I just told you about a serious ongoing problem. On what basis are you  closing this ticket?

1. Please keep the ticket open until the root cause analysis has been  completed
2. Please let me know what you have done to prevent any further outages</td>
</tr>
</tbody>
</table>
&lt;silence&gt;
