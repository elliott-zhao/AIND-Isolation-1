# AlphaGO Research Review

Go game tree depth greater, the use of traditional artificial intelligence algorithm is difficult to calculate the results.

The paper suggest to use three neural networks:

1. A supervised learning policy network trained with human moves.
1. A reinforcement learn policy network that evaluates self-play outcomes of the current state of the game.
1. A RL value network the predicts the winner of the game using the network 2.

## Implementation

### SUPERVISED LEARNING

A 13-layer policy network, termed as SL Policy Network, is trained on randomly sampled
state-action pairs from 30 million positions from the KGS Go Server. The neural network
takes input features from the board position and outputs the probability of each move on
the board being the actual next move.

### REINFORCEMENT LEARNING

The second stage of the training pipeline improved the policy network by policy gradient
reinforcement learning. The games were played between the then current policy network
and a randomly selected previous iteration of the policy network. Randomizing from a
pool of opponents in this way stabilized the training by preventing overfitting to the then
current policy.

### REINFORCEMENT LEARNING FOR VALUE NETWORK

The final stage of the training pipeline focuses on position evaluation, estimating a value
function that predicts the outcome from a position of games played by using policy for
both players. This neural network had a similar architecture to the policy network but
outputted a single prediction instead of a probability distribution.To mitigate the problem
of overfitting, a new data consisting of 30 million distinct positions was generated using a
set of self-play data set (each sampled from a separate game). Each game was played
between the RL policy network and itself until the game terminated.

### SEARCH WITH POLICY AND VALUE NETWORK

AlphaGo combined the policy and value networks in an MCTS algorithm that selected
actions by lookahead search. To efficiently combine MCTS with deep neural networks,
AlphaGo used an asynchronous multi-threaded search that executes simulations on
CPUs and computes policy and value networks in parallel on GPUs.
Results