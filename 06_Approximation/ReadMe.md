
# Online Prediction with Approximation
This covers Chapter 9 of Sutton and Barto book.
- [Contents from Chapter 9 of SB Book](https://github.com/kkm24132/ReinforcementLearning/blob/main/06_Approximation/ReadMe.md#contents-from-chapter-9-of-sb-book)
- [Understanding Points](https://github.com/kkm24132/ReinforcementLearning/blob/main/06_Approximation/ReadMe.md#understanding-points)
- [Examples](https://github.com/kkm24132/ReinforcementLearning/blob/main/06_Approximation/ReadMe.md#examples)
- [References](https://github.com/kkm24132/ReinforcementLearning/blob/main/06_Approximation/ReadMe.md#references)


## Contents from Chapter 9 of SB Book
- Value Function Approximation
- The Prediction Objective (VE_bar)
- Stochastic gradient and Semi-gradient Methods
- Linear Methods
- Feature Construction for Linear Methods
  - Polynomials
  - Fourier Basis
  - Coarse Coding
  - Tile Coding
  - Radial Basis Functions
- Selecting Step-size Parameters Manually
- Nonlinear Function Approximation
- Least-squares TD
- Memory Based Function Approximation
- Kernel Based Function Approximation 

[Back to Top](https://github.com/kkm24132/ReinforcementLearning/blob/main/06_Approximation/ReadMe.md#online-prediction-with-approximation)

## Understanding Points
- To handle large number of states (Example: Routing in a communication network)
  - Approximate the Value Function
  - Narrow down to a class of functions: parameterized and try to find the best function within the class
  - ```v_pi(s) = v_hat(s, w)``` , w is an element of R^d, d - dimensional parameter, d << |s|
- Parametrization Examples
- Linear Function Approximations
  - Polynomial bases 
    - Fourier Basis
      - Represents periodic functions as weighted sums of sine and cosine basis functions
  - NonLinear Function approximates
- Prediction Objective (VE_bar)
- Update Rule : Gradient Descent
- Gradient MC Update
- Semi-Gradient TD(0) Update
- Update Rule: TD(0) with function approximation

[Back to Top](https://github.com/kkm24132/ReinforcementLearning/blob/main/06_Approximation/ReadMe.md#online-prediction-with-approximation)


## Examples


[Back to Top](https://github.com/kkm24132/ReinforcementLearning/blob/main/06_Approximation/ReadMe.md#online-prediction-with-approximation)

## References


[Back to Top](https://github.com/kkm24132/ReinforcementLearning/blob/main/06_Approximation/ReadMe.md#online-prediction-with-approximation)


