## custom_score

Increase our moves greater than moves of opponents.

```python
diff = my_moves - opp_moves
    if diff > 0:
        return float(diff * my_moves)
    else:
        return float(diff)
```

## custom_score_2

To reduce the moves of the opponent.

```python
if opp_moves >= 2 and my_moves > 3:
        return float(my_moves * 2)
    elif opp_moves< 2 and my_moves >2:
        return float(my_moves * 5)
    elif opp_moves < 1 and my_moves >= 1:
        return float(my_moves * 10)
    else:
        return float(my_moves-opp_moves)
```

## custom_score_3

Purely defensive tactics to achieve more conservative results by lowering your own score.

```python
if opp_moves > 2:
        return float(own_moves*0.5)
    else:
        return float(own_moves*0.7)
```

## conclution

The test results showed that custom_score performed the best, so you should use this evaluation function.

![result](D:\Workspace\AIND-Isolation\result.png)