
## Policy Gradient Methods 

### Contents (From Chapter 13 in Sutton and Barto Book)
- Policy Approximation and its Advantages
- The Policy Gradient Theorem
- REINFORCE: Monte Carlo Policy Gradient
- REINFORCE with Baseline
- Actor-Critic Methods
- Policy Gradient for Continuing Problems
- Policy Parameterization for Continuous Actions

### Summary Points
- Idea: Instead of parameterizing the value function and performing greedy policy improvement we parameterize the policy and do gradient descent into a direction that improves it.

### Solutions to Exercises

- **13.1: Use your knowledge of the gridworld and its dynamics to determine an exact symbolic expression for the optimal probability of selecting the right action in Example 13.1.**
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

- **13.2**

