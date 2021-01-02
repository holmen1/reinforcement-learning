# cartpole

![gif](https://pytorch.org/tutorials/_images/cartpole.gif)

Reinforcement Learning (DQN) Tutorial from https://pytorch.org/tutorials/

Author: Adam Paszke <https://github.com/apaszke>_

This tutorial shows how to use PyTorch to train a Deep Q Learning (DQN) agent on the CartPole-v0 task from the OpenAI Gym <https://gym.openai.com/>__.

Task

The agent has to decide between two actions - moving the cart left or right - so that the pole attached to it stays upright. You can find an official leaderboard with various algorithms and visualizations at the Gym website <https://gym.openai.com/envs/CartPole-v0>__.

As the agent observes the current state of the environment and chooses an action, the environment transitions to a new state, and also returns a reward that indicates the consequences of the action. In this task, rewards are +1 for every incremental timestep and the environment terminates if the pole falls over too far or the cart moves more then 2.4 units away from center. This means better performing scenarios will run for longer duration, accumulating larger return.

The CartPole task is designed so that the inputs to the agent are 4 real values representing the environment state (position, velocity, etc.). However, neural networks can solve the task purely by looking at the scene, so we'll use a patch of the screen centered on the cart as an input. Because of this, our results aren't directly comparable to the ones from the official leaderboard - our task is much harder. Unfortunately this does slow down the training, because we have to render all the frames.

Strictly speaking, we will present the state as the difference between the current screen patch and the previous one. This will allow the agent to take the velocity of the pole into account from one image.

Here is the diagram that illustrates the overall resulting data flow.

![error](https://github.com/holmen1/reinforcement-learning/blob/master/images/reinforcement_learning_diagram.jpg)

Actions are chosen either randomly or based on a policy, getting the next step sample from the gym environment. We record the results in the replay memory and also run optimization step on every iteration. Optimization picks a random batch from the replay memory to do training of the new policy. "Older" target_net is also used in optimization to compute the expected Q values; it is updated occasionally to keep it current.
