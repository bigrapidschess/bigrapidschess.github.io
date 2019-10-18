---
title: Elo Rating
subtitle:
use_math: true
description: A brief explanation of the Elo chess rating system.
featured_image: /images/my_background_green.jpg
---

The [Elo rating system](https://en.wikipedia.org/wiki/Elo_rating_system) (pronounced EE loo) was invented by the Hungarian/American physicist, [Arpad Elo](https://en.wikipedia.org/wiki/Arpad_Elo) in the 1950s. This system is widely used in chess and other sports to produce a scaled rating of player or team abilities. These ratings are calculated according to the expected outcome between two sides given their current rating values. These expectations, in turn, are found by determining the log-odds of each player winning the match given a scaling factor of 400. The result of the scaling is that a player with a rating 400 greater than her opponent is ten time more likely to win than the other way around. When the probability of winning is plotted versus difference in rating scores, we get the graph shown below.

This is a logistic curve with an inflection point at 0 (each player has the same rating). We can calculate the expected probability of a player as follows. Let’s assume that we have a chess game between two players.
* R1 = player rating 1; example: 1720
* R2 = player rating 2; example: 1650

The first thing that we need to do is transform the player ratings into a scaled value.

* T1 = player 1 transformed rating

$$ T_{1}=10^(frac{R1}{400}) $$

For our example this  19,953 
* T2 = player 2 transformed rating = 10^(R1/400); example: 13,335

Now the expected winning probabilities for the players can be found by determining the log-odds.

* E1 = probability that player 1 wins = T1 / T1 + T2; example: 0.60 (60%)
* E2 = probability that player 2 wins = T2 / T1 + T2; example: 0.40 (40%)

The actual result of the game can only take on one of three values, 1 for a win, 0.5 for a draw, and 0 for a loss. Therefore, if player 2 wins or draws they will be outperforming their expected score. Player 1, in contrast, would need to win to outperform their expected score.

* S1 = player 1 score; example: 1
* S2 = player 2 score; example: 0

The fact that the actual scores and expected scores do not match is taken as evidence that the players’ current ratings are not accurate representations of their abilities. Thus, we will want to adjust the original ratings to consider our new game data. This is performed by comparing the actual and expected scores and altering the original rating by the difference multiplied by a scaling factor called the K-factor. The USCF and our club use the value of 32 for the K-factor. Larger K-factors make the adjusted scores move faster and smaller K-factors have less pronounced effects upon the adjustments.

* R1’ = adjusted player 1 rating = R1 + K * (S1 – E1); example: 1733 
* R2’ = adjusted player 2 rating = R2 + K * (S2 – E2); example: 1637
