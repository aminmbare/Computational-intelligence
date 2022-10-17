# LAB 1 : Set Cover 
for this LAB I have used the branch and bound method .
Branch and bound is a technique used in integer optimization problems - ie optimization problems for which the variables are integers.
for the set cover problem our variables are binary ( 1 if a subset is in the solution and 0 if the subset is not considered in the solution).
The general concept of branch and bound is the following .Imagine a binary tree, as deep as the number of variables you have, at each level, each variable can take the values 1 or 0.

A solution to the problem would be a path from the top of the tree to the bottom which reaches the highest total value under the given cost constraints
In order to reduce the number of calculations, we want to "prune" the tree, ie ignore completely sections of it which we know can't have better results than the best one we've already found, without needing to fully calculate what results they achieve. So branches are developed as long their vertexes don't increase the cost of the solution. 

Thanks to two functions : 

1-  bypass branch that bypasses a branch a not optimal solution 

2-  next vertex which is essentialy to keep exploring the tree 

## Note: A timer of 10 minutes has been set for every instance

## Results : a timer of approximately 900 seconds has been set for every instances 
| N     | Cost        | time(s)    |visited Nodes  |
| ----- |:-----------:| ----------:|--------------:|
|  5    |     5       |    0.4368  |    115458     |
|  10   |     10      |    5.0263  |    957418     |
|  20   |     23      |    0.47799 |    101999     |
|  100  |     201     |    978.981 |    22332383   |
|  500  |     1645    |    967.156 |    4424785    |
|  1000 |     3843    |    953.476 |    1763232    |

##ACKNOWLEDGEMENT

 https://github.com/AndreaRubbi/Set-Cover-problem-solution-Python

