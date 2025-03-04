# Path Optimization

This is an intermediary step for my internship project that requires the implementation of Reinforcement Learning.

We implement 2 algorithms on a simple grid world problem. In the grid world, there are obstacles and bonus points. 

The goal is simple. 
1) The AI agent has to navigate from the defined start point to the end point. 
2) Optimally, the agent should avoid the obstacles to not get penalize.
3) In contrary, the agent should get the highest possible bonus point in the least number of steps to maximize effective cumulative rewards. 

You will see 2 different algorithms. First is the standard Deep Q-Network (DQN). Second, is the extension, which is Double DQN. Throughout 1000 iterations, the agent will balance between exploration and exploitation using the greedy approach. We will deem the agent to have converge if the agent has achieved maximum score in least steps for a consecutive of 10 iterations. 

## Deep Q-Network

Follows a deep neural network-based approach to learn and optimize action-value functions. Uses only one neural network to select actions and evaluate the chosen action.

## Double DQN

Uses 2 different deep neural networks, Policy Network (Q – Network) and Target Network to reduce overestimation bias. Q – Network selects actions given at current state while the the Target Network evaluates the chosen action by computing the Q values. Both networks operate in parallel but independently. Each network maintains its own independent memory and computational resources 

## Running the code

First, ensure that you are operating with an Integrated Development Environment. A commonly used IDE is Visual 
Studio Code.

Open [https://code.visualstudio.com/download] to download and install in your computer.

Alternatively, you can open a hosted Jupyter Notebook service that requires no setup to use.

Open [https://code.visualstudio.com/download] and upload your notebook to create a new session.

If you are using DSO's AI Stack, ensure that you have installed the required packages.

### Install required packages

Ensure your IDE has the required packages, else run:

`pip install numpy torch matplotlib`

### Configure parameters
- obstacles: serves as 'out of bounds' areas that the agent has to learn to avoid.
- bonus points: extra rewards that guide the agent towards a particular path. Can be strategically placed and rewards can be adjusted.

### Run DQN Agent

To initialize a DQN Agent, run:

`DQN_agent = DQNAgent(state_dim=2, action_dim=4, snapshot_dim=9)`

For training and plotting of results, run:

```
file_name = train_dqn(env, DQN_agent, epochs=1000, batch_size=32)
plot_results_from_csv(file_name)
```

*Training may end early once convergence policy is met. Currently, the implemented convergence policy is to achieve maximum possible rewards in minimal possible moves for 10 consecutive times.*

### Run Double DQN Agent

To initialize a Double DQN Agent, run:

`Double_DQN_agent = DoubleDQNAgent(state_shape, action_size, model)`

For training and plotting of results, run:

```
file_name = train_DDQNagent(env, Double_DQN_agent, episodes=1000)
plot_results_from_csv(file_name)
```

*Training may end early once convergence policy is met. Currently, the implemented convergence policy is to achieve maximum possible rewards in minimal possible moves for 10 consecutive times.*


