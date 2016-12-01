---
layout: post
title: Developing in Ruby using Windows - forget it
date: 2011-12-21 15:12:11.000000000 +00:00
---
If you're one of the small band of people developing Ruby or Rails apps on a Windows machine then read on.

If you only have access to a Windows machine (like millions of corporate developers) and you're choosing a development language then read on.

Otherwise, this post is not for you.

Still here? OK, here's the nub: stop. You can't develop in Ruby on Windows.

Why not? Read this: <a href="http://bugs.ruby-lang.org/issues/show/4291">http://bugs.ruby-lang.org/issues/show/4291</a>

Status: Rejected

OK, so you're fine if your app will never store dates prior to 1st January 1970 (pre-epoch dates) or after 31st December 2038. But your next app might.

So get used to the idea of using another platform. Or if you're stuck on Windows, use another programming language. Nobody in the Ruby world cares enough to fix this issue in the Windows version. It's broken and always will be.

&nbsp;
