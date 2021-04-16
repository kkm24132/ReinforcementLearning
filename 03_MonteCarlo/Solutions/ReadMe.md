
### Solutions to Examples from the Book

-**Solution to Q5.1**

  - Blackjack problem: Why does the estimated value function jump up for the last two rows in the rear? 
    - It is due to the strategy that player will not stop until meeting 20 or 21. That indicates player would face the risk of failing by hitting, which results the low value part right before 20 and 21. On the 20 and 21, however, the player stops and has a very high opportunity to win, especially when dealer will stop at 17 or higher.
  - Why does it drop off for the whole last row on the left? 
    - It drop off for the whole last row on the left because if Dealer showing an ACE, It has very high possibility of getting higher score than the player when it counts as 11. Thus, the value of dealer's A has contained the dealer's winning rate of making it usable or not. Other cards have no such condition thus A is a special which makes the gap.
  - Why are the frontmost values higher in the upper diagrams than in the lower?
    - Frontmost values are higher in the upper diagrams because A represent dual values of being used as 1 and 11 in the upper diagram. It makes the player better off and is similar with the condition of having drop in the leftmost rows.

![Solution to Q5_1](https://github.com/kkm24132/ReinforcementLearning/blob/main/03_MonteCarlo/Solutions/Q5_1.png)


-**Solution to Q5.2**

  - Suppose every-visit MC was used instead of first-visit MC on the blackjack task. Would you expect the results to be very different? Why or why not?
    - **Answer:** No. Black jack does not contain two duplicate state in any episode, making first-visit and every-visit method essentially the same thing.


