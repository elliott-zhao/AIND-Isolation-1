## custom_score

```python
own_moves - 2 * opp_moves
```

This makes the player to behave more aggressively and try to actively reduce the number
of opponent’s moves. It is easy to implement, and easy to caculate. The weakness is its blindness to the position of the game.

## custom_score_2

To reduce the moves of the opponent.

```python
my_moves * opp_dist - opp_moves * my_dist
```

## custom_score_3

Purely defensive tactics to achieve more conservative results by lowering your own score. If the opponent has more than 2 steps left, punishes player's steps to take a more conservative strategy.

```python
if opp_moves > 2:
        return float(own_moves*0.5)
    else:
        return float(own_moves*0.7)
```

## conclution

![result](D:\Workspace\AIND-Isolation\result.png)

The calculation of the three functions is not very high, and it is not difficult to implement. Therefore, the main reference factor is the performance of these three functions. The test results showed that custom_score performed the best in three custom functions, and the performance is better than AB_Improved in most cases. so we should use this evaluation function.