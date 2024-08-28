### Developed By : MOHAMED ATHIL B

### Register No. 212222230081

### Date : 

# MDP REPRESENTATION

## AIM:

To represent any one real-world problem in MDP form.

## PROBLEM STATEMENT:

### Problem Description

An umpire in a sports game needs to make decisions based on the current game state, which includes the game score and the number of fouls. The umpire can either provide a score or not and call a foul or not. The aim is to determine the optimal decision-making strategy for the umpire to maximize the reward, where positive rewards are given for correct actions that align with the game rules.

### State Space

The state space consists of all possible combinations of the game score and the foul status. Each state is represented by:

> Game Score: The current score of the game.
<br>

> Foul Status: Indicates whether a foul has occurred

### Sample State

(Game Score = 3, Foul Status = True(1))

### Action Space
The action space consists of the following actions:

1.Provide Score: Update or confirm the game score.

2.Call Foul: Indicate that a foul has occurred.

3.Do Nothing: Take no action.

### Sample Action

Call Foul

### Reward Function

#### Reward of 1: If the umpire calls a foul when a foul has occurred and provides the score.

#### Reward of 0: If the umpire either does not provide the score or fails to call a foul when a foul has occurred.

### Graphical Representation


![Img](https://github.com/user-attachments/assets/23c283e1-dc60-4a6f-b942-efd0b7d60d66)




## PYTHON REPRESENTATION:
```py

mdp = {
    0: {  # Initial state with no score and no foul
        1: [(0.8, 2, 1.0, False)],  # Higher chance of scoring with a foul
        0: [(1.0, 1, 0.0, False)]  # Guaranteed transition to state 1
    },
    1: {  # Score increased, no foul called
        1: [(1.0, 3, 1.0, True)],  # Moves to terminal state with foul
        0: [(1.0, 1, 0.0, False)]  # Stays in the same state
    },
    2: {  # Score increased with a foul
        1: [(1.0, 3, 1.0, True)],  # Guaranteed transition to terminal state
        0: [(1.0, 2, 0.0, False)]  # Stays in the same state
    },
    3: {  # Terminal state
        1: [(1.0, 3, 1.0, True)],
        0: [(1.0, 3, 0.0, True)]
    }
}

```


## OUTPUT:

![image](https://github.com/user-attachments/assets/d26e9339-886c-457d-9d87-9d3c4c8a5779)


## RESULT:

Thus the given real world problem is successfully represented in a MDP form.
