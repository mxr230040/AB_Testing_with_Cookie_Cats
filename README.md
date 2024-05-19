# Cookie Cats AB-Test Analysis

## Project Overview
Cookie Cats is a hugely popular mobile puzzle game developed by Tactile Entertainment. It's a classic "connect three"-style puzzle game where the player must connect tiles of the same color to clear the board and win the level. It also features singing cats!

As players progress through the levels, they will occasionally encounter gates that force them to wait a non-trivial amount of time or make an in-app purchase to progress. This analysis explores the impact of moving the first gate from level 30 to level 40 on player retention.

Link to the project on Datacamp: (https://app.datacamp.com/learn/projects/184)

## Table of Contents
- [Understanding the Data](#understanding-the-data)
- [AB-Test Data](#ab-test-data)
- [1-Day Retention Analysis](#1-day-retention-analysis)
- [7-Day Retention Analysis](#7-day-retention-analysis)
- [Conclusion](#conclusion)

## Understanding the Data
The data we have is from 90,189 players that installed the game while the AB-test was running. The variables are:

- **userid**: A unique number that identifies each player.
- **version**: Whether the player was in the control group (gate_30) or the group with the moved gate (gate_40).
- **sum_gamerounds**: The number of game rounds played by the player during the first 14 days after install.
- **retention_1**: Did the player come back and play 1 day after installing?
- **retention_7**: Did the player come back and play 7 days after installing?

![image](https://github.com/mxr230040/AB_Testing_with_Cookie_Cats/assets/159498665/30212379-a6ad-4a2e-abc3-eece43ea39c7)

## AB-Test Data
When a player installed the game, they were randomly assigned to either gate_30 or gate_40. Number of players in each group were:

| Group   | Number of Players |
|---------|-------------------|
| gate_40 | 45,489            |
| gate_30 | 44,700            |


# Distribution of Game Rounds
The focus of this analysis will be on how the gate placement affects player retention. 

## 1-Day Retention Analysis
### Overall 1-Day Retention
A common metric in the video gaming industry for how fun and engaging a game is 1-day retention: The percentage of players that come back and play the game one day after they have installed it. The observed overall 1-Day Retention rate was 44.52%

### 1-Day Retention by AB-Group
- **Gate at Level 30**: 44.82%
- **Gate at Level 40**: 44.23%

This shows a slight decrease in 1-day retention when the gate was moved to level 40.

### Bootstrap Analysis: 1-Day Retention
It appears that there was a slight decrease in 1-day retention when the gate was moved to level 40 (44.2%) compared to the control when it was at level 30 (44.8%). It's a small change, but even small changes in retention can have a large impact. But while we are certain of the difference in the data, how certain should we be that a gate at level 40 will be worse in the future?

There are a couple of ways we can get at the certainty of these retention numbers. Here we will use bootstrapping: We will repeatedly re-sample our dataset (with replacement) and calculate 1-day retention for those samples. The variation in 1-day retention will give us an indication of how uncertain the retention numbers are.

![image](https://github.com/mxr230040/AB_Testing_with_Cookie_Cats/assets/159498665/05b8f6a1-9b14-43e3-9c57-8ea511544fd2)

These two distributions above represent the bootstrap uncertainty over what the underlying 1-day retention could be for the two AB-groups. Just eyeballing this plot, we can see that there seems to be some evidence of a difference, albeit small. 

Zooming in on the difference in 1-day retention, we can see that the most likely % difference is around 1% - 2%, and that most of the distribution is above 0%, in favor of a gate at level 30, with the probability that the difference is above 0 being 96%.

![image](https://github.com/mxr230040/AB_Testing_with_Cookie_Cats/assets/159498665/ac57034a-3071-459d-87f7-220d25574bfa)

## 7-Day Retention Analysis
### Overall 7-Day Retention
7-day retention measures what percentage of the people that installed the game also showed up a week later to play the game again. The observed overall 7-Day Retention rate was 18.61%

### 7-Day Retention by AB-Group
- **Gate at Level 30**: 19.02%
- **Gate at Level 40**: 18.20%

Similar to the 1-day retention, we observe a decrease in 7-day retention when the gate was moved to level 40.

### Bootstrap Analysis: 7-Day Retention
Like with 1-day retention, we see that 7-day retention is slightly lower (18.2%) when the gate is at level 40 than when the gate is at level 30 (19.0%). This difference is also larger than for 1-day retention, presumably because more players have had time to hit the first gate. We also see that the overall 7-day retention is lower than the overall 1-day retention; fewer people play a game a week after installing than a day after installing. But as before, let's use bootstrap analysis to figure out how certain we should be of the difference between the AB-groups.

![image](https://github.com/mxr230040/AB_Testing_with_Cookie_Cats/assets/159498665/299aa8c7-2f63-4031-9ddb-23a960ff620d)

## Conclusion
### Summary
The bootstrap result tells us that there is strong evidence that 7-day retention is higher when the gate is at level 30 than when it is at level 40. The conclusion is: If we want to keep retention high — both 1-day and 7-day retention — we should not move the gate from level 30 to level 40. There are, of course, other metrics we could look at, like the number of game rounds played or how much in-game purchases are made by the two AB-groups. But retention is one of the most important metrics. If we don't retain our player base, it doesn't matter how much money they spend in-game

### Recommendations
- **Retain the gate at level 30**: To maintain higher player retention.
- **Further Analysis**: Explore other metrics such as the number of game rounds played or in-game purchases for a more comprehensive understanding.

### Insights
The concept of hedonic adaptation suggests that forcing players to take a break when they reach a gate might prolong their enjoyment of the game. Moving the gate to level 40 results in fewer players reaching this gate and potentially increases the risk of players quitting due to boredom.

More information about the project here - (https://github.com/mxr230040/AB_Testing_with_Cookie_Cats)
