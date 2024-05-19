# Cookie Cats AB-Test Analysis

## Project Overview
Cookie Cats is a hugely popular mobile puzzle game developed by Tactile Entertainment. It's a classic "connect three"-style puzzle game where the player must connect tiles of the same color to clear the board and win the level. It also features singing cats!

As players progress through the levels, they will occasionally encounter gates that force them to wait a non-trivial amount of time or make an in-app purchase to progress. This analysis explores the impact of moving the first gate from level 30 to level 40 on player retention.

![Cookie Cats Game](https://example.com/your-image.png)

## Table of Contents
- [Understanding the Data](#understanding-the-data)
- [AB-Test Data](#ab-test-data)
- [Distribution of Game Rounds](#distribution-of-game-rounds)
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

[Back to Top](#cookie-cats-ab-test-analysis) | [Next: AB-Test Data](#ab-test-data)

## AB-Test Data
When a player installed the game, they were randomly assigned to either gate_30 or gate_40. Let's see if there are roughly the same number of players in each AB group.

| Group   | Number of Players |
|---------|-------------------|
| gate_40 | 45,489            |
| gate_30 | 44,700            |

[Back to Top](#cookie-cats-ab-test-analysis) | [Next: Distribution of Game Rounds](#distribution-of-game-rounds)

## Distribution of Game Rounds
The focus of this analysis will be on how the gate placement affects player retention. Let’s first examine the distribution of the number of game rounds players played during their first week playing the game.

| Sum of Gamerounds | Number of Users |
|-------------------|-----------------|
| 0                 | [number]        |
| 1                 | [number]        |
| ...               | ...             |
| 100               | [number]        |

[Back to Top](#cookie-cats-ab-test-analysis) | [Next: 1-Day Retention Analysis](#1-day-retention-analysis)

## 1-Day Retention Analysis
### Overall 1-Day Retention
A common metric in the video gaming industry for how fun and engaging a game is 1-day retention: The percentage of players that come back and play the game one day after they have installed it.

**Overall 1-Day Retention**: 44.52%

### 1-Day Retention by AB-Group
- **Gate at Level 30**: 44.82%
- **Gate at Level 40**: 44.23%

This shows a slight decrease in 1-day retention when the gate was moved to level 40.

[Back to Top](#cookie-cats-ab-test-analysis) | [Next: 7-Day Retention Analysis](#7-day-retention-analysis)

## 7-Day Retention Analysis
### Overall 7-Day Retention
7-day retention measures what percentage of the people that installed the game also showed up a week later to play the game again.

**Overall 7-Day Retention**: 18.61%

### 7-Day Retention by AB-Group
- **Gate at Level 30**: 19.02%
- **Gate at Level 40**: 18.20%

Similar to the 1-day retention, we observe a decrease in 7-day retention when the gate was moved to level 40.

[Back to Top](#cookie-cats-ab-test-analysis) | [Next: Conclusion](#conclusion)

## Conclusion
### Summary
The analysis indicates that retention rates are higher when the gate is placed at level 30 compared to when it is moved to level 40.

### Recommendations
- **Retain the gate at level 30**: To maintain higher player retention.
- **Further Analysis**: Explore other metrics such as the number of game rounds played or in-game purchases for a more comprehensive understanding.

### Insights
The concept of hedonic adaptation suggests that forcing players to take a break when they reach a gate might prolong their enjoyment of the game. Moving the gate to level 40 results in fewer players reaching this gate and potentially increases the risk of players quitting due to boredom.

[Back to Top](#cookie-cats-ab-test-analysis)
