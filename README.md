# DRLND Continuous Control Project

## Project Description

### Environment

In this environment, a double-jointed arm can move to target locations.
A reward of +0.1 is provided for each step that the agent's hand is in the goal location.
Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible.

The Unity environment contains 20 identical agents, each with its own copy of the environment.
This is useful for algorithms like PPO, A3C, and D4PG that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience. 

### State

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm.

### Action

Each action is a vector with four numbers, corresponding to torque applicable to two joints.
The action variable is normalized to within [-1,1] space.

### Aim

The agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically,

- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
- This yields an average score for each episode (where the average is over all 20 agents).

The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30.

## Setup

1. Unzip the required environment for your machine (in this project folder):
a. One Agent
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
    - Linux (headless): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)
b. Twenty Agent
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
    - Linux (headless): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
2. Setup virtual environment (inside this project folder)
```
$ virtualenv ENV
$ . ENV/bin/activate
```
3. Install dependencies:
```
$ pip3 install --user jupyter numpy mlagents matplotlib torch
```
4. Run Jupyter Notebook
```
$ jupyter notebook
```
A web-browser with all the required files should open up automatically now.

## Usage

Open `Report.ipynb` notebook in the web-browser (using jupyter notebook) and run
the commands as described in the file.

For training the model, mark the flag `train_flag=True`.
Once proceeding with the code in the notebook file, this setting with train the
model designed and store the weights as `checkpoint.pth`.

For simply testing the performance of the trained model, simply set
`train_flag=False`.
This setting will assume that `checkpoint.pth` is present and test the
respective model's performance, when code in the notebook file is run.

## References

- [1] https://github.com/udacity/deep-reinforcement-learning
- [2] Schaul, T., Quan, J., Antonoglou, I., & Silver, D. (2015). Prioritized experience replay. arXiv preprint arXiv:1511.05952.
- [3] Van Hasselt, H., Guez, A., & Silver, D. (2016, March). Deep reinforcement learning with double q-learning. In Thirtieth AAAI conference on artificial intelligence.
- [4] https://github.com/ltbringer/drlnd_continuous_control
- [5] Lillicrap, T. P., Hunt, J. J., Pritzel, A., Heess, N., Erez, T., Tassa, Y., ... & Wierstra, D. (2015). Continuous control with deep reinforcement learning. arXiv preprint arXiv:1509.02971.
