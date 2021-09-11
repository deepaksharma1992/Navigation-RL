# Project Navigation

## Objective: Train an Reinforcement Learning agent to collect bananas

For this project, I have trained an RL agent to navigate (and collect bananas!) in a large, square world.

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of agent is to collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

- 0 - move forward.
- 1 - move backward.
- 2 - turn left.
- 3 - turn right. The task is episodic, and in order to solve the environment, agent must get an average score of +13 over 100 consecutive episodes.

Find the training plot below
![Training Plot](https://github.com/deepaksharma1992/Navigation-RL/blob/main/plot_average.PNG)

## Model Implementattion
### Deep Q Network
Project implements value based methods RL technique [based on Deep-Q-Networks paper](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) 
In deep Q-learning, we use a neural network to approximate the Q-value function. The state is given as the input and the Q-value of all possible actions is generated as the output. 

- Preprocess and feed the game screen (state s) to our DQN, which will return the Q-values of all possible actions in the state
- Select an action using the epsilon-greedy policy. With the probability epsilon, we select a random action a and with probability 1-epsilon, we select an action that has a maximum Q-value, such as a = argmax(Q(s,a,w))
- Perform this action in a state s and move to a new state s’ to receive a reward. This state s’ is the preprocessed image of the next game screen. We store this transition in our replay buffer as <s,a,r,s’>
- Next, sample some random batches of transitions from the replay buffer and calculate the loss
- Perform gradient descent with respect to our actual network parameters in order to minimize this loss
- After every C iterations, copy our actual network weights to the target network weights
- Repeat these steps for M number of episodes

![Neural Network Diagram](https://github.com/deepaksharma1992/Navigation-RL/blob/main/neuralnetwork.PNG)

The neural network is convolution neural network architecture, with a series of 2 convolution layers with relu activation function feed to two fully connected layers and the final layer is having linear output.

### Hyper parameters choosen to train the model
- BUFFER_SIZE = int(1e5)  # replay buffer size
- BATCH_SIZE = 64         # minibatch size
- GAMMA = 0.99            # discount factor
- TAU = 1e-3              # for soft update of target parameters
- LR = 5e-4               # learning rate 
- UPDATE_EVERY = 4        # how often to update the network
- n_episodes (int): maximum number of training episodes
- max_t (int): maximum number of timesteps per episode
- eps_start (float): starting value of epsilon, for epsilon-greedy action selection
- eps_end (float): minimum value of epsilon
- eps_decay (float): multiplicative factor (per episode) for decreasing epsilon


## Ideas to improve the reinforcement learning agents
- We can train our RL Model on more episodes
- We can further decrease the learning rate, so that our model can further converge
- For better performance, increase the training budget, it will include CPU or TPU budget
- Can explore policy based models and test the model on it.
- Evaluate the model performance using a separate test environment
- Use Double DQN in future for better results
- Use Prioritized experience replay for better results.
