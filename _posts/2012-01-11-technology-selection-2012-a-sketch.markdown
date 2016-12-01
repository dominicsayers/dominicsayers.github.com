---
layout: post
title: Technology selection 2012 - a sketch
date: 2012-01-11 15:37:38.000000000 +00:00
tags: locomotive
---
I'm not suggesting this is the right way to choose your multinational's ERP suite, but I've just made a technology choice. The success of my decision is yet to become apparent - I'm documenting this without the benefit of hindsight.

I hope I'm brave enough to do a follow-up post when it becomes clear whether I made the right choice.
<h3>1. Identify the constraints</h3>
I have chosen a Content Management System for a small company's website. We may have to integrate with an app already written in Ruby on Rails, and that's the programming language my developers are happiest in.

We'll almost certainly deploy to Heroku, which adds additional constraints like a limited selection of databases.
<ul>
	<li>Constraint: Ruby on Rails, specifically Rails 3+</li>
	<li>Constraint: Heroku-compatible</li>
	<li>Constraint: MongoDB, Postgres, MySQL  and a few others</li>
</ul>
<h3>2. Draw up a shortlist</h3>
Aside: I'm starting to mistrust Google because of their evil attempts to promote Google-hosted content over other services. Boo. But Bing is no less evil so I still use Google for the moment.

I Googled my search for a Ruby on Rails CMS. I eliminated opinion pieces from 2009 and earlier. I made a list of CMSes that matched my constraints.

The list was
<ul>
	<li><a href="http://www.locomotivecms.com/" target="_blank">Locomotive</a></li>
	<li><a href="http://refinerycms.com/" target="_blank">Refinery</a></li>
	<li><a href="http://radiantcms.org/" target="_blank">Radiant</a></li>
</ul>
<h3>3. Final selection</h3>
To select a winner, I read the marketing fluff on each website. I then forgot everything I'd read and got on with making a rational decision.

I made a subjective judgement about how easy my users would find it to create &amp; maintain content using the admin tools for each CMS. In fact they were all OK. I couldn't rule any of them out on this basis.

I then looked at the GitHub repository for each tool. I looked at three things:
<ol>
	<li>How active the codebase was</li>
	<li>How many people were contributing to the project</li>
	<li>How successfully they dealt with issues that had been raised</li>
</ol>
All the projects had been updated in the last week but had already gone through several releases. All looked to be quite mature code under active development. A good sign.

All the tools had a wide range of contributors: <a href="https://github.com/locomotivecms/engine" target="_blank">Locomotive</a> 29, <a href="https://github.com/resolve/refinerycms" target="_blank">Refinery</a> 199, <a href="https://github.com/radiant/radiant" target="_blank">Radiant</a> 59.

All the tools seemed to be using GitHub to manage issues, which helped speed up my research. Here there was a clear winner
<table>
<tbody>
<tr>
<th>Tool</th>
<th>Open issues</th>
<th>Closed issues</th>
<th>Ratio</th>
</tr>
<tr>
<td>Locomotive</td>
<td>38</td>
<td>232</td>
<td>16%</td>
</tr>
<tr>
<td>Refinery</td>
<td>16</td>
<td>1196</td>
<td>1%</td>
</tr>
<tr>
<td>Radiant</td>
<td>41</td>
<td>267</td>
<td>15%</td>
</tr>
</tbody>
</table>
Admittedly a crude measure, but I like Refinery's clear-up rate. And I even like that they have had more issues - it matches with their wider community involvement.

We're going with Refinery, but the others are respectable choices too. If we discover a showstopper early on with Refinery I'd have no qualms trying one of the other two.

&nbsp;
