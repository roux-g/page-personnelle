---
title: Autour de l'exponentielle complexe
prérequis: Complexes
---
Tout cours sur les nombres complexes qui se respecte vous dira que, étant donné un réel $\theta$, on définit $e^{i\theta}$ de la manière suivante :
$$
e^{i\theta} = \cos(\theta) + i\sin(\theta)
$$
Cependant, au moment de poser cette emblématique définition, on omet souvent de répondre à cette simple question :
<p style="text-align: center; font-weight: bold;">
... Pourquoi ?
</p>
Au-delà l'imparable - et extrêmement frustrant - "parce que ça nous arrange bien", il existe en réalité de très bonnes raisons de choisir cette définition plutôt qu'une autre. De bonnes raisons qui mettent en jeu certaines propriétés fondamentales de l'exponentielle, et sont l'occasion d'explorer différentes facettes de cette fonction si particulière.

Ci-dessous, on présente trois justifications possibles : une géométrique, une analytique, et une algébrique. Une fois la définition de $e^{i\theta}$ copieusement justifiée, on en profite ensuite pour définir $e^z$ pour tout $z\in \mathbb{C}$ et aborder quelques propriétés de cette exponentielle complexe.



## 3 bonnes raisons
### Via un peu de géométrie

Il s'agit là peut-être de l'approche la plus élégante, et en tout cas certainement la plus rapide. Imaginons que la quantité $e^{i\theta}$ fasse sens, quel que soit $\theta\in \mathbb{R}$, et vérifie des propriétés similaires à celles de l'exponentielle réelle (ce serait quand même la moindre des choses ... on est en train de chercher à étendre l'exponentielle réelle à un nouveau type de nombres, mais on ne va quand même pas faire cette extension n'importe comment !).\
On cherche à déterminer à quel point du plan complexe correspond cet hypothétique $e^{i\theta}$.

L'idée est alors la suivante : au lieu de chercher directement à localiser le point du plan complexe associé à $e^{i\theta}$, on a va à la place étudier un *chemin* menant à ce point. Plus précisément, on va poser la fonction suivante :
$$
\forall t\in [0,\theta], \quad f(t)=e^{it}
$$
(si $\theta<0$, on remplace $[0,\theta]$ par $[\theta, 0]$)

Quand $t$ varie de 0 à $\theta$, $f(t)$ trace un chemin dans le plan complexe, allant de $f(0)=1$ (dont on connait bien la position !) à $f(\theta)= e^{i\theta}$. Si l'on comprend la forme de ce chemin, on saura alors où il arrive, et donc où placer $e^{i\theta}$.

Avantage de raisonner sur une fonction plutôt que juste sur un point : on peut la dériver ! (ce qui n'est pas sans rappeler [[somme-alt#^648def|une astuce similaire vue dans une autre démonstration]] ...)\
Toujours en supposant que $e^{it}$ existe bien pout tout $t\in \mathbb{R}$, et vérifie des propriétés similaires à l'exponentielle réelle, y compris en matière de dérivation, il faudrait alors avoir :
$$
\forall t\in [0,\theta], \quad f'(t)=ie^{it}=if(t)
$$
Or, multiplier par $i$, cela a pour effet d'effectuer une rotation de $\frac{\pi}{2}$ dans le plan complexe. Cela signifie que, en tout point du chemin décrit par $f$, la vitesse de déplacement est orthogonale à la position. Cela est caractéristique d'un cercle !

<!--
<img src="expo_complexe.png" style="display: block; margin-left: auto; margin-right: auto; max-width: 400px;">
-->

![[expo_complexe.png | center]]

Quand $t$ varie de $0$ à $\theta$, $f(t)$ parcourt donc le cercle de centre 0 et de rayon 1 - notre bon vieux cercle trigonométrique. On peut même être encore plus précis : puisque $f(t)$ appartient au cercle trigonométrique pour tout t, on a
$$
\forall t\in [0,\theta], \quad |f'(t)|= |if(t)| = |f(t)| = 1
$$
On est donc en train de parcourir ce cercle à une vitesse constante égale à 1. Par conséquent, au bout d'un temps $\theta$, on a parcouru une distance de $\theta$ sur le cercle trigonométrique : par définition des radians, on est donc arrivé au point du cercle associé à l'angle $\theta$. Ainsi, l'extrémité de notre chemin, $e^{i\theta}$, est le point du cercle trigonométrique associé à l'angle $\theta$, en d'autres termes :
$$
e^{i\theta} = \cos(\theta) + i\sin(\theta).
$$

Cette idée est joliment animée dans une [courte vidéo de 3Blue1Brown](https://www.youtube.com/watch?v=v0YEaeIClKY).

### Via un peu d'analyse

Si vous trouvez l'approche précédente peu rigoureuse, voici une autre approche plus technique mais plus précise.

Il existe une autre façon de définir l'exponentielle, moins couramment utilisée, consistant à la définir comme la limite suivante :

> [!thm] Proposition
> $$
> \forall x\in \mathbb{R}, \quad e^x = \lim_{ n \to \infty } \left( 1+ \dfrac{x}{n} \right)^n.
> $$

> [!dem]- Démonstration
> C'est évident pour $x=0$. Pour $x\neq 0$, on passe sous forme exponentielle :
> $$
> \left( 1+ \dfrac{x}{n} \right)^n = e^{n \ln\left( 1+ \frac{x}{n} \right)} = e^{x  \frac{\ln\left( 1+ \frac{x}{n} \right)}{\frac{x}{n}}}
> $$
> et en utilisant la limite usuelle $\dfrac{\ln(1+u)}{u} \underset{u\to 0}{\longrightarrow} 1$ et la continuité de l'exponentielle, on obtient le résultat souhaité.

Dès lors, il parait naturel de chercher à définir $e^{i\theta}$ de façon analogue, en posant par définition :
$$
e^{i\theta} = \lim_{ n \to \infty } \left( 1+ i\dfrac{\theta}{n} \right)^n.
$$
Pour comprendre ce que vaut $e^{i\theta}$ avec une telle définition, il faut donc déterminer la limite de la suite de nombres complexes $u_n = \left( 1+ i\dfrac{\theta}{n} \right)^n$. Si $\theta=0$, c'est facile (la suite est constante égale à 1 ... donc tend vers 1). En revanche, si $\theta\neq 0$, trouver cette limite n'est *a priori* pas évident ! Heureusement, on peut décomposer le problème en deux problèmes plus simples : on va étudier séparément le module $|u_n|$ et un argument $\arg(u_n)$ de cette suite.

Pour cela, commençons par constater que, par calcul ou par lecture graphique sur le dessin ci-dessous, on a :
- $\left| 1+ i\dfrac{\theta}{n} \right| = \sqrt{ 1+ \dfrac{\theta^{2}}{n^{2}}}$
- $\arg\left( 1+ i\dfrac{\theta}{n} \right) = \arctan\left( \dfrac{\theta}{n} \right)$.

<!--
<img src="expo_complexe_polaire.png" style="display: block; margin-left: auto; margin-right: auto; max-width: 400px;">
-->

![[expo_complexe_polaire.png | center]]

#### Étude du module

En passant sous forme exponentielle :
$$
\left|\left( 1+ i\dfrac{\theta}{n} \right)^n\right| = \left| 1+ i\dfrac{\theta}{n} \right|^n = \left(\sqrt{ 1+ \dfrac{\theta^{2}}{n^{2}}} \right)^n = e^{n \ln \sqrt{ 1+ \frac{\theta^{2}}{n^{2}}}}
$$
On peut alors faire apparaître la limite usuelle $\dfrac{\ln(1+u)}{u} \underset{u\to 0}{\longrightarrow} 1$ :
$$
e^{n \ln \sqrt{ 1+ \frac{\theta^{2}}{n^{2}}}} = e^{ \frac{1}{2} n \ln \left( 1+ \frac{\theta^{2}}{n^{2}}\right) } = e^{ \frac{\theta^{2}}{2n} \times \frac{\ln \left( 1+ \frac{\theta^{2}}{n^{2}}\right)}{\frac{\theta^{2}}{n^{2}}} } \ \underset{n\to +\infty}{\longrightarrow} \ e^{0\times 1} =1.
$$
#### Étude d'un argument

Puisque $\arctan\left( \dfrac{\theta}{n} \right)$ est un argument de $1+ i\dfrac{\theta}{n}$, on en déduit que $n\arctan\left( \dfrac{\theta}{n} \right)$ est un argument de $\left( 1+ i\dfrac{\theta}{n} \right)^n$. Or, en utilisant la limite usuelle $\dfrac{\arctan(u)}{u} \underset{u\to 0}{\longrightarrow} 1$, on a :
$$
n\arctan\left( \dfrac{\theta}{n} \right) = \theta \times \dfrac{\arctan\left( \frac{\theta}{n} \right)}{\frac{\theta}{n}} \ \underset{n\to +\infty}{\longrightarrow} \ \theta.
$$

#### Conclusion

Ainsi on a montré que $|u_n| \ \underset{n\to +\infty}{\longrightarrow} \ 1$  et que $\arg(u_n) \ \underset{n\to +\infty}{\longrightarrow} \ \theta$. La suite $(u_n)$ converge donc vers le complexe de module 1 et d'argument $\theta$ ... qui n'est autre que $\cos(\theta) + i\sin(\theta)$ !

Avec cette définition, on retrouve ainsi bien le fait que la "bonne" façon de définir $e^{i\theta}$ - ou en tout cas, la façon la plus compatible avec cette définition particulière de l'exponentielle - consiste à poser que $e^{i\theta} = \cos(\theta) + i\sin(\theta)$.

### Via un peu d'algèbre

Une troisième façon de procéder consiste à plonger plus profondément dans les propriétés algébriques de $\mathbb{R}$ et de $\mathbb{C}$, et à prendre du recul sur une propriété clé de l'exponentielle : le fait qu'elle transforme les sommes en produits ($e^{x+y}=e^x e^y$).

Pour en savoir plus, je vous renvoie à la magnifique [vidéo de 3Blue1Brown](https://www.youtube.com/watch?v=mvmuCPvRoWQ) à ce sujet.

## Vers l'exponentielle complexe

A présent que l'on a donné du sens à $e^{i\theta}$ pour $\theta\in \mathbb{R}$, se pose une autre inévitable question : peut-on faire de même pour $e^z$ quel que soit $z\in \mathbb{C}$, et ainsi créer une fonction exponentielle allant de $\mathbb{C}$ dans $\mathbb{C}$, ayant des propriétés similaires à l'exponentielle réelle ?

La réponse est oui ; en fait, on a déjà fait le plus dur du travail ! En effet, étant donné $z=a+ib$, la seule façon "naturelle" de définir $e^z$, pour respecter le fait qu'elle transforme les sommes en produits, est de poser :
$$
e^z = e^a e^{ib}
$$
où $e^a$ est l'exponentielle d'un réel, donc bien définie, et $e^{ib}$ vaut $\cos(b)+i\sin(b)$.

En d'autres termes, on définit l'exponentielle complexe par :

> [!def] Définition
> $$
> \forall a,b\in \mathbb{R}, \quad e^{a+ib} = e^a ( \cos b + i \sin b ).
> $$

On a ainsi défini une fonction $\exp : \mathbb{C} \to \mathbb{C}$ qui étend l'exponentielle réelle $\exp : \mathbb{R} \to \mathbb{R}$ (par là, on entend que ces deux fonctions coïncident sur les réels - ce qui justifier de les appeler et de les noter de la même façon, d'ailleurs).

#### Visualisation de l'effet de l'exponentielle complexe

Pour comprendre l'effet de l'exponentielle complexe sur le plan complexe, il est très utile de remarque que $e^a e^{ib}$ est en fait écrit sous forme exponentielle : il s'agit du nombre de module $e^a$ et d'argument $b$. Par conséquent :
- Si $a$ est constant et $b$ varie, $e^a e^{ib}$ décrit le cercle de centre 0 et de rayon $e^a$. L'exponentielle complexe envoie donc les droites verticales ($a=\text{constante}$) sur des cercles concentriques centrés en 0.
- Si $b$ est constant et $a$ varie, $e^a e^{ib}$ décrit une demi-droite partant de 0 et formée de tous les points d'argument $b$. L'exponentielle complexe envoie donc les droites horizontales ($b=\text{constante}$) sur les demi-droites partant de l'origine du plan.

Cet effet est superbement animé à la [fin de cette vidéo de 3Blue1Brown](https://youtu.be/mvmuCPvRoWQ?t=1428) :

<div class="video-container">
<iframe width="560" height="315" src="https://www.youtube.com/embed/mvmuCPvRoWQ?si=TKEV6J_JHbUBN4ik&amp;start=1428" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>