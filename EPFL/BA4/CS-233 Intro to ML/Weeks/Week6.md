---
Week: 6
Themes: 
Lecture1: true
Coding exercices: false
Exercises: true
---

  

# Notes

  

## Lecture 1
Overfitting, Cross-validation and Regularization
k-Nearest Neighbors :
Classification: 
1. Compute the distance between the test $x$ sample and all training samples $\{x_i\}$ 
2. Find the $k$ samples $\{x_{NN1},...,  x_{NNN}\}$ with minimum distances 
3. Find the most common label among these $k$ nearest neighbors (majority vote) 
4. Assign the corresponding label $y_{MV}$ to the test sample
Regression: 
1. Compute the distance between the test sample $x$  and all training samples $\{x_i\}$ 
2. Find the $k$  samples $\{x_{NN1}, ... , x_{NNk}\}$ with minimum distances 
3. Compute the value $\hat{y}$ for the test sample based on that of these $kNN$

  • Advantages: 
  • Simple method
   • Effective to handle nonlinear data 
   • Only requires defining one parameter (k)
   Drawbacks: 
   • The results depend on 
   • Becomes expensive as and/or grow 
   • May be unreliable with a large kNDD


For $k$, the error is 0 on the training data, but large on the test data. This is called overfitting
For large values, the error is large on both the training and the test data. This is called underfitting
![[Pasted image 20240326092841.png|500]]
![[Pasted image 20240326093531.png|500]]

## Lecture 2


