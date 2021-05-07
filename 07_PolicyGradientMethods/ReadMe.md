
## Policy Gradient Methods 

### Contents (From Chapter 13 in Sutton and Barto Book)
- Policy Approximation and its Advantages
- The Policy Gradient Theorem
- REINFORCE: Monte Carlo Policy Gradient
- REINFORCE with Baseline
- Actor-Critic Methods
- Policy Gradient for Continuing Problems
- Policy Parameterization for Continuous Actions

### Algorithms

Algorithms can be referred [here](https://github.com/kkm24132/ReinforcementLearning/tree/main/07_PolicyGradientMethods/Algorithms)

### Summary Points
- Idea: Instead of parameterizing the value function and performing greedy policy improvement we parameterize the policy and do gradient descent into a direction that improves it.
- Sometimes the policy is easier to approximate than the value function. Additionally, we need a parameterized policy to deal with continuous action spaces and environments where we need to act stochastically.
- Policy Score Function ```J(theta)```: Intuitively, it measures how good our policy is. For example, we can use the average value or average reward under a policy as our objective.
- Common choices for the policy function: Softmax for discrete actions, Gaussian parameters for continuous actions.
- Policy Gradient Theorem: ```grad(J(theta)) = Ex[grad(log(pi(s, a))) * Q(s, a)]```. Basically, we move our policy into a direction of more reward.
- REINFORCE (Monte Carlo Policy Gradient): We substitute a samples return ```g_t``` form an episode for Q(s, a) to make an update. Unbiased but high variance.
- REINFORCE Baseline: Instead of measuring the absolute goodness of an action we want to know how much better than "average" it is to take an action given a state. E.g. some states are naturally bad and always give negative reward. This is called the advantage and is defined as ```Q(s, a) - V(s)```. We use that for our policy update, e.g. ```g_t - V(s)``` for REINFORCE.
- Actor-Critic: Instead of waiting until the end of an episode as in REINFORCE we use bootstrapping and make an update at each step. To do that we also train a Critic Q(theta) that approximates the value function. Now we have two function approximators: One of the policy, one for the critic. This is basically TD, but for Policy Gradients. A good estimate of the advantage function in the Actor-Critic algorithm is the td error. Our update then becomes ```grad(J(theta)) = Ex[grad(log(pi(s, a))) * td_error]```
- Can use policy gradients with td-lambda, eligibility traces, and so on.
- Deterministic Policy Gradients: Useful for high-dimensional continuous action spaces where stochastic policy gradients are expensive to compute. The idea is to update the policy in the direction of the gradient of the action-value function. To ensure exploration we can use an off-policy actor-critic algorithm with added noise in action selection.
- Deep Deterministic Policy Gradients: Apply tricks from DQN to Deterministic Policy Gradients.
- Asynchronous Advantage Actor-Critic (A3C): Instead of using an experience replay buffer as in DQN use multiple agents on different threads to explore the state spaces and make decorrelated updates to the actor and the critic.


### References
- Reference from [Lilian Weng on Policy Gradient Algos](https://lilianweng.github.io/lil-log/2018/04/08/policy-gradient-algorithms.html)
- Baseline for Policy Gradients - [The optimal reward baseline for gradient-based RL](https://arxiv.org/ftp/arxiv/papers/1301/1301.2315.pdf)
- Deck on Policy Gradients by [UC Berkely Lecture CS285:Sergey Levine](http://rail.eecs.berkeley.edu/deeprlcourse/static/slides/lec-5.pdf)

### Solutions to Exercises

- **Exercise 13.1: Use your knowledge of the gridworld and its dynamics to determine an exact symbolic expression for the optimal probability of selecting the right action in Example 13.1.**
  - Let's consider p = P(Right), hence P(Left) = 1-p
  - Then we will label states 1-3 from Right to Left
  - Value of Terminal state is set to 0
  - Bellman equation will be as follows:
  ```
  v_pi(1) = p * v_pi(2) - 1
  v_pi(2) = p * v_pi(1) - 1 + (1-p) * v_pi(3)
  v_pi(3) = (1-p) * v_pi(2) - 1
  ```
  - Setting f(p) for the value of initial state and solving the system gives us the following:
  ```
  f(p) = (p^2 - 2p + 2) / (p * (1-p))
  
  This attains maximum at a value p = 2^0.5 * (2^0.5 - 1)
  
  f is defined on the open interval (0,1), the performance becomes infinity as p -> 0,1
  ```

- **Exercise 13.2: Generalize the box on page 199, the policy gradient theorem (13.5), the proof of the policy gradient theorem (page 325), and the steps leading to the REINFORCE update equation (13.8), so that (13.8) ends up with a factor of #t and thus aligns with the general algorithm given in the pseudocode.**

  - Generalisation of the recursion equation that governs expected time in each state can be represented as per below: 

![Exercise solution 13.21](https://github.com/kkm24132/ReinforcementLearning/blob/main/07_PolicyGradientMethods/figure/Solution13.21.png) 


  - The generalisation of the proof of the policy gradient theorem comes with the use of the Bellman equation unfolding for the value function. We therefore arrive at the following gradient:

![Exercise solution 13.22](https://github.com/kkm24132/ReinforcementLearning/blob/main/07_PolicyGradientMethods/figure/Solution13.22.png) 

and the theorem follows as before.

  - In order for us to incorporate discounting "Gamma" fully, we need to view it as a form of termination. Therefore, the Policy Gradient Theorem becomes the following:

![Exercise solution 13.23](https://github.com/kkm24132/ReinforcementLearning/blob/main/07_PolicyGradientMethods/figure/Solution13.23.png)


- **Exercise 13.4**

![Exercise problem 13.4](https://github.com/kkm24132/ReinforcementLearning/blob/main/07_PolicyGradientMethods/figure/Exercise13.4.png)

- **Answer**
- 
![Exercise solution 13.4](https://github.com/kkm24132/ReinforcementLearning/blob/main/07_PolicyGradientMethods/figure/Solution13.4.png)


