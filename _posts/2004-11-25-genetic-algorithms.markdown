---
layout: post
title: Genetic Algorithms
date: 2004-11-25 13:21:17.000000000 +00:00
---
I'm running an offsite next month. 24 people will be divided into 4 teams of 6 for breakout sessions. How do I make the right teams for each breakout session?

I want the team members to have some interest and aptitude for the subject of the breakout session, but I also want each team to come from diverse backgrounds: a range of locations, departments and seniority.

There are 2.5 * 10 ^ 23 permutations of 24 people (that's a lot). Too many to try each permutation manually. Too many, in fact, for my little PC to try each permutation itself.

But the PC can help.

I can score each permutation by rating the aptitudes of the team members and giving a score to the diversity of their backgrounds. Then what I need to do is maximise that score - that is, find the permutation that gives me the best score I can achieve.

This is where Genetic Algorithms come in. I downloaded <a href="https://www.palisade-europe.com/html/evolver.html">Evolver</a> from <a href="https://www.palisade-europe.com/Default.htm">Palisade</a> on the recommendation of my very good friend Jan Jones.

Then I just told it to rearrange the attendees into 4 teams of 6 and work out the score for that permutation. Easy peasy, and it got to the maximum score within about 90 seconds and 20000 iterations. I left it running for much longer but it didn't improve on the score it got in the first 90 seconds.

The fun bit is tweaking your scoring function to get what you know are some of the right answers. In other words, if Evolver puts a person in the wrong team then it's your scoring function that's at fault. After a few tries I got what looked like a great set of teams.
