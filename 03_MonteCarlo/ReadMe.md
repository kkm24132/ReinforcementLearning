## Monte Carlo Methods

- Chapter 5 of Sutton and Barto book can be referenced for this.
- From definition perspective, we understand that any method which solves a problem by generating suitable random numbers, and observing that fraction of numbers obeying some properties, can be classified as a Monte Carlo method.

- Gridworld example: https://github.com/michaeltinsley/Gridworld-with-Q-Learning-Reinforcement-Learning-/blob/master/Gridworld.ipynb

- Blackjack example for MC with first visit: https://github.com/ShangtongZhang/reinforcement-learning-an-introduction/tree/master/chapter05
- Some more Blackjack and MC examples: https://github.com/udacity/deep-reinforcement-learning/blob/master/monte-carlo/Monte_Carlo_Solution.ipynb

- Other Youtube examples from Siraj videos: https://www.youtube.com/watch?v=-YpalutQCKw


### Monte Carlo RL

- The MC method for RL learns directly from episodes of experience without any prior knowledge of MDP transitions. The random component is the return or reward.
- One caveat here is that it can only be applied to episodic MDPs. The reason is that the episode has to terminate before we can calculate any returns. Here, we don’t do an update after every action, but rather after every episode. It uses the simplest idea – the value is the mean return of all sample trajectories for each state.
- Recalling the idea from MABPs, every state is a separate multi-armed bandit problem and the idea is to behave optimally for all multi-armed bandits at once.
- Similar to dynamic programming, there is a policy evaluation (finding the value function for a given random policy) and policy improvement step (finding the optimum policy).

### Monte Carlo Policy Evaluation

- Goal: is to learn the value function v_pi(s) from episodes of experience under a policy pi. Recall that the return is the total discounted reward: ```S1, A1, R2, ...Sk ~ pi```
- Value function is the expected return: ```v_pi(s) = E-pi(Gt | St = s)```
- We can estimate any expected value simply by adding up samples and dividing by the total number of samples: ```Vbar_pi(s) = Sum of Gi,s / N ...for i=1 to N```  (i = episode index, s = index of state). For every episode we play, we’ll have a sequence of states and rewards. And from these rewards, we can calculate the return by definition, which is just the sum of all future rewards.

### First-visit Monte Carlo

Average returns only for first time s is visited in an episode.
- 1. Initialize the policy, state-value function
- 2. Start by generating an episode according to the current policy
  - Keep track of the states encountered through that episode
- 3. Select a state in previous step
  - Add to a list the return received after first occurrence of this state
  - Average over all returns
  - Set the value of the state as that computed average
- 4. Repeat previous step
- 5. Repeat 2 through 4 until satisfied

### Every visit Monte Carlo

Average returns for every time s is visited in an episode.
Only step 3.1 below is different than that of above first-visit MC method.

- 1. Initialize the policy, state-value function
- 2. Start by generating an episode according to the current policy
  - Keep track of the states encountered through that episode
- 3. Select a state in previous step
  - Add to a list the return received after every occurrence of this state
  - Average over all returns
  - Set the value of the state as that computed average
- 4. Repeat previous step
- 5. Repeat 2 through 4 until satisfied


### Monte Carlo Control

Once we have the value function for a random policy, the key task that still remains is that of finding the optimal policy using Monte Carlo. (Similar to dynamic programming) Recall that the formula for policy improvement in DP required the model of the environment as shown in the following equation:
```pi_dash(s) = argmax a Sum p(s_dash, r | s,a)(r + gamma * v_pi(s_dash)) ```
It finds out the optimal policy by finding actions that maximize the sum of rewards. However, a major caveat here is that it uses transition probabilities, which is not known in the case of model-free learning. Since we do not know the state transition probabilities p(s’,r/s,a), we can’t do a look-ahead search like DP. Hence, all the information is obtained via experience of playing the game or exploring the environment. Policy improvement is done by making the policy greedy with respect to the current value function. In this case, we have an action-value function, and therefore no model is needed to construct the greedy policy.
``` pi(s) = argmax a  q(s,a) ```
A greedy policy (like this) will always favor a certain action if most actions are not explored properly. There are two solutions for this: a) MC with exploring starts, b) MC with epsilon-Soft



