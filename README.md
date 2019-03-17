# DRLND_Navigation_Agent

## Summary

For this project, an agent will be trained to navigate (and collect bananas!) in a large, square world.

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

0 - move forward.
1 - move backward.
2 - turn left.
3 - turn right.

The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.


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
