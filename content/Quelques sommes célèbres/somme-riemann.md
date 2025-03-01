---
ordre: 40
title: Une première série de Riemann
---
Les *séries de Riemann* sont les séries de la forme
$$
\dfrac{1}{1^\alpha}+\dfrac{1}{2^\alpha}+\dfrac{1}{3^\alpha}+\dfrac{1}{4^\alpha}+\ldots
$$
où $\alpha$ est un nombre fixé. Leur étude ouvre des questions extrêmement profondes : cela fait des siècles que l'on connait précisément leur comportement pour certaines valeurs spécifiques de $\alpha$, mais en revanche la question des propriétés de ces objets pour un $\alpha$ quelconque est toujours un problème étudié de nos jours, en lien étroit avec des résultats sur la répartition des nombres premiers ainsi qu'avec une des conjectures les plus célèbres de l'histoire des Mathématiques, toujours indémontrée de nos jours : l'hypothèse de Riemann.

Ces sujets fascinants seront brièvement abordés [[#Généralisation : les séries de Riemann|en fin de page]], mais pour l'instant on va s'intéresser de plus près à certains des cas particuliers qui sont les mieux connus à ce jour. Il est en effet remarquable que, lorsque $\alpha$ est un nombre entier pair, on est capable d'exprimer exactement la valeur de cette somme infinie : par exemple,
$$
1+\dfrac{1}{4}+\dfrac{1}{9}+\dfrac{1}{16}+\ldots = \dfrac{\pi^2}{6}
$$

$$
1+\dfrac{1}{2^4}+\dfrac{1}{3^4}+\dfrac{1}{4^4}+\ldots = \dfrac{\pi^4}{90}
$$

$$
1+\dfrac{1}{2^6}+\dfrac{1}{3^6}+\dfrac{1}{4^6}+\ldots = \dfrac{\pi^6}{945}
$$

$$
1+\dfrac{1}{2^8}+\dfrac{1}{3^8}+\dfrac{1}{4^8}+\ldots = \dfrac{\pi^8}{9450}
$$
Et plus généralement, pour tout $p\in \mathbb{N}^\ast$, il existe un nombre rationnel $r_p$ (que l'on est capable de calculer !) tel que
$$
1+\dfrac{1}{2^{2p}}+\dfrac{1}{3^{2p}}+\dfrac{1}{4^{2p}}+\ldots = r_p \pi^{2p}.
$$
Fait amusant : lorsque $\alpha$ est un nombre entier impair, en revanche, on n'a toujours à ce jour aucune idée de la valeur prise par cette somme infinie. On sait seulement que lorsque $\alpha=3$, la valeur de cette somme infinie est un nombre irrationnel ! Ce résultat a été démontré par Roger Apéry en 1978, et ce mystérieux nombre irrationnel porte désormais son nom.

Sur cette page, on va se pencher tout particulièrement sur un des cas particuliers les plus célèbres : le cas $\alpha=2$. On va démontrer que :

$$
1+\dfrac{1}{4}+\dfrac{1}{9}+\dfrac{1}{16}+\ldots = \dfrac{\pi^2}{6}, \qquad \text{i.e.} \qquad \sum_{k=1}^{+\infty} \dfrac{1}{k^2} = \dfrac{\pi^2}{6}.
$$
On formalise ce concept de somme infinie à l'aide de la notion de limite ; la formule précédente signifie ainsi, par définition, que :

> [!thm] Théorème
> $$
> \sum_{k=1}^{n} \dfrac{1}{k^2} \underset{n\to +\infty}{\longrightarrow} \dfrac{\pi^2}{6}.
> $$

Ce (très joli) résultat porte le nom de *Problème de Bâle*, du nom de la ville natale de plusieurs des mathématiciens qui se sont penchés sur ce problème (Bernoulli, Euler). Il a longtemps résisté aux tentatives des plus éminents d'entre eux : initialement posé par Pietro Mengoli en 1644, ce n'est qu'un siècle plus tard, en 1741, que Leonhard Euler en donna finalement une preuve rigoureuse.

Le sujet ayant semble-t-il inspiré des générations de mathématiciens, d'autres démonstrations ont été proposées au fil des années, tant et si bien que de nos jours la liste des démonstrations possibles semble [s'étendre à n'en plus finir](https://en.wikipedia.org/wiki/Basel_problem). Ci-dessous, j'ai sélectionné certaines des preuves les plus accessibles.



## Une preuve géométrique

La chaîne YouTube 3Blue1Brown donne [cette très belle preuve](https://www.youtube.com/watch?v=d-o3eB9sfls) basée des raisonnements physiques et géométriques, et sur la propagation des rayons lumineux.

## Une preuve peu rigoureuse



## Une preuve plus élémentaire mais plus technique



La preuve consiste à étudier deux suites définies par des intégrales :
$$

A_{n}=\int_{0}^{\frac{\pi}{2}} \cos ^{2 n} x \ dx \quad \text { et } \quad B_{n}=\int_{0}^{\frac{\pi}{2}} x^{2} \cos ^{2 n} x \ dx.

$$

On commence par prouver quelques relations utiles, par intégration par parties :

> [!thm] Lemme
> Pour tout $n\geq 1$,
> $$
> \int_{0}^{\frac{\pi}{2}} \sin ^{2} x \cos ^{2(n-1)} x \ dx = \frac{A_n}{2n-1} = \frac{A_{n-1}}{2n} \qquad (\ast)
> $$
> $$
> \text{et} \qquad A_n = (2n-1)n B_{n-1} - 2n^2 B_n. \qquad (\ast \ast)
> $$

> [!dem]- Démonstration
> Pour la première relation, on part de $A_n$ en écrivant
> $$
> A_{n}=\int_{0}^{\frac{\pi}{2}} \cos x \cos ^{2 n - 1} x \ dx
> $$
> et on fait une intégration par parties en primitivant $\cos x$ et en dérivant $\cos ^{2 n - 1} x$. On obtient, après simplifications,
> $$
> A_n = (2n-1)\int_{0}^{\frac{\pi}{2}} \sin ^{2} x \cos ^{2(n-1)} x \ dx
> $$
> ce qui prouve déjà la première égalité ; de plus, en utilisant le fait que $\cos^2 x + \sin^2 x = 1$,
> $$
> \begin{align*}
> A_n &=  (2n-1)\int_{0}^{\frac{\pi}{2}} (1- \cos ^{2} x) \cos ^{2(n-1)} x \ dx \\
> &= (2n-1)\left( \int_{0}^{\frac{\pi}{2}} \cos ^{2(n-1)} x \ dx - \int_{0}^{\frac{\pi}{2}}  \cos ^{2n} x \ dx\right)\\
> &= (2n-1)(A_{n-1} - A_n).
> \end{align*}
> $$
> et de $A_n = (2n-1)(A_{n-1} - A_n)$ on tire le fait que $\frac{A_n}{2n-1} = \frac{A_{n-1}}{2n}$.
> 
> Pour la seconde relation, on part à nouveau de la forme originelle de $A_n$ et l'on fait cette fois une double intégration par parties ! On écrit
> $$
> A_{n}=\int_{0}^{\frac{\pi}{2}} 1\times \cos ^{2 n} x \ dx
> $$
> et l'on primitive deux fois le "1" (ce qui fait apparaître le facteur $x^2$ présent dans $B_n$ et qui manquait dans $A_n$), tout en dérivant deux fois le reste. Après quelques calculs et réarrangements en utilisant à nouveau le fait que $\cos^2 x + \sin^2 x = 1$, on finit par tomber sur la relation souhaitée.


On prend alors la relation $(**)$ et on la divise par $n^2 A_n$, ce qui donne :
$$
\dfrac{1}{n^2} = \dfrac{(2n-1)B_{n-1}}{nA_n} - \dfrac{2B_n}{A_n}
$$
ce qui se simplifie, au vu de la relation $(*)$, sous la forme :
$$
\frac{1}{n^2} = \dfrac{2B_{n-1}}{A_{n-1}} - \dfrac{2B_n}{A_n}
$$
Le temps est alors enfin arrivé de faire le lien avec notre problème initial :

> [!thm] Lemme
> $$
> \sum_{k=1}^n \dfrac{1}{k^2} = \dfrac{\pi^2}{6} - 2 \dfrac{B_n}{A_n}.
> $$

> [!dem]- Démonstration
> Par télescopage, en utilisant ce que l'on vient juste d'établir :
> $$
> \sum_{k=1}^n \dfrac{1}{k^2} = \sum_{k=1}^n \left(\frac{2 B_{k-1}}{A_{k-1}}-\frac{2 B_{k}}{A_{k}}\right) = \frac{2 B_{0}}{A_{0}}-\frac{2 B_{n}}{A_{n}} = \dfrac{\pi^2}{6} - 2 \dfrac{B_n}{A_n}.
> $$
> (En effet, par calcul direct, $A_0 = \dfrac{\pi}{2}$ et $B_0 = \left[ \dfrac{x^3}{3} \right]_0^{\frac{\pi}{2}} = \dfrac{\pi^3}{24}$)


Pour terminer la démonstration, il ne reste plus alors qu'à prouver que $\dfrac{B_n}{A_n} \underset{n\to +\infty}{\longrightarrow} 0$. Comme souvent quand on étudie des suites définies par des intégrales, on va pour cela chercher à raisonner par encadrement ... mais cet encadrement n'est ici pas facile à obtenir. En effet, pour encadrer $\dfrac{B_n}{A_n}$, il faudrait réussir à comparer $B_n$ à $A_n$.

Une façon de procéder est de faire appel à nouveau appel à la relation $(*)$, mais appliquée cette fois avec $n+1$ au lieu de $n$, de sorte à obtenir :
$$
\int_{0}^{\frac{\pi}{2}} \sin ^{2} x \cos ^{2n} x \ dx = \frac{A_{n+1}}{2n+1} = \frac{A_{n}}{2(n+1)}.
$$
On est ainsi ramenés à comparer les deux intégrales :
$$
A_{n}= 2(n+1)\int_{0}^{\frac{\pi}{2}} \sin ^{2} x \cos ^{2n} x \ dx \quad \text { et } \quad B_{n}=\int_{0}^{\frac{\pi}{2}} x^{2} \cos ^{2 n} x \ dx.
$$
Or, par concavité de la fonction sinus sur $\left[ 0, \dfrac{\pi}{2} \right]$,
$$
\forall x\in \left[ 0, \dfrac{\pi}{2} \right], \ \sin x \geq \dfrac{2x}{\pi}.
$$
![[sinus_corde.png |center]]

On en déduit que
$$
A_{n}= 2(n+1)\int_{0}^{\frac{\pi}{2}} \sin ^{2} x \cos ^{2n} x \ dx \geq  2(n+1)\int_{0}^{\frac{\pi}{2}} \frac{4x^2}{\pi^2} \cos ^{2n} x \ dx = \dfrac{8(n+1)}{\pi^2}B_n.
$$
Ainsi, on a montré que, pour tout $n\geq 1$,
$$
0 \leq \dfrac{B_n}{A_n} \leq \frac{\pi^2}{8(n+1)}
$$
ce qui entraîne par encadrement que $\dfrac{B_n}{A_n} \underset{n\to +\infty}{\longrightarrow} 0$, et donc finalement, d'après le lemme établi plus haut, que :
$$
\sum_{k=1}^n \dfrac{1}{k^2} = \dfrac{\pi^2}{6} - 2 \dfrac{B_n}{A_n}  \underset{n\to +\infty}{\longrightarrow} \dfrac{\pi^2}{6}.
$$
CQFD !

## Généralisation : les séries de Riemann

Les *séries de Riemann* sont les séries de la forme
$$
\frac{1}{1^\alpha} + \frac{1}{2^\alpha} + \frac{1}{3^\alpha} + \frac{1}{4^\alpha} + \ldots 
$$
Celle étudiée dans cette page correspond ainsi au cas $\alpha = 2$.

Il est donc naturel de se demander ce qu'il en est pour les autres valeurs. 