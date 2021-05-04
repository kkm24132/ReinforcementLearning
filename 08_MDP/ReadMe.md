## Finite Markov Decision Processes

### **Contents (From Chapter 3 in Sutton and Barto Book)**

- The Agent-Environment Interface
- Goals and Rewards
- Returns and Episodes
- Unified Notation for Episodic and Continuing Tasks
- Policies and Value Functions
- Optimal Policies and Optimal Value Functions
- Optimality and Approximation

### Summary Points

- Agent & Environment Interface: At each step ```t``` the agent receives a state ```S_t```, performs an action ```A_t``` and receives a reward ```R_{t+1}```. The action is chosen according to a policy function ```pi```.
- The total return ```G_t``` is the sum of all rewards starting from time t . Future rewards are discounted at a discount rate ```gamma^k```.
- Markov property: The environment's response at time ```t+1``` depends only on the state and action representations at time t. The future is independent of the past given the present. Even if an environment doesn't fully satisfy the Markov property, we still treat it as if it is and try to construct the state representation to be approximately Markov.
- Markov Decision Process (MDP): Defined by a state set S, action set A and one-step dynamics ```p(s',r | s,a)```. If we have complete knowledge of the environment we know the transition dynamic. In practice, we often don't know the full MDP (but we know that it's some MDP).
- 
