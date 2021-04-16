
**This sub-repository contains solutions to exercises that are part of Chapter 5 in Sutton and Barto Book**

### Solutions to Examples from the Book

-**Solution to Q5.1**

  - Blackjack problem: Why does the estimated value function jump up for the last two rows in the rear? 
    - It is due to the strategy that player will not stop until meeting 20 or 21. That indicates player would face the risk of failing by hitting, which results the low value part right before 20 and 21. On the 20 and 21, however, the player stops and has a very high opportunity to win, especially when dealer will stop at 17 or higher.
  - Why does it drop off for the whole last row on the left? 
    - It drop off for the whole last row on the left because if Dealer showing an ACE, It has very high possibility of getting higher score than the player when it counts as 11. Thus, the value of dealer's A has contained the dealer's winning rate of making it usable or not. Other cards have no such condition thus A is a special which makes the gap.
  - Why are the frontmost values higher in the upper diagrams than in the lower?
    - Frontmost values are higher in the upper diagrams because A represent dual values of being used as 1 and 11 in the upper diagram. It makes the player better off and is similar with the condition of having drop in the leftmost rows.

-**Solution to Q5.2**



