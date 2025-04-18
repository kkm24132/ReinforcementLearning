
# Monte Carlo Methods
- [Core Topics from Chapter5 in Sutton and Barto Book](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#core-topics-from-chapter5-in-sutton-and-barto-book)
- [Solutions to Exercises](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#solutions-to-exercises)
- Understanding Points
  - [Introduction](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#introduction)
  - [Monte Carlo Policy Evaluation](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#monte-carlo-policy-evaluation)
  - [First-Visit Monte Carlo](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#first-visit-monte-carlo)
  - [Every-Visit Monte Carlo](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#every-visit-monte-carlo)
  - [Monte Carlo Control](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#monte-carlo-control)
  - [MC with Exploring Starts (ES)](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#mc-with-exploring-starts-es)
  - [Off-Policy MC Prediction Procedure](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#off-policy-mc-prediction-procedure)
  - [Off-Policy MC Control Procedure](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#off-policy-mc-control-procedure)
  - [Discounting Aware Importance Sampling](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#discounting-aware-importance-sampling)
- [Example Problem Solving](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#example-problem-solving)
- [References](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#references) 


## Core Topics from Chapter5 in Sutton and Barto Book
  - Monte Carlo Prediction
  - Monte Carlo Estimation of Action Values
  - Monte Carlo Control
  - Monte Carlo Control without Exploring Starts
  - Off-Policy Prediction via Importance Sampling
  - Incremental Implementation
  - Off-Policy Monte Carlo Control
  - Discounting-aware Importance Sampling
  - Per-decision Importance Sampling

[Back to Top](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#contents---monte-carlo-methods)

## Solutions to Exercises
  - Solutions to [Chapter5 : Monte Carlo Methods is Here](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo/Solutions)

[Back to Top](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#contents---monte-carlo-methods)

## Understanding Points

### Introduction
- From definition perspective: Mnte Carlo Methods: we understand that any method which solves a problem by generating suitable random numbers, and observing that fraction of numbers obeying some properties, can be classified as a Monte Carlo method.
- The MC method for RL learns directly from episodes of experience without any prior knowledge of MDP transitions. The random component is the return or reward.
- One caveat here is that it can only be applied to episodic MDPs. The reason is that the episode has to terminate before we can calculate any returns. Here, we don’t do an update after every action, but rather after every episode. It uses the simplest idea – the value is the mean return of all sample trajectories for each state.
- Recalling the idea from MABPs, every state is a separate multi-armed bandit problem and the idea is to behave optimally for all multi-armed bandits at once.
- Similar to dynamic programming, there is a policy evaluation (finding the value function for a given random policy) and policy improvement step (finding the optimum policy).

### Monte Carlo Policy Evaluation
- Goal: is to learn the value function v_pi(s) from episodes of experience under a policy pi. Recall that the return is the total discounted reward: ```S1, A1, R2, ...Sk ~ pi```
- Value function is the expected return: ```v_pi(s) = E-pi(Gt | St = s)```
- We can estimate any expected value simply by adding up samples and dividing by the total number of samples: ```Vbar_pi(s) = Sum of Gi,s / N ...for i=1 to N```  (i = episode index, s = index of state). For every episode we play, we’ll have a sequence of states and rewards. And from these rewards, we can calculate the return by definition, which is just the sum of all future rewards.

### First-Visit Monte Carlo
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

### Every-Visit Monte Carlo
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

### MC with Exploring Starts (ES)
![MC With Exploring Starts](https://github.com/kkm24132/ReinforcementLearning/blob/main/03_MonteCarlo/MC_With_ExploringStarts.png)

### Off-Policy MC Prediction Procedure
Q(S_t,A_t) <- Q(S_t,A_t) + w / C(S_t,A_t)

### Off-Policy MC Control Procedure
By Control - we mean more optimal target policy
Constraint problem

- Assume that behaviour soft i.e. there is non-zero probability of selecting every feasible action in each state
- Algorithm: (Off  Policy MC Control for estimating Policy pi = pi_star)
  - Initialize Q(s,a) E R
  - Initialize C(s,a) <- 0
  - pi(s) <- argmax a  Q(s,a)

### Discounting Aware Importance Sampling
- One needs to take into account that returns are discounted while deriving Importance Sampling (IS) estimates
- Example: 
  - Let Gamma = 0
  - Episodes last for 100 steps
  - Return from time 0 is then: G_0 = R_1 + Gamma R_2 + .......Gamma ^ T-1 . R_T = R1
  - IS Ratio : 
  - These terms do not contribute to the bias in the estimator, but do contribute to the variance
- Thus, the return from time t can be written as a partial sum of discounted returns
- G_t =
- These returns can be scaled using truncated IS ratios
- Ordinary IS Estimator
- Weighted IS Estimator
- 2nd approach: Per decision IS
  - Can reduce variance even when Gamma=1
- Ordinary IS Estimator - research problem - Not clear f there exists a per-decision version of weighted IS and all estimates proposed in literature do not converge to true value.

[Back to Top](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#contents---monte-carlo-methods)

## Example Problem Solving

- **Problem 1:** Consider an MDP with a single non-terminal state (NT) and two terminal states T1 and T2, respectively. When in state NT, the next state is NT itself with probability 0.6, T1 with probability 0.2 or T2 with probability 0.2, respectively. If the transition from NT is to either NT itself or to T1, the single-stage reward is 1. On the other hand, if the transition from NT is to T2, the single-stage reward is 0. We observe two episodes of this MDP both starting in state NT. The first episode terminates in T1 and gives a total reward of 16. The second episode terminates in T2 and gives a total reward of 6.
  - We have to write down both the episodes completely by writing the sequence of states visited and single-stage reward obtained.
  ![Solution](https://github.com/kkm24132/ReinforcementLearning/blob/main/03_MonteCarlo/MC_Problem1.jpeg)
  Episode 1 and Episode 2 are mentioned in above diagram.
  
  - We need to find out first visit and every visit estimates of the value of NT.
    - First visit estimates:
      - V1(NT) = 16
      - V2(NT) = 6
    - Every visit estimates:
      - Vi(NT) = 17 - i  , for all i = 1,2,3....16
      - V17(NT) = 6
      - V18(NT) = 5
      - V19(NT) = 4
      - V20(NT) = 3
      - V21(NT) = 2
      - V22(NT) = 1
      - V23(NT) = 0
  
  - We need to compute how many estimates are obtained for first visit and every visit estimators.
    - First visit: there are 2 estimates
    - Every visit: there are 23 estimates
  - We need to find the value of NT obtained from (i) the first visit estimators and (ii) every visit estimators.
    - First visit: Value of NT = (16 + 6)/2 = 22/2 = 11
    - Every visit: Value of NT = 1/23 (1+2+3+...+16+1+2...+6) = 1/23 [(16*17 / 2) + (6*7 / 2)] = 1/23 [136 + 21] = 157/23 ~ 6.83


[Back to Top](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo#contents---monte-carlo-methods)

## References
- Chapter 5 of Sutton and Barto book can be referenced for this.
- Gridworld example: https://github.com/michaeltinsley/Gridworld-with-Q-Learning-Reinforcement-Learning-/blob/master/Gridworld.ipynb
- Blackjack example for MC with first visit: https://github.com/ShangtongZhang/reinforcement-learning-an-introduction/tree/master/chapter05
- Some more Blackjack and MC examples: https://github.com/udacity/deep-reinforcement-learning/blob/master/monte-carlo/Monte_Carlo_Solution.ipynb
- Other Youtube examples from Siraj videos: https://www.youtube.com/watch?v=-YpalutQCKw

