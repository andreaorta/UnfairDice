# Project: Unfair dice

I want to simulate rolling one or more dice, having set the weights of each of their faces. 
For instance, I might want to roll (1, 2, 3, 4, 5, 6) with probability (0.25, 0.2, 0.15, 0.05, 0.1, 0.25).

If rolling multiple dice, I'll take them to be copies of one another (i.e. same weights) to avoid compensating effects, 
but I might generalise this at a later stage. 

I plot the statistics of dice rolls.

Given a list of outcomes, I'll test the statistical hypothesis that the dice is/are fair.

Given a set of simulated outcomes, I'll train a supervised learning algorithm to detect unfair dice.
Moreover, I'll ask the algorithm to identify dominant features, namely the faces coming up with higher likelihood.
