---
Week: 7
Themes: 
Lecture1: true
Lecture2: true
Exercises: false
---

  

## Notes

  

## Lecture 1
A graph G = (V,E) is a set of vertex V, an edge set containing pairs of vertices.
direct or undirect : with arrows or not 
Array of adjacency : ![[Pasted image 20240410175827.png|500]]
or with directed graphs : ![[Pasted image 20240410175908.png|500]]
adjacency matrix : a $\textbar V \textbar \times \textbar V \textbar$  where $a_{ij} = 1 \; if \;(i,j) \in E$
![[Pasted image 20240410181026.png|500]]
![[Pasted image 20240410181056.png|500]]

### TRAVERSING/SEARCHING A graph
Breadth-First Search :
input : Graph G = (V,E) and source vertex $s \in C$
output : v.d = distance from s to v, for all $v \in V$ 
|Send a wave out from s 
|First hits all vertices 1 edge from s 
|From there, hits all vertices 2 edges from s 
![[Pasted image 20240410181740.png|200]]
$O(V+E)$ 

Depth-First Search
INPUT: Graph $G = (V, E)$, either directed or undirected
OUTPUT: 2 timestamps on each vertex: v.d = discovery time and v.f = finishing time


  

#### Lecture 2

