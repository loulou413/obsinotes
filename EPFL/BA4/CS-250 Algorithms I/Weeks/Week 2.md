---
Week: 2
Themes: 
Lecture1: true
Lecture2: true
Exercises: false
---

  

## Notes

  

#### Lecture 1

  

#### Lecture 2

|           | worst case running time | in time |
| --------- | ----------------------- | ------- |
| Insertion | $\Theta(n^2)$           | YES     |
| Merge     | $\Theta(nlogn)$         | NO      |

Use a recurrence equation to describe the running time:
- Let T(n) = “running time on a problem of size n” 
-  If n is small enough say $n \leq c$  for some constant c then T(n) = (1) (by brute force) 
- Otherwise, suppose we divide into a sub problems each of size n/b. 
- Let D(n) be the time to divide and let C(n) the time to combine solutions. 
- We get the recurrence 

$T(n) = \begin{cases}  \Theta (1) \; \text{if} \;  n \leq c  \\ aT(\frac{n}{b})+D(n)+C(n) \; otherwise \end{cases}$

Recursive trees : Exemple 
$T(1)= c$ and $T(n) = 2T\left(\frac{n}{2}\right) + cn$ 
![[Pasted image 20240301111254.png]]
$T(n) = cn \log_{2(n)}= \Theta(n\log n)$ 

**Theorem (Master Theorem)** :
$T(n) = aT(\frac{n}{b}) + f (n)$ 
If $f(n) =  O(nlogb^{a-\epsilon})$ for some constant $\epsilon > 0$ , then $T(n) = (n^ {\log_ba})$  
If $f(n) =  O(nlogb^a)$  then $T(n) = (n^ {\log_{ba}}\log n)$
If $f(n) =  O(nlogb^{a+\epsilon})$ for some constant $\epsilon > 0$ and if $a f\left(\frac{n}{b}\right) \leq f(n)$ for some constant $c < 1$ and large n  , then $T(n) = \Theta(f(n))$ 


### Maximum subarray problem 
Input : An array $A[1\dots n]$ 
Output : indices i and j such that $A[i \dots j]$ has the biggest sum 
