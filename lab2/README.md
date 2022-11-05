#  LAB 2 : GENETIC ASLGORITHM FOR SET COVERING PROBELM 

for this lab I used the genetic algoritrhm to solve thebset covering problem 

**Let**

```math
\I =  set of numbers to cover , we will refer to them as rows,
\J =  total subsets used to cover I, we will refer to them as columns,
\alpha_i = the set of  columns that cover row \i, \i \in \I ,
\beta_j = the set of rows covered by columns \j , \j \in \J ,
\S = the set of columns in a solution,
\U = the set of uncovered rows,
\w-i = the number of columns that cover row \i ,
```

## POPULATION SIZE AND  INITIAL POPULATION 

**initial population**

``
(i) initiliase \S_p := \emptyset , initialise \w_i := 0, \forall i \in \I ,
(ii) for eacvh row \i in \I : 
        (a) randomly select a column j in \alpha_i , 
        (b) add \j to \S_p and set \w_i := \w_i + 1, \forall \i \in \beta_j . 

(iii) Let \T := \S_p 
(iv) Randomly select a column \j , \j \in \T and set \T := \T - \j . If \w_i \geq 2 , \forall i \in \beta_j ,
set \S_p := \S_p - \j and set w_i := \w_i - 1, \forall \i \in \beta_j .
(v) Repeat step (iv) until \T = \emptyset
``




