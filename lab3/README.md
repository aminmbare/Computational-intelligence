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

-  we pick the longest pillar and we try to keep just one element in it after we finish our move. 

• if the active pillars in Nim game is equal 

Below we will provide the winning ratio for out rule based agent against the random agent and optimal agent. 

The evaluation is based on 100 Nim matches.

We set our hyper parameters to be $p$ = 0.5 and $q$ = 0.5

We assume that our agent will make the "first move".

| Oponent          | Winning ratio     |
| ---------------- |:-----------------:|
| Random Agent     |  86%              | 
| Optimal Agent    |  0%               | 


## TASK3.2

The goal is to find the optimal or sub optimal set of $p$ and $q$ (defined in task one) by using a genetic algorithm. 
By optimality we mean the set that will guarantee the highest winning ratio against the Random Agent

### ENCODING 

Each chromosome will consist of two genes one that represent the $p$ hyper-parameter and the second will represent $q$. 

### Initial Popilation

Our population will be randomly generated , we will randomly assign a value in  the range (0,1) for every gene in each inidivual 

Our population will consist of 30 individuals

### Cross-Over

It  consists on taking the average of every the genes frolm both parents and assigning it to the child's

### FiTNESS 

The sum of the winning ratio of our agent against the random agent for the three NIM NUMBERS [4,5,6]

## GA 

"INITIAL POPULATION" will be equal to 30. 

"OFF SPRING" size is set to 3 and "NUMBER OF GENERATION" is equal to 200. 

the fittest inidivual among the population after evolving it has $p$ = 0.2422 and $q$ = 0.898591 . 

We assume that that the EVOLVED AGENT ALWAYS MAKES THE "FIRST MOVE". 

| Oponent                     | Winning ratio     |
| --------------------------- |:-----------------:|
| Random Agent                |  95%              | 
| Optimal Agent               |  0%               | 
| rule based (p =0.5 , q =0.5 | 70%               |

If we assume that the evolved agent goes second against the rule based agent . the winning ratio 0.63 for the evolved agent. 
