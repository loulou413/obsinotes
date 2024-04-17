---
Week: 1
Themes: 
Lecture1: true
Lecture2: true
Exercises: true
---

# Notes

## Analyse complexe :

### 0. Rappels et notations

L'ensemble des nombres complexes est :
$$ \mathbb{C} = \{z = x+iy \ | \ x,y \in \mathbb{R}\} \; , \; i^2 = -1 $$


Avec pour partie réelle et partie imaginaire : 
$$ \mathbb{R}e(z) = x, \quad \mathbb{I}m(z) = y $$


Le congugé complexe de z : 
$$\overline{z} = x - iy $$



La forme polaire de z : 
$$ z = x + iy = r[cos(\theta) + sin(\theta)] $$
Avec
$$ r = \sqrt{x^2 + y^2} $$
$$ \theta = arg(z) $$
$$
 arg(z) = \left\{
     \begin{array}{lr}
       arctan(\frac{y}{x}), & x > 0 \,, \, y \in \mathbb{R} \\
       \frac{\pi}{2}, &  x = 0\, , \, y > 0\\ 
       arctan(\frac{y}{x}) + \pi, & x < 0 \, , \, y \geq 0 \\
       arctan(\frac{y}{x}) - \pi, & x <0 \, , \, y < 0 \\
       -\frac{\pi}{2}, & x = 0 \, , \, y < 0
     \end{array}
\right.
$$


L'identité d'Euler : 
$$ e^{i\theta} = cos(\theta) + isin(\theta)$$
Avec, 
	$$ \lVert{e^{i\theta}} \rVert = 1 \, , \, arg(e^{i\theta}) = \theta$$ 
Forme exponentielle : 
$$ z = re^{i\theta} $$
Racine n-ème complexe :
$$z^{n}= w  = \lvert w \rvert \times e^{iarg(w) + 2 \pi i k }$$
$$ \implies z = \sqrt[n]{\lvert w \rvert}$$
###  1. Fonctions holomorphes 

une fonction complexe est notée : 
$$ f : \mathbb{C} \longmapsto \mathbb{C} $$
$$ z \longmapsto f(z) = f(x + iy) $$
ainsi : 
$$ f(x+iy) = u(x,y) + iv(x,y) = \mathbb{R}e(f(x+iy)) + i\,\mathbb{I}m(f(x+iy)) $$

$$avec\; u,v : \mathbb{R}^2 \mapsto \mathbb{R} $$
Soient $$ f : \mathbb{C} \mapsto \mathbb{C}$$ $$et \;  z_0 \in \mathbb{C} $$
La limite de $f(z)$ quand $z \rightarrow z_0$ est $L \in \mathbb{C}$ tq , $\forall \epsilon > 0 \; , \exists  \delta > 0$ tq si $\lvert z-z_0 \rvert < \delta$ alors :
$$\lvert f(z) - L \rvert < \epsilon$$ On note : 
$$L = \lim_{z \to z_0} f(z)$$
$f$ est continue en $z_0$ si : 
$$\lim_{z \to z_0} f(z) = f(z_0)$$
#### Def : fonction holomorphe
Soient $\Omega \subset \mathbb{C}$ un ensemble ouvert, $f : \Omega \mapsto \mathbb{C}$ et $z_0 \in \mathbb{C}$. 
$f$ est holomporhe en $z_0$ si la limite suivante existe :
$$\lim_{h \to 0}\frac{f(z_0 + h) - f(z_0)}{h}$$
Si elle existe, nous la notons $f'(z_0)$ 

De plus, nous disons que $f$ est holomorphe sur $\Omega$ si $f$ 






  

