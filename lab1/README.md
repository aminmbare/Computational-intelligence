#  LAB 1 : Set Cover 

for this LAB I have used the branch and bound method .
Branch and bound is a technique used in integer optimization problems - ie optimization problems for which the variables are integers.
for the set cover problem our variables are binary ( 1 if a subset is in the solution and 0 if the subset is not considered in the solution)
The general concept of branch and bound is this - imagine a binary tree, as deep as the number of variables you have, at each level, each variable can take the values 1 or 0 
A solution to the problem would be a path from the top of the tree to the bottom which reaches the highest total value under the given cost constraints
In order to reduce the number of calculations, we want to "prune" the tree, ie ignore completely sections of it which we know can't have better results than the best one we've already found, without needing to fully calculate what results they achieve. So branches are developed as long their vertexes don't increase the cost of the solution. 
Thanks to two functions : 
1-  bypass branch that bypasses a branch a not optimal solution 
2-  next vertex which is essentialy to keep exploring the tree 


## Note :a timer of 10 minutes has been set for every instance

this work has been inspired by another source from github , andrea rubbi . another student that has solved the set Covering problem however the idea to use branch and bound was thought by myself since I have gotten familliar with cited method through an operational research course that I have followed last year. 

