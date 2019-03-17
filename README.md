# DRLND_Navigation_Agent

## Summary
an agent moves through a virtual field filled with bananas, some of them are blue and some of them are yellow. If the agent collects a blue banana it receives a negative rewards, while if the agent a yellow banana it collects a positive rewards.

The objective is to maximize reward through episodes of 1000 time steps.

## Learning Algorithm
Source code of learning algorithm is placed in main/ directory. The algorithm is composed mainly of next three parts.

#### Double DQN
As reinforcement learning algorithm, I implemented Double DQN (DDQN). Because Double DQN overcome the tendency which DQN overestimates the reward of action, DDQN can achieve better performance then DQN on average (but I don't have enough time to check it..)

Inside DDQN, I used two layer neural network as Q-Value Estimator. Hidden layers are composed of State -> 64 -> LeakyReLU -> 64 -> LinearReLU -> Action

#### Experience Replay
Similarly to original DQN paper, I implemented Experience Replay. In this technique, D-DQN model is trained by mini-batch from replay buffer.

#### Epsilon Greedy
Agent select next action based on Epsilon Greedy. At probability epsilon, agent select at random from action space. The value of epsilon is set 0.95, and decrease gradually with time until 0.000001.

## Agent Results
This is plot of rewards when training. At Episode 524, agent performance met the criteria and stopped training. (mean scores of last 100 episodes is above +13)
