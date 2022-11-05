#  LAB 2 : GENETIC ASLGORITHM FOR SET COVERING PROBELM 

for this lab I used the genetic algoritrhm to solve the set covering problem 

**Let**


$I$ =  set of numbers to cover , we will refer to them as rows, 

$J$ =  total subsets used to cover $I$, we will refer to them as columns, 

$\alpha_i$ = the set of  columns that cover row $i$ , $i$  $\in$  $I$ , 

$\beta_j$ = the set of rows covered by columns $j$ , $j$ $\in$ $J$ ,  

$S$ = the set of columns in a solution, 

$U$ = the set of uncovered rows, 

$w_i$ = the number of columns that cover row $i$ ,

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

We chose the roulette for the parent selection with a bias towards the fittest individual , with a selection pressure equal to 50 



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

