---
layout: post
title: Parsing the Cricinfo DRS text
date: 2011-04-12 12:53:11.000000000 +01:00
---
NB this post may be of limited interest (read: zero interest) to anybody but me.

<a title="Cricinfo website" href="http://cricinfo.com" target="_blank">Cricinfo</a> records <a title="Wikipedia article" href="http://en.wikipedia.org/wiki/Umpire_Decision_Review_System" target="_blank">Umpire Decision Review System</a> (DRS or UDRS) outcomes in its match notes. Here are a few examples:
<ul>
	<li>Over 18.2: Refferal by South Africa, Umpire- SJ Davis, Batsman- AG Prince(Upheld)</li>
	<li>Over 39.2: Referral by England, Umpire- Aleem Dar, Batsman- JH Kallis (Struck down)</li>
	<li>Over 3.5: Review by Australia (Bowling), Umpire - Aleem Dar, Batsman - IJL Trott (Struck down)</li>
	<li>34.5: Referral by Australia, Umpire-MR Benson, Batsman - S Chanderpaul (Struck down)</li>
	<li>Over 103.1 Referral by West Indies, Umpire-IJ Gould, Batsman - SJ Benn (Struck down)</li>
	<li>Over 16.3; Referral by Australia, Umpire BF Bowden, Batsman-SR Watson (Struck down)</li>
</ul>
Here, as far as I can make out, is the ABNF describing the Cricinfo match notes that tell us about DRS outcomes:
<pre>Review-text     = ["Over" 1*WSP] Over-ball [":" / ";"] Review-name Team [Role] ", " Umpire ", " Batsman Outcome

Over-ball       = 1*3DIGIT "." Ball ; When the review happened in the innings

Ball            = %x30-36 ; 0-6 (assuming 6-ball overs)

Review-name     = 1*WSP ["Review" / "Referral" / "Refferal"] " by " ; Has been referred to using various names (and typos)

Team            = "England"
                / "Australia"
                / "South Africa"
                / "India"
                / "Pakistan"
                / "Sri Lanka"
                / "West Indies"
                / "New Zealand"
                / ICC-member

ICC-member      = 1*ALPHA ; Unique string identifying the team asking for the review

Role            = 1*WSP "(" ("Batting" / "Bowling") ")"

Umpire          = "Umpire" [*WSP "-" *WSP] Umpire-name

Umpire-name     = 1*ALPHA

Batsman         = "Batsman" [*WSP "-" *WSP] Batsman-name

Batsman-name    = 1*ALPHA

Outcome         = *WSP "(" ("Upheld" / "Struck down") ")"</pre>
