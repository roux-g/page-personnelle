---
ordre: 20
prérequis: Intégration
title: La série harmonique alternée
---
On appelle *série harmonique alternée* :
$$
1-\dfrac{1}{2}+\dfrac{1}{3}-\dfrac{1}{4}+\ldots
$$
Cette série est convergente, de somme égale à $\ln(2)$ :
$$
1-\dfrac{1}{2}+\dfrac{1}{3}-\dfrac{1}{4}+\ldots = \ln(2), \qquad \text{i.e.} \qquad \sum_{k=1}^{+\infty} \dfrac{(-1)^{k-1}}{k} = \ln(2).
$$
On formalise ce concept de somme infinie à l'aide de la notion de limite ; la formule précédente signifie ainsi, par définition, que :

> [!thm] Théorème
> $$
> \sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k} \underset{n\to +\infty}{\longrightarrow} \ln(2).
> $$

^648def

## Démonstration

On va procéder en deux grandes étapes.

### Étude de la fonction génératrice associée

Il est parfois utile, en maths, de réaliser que le problème que l'on étudie n'est en fait qu'un cas particulier d'un problème certes plus général, mais plus facile à étudier. Ici, par exemple, au lieu de s'intéresser seulement à la somme mentionnée dans le théorème ci-dessus, on va élargir nos ambitions et considérer plutôt la *fonction* $f_n$ définie par :
$$
f_n(x)=\sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k}x^k.
$$
La somme qui nous intéresse n'est alors autre que $\displaystyle f_n(1)=\sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k}$.

Mais quel est l'intérêt de complexifier ainsi le problème en introduisant une fonction ? Eh bien, cela permet d'enrichir l'éventail des outils à notre disposition : parler de fonctions, cela débloque toute la puissance de l'Analyse ! On peut faire avec la fonction $f_n$ certaines opérations que l'on ne pouvait faire avec la série initiale, typiquement la dériver ou l'intégrer pour obtenir des informations sur elle.

Cela va nous permettre d'établir que :

> [!thm] Lemme
>  $$
> \sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k} = \ln(2) -  \int_{0}^1 \dfrac{(-x)^n}{1+x} \, dx.
> $$

Petite indication pour le lecteur intrépide qui voudrait tenter de démontrer ce lemme par lui-même avant de lire la suite : commencer par déterminer une expression simple pour $f_n'(x)$.

> [!dem]- Démonstration
> La dérivée de $f_n$ se trouve être particulièrement agréable :
> $$
> f_n'(x) = \sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k}kx^{k-1} = \sum_{k=1}^n  (-x)^{k-1} = \sum_{k=0}^{n-1}  (-x)^{k}
> $$
> On reconnaît une somme de termes d'une suite géométrique de raison $-x$, ce qui permet d'écrire, si $x\neq -1$ :
> $$
> f_n'(x)=\dfrac{1-(-x)^n}{1-(-x)} = \dfrac{1}{1+x}-\dfrac{(-x)^n}{1+x}.
> $$
> Pour récupérer la somme qui nous intéresse, $f_n(1)$, il reste à intégrer cette égalité !
> $$
> \begin{align*}
>  \int_{0}^1 f_n'(x) \, dx &= \int_{0}^1 \dfrac{1}{1+x} \, dx - \int_0^1 \dfrac{(-x)^n}{1+x} \, dx \\[10pt]
> \text{i.e.  } \  f_n(1) - f_n(0) &= \big[ \ln(1+x) \big]_0^1  -  \int_{0}^1 \dfrac{(-x)^n}{1+x} \, dx.\\[10pt]
> \text{i.e.  }  \sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k} &= \ln(2) -  \int_{0}^1 \dfrac{(-x)^n}{1+x} \, dx.
> \end{align*}
> $$


### Étude d'une intégrale

Vu le lemme établi plus haut, pour établir le théorème souhaité, il reste à prouver que :
$$
\int_{0}^1 \dfrac{(-x)^n}{1+x} \, dx \ \underset{n\to +\infty}{\longrightarrow} \ 0.
$$
> [!dem]- Démonstration
> On peut vérifier cela par un rapide encadrement, en majorant cette intégrale en valeur absolue par une quantité tendant vers 0 :
> $$
> \begin{align*}
> \left| \int_0^1 \dfrac{(-x)^n}{1+x} \, dx \right | &\leq \int_0^1 \left|\dfrac{(-x)^n}{1+x}\right| \, dx  \quad \text{par inégalité triangulaire} \\
> &= \int_0^1 \dfrac{|-x|^n}{1+x} \, dx \\
> & = \int_0^1 \dfrac{x^n}{1+x} \, dx \\
> & \leq \int_0^1 x^n \, dx \quad \text{car pour }x\in [0,1], \  1+x\geq 1 \text{ donc }\dfrac{x^n}{1+x} \leq x^n  \\
> &= \left[  \frac{x^{n+1}}{n+1}  \right]_0^1 = \frac{1}{n+1}.
> \end{align*}
> $$
> Puisque $\frac{1}{n+1}\ \underset{n\to +\infty}{\longrightarrow} \ 0$, on en déduit par encadrement que l'intégrale encadrée tend vers 0 également.

Et ainsi, en combinant cela avec le lemme prouvé plus haut, on a démontré que :
$$
\sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k} = \ln(2) -  \int_{0}^1 \dfrac{(-x)^n}{1+x} \, dx. \ \underset{n\to +\infty}{\longrightarrow} \  \ln(2)
$$
CQFD !
## Et si l'on changeait l'ordre des termes ?

La somme que l'on vient d'étudier est d'un genre assez particulier : si elle tend vers une valeur finie, c'est parce que les termes positifs et les négatifs se "compensent les uns les autres". Sans cette alternance des signes, elle tendrait en fait vers $+\infty$ :
$$
1+\frac{1}{2}+\frac{1}{3}+\frac{1}{4}+\ldots = +\infty.
$$
On parle de *semi-convergence*. Ce genre de somme présente une propriété remarquable : en réordonnant ses termes, on peut la faire converger vers *n'importe quelle valeur* !

> [!thm] Théorème de réarrangement de Riemann
> Soit $(u_n)_{n\in \mathbb{N}}$ une suite de réels telle que :
> $$
> \sum_{k=0}^{n} u_{k} \ \underset{n\to +\infty}{\longrightarrow} \ \ell \quad \text{et} \quad \sum_{k=0}^{n} |u_{k}| \ \underset{n\to +\infty}{\longrightarrow} \  +\infty.
> $$
> Alors, pour tout $m\in \mathbb{R}$, il existe une bijection $\sigma : \mathbb{N} \to \mathbb{N}$ telle que
>  $$
> \sum_{k=0}^{n} u_{\sigma(k)} \ \underset{n\to +\infty}{\longrightarrow} \ m.
> $$

> [!dem]- Idée de la démonstration
> Il s'agit de construire une bijection $\sigma$ qui convienne, c'est-à-dire de choisir dans quel ordre mettre les termes de $(u_n)$ pour que la somme de ceux-ci tende vers $m$.
> 
> Pour cela, on commence par choisir des termes positifs de $(u_n)$ (sans en omettre, en les prenant dans l'ordre dans lequel ils se présentent au sein de la suite). On les somme jusqu'à ce que leur somme dépasse $m$.
> 
> On ajoute ensuite des termes strictement négatifs de $(u_n)$ (toujours en suivant l'ordre dans lequel ils apparaissent dans la suite), jusqu'à ce que la somme redevienne inférieure à $m$.
> 
> On continue ainsi en répétant cette procédure : on ajoute les termes positifs suivants dans la suite jusqu'à ce que la somme dépasse à nouveau $m$, etc.
> Cela fait osciller la somme ainsi construite autour de $m$ ; mais comme les termes que l'on ajoute ont tendance à devenir de plus en plus petits, ces oscillations sont d'amplitude de plus en plus faible, de sorte que la somme en question converge vers $m$.

Exemple : prenons la série harmonique alternée étudiée plus haut, et réordonnons ses termes de façon à sommer deux fois plus vite les $\frac{1}{k}$ avec $k$ pair que les $\frac{1}{k}$ avec $k$ impair. On obtient alors une nouvelle série dont la somme n'est plus égale à $\ln(2)$, mais à $\dfrac{\ln(2)}{2}$ ! En effet :
$$
\begin{align*}
& \left(1-\frac{1}{2}-\frac{1}{4}\right)+\left(\frac{1}{3}-\frac{1}{6}-\frac{1}{8}\right)+\left(\frac{1}{5}-\frac{1}{10}-\frac{1}{12}\right)+\ldots+\left(\frac{1}{2 k-1}-\frac{1}{4 k-2}-\frac{1}{4 k}\right)+\ldots \\
& =\left(\frac{1}{2}-\frac{1}{4}\right)+\left(\frac{1}{6}-\frac{1}{8}\right)+\left(\frac{1}{10}-\frac{1}{12}\right)+\ldots+\left(\frac{1}{4 k-2}-\frac{1}{4 k}\right)+\ldots \\
& =\frac{1}{2}\left(1-\frac{1}{2}+\frac{1}{3}-\frac{1}{4}+\ldots\right)=\frac{\ln(2)}{2} .
\end{align*}
$$
