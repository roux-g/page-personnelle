
On appelle *cardinal* d'un ensemble le nombre d'éléments de cet ensemble. Bien que ce concept se comprenne très bien à un niveau intuitif, la définition rigoureuse de ce que l'on entend par "nombre d'éléments" est cependant (bien) plus délicate à appréhender.

Au cœur de la notion de cardinal se cache en effet la notion de **bijection** : dire qu'un ensemble $A$ possède $n$ éléments, c'est dire que l'on peut "numéroter ses éléments de 1 à n". Formellement, cela revient à créer une fonction bijective qui à chaque élément de $A$ associe un des entiers de $\llbracket 1, n \rrbracket$.

> [!def] Définition
> - On dit qu'un ensemble $A$ est de *cardinal* $n\in \mathbb{N}^\ast$ s'il existe une bijection entre $A$ et $\llbracket 1, n \rrbracket$. On le note ainsi : $Card(A)=n$.
> - On convient que l'ensemble vide est de cardinal 0.
> - On dit qu'un ensemble $A$ est *fini* s'il $A$ est de cardinal $n$ pour un certain $n \in \mathbb{N}$.
> - Dans le cas contraire, on dit que $A$ est *infini*.

Notons au passage que, puisqu'une bijection entre deux ensembles finis $A$ et $B$ met en correspondance 2 à 2 les éléments de $A$ avec les éléments de $B$, alors l'existence d'une bijection entre $A$ et $B$ contraint ces deux ensembles à avoir le même nombre d'éléments  (ce n'est en réalité pas si évident à démontrer : il faudrait commencer par établir que si $m\neq n$, alors il n'existe aucune bijection entre $\llbracket 1, n \rrbracket$ et $\llbracket 1, m \rrbracket$. Mais ) La réciproque est d'ailleurs également vraie, et ainsi :

> [!thm] Proposition
> Soient $A$ et $B$ deux ensembles finis. Alors $Card(A)=Card(B)$ si et seulement si il existe une bijection entre $A$ et $B$.

C'est là que les choses intéressantes commencent : rien n'empêche en effet de parler de bijections entre ensembles infinis ... Et donc de comparer les "tailles" de deux ensembles infinis !

> [!def] Définition
> Soient $A$ et $B$ deux ensembles (éventuellement infinis).
> On dit que $A$ et $B$ ont *même cardinal* s'il existe une bijection entre $A$ et $B$.

**Deux exemples**
- Avec cette définition, $\mathbb{N}$ et $\mathbb{Z}$ ont même cardinal ! En effet, on peut mettre les éléments de $\mathbb{N}$ en correspondance 2 à 2 avec ceux de $\mathbb{Z}$ de la manière suivante :
$$
\begin{array}{ccr}
0 & \mapsto & 0 \\
1 & \mapsto & 1 \\
2 & \mapsto & -1 \\
3 & \mapsto & 2 \\
4 & \mapsto & -2 \\
5 & \mapsto & 3 \\
6 & \mapsto & -3 \\
\vdots & & \vdots
\end{array}
$$
- $\mathbb{R}$ et $\left] -\frac{\pi}{2}, \frac{\pi}{2}\right[$ ont eux aussi le même cardinal : en effet, la fonction
$$
f : \left|\begin{array}{ccc}
\left] -\frac{\pi}{2}, \frac{\pi}{2}\right[ & \to & \mathbb{R}\\
x & \mapsto & \tan(x)
\end{array}\right.
$$
réalise une bijection entre ces deux ensembles.

Dans ces deux exemples, on observe un phénomène intrigant : on a construit à chaque fois une bijection entre un ensemble ($\mathbb{Z}$, $\mathbb{R}$) et une partie de lui-même ($\mathbb{N}$, $\left] -\frac{\pi}{2}, \frac{\pi}{2}\right[$). Il se trouve que cela reflète en réalité une propriété plus générale : un ensemble est infini si et seulement on peut le mettre en bijection avec une partie stricte de lui-même.

> [!thm] Théorème (caractérisation des cardinaux infinis)
> Soit $A$ un ensemble. Alors $A$ est infini si et seulement il existe une partie $B\subset A$, avec $B\neq A$, telle que $A$ est en bijection avec $B$.

> [!dem]-
> Procédons par double implication.

> [!exo]
> Test

> [!rem]
> test



Liens :
- Une vidéo de [ScienceEtonnante](https://www.youtube.com/watch?v=1YrbUBSo4Os)
- Une vidéo de la série [Voyage au pays des maths](https://www.youtube.com/watch?v=o79bss3Hc60)
- Une vidéo d'[El Jj](https://www.youtube.com/watch?v=N_cDA6tF-40)


