---
Week: 1
Themes:
  - Intro
Lecture1: true
Coding exercices: true
Exercises: true
---

## Notes

  

# Lecture 1

forewords : prepare yourself to coding interview : [![[Get Prepped for Tech PPT Deck 9-29-22_withTechExample.pdf]]
https://github.com/Avinash987/Coding/blob/master/Cracking-the-Coding-Interview-6th-Edition-189-Programming-Questions-and-Solutions.pdf
https://github.com/Mcdonoughd/CS2223/blob/master/Books/Algorithhms%204th%20Edition%20by%20Robert%20Sedgewick%2C%20Kevin%20Wayne.pdf
https://sd.blackball.lv/library/Introduction_to_Algorithms_Third_Edition_(2009).pdf
## What is Machine learning ? 
It is great
## What data  ?
Anything
data set is a set of data sample
## What insight ? 
Precise, concrete prediction. E.g., the category depicted by an image. Can also be a better understanding of the dataset. 
We'll see :
1. Regression : Predict continuous values for a given sample  -> order 
2. Classification :  Predict one discrete label for a given sample -> no order
## 2 types of data 
unsupervised :  only an observation 
supervised : + additional annotation
## Implies 2 types of algo 
Supervised learning : w/ sup data -> 
 Stage 1 : use true labels to optimize model parameter
 Stage 2 : Testing : predict the output for a new data sample which is completely different from the practice stage 
Unsupervised learning : w/ unsup dat a -> analyze the whole data, transform it for analysis
Reinforcement learning (not covered in this class)

# The linear model 
We denote $i^{th}$ the data sample (input) in the collection $N$  of samples as $x_i \in \mathbb{R}^D$ a column of dim $D$  same for $y_i$ a value or column vector of dim $C$
Exemple : predict weight from height of a fish 

![[Pasted image 20240220094854.png]]
we then can find the weight of a fish if his length follows this model

## 1D Linear regression : training 
• In essence, fitting a line consists of finding the best line parameters $w^{(0)^*}$ and $w^{(1)^*}$ for some given data
we can use Euclidian distance : $\sqrt{(\hat{y}_i-y_i)^2}$  or the square distance $(\hat{y}_i-y_i)^2$ and find the min for the sum over all $i$ 





 









# Lecture 2





