# Reinforcement Learning (RL)

This repository focuses on Reinforcement Learning related concepts, use cases, point of views and learning approaches. These are purely based on my learnings, readings, experiences in dealing with practical / real-life context and scenarios.

### Structure of Repository

- [**01_Introduction**](https://github.com/kkm24132/ReinforcementLearning/tree/main/01_Introduction) covers Key Terms used in RL, Basic elements, Concepts/Topics around RL etc.
- [**02_MAB**](https://github.com/kkm24132/ReinforcementLearning/tree/main/02_MAB) covers Multi-Armed Bandit Problem area
- [**03_Monte Carlo Methods**](https://github.com/kkm24132/ReinforcementLearning/tree/main/03_MonteCarlo) covers Monte Carlo Methods
- [**04_Temporal Difference Learning**](https://github.com/kkm24132/ReinforcementLearning/tree/main/04_TemporalDiff) covers Monte Carlo Methods
- [**05_Dynamic Programming**](https://github.com/kkm24132/ReinforcementLearning/tree/main/05_DynamicProgramming) covers Dynamic Programming

### Areas covered
- Multi-Armed Bandit Problems (MABP)
- Finite Markov Decision Processes (MDP)
- Dynamic Programming Methods
- Monte Carlo Methods
- Temporal Difference (TD) Learning
- n-Step Bootstrapping
- Tabular Solution Methods and Approximate Solution Methods

### How to be Successful in implementing RL

- Figure out the Adoption factor and ensure "right" stakeholder blessings are met upfront
- Identify "appropriate" business use case within the context of the industry / sub-industry / sub-segment : relevancy is a must
- Identify compute costs upfront and put together a "short term" and "long term" ROI plan to track tasks and how it benefits : we also need to see a pattern of our outcomes so that we can re-adjust and tweak the strategy in the process to stay effective and stay successful
- Focus on simulation method and see how we can strategy for multiple use cases / related use cases and not just one or two use cases 

**This is where the difference between LEADERS and LAGGARDS in this space !!**


### Use Cases (Non-exhaustive, for understanding purposes)

|Use Case Theme | Description  | Industry Relevancy | Category |
|      ---      |     ---      |       ----         |   ---    |
|Pricing and Promotion Analytics | Ability to apply advanced pricing and promotion strategies to improve product margins | Agriculture | Next Best Actions for Customer
|Waste and Cost reduction | Optimize warehouse logistics and network for reduced waste and maintenance cost reduction | Agriculture | Optimize Complex Operations 
|Clinical Trials | The well being of patients during clinical trials is extremely important along with the actual results of the study. In this scenario, the exploration is equivalent to identifying the best treatment, and exploitation is treating patients as effectively as possible during the trial process.| Life Sciences | Optimize Complex Operations
|Trading Strategy Optimization | Ability to optimize the trading strategy for an options-trading portfolio | Financial Services | Optimize Complex Operations
|Customer HyperPersonalization | Delivering advanced personalization abilities that adapt promotions, next best offers and recommendations for increase customer satisfaction and increased sales | Financial Services | Next Best Actions for Customer
|Load Balancing | Ability to balance the load of electricity grids in a situation of varying demand cycles | Energy and Utilities | Optimize Complex Operations
|Effective Inventory Management with Robotics| Stock and pick inventory using Robots |Retail and CPG | Optimize Product Development Cycle / Design
|Network Routing | Routing is the process of selecting a path for traffic in a network, such as telephone networks or computer networks (internet) etc. Allocation of channels to the right users, such that the overall throughput is maximised, can be formulated as a MABP. | Generic / Common | Optimize Product Development Cycle / Design
|Online Advertising | The goal of an advertising campaign is to maximise revenue from displaying ads. The advertiser makes revenue every time an offer is clicked by a web user. Similar to MABP, there is a trade-off between exploration, where the goal is to collect information on an ad’s performance using click-through rates, and exploitation, where we stick with the ad that has performed the best so far. | Generic / Common | Next Best Actions for Customer

**Other References:**
- [10 real life problems](https://neptune.ai/blog/reinforcement-learning-applications)
- [Applications in real world](https://towardsdatascience.com/applications-of-reinforcement-learning-in-real-world-1a94955bcd12)

### "Staying Current" in RL

- There are 3 key aspects which are pertinent to greater control of RL algorithms and it's solving power:
  - **Design approach** to see how rewards can be maximized when agent learns
  - Importance and relevancy of **the Learning environment**
  - **Compute power** which is significant where we look for approximation or linear/non-linear function approximations
- Soft-actor critic algorithms are significantly increasing the training efficiency and decreasing compute costs
  - [Off Policy Maximum Entropy Deep RL with a stochastic actor](https://arxiv.org/abs/1801.01290)
  - [Tuomas Haarnoja et al on other Soft-actor critic algorithms](https://arxiv.org/abs/1812.05905)
- Some of the Key cloud computing work that can be looked at:
  - Microsoft Project Bonsai [Here](https://docs.microsoft.com/en-us/bonsai/product/)
  - Google SEED-RL [Here](https://research.google/pubs/pub48767/)
  - Amazon Sagemaker RL [Here](https://docs.aws.amazon.com/sagemaker/latest/dg/reinforcement-learning.html)

### Reference Materials
- Book1: [Sutton and Barto](http://incompleteideas.net/book/the-book-2nd.html)
- Book2: [DL by Ian Goodfellow et al](https://www.deeplearningbook.org/)
- RL from Stanford: [CS234](https://web.stanford.edu/class/cs234/)
- RL Winter 2021 Stanford: [Modules and Videos](https://web.stanford.edu/class/cs234/modules.html)
- [Common RL Examples on Sagemaker](https://github.com/kkm24132/amazon-sagemaker-examples/tree/master/reinforcement_learning)
- Initial Part MABPs: [Epsilon, epsilon-Greedy methods](https://www.datahubbs.com/multi_armed_bandits_reinforcement_learning_1/)
- Advanced MABPs: [UCB Bandits, Gradient Bandits, Nonstationary Bandits](https://www.datahubbs.com/multi-armed-bandits-reinforcement-learning-2/)

### Resources
- [RL resource references](https://medium.com/datadriveninvestor/absolutely-free-resources-for-reinforcement-learning-d16a5230cb0f)

![Using RL and multi-armed bandits to find Best Classification Model](https://github.com/kkm24132/ReinforcementLearning/blob/main/01_Introduction/RL_AWS_BestClassfn_Model.png)
