+++
date = '2025-05-16'
draft = false
title = 'Is the NBA lottery rigged?'
math = true
+++

{{< figure src="lottery.jpg" alt="The Dallas Mavericks winning the 2025 NBA draft lottery" caption="2025 Draft Lottery" >}}

Following the 2025 NBA draft lottery that saw the Dallas Mavericks win the number one overall pick, the sports world was abuzz with claims that the lottery was rigged. Not only were the odds tiny (1.8%), but months before the Mavs had also puzzlingly traded superstar Luka Doncic to the Lakers, the NBA's most marketable team. This isn't without precedent either - conspiracies arose in the 1985 Draft Lottery, when the New York Knicks were awarded the 1st pick following an [enevelope debacle](https://en.wikipedia.org/wiki/1985_NBA_draft#Conspiracy_theories_about_the_first_pick).

So is the lottery actually rigged? Is the NBA putting up a front of fairness/randomness, when all it really cares about is money? Let's use this fun example as a refresher for statistical tests, and see if we can draw any conclusions given our limited sample size.

How does the lottery work?
--------------------------
It's pretty simple:

**The setup:**
The lottery consists of 1000 balls which are divided up among the 14 non-playoff teams; the worse your regular-season record was, the more balls you will get. Here were the lottery odds for the most recent NBA lottery:

{{< figure src="odds.jpg" alt="2025 NBA lottery odds, table" caption="2025 lottery odds" >}}

The Utah Jazz had a 14.0% chance of getting the first pick <==> 140 balls.

**The drawing:**
The top 4 picks are up for grabs in the lottery (prior to 2019, it was 3); after these 4 picks have been determined, the rest are assigned by regular-season record. Starting from the first pick, we sequentially draw 4 balls (without replacement, since a team can't win multiple lottery picks).

How \~unlikely\~ was the 2025 lottery?
-------------
{{< figure src="results.jpg" alt="List of NBA Lottery results, in order" caption="2025 Draft Lottery results" >}}

As mentioned before, every year's lottery consists of 4 random picks; the order of the remanining 9 picks are also determined by these 4 picks, so we will disregard these.

If we let $P\_{2025}$ represent the probability of observing {1. DAL, 2. SAS, 3. PHI, 4. CHA}:

$P\_{2025} = \frac{18}{1000} \cdot \frac{60}{1000-18} \cdot \frac {105}{1000-18-60} \cdot \frac{1400}{1000-18-60-105}$,

which comes out to roughly **0.002146%, or ~ 1 in 46,600**.

But how ~unlikely~ is this? Any single lottery outcome will have a low percentage by nature. For reference, the most likely single outcome {1. UTA, 2. WAS, 3. CHA, 4. NOP} had probability **0.0955%, or ~ 1 in 1,047**.

So around 40x less likely than the most likely single outcome, which still doesn't tell us much.

What if we simulate this across many trials, and see how many of these trials would be less likely than our actual outcome ($P_{2025} = 0.002146\%$)?