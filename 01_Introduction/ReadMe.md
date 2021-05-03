## Introduction to Reinforcement Learning


![Agent Env Interaction](https://github.com/kkm24132/ReinforcementLearning/blob/main/01_Introduction/AgentEnv_RL.png)

Source of image: http://www.incompleteideas.net/book/ebook/node28.html (Sutton and Barto Book)

### How RL is different compared to Supervised and Unsupervised Learning

![RLvsOthers](https://github.com/kkm24132/ReinforcementLearning/blob/main/01_Introduction/RLvsOthers.png)

### Key Terms Used in RL
- **Agent**: "The learner". Agent is the main part of a RL setup. From an example perspective, it could be a robot learning to do certain things as an agent, can be walking for that matter, or it could be an agent learning to "drive" a vehicle. They explore environments
- **State**: This is the position the agent is at a given period. It changes when the agent moves. Different positions in a given environment is called as "State". State of the system summarizes the key characteristics of environment at any given point of time.
- **Environment**: This is the agent's learning area or learning space.
- **Action**: This is choice of activity in a state,the action is taken by the agent: may be positive or negative. Correct actions by agent lead to positive rewards. This is the control picked up by agent or decision maker.
- **Goal** or **Mission**: Objective of the agent. The goal of the agent is to pick a sequence of actions in response to the states of the environment in order to maximize a long term reward. Various notions of *long-term reward* is as follows:
  - Episodic or shortest path problems
  - Infinite horizon discounted reward problems
  - Long-run average reward problems
  - Finite horizon problems

### Basic Elements of RL
- **Policy**: Strategy or method for determining the best action. It is a map from states of environment to action of agent. It can be a lookup table as well. A policy can be either *deterministic* or *stochastic* .
- **Reward**: This is the prize for taking incorrect or correct action. This is reinforcement signal from environment to agent.
  - It defines the goal of an RL problem
  - Reward signal can be either *deterministic* or *stochastic* as well.
- **Value function**: A function from states of environment to real numbers. It specifies what is good course of action to choose in the long run. It specifies the long run desirability of a state after taking into account states that are likely to follow and the reward obtained in those states.
Model of environment
- **Environment Models** or **Models of environment**: It mimics the behaviour of the environment. It can be used for predicting the next states and rewards given the current state and action. These are of two types.
  - Model Free (Agent have no idea of the environment and tries to learn from "unknown" environment) - trial and error methods, no planning. Real learning happens here.
  - Model Based (Agent learns with full knowledge of the environment) - with adequate planning.
- **Trade Off** between Exploration and Exploitation:
  - **Exploitation** is selecting actions tried by the agent that are known to give high rewards
  - **Exploration** is selecting actions never tried before to see what rewards they might give
  - **TradeOff**: exploit by picking actions known to yield good results while exploring actions not picked previously
  - **Strategy**: is to initially favor exploration and then lean towards exploitation
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
  - Represented as: ``` V_π (S)=E_π [R_t+|+γV_Π (S_(t+1) )| S_(t=) s] ```

### Monte Carlo Method
- One way an Agent can take the best path/policy/trajectory so as to get the best cumulative reward.
- Equiprobable Random Policy: initial policy used by the agent with no prior knowledge of the environment
- Updates Q-table at the end of every episode
- First-visit and Every-visit MC prediction:
  - First-visit MC Prediction: Takes only the first visit to a state into consideration
  - Every-visit MC prediction: Takes a state as a new state every time it is visited
- Monte Carlo Control:
  - Iterates between exploration and exploitation to improve policy. The Monte Carlo Control is about switching between below 3 steps to accomplish best policy and reward.
  - Step1: Construct Q-table using equiprobable random policies
  - Step2: Improve policy using Bellman Equation
  - Step3: Update Q-table
- Monte Carlo with and without Incremental Mean:
  - With Incremental Mean: Updates Q-table after an episode
  - Without Incremental Mean: Updates Q-table after multiple episodes
 
### Additional Terms used in RL
- **Greedy Policies**: Policies that only select the best action
- **Epsilon-Greedy Policies**: Policies that select other actions
- **Incremental Mean**: Used to update the policy after every episode, Tending towards TD method
- **Constant Alpha**: Rate at which the agent learns. Used to update the policy after every episode

### On-Policy and Off-Policy Methods

On-Policy Method | Off-Policy Method
-----------------|------------------
Evaluate or improve policy used to make decisions | Evaluate or improve a policy different from that used to make decisions
Work with data generated from target policy itself | Work with data generated from a behaviour policy (different from target policy)
Lower variance and Faster convergence | Higher variance and slower convergence (since data is from a different policy)
Less general methods | More general and powerful approaches (since they contain on-policy methods for the case when  Target Policy = Behaviour Policy)
These are NOT needed where data can only be generated using a given policy while still the goal is to get to the optimal policy | These are needed where data can only be generated using a given policy while still the goal is to get to the optimal policy
They Do NOT solve a constrained optimization problem in the sense of data availability | They solve a constrained optimization problem as opposed to On-Policy methods in the sense of data availability
Example: SARSA and Expected-SARSA | Example: Q-learning


### Temporal Difference Method
- Updates estimates of value function: ``` v(s_t )=v(s_t )+α(r_(t+1)+v(s_(t+1) )-v(s_t )) ```
- Updates Q-table at every time step


### Deep Reinforcement Learning
- Using Neural Nets to map states and actions to rewards

### Inverse Reinforcement Learning
- Agents learning by imitation

### Multi-Agent Reinforcement Learning
- Multiple RL agents learning side by side at the same time


