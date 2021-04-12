

## Dynamic Programming

**Covers Chapter 4 related topics in Sutton and Barto content**

- Policy Evaluation prediction
- Policy Improvement
- Policy Iteration
- Value Iteration
- Asynchronous Dynamic Programming
- Generalized Policy Iteration
- Efficiency of Dynamic Programming

### Dynamic Programming (DP)

- DP refers to the collection of algorithms that can be used to compute the optimal policy given model information ```knowledge of p(s',r|s,a)``` 
- Optimal values need not be unique, whereas optimal value functions should necessarily be unique.
- Bellman equation can be solved iteratively ... The algorithm converges as ``` V_k --> V_pi as k --> infinity ```
- Contraction mapping theorem: a unique fixed point where ``` v_pi = T_pi * v_pi ```
- Iterative solution procedure : Iterative Policy Evaluation
  - Start with an initial estimate V_0 of the value function
  - Iterate over k>=0 to obtain the update
  - Iterative PE for estimating V ~ V_pi
- Policy Improvement Step: Finds an improved policy by making it greedy with regards to value function of the original policy
- Policy Iteration Procedure : Policy Evaluation (PE) and Policy Improvement (PI)
- Since Policy Improvement happens at every step until convergence and number of policies is finite, the policy improvement procedure is guaranteed to converge in a finite number of steps
- Policy Iteration (using Iterative PE) for estimating ``` pi ~ pi_* ```
- Value Iteration : directly works with the Bellman equation of optimality
- Value Iteration Algorithm
- Modified Policy Iteration(MPI): ``` As m --> infinity, Vm(s) --> Vpi_k(s)```
  - MPI generalizes the PI and VI iteration procedures by allowing for any value of m_k >= 1
- Geometric interpretation of VI and PI : V* = TV* 


