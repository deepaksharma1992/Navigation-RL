# Navigation-RL
## The Environment
For this project, I have trained an RL agent to navigate (and collect bananas!) in a large, square world.

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of agent is to collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

- 0 - move forward.
- 1 - move backward.
- 2 - turn left.
- 3 - turn right.
The task is episodic, and in order to solve the environment, agent must get an average score of +13 over 100 consecutive episodes.

I have completed this project on Udacity provided environment, but to set up this project on personal machine.

- Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
- Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
- Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
- Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)

Then, place the file in the p1_navigation/ folder in the DRLND GitHub repository, and unzip (or decompress) the file.

(For Windows users) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(For AWS) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use this link to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the Linux operating system above.)

## Installing Dependencies
To set up your python environment to run the code in this repository, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

- Linux or Mac:


conda create --name drlnd python=3.6

source activate drlnd


- Windows:

conda create --name drlnd python=3.6 

activate drlnd

2. Follow the instructions in this repository to perform a minimal install of OpenAI gym.

- Next, install the classic control environment group by following the instructions here.
- Then, install the box2d environment group by following the instructions here.

3. Clone the repository (if you haven't already!), and navigate to the python/ folder. Then, install several dependencies.

git clone https://github.com/udacity/deep-reinforcement-learning.git

cd deep-reinforcement-learning/python

pip install .

4.Create an IPython kernel for the drlnd environment.

python -m ipykernel install --user --name drlnd --display-name "drlnd"

5. Before running code in a notebook, change the kernel to match the drlnd environment by using the drop-down Kernel menu.

[You can follow the link here if facing any difficulty with above steps](https://github.com/udacity/deep-reinforcement-learning#dependencies)

## How to run the code

- The project can be run from the file Navigation.ipynb notebook file
- First step: will be to install all library dependencies and import all libraries.
- Second step: Create the env of UnityEnvironment from "Banana.x86_64" and complete other steps
- Third step: Run the **QNetwork** class which have neural network layers and activation function it them.
- Fourth step: Run the **ReplayBuffer** and **Agent** class which will create the agent from QNetwok neural networks and ReplayBuffer memory.
- Fifth step: Create the object of Agent, by providing parameters state_size=37 and action_size=4
- Sixth step. Run the dqn() python function with default parameters to start training the RL agent. This function will append and print the scores list and save the best model if the mean score is greater than 13.0. This loop will currently halt if the agent average score is above or equal to 13.0.
- Seventh step. Finally the plot can be plotted between episode and score arrays.
- Finally the saved model checkpoint can be loaded and our model is ready to be deployed. 
