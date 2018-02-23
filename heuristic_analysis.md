## custom_score

This heuristic evaluates the ratio between the difference in number of the moves left and the Manhattan distance between two players. The more moves left and the closer to the opponent, the higher score is for the player. The more moves left, the more advantages player have. The closer to the opponent, the easier to block the opponent.


```
 Match #   Opponent    AB_Improved   AB_Custom
                        Won | Lost   Won | Lost
    1       Random      19  |   1    19  |   1
    2       MM_Open     15  |   5    15  |   5
    3      MM_Center    18  |   2    20  |   0
    4     MM_Improved   15  |   5    14  |   6
    5       AB_Open     11  |   9    14  |   6
    6      AB_Center    14  |   6    10  |  10
    7     AB_Improved    9  |  11    10  |  10
--------------------------------------------------------------------------
           Win Rate:      72.1%        72.9%
```

The win rate is higher than AB_Improved by 0.8% in this tournament.

## custom_score_2

The 2nd heuristic evaluates the difference in total number of the moves left in current and future state between player and opponent. The more total moves player has, the higher score the player got.This heuristic focus on expanding the gap between the two numbers of moves in the future state.

```
Match #   Opponent    AB_Improved  AB_Custom_2
                        Won | Lost   Won | Lost
    1       Random      18  |   2    19  |   1
    2       MM_Open     17  |   3    13  |   7
    3      MM_Center    19  |   1    17  |   3
    4     MM_Improved   12  |   8    15  |   5
    5       AB_Open      8  |  12     7  |  13
    6      AB_Center    11  |   9     8  |  12
    7     AB_Improved    8  |  12     8  |  12
--------------------------------------------------------------------------
           Win Rate:      66.4%        62.1%
```
The win rate is lower than AB_Improved by 4.3% in this tournament.

## custom_score_3

The 3rd heuristic evaluates the difference in number of the moves left. But if there is no difference between the number, it will consider the difference in  Manhattan distance to the center of the board.

When a player has more moves than the opponent, the heuristic got a higher score. When they have the same number of moves, the closer to the center of the board, it is more likely to do better than the one close to the edge of the board, so it will go a better score.
```
 Match #   Opponent    AB_Improved  AB_Custom_3
                        Won | Lost   Won | Lost
    1       Random      19  |   1    19  |   1
    2       MM_Open     13  |   7    18  |   2
    3      MM_Center    16  |   4    17  |   3
    4     MM_Improved   16  |   4    15  |   5
    5       AB_Open     13  |   7    11  |   9
    6      AB_Center    10  |  10    13  |   7
    7     AB_Improved    7  |  13     6  |  14
--------------------------------------------------------------------------
           Win Rate:      67.1%        70.7%
```
The win rate is higher than AB_Improved by 3.6% in this tournament.

## conclution

The calculation of the three functions is not very high, and it is not difficult to implement. And all three can have comparable or better performance than the AB_Improved. 

These three functions are advisable both in terms of the amount of computation and the difficulty of implementation or from the performance considerations.

Although there may be other better implementations, existing solutions are also good options.