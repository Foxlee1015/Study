---
layout: post
title: Algorithms(1. DP)
categories:
- blog
---
> # Dynamic programming


* *Dynamic programming*, like the divide-and-conquer method, solves problems by combining the solutions to subproblems. 
  (“Programming” in this context refers to a tabular method, not to writing computer code.) 
  As we saw in Chapters 2 and 4, *divide-and-conquer algorithms partition the problem into disjoint subproblems*,
  solve the subproblems recursively, and then combine their solutions to solve the original problem.

* Incontrast, dynamic programming applies **when the subproblems overlap—that is, when subproblems share subsubproblems**. 
In this context, a divide-and-conquer algorithm does more work than necessary, repeatedly solving the common subsubproblems. 
* A dynamic-programming algorithm solves each subsubproblem just once and then saves its answer in a table,(??) 
thereby avoiding the work of recomputing the answer every time it solves each subsubproblem. 
We typically apply dynamic programming to optimization problems. Suchproblems can have many possible solutions. 
Each solution has a value, and we wish to ﬁnd a solution with the optimal (minimum or maximum) value. 
We call such a solution an optimal solution to the problem, as opposed to the optimal solution, 
since there may be several solutions that achieve the optimal value. 
When developing a dynamic-programming algorithm, we follow a sequence of four steps: 
1. Characterize the structure of an optimal solution. 
2. Recursively deﬁne the value of an optimal solution. 
3. Compute the value of an optimal solution, typically in a bottom-up fashion. 
4. Construct an optimal solution from computed information. 

Steps 1–3 form the basis of a dynamic-programming solution to a problem. 
If we need only the value of an optimal solution, and not the solution itself, then we can omit step 4. 
When we do perform step 4, we sometimes maintain additional information during step 3 so that we can easily construct an optimal solution.
The sections that follow use the dynamic-programming method to solve some optimization problems. 
