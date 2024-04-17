---
Week: 1
Themes: 
Lecture1: true
Lecture2: true
Exercises: false
---

  

## Notes

## Lecture 1
### Why study algo ? 
- optimize solutions to common problems 
- way of think 

- Truly fun quizzes every week : https://cs250.vercel.app/
### Let's starts 
#### What is an algo ? 
computational procedure ::   

| input -> | algo -> | output |
| ---- | ---- | ---- |
exemple : 
input : A number n , output : the value of $\sum_{i=1}^{n} i$
232 is an instance of the pb

~~~ python
CalculateSum(n): 
ans = 0
for i = 1, 2,..., n 
ans = ans + i
return ans
~~~
is it efficient ?        in space ? yes store 2nb, in time ? yes constant # of operations

clever version : 
~~~python
CalculateSum(n):
retun n(n+1)/2
~~~
less space used

The sorting problem :
in : a sequence 
out : sorted sequence 
~~~python
Insertion-Sort(A,n):
for j = 2 to n 
	key = A[j]
	i = j-1
	while i > 0 and A[i] > key 
	A[i+1] = A[i]
	i  = i-1
  A[i+1] = key
~~~

### Analysing algos 
Use ram : execute one instruction by one


Summary
![[Pasted image 20240221112010.png]]
## Lecture 2 

### The growth of functions


```functionplot
---
title: Growth of funtion
xLabel: 
yLabel: 
bounds: [0,150,0,60000]
disableZoom: true
grid: true
---
f(x) = 2x^2
g(x)  = 1000log(x)
h(x) = 2^x
```
R : $1000\log (x)$ 
G : $2^x$
B : $2x^2$ 
### Proving Algorithms Correct 
Loop invariant : At the start of each iteration of the outer for loop, the subarray A[1,...,j-1]
- Initialization: It is true prior to the first iteration of the loop.
- Maintenance: If it is true before an iteration of the loop, it remains true before the next iteration.
- Termination: When the loop terminates, the invariant — usually along with the reason that the loop terminated — gives us a useful property that helps show that the algorithm is correct

### Sorting by divide and conquer : Merge sorting

```python
MergeSort(A,p,r):
if(p<r)
	q = floor((p+r)/2)
	MergeSort(A,p,q)
	MergeSort(A,q+1,r)
	Merge(A,p,q,r)
```
What does merge() ? 
Takes Array A and $p \leq q < r$ such that $A[p...q]$ and $A[q+1...r]$ Are sorted, as input and outputs a sigle sorted array $A[p...r]$ 
We'll see how to do this in $\Theta$ (n) with $n = r-p+1$  
```python
Merge(A,p,q,r)
n1=q-p+1
n2=r-q
L[1...n1+1], R[1...n2+1]
for i=1 to n1
	L[i]=A[p+i-1]
for j=1 to n2
	R[j]=A[q+j]
L[n1+1]= inf
R[n2+1]= inf
i=1
j=1
for k=p to r
	if L[i] <= R[j]
		A[k]=L[i]
		i=i+1
	else A[k]=R[j]
	j=j+1
```
 
