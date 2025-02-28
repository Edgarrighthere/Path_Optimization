# Path Optimization

This is an intermediary step for my internship project that requires the implementation of Reinforcement Learning.

We implement 2 algorithms on a simple grid world problem. In the grid world, there are obstacles and bonus points. The goal is simple. The AI agent has to navigate from the defined start point to the end point. Optimally, the agent should avoid the obstacles to not get penalize. In contrary, the agent should get the highest possible bonus point in the least number of steps to maximize effective cumulative rewards. 

You will see 2 different algorithms. First is the standard Deep Q-Network (DQN). Second, is the extension, which is Double DQN. Throughout 1000 iterations, the agent will balance between exploration and exploitation using the greedy approach. We will deem the agent to have converge if the agent has achieved maximum score in least steps for a consecutive of 10 iterations. 



