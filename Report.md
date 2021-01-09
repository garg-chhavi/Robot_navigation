
# Project: Robot Navigation


## Introduction

In this project we train an agent to navigate and collect yellow bananas while avoiding blue bananas in a large, square world using deep reinforcement learning.

## Learning Algorithm

To train the agent to navigate the world and collect yellow bananas, Deep Q Learning algorithm has been implemented. This algorithm has 2 main processes:

1. Sample the environment by performing actions and store the observed experience tuples (State, action, reward, next state and done) in a replay memory
2. Select a small batch of tuples from the memory randomly and learn (i.e. train neural network) from that batch usig gradient descent step.

For more details please refer to [Deep Q learning paper](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf)

### Hyperparameters 

1. BATCH_SIZE = 64: 64 experience tuples are used at atime to train the network.
2. GAMMA = 0.99: Discount factor to calculate future rewards. Set to high number so that agent cares about future rewards as much.
3. TAU = 1e-3: Set to a small number so that target network weights changes gradually.
4. LR = 5e-4: Learning rate for weight updation.
5. UPDATE_EVERY = 4: Number of time steps in an episde after which network can be updated.

### Model Architecture

1. Input Layer: Fully connected linear layer which accepts 37 state dimensions as input and outputs 64 hidden units. Hidden values pass through non-linear activation - RELU.
2. Hidden Layer: 64 input nodes as well as output nodes with non-linear activation - RELU
3. Output Layer: 64 input nodes and 4 output nodes


## Plot of Rewards
![Alt text](./rewards.png?raw=true "Title")


## Ideas for Future Work

The current implementtaion used Experience replay as well as Fixed Q target concepts. The implementation can be further enhanced by incorporating Prioritised Experience Replay and Double DQN.