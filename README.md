# Reinforcement Learning
Focuses on Reinforcement Learning related concepts, use cases and learning approaches

### Key Terms
- **Agent**: "The learner". Agent is the main part of a RL setup. From an example perspective, it could be a robot learning to do certain things as an agent, can be walking for that matter, or it could be an agent learning to "drive" a vehicle. They explore environments
- **State**: This is the position the agent is at a given period. It changes when the agent moves. Different positions in a given environment is called as "State".
- **Environment**: This is the agent's learning area or learning space.
- **Action**: This is choice of activity in a state, the action is taken by the agent: may be positive or negative. Correct actions by agent lead to positive rewards.
- **Reward**: This is the prize for taking incorrect or correct action.
- **Policy**: Strategy or method for determining the best action.
- **Goal** or **Mission**: Objective of the agent

- **Environment Models** are of two types:
  - Model Free (Agent have no idea of the environment and tries to learn from "unknown" environment)
  - Model Based (Agent learns with full knowledge of the environment)
- **Task Type** are of two categories:
  - Episodic (Tasks that have a definite goal or end point) - are solved by model-based methods
  - Continuing Tasks (Tasks do not have a definite goal, they continue for ever) - are typically solved by model-free methods

### Markov Decision Process (MDP)
- How RL problems are represented mathematically
- Typical parameters are States, Actions, Rewards, Environment, Discount Factor etc.
- Discount Factor = Reward Function
- **Bellman Equation** is used to solve MDP
  - State Value Function (Expected Value of Reward in a particular state) : Total reward gained by agent from its current state to it's goal state
  - Action Value Function (used for more optimal policies - Expected Value of Reward in a particular state given that the agent has taken an initial action)


### Areas
- MABP (Multi-Armed Bandit Problems)

### Use Cases
- Clinical Trials: The well being of patients during clinical trials is extremely important along with the actual results of the study. In this scenario, the exploration is equivalent to identifying the best treatment, and exploitation is treating patients as effectively as possible during the trial process.
- Network Routing: Routing is the process of selecting a path for traffic in a network, such as telephone networks or computer networks (internet) etc. Allocation of channels to the right users, such that the overall throughput is maximised, can be formulated as a MABP.
- Online Advertising: The goal of an advertising campaign is to maximise revenue from displaying ads. The advertiser makes revenue every time an offer is clicked by a web user. Similar to MABP, there is a trade-off between exploration, where the goal is to collect information on an ad’s performance using click-through rates, and exploitation, where we stick with the ad that has performed the best so far.
- [10 real life problems](https://neptune.ai/blog/reinforcement-learning-applications)
- [Applications in real world](https://towardsdatascience.com/applications-of-reinforcement-learning-in-real-world-1a94955bcd12)

### References
- Book1: [Sutton and Barto](http://incompleteideas.net/book/the-book-2nd.html)
- Book2: [DL by Ian Goodfellow et al](https://www.deeplearningbook.org/)
- RL from Stanford: [CS234](https://web.stanford.edu/class/cs234/)
- RL Winter 2021 Stanford: [Modules and Videos](https://web.stanford.edu/class/cs234/modules.html)
- [Common RL Examples on Sagemaker](https://github.com/kkm24132/amazon-sagemaker-examples/tree/master/reinforcement_learning)
- Initial Part MABPs: [Epsilon, epsilon-Greedy methods](https://www.datahubbs.com/multi_armed_bandits_reinforcement_learning_1/)
- Advanced MABPs: [UCB Bandits, Gradient Bandits, Nonstationary Bandits](https://www.datahubbs.com/multi-armed-bandits-reinforcement-learning-2/)

### Resources
- [RL resource references](https://medium.com/datadriveninvestor/absolutely-free-resources-for-reinforcement-learning-d16a5230cb0f)
