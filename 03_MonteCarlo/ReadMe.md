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



