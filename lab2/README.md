#  LAB 2 : GENETIC ALGORITHM FOR SCP 


**Let**

$I$ =  set of numbers to cover , we will refer to them as rows, 

$J$ =  total subsets used to cover $I$, we will refer to them as columns, 

$\alpha_i$ = the set of  columns that cover row $i$ , $i$  $\in$  $I$ , 

$\beta_j$ = the set of rows covered by columns $j$ , $j$ $\in$ $J$ ,  

$S$ = the set of columns in a solution, 

$U$ = the set of uncovered rows, 

$w_i$ = the number of columns that cover row $i$ . 

## SOLUTION ENCODING 

We picked the usual 0-1 binary representation. We used an n-bit binary list as the chromosome structure where n is the number of columns in $J$.

A value of 1 for the ith bit implies that column i is in the solution.


## POPULATION SIZE AND  INITIAL POPULATION 

**initial population**

(i) initiliase $S_p$ := $\emptyset$ , initialise $w_i$ := 0, $\forall$ $i$ $\in$ $I$ ,

(ii)  for each row $i$ in $I$ : 
        
   (a) randomly select a column j in $\alpha_i$ , 
        
   (b) add $j$ to $S_p$ and set $w_i$ := $w_i$ + 1, $\forall$ $i$ $\in$ $\beta_j$ . 

(iii) Let $T$ := $S_p$ 

(iv) Randomly select a column $j$ , $j$  $\in$ $T$ and set $T$ := $T$ - $j$ .  If $w_i$ $\geq$ 2 , $\forall$ i $\in$ $\beta_j$ ,

set $S_p$ := $S_p$ - $j$ and set $w_i$ := $w_i$ - 1, $\forall$ $i$ $\in$ $\beta_j$ .

(v) Repeat step (iv) until $T$ = $\emptyset$


## PARENT SELECTION

For the parent selection , We made an operator that works in two phases .

(i) Ranfomly select from the population k individuals , the probabilty of taking an Individual is not the same for all individuals ,but instead biased based the respective fitness of the individuals ( inspired by roulette ) 

(ii) Make a tournament out of the k selected individuals and pick the fittest out of them as the parent 



## CROSS OVER OPERATOR 

We will apply a one-point cross-over


## HEURISTIC FEASABILITY OPERATOR 

(i) Initialise $w_i$ := | S $\cap$ $\alpha_i$ | , $\forall$ $i$ $\in$ $I$ },

(ii) Initialise $U$ := { $i$ | $w_i$ = 0 , $\forall$ $i$ $\in$ $I$ , 

(iii) For each row $i$ in $U$ ( in increasing order of i ):
        
   (a) find the first column $j$ (in increasing order of j ) in $\alpha_i$ that minimises $c_j$ / | $U$ $\cap$ $\beta_j$ | , 
   
   (b) add $j$ in $S$ and set $w_i$ := $w_i$ + 1 , $\forall$ $\in$ $\beta_j$ . Set $U$ := $U$ - $\beta_j$
   
(iv) For each column $j$ in $S$ (in decreasing order of $j$ ) , if $w_i$ $\geq$ 2 , $\forall$ $i$ $\in$ $\beta_j$ ,

set $S$ := $S$ - $j$ and set $w_i$ := $w_i$ - 1 , $\forall$ $i$ $\in$ $\beta_j$ .

(v) $S$ is now in a feasible solution and contains no redundant columns 


## OVERVIEW

To summarise our GA , the following steps are used.

(i) Generate an initial population of $N$ random solution , Set $t$ := 0.

(ii) Select two solutions $P_1$ and $P_2$ from the populatiuon using the roulette.

(iii) Combine $P_1$ and $P_2$  to form a new solution $C$ using the fusion crossover operator. 

(iv) Mutate $k$ randomly selected genes in $C$. 

(v) Make $C$ feasible and remove redundant columns in $C$ by applying the heuristic operator .

(vi) Repeat (iii)-(v) until the off-spring is ready 

(vii) Replace the least fit Individuals in the old generation by the off-spring

(viii)  Repeat (ii)-(vii) until $t$ = $M$ solutions have been generated. The best solution is the one with the smalled fitness in the population

## RESULTS 

| Trial  | N     | Cost        | time       | generations   |
| ------ |:-----:|:-----------:|:----------:|--------------:|
| 1      |  5    |     5       |     1s     |     1000      |
| 2      |  10   |     10      |     1.5s   |      1000     |
| 3      |  20   |     23      |     9s     |       10000   |
| 4      |  100  |     165     |    50s     |      1500     |
| 5      |  100  |     163     |    50s     |      1500     |
| 5      |  100  |     171     |    50s     |      1500     | 
| 6      |  100  |     159     |    50s     |       1500    |
| 7      |  500  |     1387    |    22m     |       1000    |
| 8      |  500  |     1353    |    22m     |       1000    |
| 9      |  500  |     1334    |    22m     |       1000    |
| 10     |  1000 |     3289    |    133m    |       1500    |
| 11     |  1000 |     3299    |    72m     |       800     |
| 12     |  1000 |     3338    |    73m     |       800     |

## ACKNOWLEDGEMENT

J.E. Beasley , RC. Chu (1995). A genetic algorithm for the set covering problem

