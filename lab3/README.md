#  LAB 3 : Policy Search

Write agents able to play Nim.

The player taking the last object wins.

Task3.1: An agent using fixed rules based on nim-sum (i.e., an expert system)
Task3.2: An agent using evolved rules
Task3.3: An agent using minmax
Task3.4: An agent using reinforcement learning


## TASK3.1

For this task we will create an agent based on rules fixed by us ( an expert system ). 

the expert system consists in some rules to following depending on the amount of pillars remaining during the NIM game. 
the rules and instructions picked are based on the nim sum strategy taken from this [Nim](https://web.mit.edu/sp.268/www/nim.pdf).

• if the active pillars in Nim game is higher than 3(two rules based on the $p$ ): 
    
- pick the longest pillar and take all the elements in it. 

- Since doing binary addition is kind of hard to do in your head for large numbers, a more feasible strategy is often needed. 
An easy way to think about making the nim-sum 0 is to always leave even subpiles of the powers of 2 . So if we the active number of piles is odd , we try to eleminate the piles that are not powers of 2. However, if the number of pilars is even ,we pick the longest pillar and we try to keep just one element in it after we finish our move. 

• if the active pillars in Nim game is equal to 3(two rules based on the $q$ ): 

- if there is a pair of pillars that contain the same amount of elements , we eliminate the third pillar that is different from the identical pair, or if the previous case is true. We pick the longest pillar and we try to keep just one element in it after we finish our move. 

-  pick the longest pillar and take all the elements in it. 

• if the active pillars in Nim game is equal 