---
layout: post
title: Definition of root cause
date: 2007-11-29 12:00:30.000000000 +00:00
---
I was asked for a definition of <em>root cause</em> today. Here is what I came up with:
<p style="margin:0;" class="MsoNormal"><font face="Calibri">ITIL doesn’t define “root cause” in any useful way. The official ITIL definition is “the underlying or original cause of an Incident or Problem” (ITIL v3 glossary). </font></p>
<font face="Calibri">CMMI is more helpful: “A root cause is a source of a defect such that if it is removed, the defect is decreased or removed.” (CMMI v1.1, Causal Analysis and Resolution process area).</font>

<font face="Calibri">There are two effective parts to a useful definition: a root cause is that which <strong>we</strong> can alter to effect a <strong>permanent fix</strong> to a problem. So the important points are (i) addressing the root cause fixes the problem and (ii) it is something we can directly affect.</font>

<font face="Calibri">Examples:</font>

<span><span><font face="Calibri">1.</font><span style="font:7pt 'Times New Roman';">       </span></span></span><font face="Calibri">Database fails because it is full. The root cause is that we failed to monitor its usage effectively to take preventative action in time. So the action we take to fix the Incident (increase the database size) is different to the action we take to fix the Problem (start monitoring capacity usage effectively).</font>

<span><span><font face="Calibri">2.</font><span style="font:7pt 'Times New Roman';">       </span></span></span><font face="Calibri">Database fails because a virus infects the database software. Here we are not interested in the coding error that allowed the virus to strike, we are only interested in addressing our technology choice or patching regime. In other words, the root cause for the vendor (software bug) is different to the root cause for us (technology management).</font>

Wikipedia is very helpful on this and has good articles on <a target="_blank" href="https://en.wikipedia.org/wiki/Root_cause">root cause</a> and <a target="_blank" href="https://en.wikipedia.org/wiki/Root_cause_analysis">root cause analysis</a>. The temptation is to get too philosophical about causation when a useful definition is circumscribed by your own sphere of influence.
