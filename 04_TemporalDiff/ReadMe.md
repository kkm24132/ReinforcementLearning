# Contents on TD
This Repository comprises of the following content areas which focus on TD (Temporal Difference Learning) methods in RL:

- [Topics from the SB Book Chapter 6](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/ReadMe.md#topics-from-the-sb-book-chapter-6)
- [Understanding Points](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/ReadMe.md#understanding-points)
- [Exercise Problem Solving](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/ReadMe.md#exercise-problem-solving)
- [References](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/ReadMe.md#references)


## Topics from the SB Book Chapter 6
- TD Prediction
- Advantages of TD Prediction Methods
- Optimality of TD(0)
- SARSA: On-Policy TD Control
- Q-learning: Off-Policy TD Control
- Expected SARSA
- Maximization Bias and Double Learning
- Games, Afterstates and Other Special Cases 


[Back to Top](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/ReadMe.md#contents-on-td)

## Understanding Points

- Temporal Difference is part of Prof Sutton's PhD work in 1984
- Lookup table case
- Proof : Van Roy and J.Tsitsikhs, 1997 - IEEE Trs on Autonomous Contribution
- Simplest TD Method: V(S_t) <- V(S_t) + alpha * {R_t+1 + Gamma . V(S_t+1) - V(S_t)}
- In TD method, we keep on updating the values of states as they are visited.
- TD Algorithms perform Bootstrapping - i.e. update values of states based on values of other states
- SARSA and Q-learning comparision:

![SARSA vs Q-learning](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/figure/SARSA_Qlearning.png)

[Back to Top](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/ReadMe.md#contents-on-td)

## Exercise Problem Solving


[Back to Top](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/ReadMe.md#contents-on-td)


## References


[Back to Top](https://github.com/kkm24132/ReinforcementLearning/blob/main/04_TemporalDiff/ReadMe.md#contents-on-td)


