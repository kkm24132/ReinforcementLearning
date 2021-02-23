## Introduction to Reinforcement Learning

### Key Terms Used in RL
- **Agent**: "The learner". Agent is the main part of a RL setup. From an example perspective, it could be a robot learning to do certain things as an agent, can be walking for that matter, or it could be an agent learning to "drive" a vehicle. They explore environments
- **State**: This is the position the agent is at a given period. It changes when the agent moves. Different positions in a given environment is called as "State". State of the system summarizes the key characteristics of environment at any given point of time.
- **Environment**: This is the agent's learning area or learning space.
- **Action**: This is choice of activity in a state, the action is taken by the agent: may be positive or negative. Correct actions by agent lead to positive rewards. This is the control picked up by agent or decision maker.
- **Reward**: This is the prize for taking incorrect or correct action. This is reinforcement signal from environment to agent.
- **Policy**: Strategy or method for determining the best action.
- **Goal** or **Mission**: Objective of the agent. The goal of the agent is to pick a sequence of actions in response to the states of the environment in order to maximize a long term reward. Various notions of *long-term reward* is as follows:
  - Episodic or shortest path problems
  - Infinite horizon discounted reward problems
  - Long-run average reward problems
  - Finite horizon problems

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

### Monte Carlo Method
- One way an Agent can take the best path/policy/trajectory so as to get the best cumulative reward.
- Equiprobable Random Policy: initial policy used by the agent with no prior knowledge of the environment


