

## Dynamic Programming

### **Contents (From Chapter 4 in Sutton and Barto Book)**

- Policy Evaluation prediction
- Policy Improvement
- Policy Iteration
- Value Iteration
- Asynchronous Dynamic Programming
- Generalized Policy Iteration
- Efficiency of Dynamic Programming

### Summary Points

- DP refers to the collection of algorithms that can be used to compute the optimal policy given model information ```knowledge of p(s',r|s,a)``` 
- Optimal values need not be unique, whereas optimal value functions should necessarily be unique.
- Bellman equation can be solved iteratively ... The algorithm converges as ``` V_k --> V_pi as k --> infinity ```
- Contraction mapping theorem: a unique fixed point where ``` v_pi = T_pi * v_pi ```
- Iterative solution procedure : Iterative Policy Evaluation
  - Start with an initial estimate V_0 of the value function
  - Iterate over k>=0 to obtain the update
  - Iterative PE for estimating V ~ V_pi
- **Iterative Policy Evaluation, for estimating ```V ≈ v_π```**
![Iterative Policy Evaluation](https://github.com/kkm24132/ReinforcementLearning/blob/main/05_DynamicProgramming/IterativePolicyEvaluation.png)
- Policy Improvement Step: Finds an improved policy by making it greedy with regards to value function of the original policy
- Policy Iteration Procedure : Policy Evaluation (PE) and Policy Improvement (PI)
- Since Policy Improvement happens at every step until convergence and number of policies is finite, the policy improvement procedure is guaranteed to converge in a finite number of steps
- **Policy Iteration (using Iterative Policy evaluation) for estimating ```π ≈ π*```**
![Policy Iteration](https://github.com/kkm24132/ReinforcementLearning/blob/main/05_DynamicProgramming/PolicyIteration.png)
- Value Iteration : directly works with the Bellman equation of optimality
- Value Iteration Algorithm
- Modified Policy Iteration(MPI): ``` As m --> infinity, Vm(s) --> Vpi_k(s)```
  - MPI generalizes the PI and VI iteration procedures by allowing for any value of m_k >= 1
- Geometric interpretation of VI and PI : V* = TV* 

### Solutions to Examples from the Book

- **Solution to Q4.1**

![Solution to Q4_1](https://github.com/kkm24132/ReinforcementLearning/blob/main/05_DynamicProgramming/Q4_1.png)

- **Solution to Q4.2**

![Solution to Q4_2](https://github.com/kkm24132/ReinforcementLearning/blob/main/05_DynamicProgramming/Q4_2.png)

- **Solution to Q4.3**

  - Equations for action-value functions are captured with regards to relevant state-value functions

![Solution to Q4_3](https://github.com/kkm24132/ReinforcementLearning/blob/main/05_DynamicProgramming/Q4_3.png)

- **Solution to Q4.4**

  - The policy iteration algorithm as per Page 80 in Sutton and Barto book has a subtle bug in that it may never terminate if the policy continually switches between two or more policies that are equally good. This is okay for pedagogy, but not for actual use. We want to modify the pseudocode so that convergence is guaranteed. Following can be used:
    - Instead of the following step: 
      - ``` If old-action ≠ Π(s) then policy-stable <-- false ```
    - Use the following step:
      - ``` If old-action ∉ { a_i }, which is the all equi-best solutions from Π(s)  , then policy-stable <-- false ``` 

- **Solution to Q4.5**

  - The question is regarding how would policy iteration be defined for action values? We need to give a complete algorithm for computing q_*, analogous to that on Page 80 in the book, for computing v_*. Below is a desired snapshot of the solution.

  ![Solution to Q4_5](https://github.com/kkm24132/ReinforcementLearning/blob/main/05_DynamicProgramming/Q4_5.png)


- **Solution to Q4.6**

  - Suppose we are restricted to considering only policies that are "Epsilon-soft, meaning that the probability of selecting each action in each state, s, is at least "Epsilon/|A(s)|. Now we have to describe qualitatively the changes that would be required in each of the steps 3, 2, and 1, in that order, of the policy iteration algorithm for v_* on page 80 of the Barto book.
    - Step 3 change recommendations:
      - We will only determine policy-stable is false under the condition that the policy does not explore.
    - Step 2 change recommendations:
      - Theta should not be set above the limit of any Epsilon-soft method.
    - Step 1 change recommendations: 
      - Pi should be well-defined as Epsilon-soft method. Epsilon value should be given.
 
- **Solution to Q4.7**


