---
Week: 6
Themes: 
Lecture1: true
Lecture2: false
Exercises: false
---

  

## Notes

  

## Lecture 1
Dynamic programming algorithm
When Can Dynamic Programming Be Used?
1 Optimal Substructure. 
- An optimal solution can be built by combining optimal solutions for subproblems.
-  Implies that the optimal value can be given by a recursive formula. 

2 Overlapping subproblems

Matrix chain multiplication :
Input : A chain $\{A_1,A_2,...,A_n\}$ of $n$ matrices, where for  $i= 1,2,...,n$, matric $A_i$ has dimension  $p_{i-1} \times p_i$ 
Output : A full parenthesization of the product $A_{1}A_{2}...A_{n}$ in a way that minimizes the number of scalar multiplications 
  I A product $A_{1}A_{2}A_{3}$ with dimensions: $50 \times  5 \,, 5 \times 100 \; and \; 100 \times 10$
![[Pasted image 20240326145237.png| 500]]
![[Pasted image 20240326145713.png|500]]
$m[i,j]$ is the optimal number of scalar multiplications for calculating $A_{i}A_{i+1}...A_{j}$


#### Lecture 2


