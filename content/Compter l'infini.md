## Prologue : l'hôtel de Hilbert

Dans les conférences qu'il donnait sur le sujet de l'infini au début du XXe siècle, David Hilbert aimait illustrer ses propos par une amusante - et un peu perturbante - expérience de pensée que la postérité a retenu sous le nom d'*hôtel de Hilbert*. En voici une présentation un peu romancée.

L'hôtel de l'infini est un hôtel un peu particulier : il possède une infinité de chambres, numérotées 1, 2, 3, et ainsi de suite jusqu'à l'infini. Une propriété bien pratique pour accueillir beaucoup de clients - et le moins que l'on puisse dire, c'est que les affaires marchent bien, car ce soir, l'hôtel de l'infini est complet. Absolument toutes ses chambres sont occupées. Le concierge de l'hôtel de l'infini, assis à son bureau, laisse échapper un soupir de satisfaction : enfin un peu de repos après avoir assigné leurs chambres à cette infinité de clients !

Hélas pour lui, son répit est de courte durée, car la porte d'entrée de l'hôtel s'ouvre soudain sur une arrivée imprévue : un voyageur, qui demande à être logé pour la nuit. Le concierge sent la panique le gagner ; l'hôtel de l'infini a la réputation d'avoir toujours des chambres disponibles, il serait impardonnable de ne pas lui en proposer une ! Mais les chambres sont déjà toutes attribuées ...

Heureusement, notre rusé concierge a une brillante idée. Il demande au client de la chambre n°1 de déménager dans la chambre n°2 ; à celui de la chambre n°2, de déménager dans la chambre n°3 ; et ainsi de suite jusqu'à l'infini, chaque client déménageant dans la chambre d'à côté. Les clients obtempèrent (non sans maugréer), et à la fin de l'opération, toutes les chambres sont à nouveau occupées ... sauf la n°1. Et le concierge de tendre, non sans une certaine fierté, la clé de la chambre n°1 au voyageur fraîchement arrivé.

L'histoire de l'hôtel de Hilbert possède plusieurs variantes, posant des [défis de plus en plus difficiles](https://en.wikipedia.org/wiki/Hilbert%27s_paradox_of_the_Grand_Hotel) au pauvre concierge qui en a la charge. Les vidéos suivantes les évoquent au moins en partie, avec d'autres considérations paradoxales autour de la notion d'infini :
- Une vidéo de [ScienceEtonnante](https://www.youtube.com/watch?v=1YrbUBSo4Os)
- Une vidéo de la série [Voyage au pays des maths](https://www.youtube.com/watch?v=o79bss3Hc60)
- Une vidéo d'[El Jj](https://www.youtube.com/watch?v=N_cDA6tF-40)

Cette histoire, loin d'être une simple anecdote amusante, touche en fait à un phénomène caractéristique des ensembles infinis, et la technique qu'elle illustre est une idée qui intervient dans de nombreuses preuves mathématiques. Dans la suite de cette page, on va présenter deux résultats dont la démonstration repose fondamentalement sur la belle idée de notre concierge :
- une [[Compter l'infini#^eb987a|caractérisation des ensembles infinis]] ;
- et le [[Compter l'infini#^16752a|théorème de Cantor-Bernstein]].

Cela sera aussi l'occasion de définir plus rigoureusement ce que l'on entend par "ensemble infini", et de voir que tous les ensembles infinis ne sont pas forcément de la même taille ...
## Premiers pas : cardinal d'un ensemble

On appelle *cardinal* d'un ensemble le nombre d'éléments de cet ensemble. Bien que ce concept se comprenne très bien à un niveau intuitif, la définition rigoureuse de ce que l'on entend par "nombre d'éléments" est cependant plus délicate à appréhender.

Au cœur de la notion de cardinal se cache en effet la notion de **bijection** : dire qu'un ensemble $A$ possède $n$ éléments, c'est dire que l'on peut "numéroter ses éléments de 1 à n". Formellement, cela revient à créer une fonction bijective qui à chaque élément de $A$ associe un des entiers de $\llbracket 1, n \rrbracket$.

> [!def] Définition
> - On dit qu'un ensemble $A$ est de *cardinal* $n\in \mathbb{N}^\ast$ s'il existe une bijection entre $A$ et $\llbracket 1, n \rrbracket$. On le note ainsi : $Card(A)=n$.
> - On convient que l'ensemble vide est de cardinal 0.
> - On dit qu'un ensemble $A$ est *fini* s'il $A$ est de cardinal $n$ pour un certain $n \in \mathbb{N}$.
> - Dans le cas contraire, on dit que $A$ est *infini*.

Notons au passage que, puisqu'une bijection entre deux ensembles finis $A$ et $B$ met en correspondance 2 à 2 les éléments de $A$ avec les éléments de $B$, alors l'existence d'une bijection entre $A$ et $B$ contraint ces deux ensembles à avoir le même nombre d'éléments  (ce n'est en réalité pas si évident à démontrer : il faudrait commencer par établir que si $m\neq n$, alors il n'existe aucune bijection entre $\llbracket 1, n \rrbracket$ et $\llbracket 1, m \rrbracket$. Même si c'est intuitif, en toute rigueur, il faudrait le prouver, typiquement par récurrence sur $m$ ...) La réciproque est d'ailleurs également vraie, et ainsi :

> [!thm] Proposition
> Soient $A$ et $B$ deux ensembles finis. Alors $Card(A)=Card(B)$ si et seulement si il existe une bijection entre $A$ et $B$.

## Vers l'infini (et au-delà ?)

C'est là que les choses intéressantes commencent : rien n'empêche en effet de parler de bijections entre ensembles infinis ... Et donc de comparer les "tailles" de deux ensembles infinis !

> [!def] Définition
> Soient $A$ et $B$ deux ensembles (éventuellement infinis).
> On dit que $A$ et $B$ ont *même cardinal* s'il existe une bijection entre $A$ et $B$.

^6f430a

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

> [!thm] Théorème (caractérisation des ensembles infinis)
> Soit $A$ un ensemble. Alors $A$ est infini si et seulement il existe une partie $B\subset A$, avec $B\neq A$, telle que $A$ est en bijection avec $B$.

^eb987a

> [!dem]- Démonstration
> Commençons par régler le principal problème : la définition donnée plus haut d'un ensemble infini n'est pas *du tout* pratique. Par définition, un ensemble est infini s'il n'est en bijection avec aucun $\llbracket 1, n \rrbracket$ pour $n\in \mathbb{N}$. Les propriétés "négatives" de ce genre sont rarement commodes à manipuler en maths ... On va donc donner une caractérisation "positive" plus facile à utiliser :
> > [!thm] Lemme
> > 
> > Un ensemble $A$ est infini si et seulement si on peut trouver dans $A$ une suite $x_{0}$, $x_1$, $x_2$, ... d'éléments deux à deux distincts.
> 
> > [!dem]- Démonstration
> > Procédons par double implication.
> > 
> > $(\Longrightarrow)$ Supposons que $A$ est infini. Alors :
> > - $A\neq \emptyset$ donc il existe $x_0 \in A$.
> > - $A \neq \{x_0\}$, car sinon $A$ serait en bijection avec $\{1\}$ et donc de cardinal 1. Par conséquent, il existe $x_1 \in A$ avec $x_1 \neq x_0$.
> > - $A \neq \{x_0, x_1\}$, car sinon $A$ serait en bijection avec $\{1, 2\}$ et donc de cardinal 2. Par conséquent, il existe $x_2 \in A$ avec $x_2 \neq x_0, x_1$.
> > - En continuant ainsi, on construit une suite d'éléments deux à deux distincts de $A$.
> > 
> > $(\Longleftarrow)$ Supposons qu'il existe une suite $(x_n)$ d'éléments deux à deux distincts de $A$. Montrons qu'alors $A$ est infini.  
> > Par l'absurde, supposons que $A$ est fini : $A$ étant non vide, il existe un certain $n\in \mathbb{N}^\ast$ tel que $A$ est en bijection avec $\llbracket 1, n \rrbracket$. Notons $f:A \to \llbracket 1, n \rrbracket$ cette bijection.  
> > Mais alors, puisque $x_0$, ..., $x_n$ sont des éléments deux à deux distincts de $A$, on obtient que $f(x_0)$, ..., $f(x_n)$ sont des éléments deux à deux distincts de $\llbracket 1, n \rrbracket$. On a donc trouvé $n+1$ éléments deux à deux distincts de $\llbracket 1, n \rrbracket$, ce qui est absurde. (Pour être 100% rigoureux, il faudrait même démontrer l'absurdité de cette dernière affirmation par récurrence ... mais la preuve étant déjà suffisamment longue comme cela, je laisse ce plaisir au lecteur de ces lignes.)
> 
> Munis de ce lemme fort pratique, on peut à présent attaquer la preuve principale, que l'on va également faire par double implication !
> 
> $(\Longrightarrow)$ Supposons que $A$ est infini. D'après le lemme, cela signifie qu'il existe une suite $(x_n)$ d'éléments deux à deux distincts de $A$.\
> On va alors suivre l'exemple de l'avisé concierge de l'hôtel de Hilbert, en "relogeant" chacun des $x_n$ à la place de $x_{n+1}$, de sorte à libérer la place occupée initialement par $x_0$ !\
> Pour formaliser cela, on définit $B = A\setminus \{x_0\}$ ; on construit ensuite une bijection de $A$ dans $B$ en "poussant" tous les éléments de la suite $(x_n)$ sur l'élément suivant, tout en ne touchant pas au reste de $A$ :
> $$
> \begin{array}{rcl}
> f : \ A & \to & B\\
> x_0 & \mapsto & x_{1}\\
> x_1 & \mapsto & x_{2}\\
> x_2 & \mapsto & x_{3}\\
> \vdots & & \vdots \\
> y & \mapsto & y \text{ si }y\notin \{x_0, x_1, x_2, \ldots\}.
> \end{array}
> $$
> On a ainsi construit une bijection entre $A$ et une partie $B$ de lui-même.
> 
> $(\Longleftarrow)$ Supposons qu'il existe une partie $B\subset A$, avec $B\neq A$, telle que $A$ est en bijection avec $B$. Notons $f:A\to B$ cette bijection.\
> Puisque $B\neq A$, il existe $x_0\in A\setminus B$. On va alors construire une suite $(x_n)$ en posant, pour tout $n\in \mathbb{N}$ :
> $$
> x_{n+1} = f(x_n).
> $$
> Notons que, puisque $f:A\to B$, on a $x_1 = f(x_0) \in B$, et en particulier $x_1 \neq x_0$. Puisque $f$ est injective, on en déduit que $f(x_1)\neq f(x_0)$, i.e. $x_2 \neq x_1$ ; et bien sûr $x_2 \neq x_0$ puisque $x_2 \in B$ et que $x_0 \notin B$. En répétant cela, on voit que les $x_n$ sont tous deux à deux distincts (on laisse le soin au lecteur motivé de le démontrer proprement par récurrence ...).
> Ainsi, on a construit une suite $(x_n)$ d'éléments deux à deux distincts de $A$ ; d'après le lemme, $A$ est donc infini !


## Quand un infini est plus petit qu'un autre

A l'aide du concept de bijection, on s'est donné un moyen de déterminer si un ensemble infini est de la "même taille" qu'un autre. Mais peut-on affiner les choses ? Peut-on comparer les ensembles infinis les uns aux autres, en d'autres termes, est-il possible de donner un sens au fait qu'un ensemble infini soit "plus petit" qu'un autre ?

Comme précédemment, on va commencer par s'appuyer sur ce que l'on connait (et comprend) bien : le cas des ensembles finis. Pour ces ensembles là, les choses sont plus simples, et l'on dispose du résultat classique et assez intuitif suivant.

> [!thm] Proposition
> Soient $A$ et $B$ deux ensembles finis.\
> S'il existe une injection $f:A\to B$, alors $Card(A)\leq Card(B)$.

On va en profiter pour refaire le même coup que dans la partie précédente, en extrapolant ce résultat pour en faire une définition pour les ensembles de toute taille, finis ou infinis :

> [!def] Définition
> Soient $A$ et $B$ deux ensembles (éventuellement infinis).\
> On dit que $A$ est de cardinal plus petit ou égal à celui de $B$ s'il existe une injection de $A$ dans $B$.

**Exemples**
- Toute inclusion $A\subset B$ d'un ensemble dans un autre peut aussi être vue comme une injection (à savoir, $f:A\to B$ qui à tout $x$ de $A$ associe ... eh bien, $x$). Par conséquent, avec cette définition, si $A\subset B$ alors le cardinal de $A$ est inférieur ou égal à celui de $B$ (encore heureux !!).
- Le cardinal de $[0,1[$ est inférieur ou égal à celui de $\mathbb{N}^\mathbb{N}$, l'ensemble des suites d'entiers.\
En effet, on peut considérer $f$ l'application qui à chaque réel de $[0,1[$ associe la suite de ses décimales (où l'on convient, pour éviter de toute ambiguïté, de ne jamais écrire une développement décimal finissant en "99999..." : par exemple, au nombre 0,35, on associera la suite 3, 5, 0, 0, 0, etc., et non la suite 3, 4, 9, 9, 9, 9, ...). Puisque la suite des décimales d'un réel de $[0,1[$ caractérise complètement ce réel, l'application $f$ ainsi définie est injective.


On s'est ainsi doté d'une définition permettant de comparer les cardinaux d'ensembles infinis. Notons au passage que cette définition est cohérente avec [[Compter l'infini#^6f430a|la définition donnée plus tôt pour l'égalité entre cardinaux]] : si l'on a simultanément $Card(A)\leq Card(B)$ et $Card(B)\leq Card(A)$, cela signifie qu'il existe une injection de $A$ dans $B$ et une injection de $B$ dans $A$, et donc que, euh ... un instant ...

Il y a un souci : on voudrait pouvoir en déduire qu'il existe une bijection entre $A$ et $B$, et donc que $Card(A)=Card(B)$  ; mais soudain cela ne semble pas si évident ...

On a en fait mis le doigt sur un point pas du tout trivial pour les ensembles infinis : le fait que l'existence d'une injection dans les deux sens implique l'existence d'une bijection. Il va falloir le démontrer si l'on veut que notre théorie tienne debout !

> [!thm] Théorème de Cantor-Bernstein
> Soient $A$ et $B$ deux ensembles.
> S'il existe une injection de $A$ dans $B$ et une injection de $B$ dans $A$, alors il existe une bijection de $A$ dans $B$.

^16752a

> [!dem]- Démonstration
> Notons $f:A\to B$ et $g:B\to A$ ces injections.  
> Pour rendre plus apparent l'argument clé au cœur de la preuve, on va procéder en deux temps, en commençant d'abord par réduire le problème à un problème plus simple.
> 
> **1ere étape : simplification du problème**  
> Posons $C=g(B)$. Alors les ensembles $B$ et $C$ sont en bijection l'un avec l'autre, via
> $$
> \begin{array}{rlc}
> B & \to & C=f(B)\\
> x & \mapsto & g(x)
> \end{array}
> $$
> (bien injective car $g$ l'est, et surjective par définition de $C$)  
> Par conséquent, puisqu'une composée de bijections est encore une bijection :
> $$
> \begin{array}{c}
> \text{Montrer qu'il existe une bijection entre $A$ et $B$,} \\
> \text{c'est équivalent à montrer qu'il existe une bijection entre $A$ et $C$.}  
> \end{array}
> $$
> **On s'est donc ramené à devoir montrer que $A$ est en bijection avec une certaine partie $C$ de lui-même** (ce qui n'est pas sans rappeler un certain [[Compter l'infini#^eb987a|théorème vu plus haut]] ...).  
> Reste à voir ce que deviennent nos hypothèses de départ avec ce changement de point de vue : en posant $h=g\circ f$, on obtient une fonction $h:A \to C$, qui est injective puisque $f$ et $g$ le sont. C'est tout ce dont on va avoir besoin pour conclure.
> 
> **2nde étape : construire la bijection**  
> Résumons les choses : on dispose de deux ensembles $A$ et $C$ tels que
> - $C \subset A$ ;
> - $h : A \to C$ est une injection.
> 
> Et l'on cherche à construire une bijection de $A$ dans $C$.\
> Pour cela, on va partir de $h$, qui a l'avantage d'être déjà injective, et l'utiliser pour "pousser" $A$ dans $C$. C'est le moment de réutiliser l'astuce de notre bon vieux concierge !
> - Le "nouveau client", c'est la partie de $A$ qui n'est pas encore dans $C$. Notons-la $A' = A\setminus C$. On "loge" cette partie dans $C$ en lui appliquant la fonction $h$, et elle se retrouve ainsi envoyée sur $h(A')\subset C$.
> - Problème : en faisant ainsi, on "dérange" les éléments de $h(A')$ qui étaient déjà là, bien à leur place dans $C$. Qu'à cela ne tienne : on les envoie plus loin, en leur appliquant à eux aussi la fonction $h$. Ils se retrouvent "logés" dans $h(h(A'))$.
> - Cela dérange alors les éléments de $h(h(A'))$, que l'on va eux aussi reloger en leur appliquant $h$, et ainsi de suite.
> 
> Dit de façon plus formelle : on définit une suite $(A_k)$ de parties de $A$ par $A_0=A\setminus C$ et $A_{k+1}=h(A_k)$. Grâce à l'injectivité de $h$, ces parties sont deux à deux disjointes (cela se montre par une récurrence rapide). On définit alors la fonction $\phi : A \to C$ ainsi :
> $$
> \phi(x) = 
> \left\{
> \begin{array}{cl}
> h(x) & \text{ si }x\text{ appartient à l'un des }A_k \\
> x & \text{ sinon.}
> \end{array}
> \right.
> $$
> Cette fonction envoie chaque $A_k$ sur $A_{k+1}$, "relogeant" chacune de ces parties à l'emplacement de la suivante afin de faire de la place dans $C$ pour accueillir $A_0 = A\setminus C$. Ainsi $\phi$ est la bijection tant recherchée entre $A$ et $C$ !


**Application**  
Plus haut, on avait prouvé que le cardinal de $[0,1[$ est inférieur ou égal à celui de $\mathbb{N}^\mathbb{N}$, l'ensemble des suites d'entiers. Ces deux ensembles ont en fait le même cardinal !
En effet :
- On a déjà prouvé dans l'exemple plus haut qu'il existait une injection $f$ de $[0,1[$ dans $\mathbb{N}^\mathbb{N}$.
- Réciproquement, il existe une injection de $\mathbb{N}^\mathbb{N}$ dans $[0,1[$ ; par exemple, on peut considérer l'application suivante :
$$
\begin{array}{rcl}
g : \ \mathbb{N}^\mathbb{N} & \to & [0,1[\\ \\
(a_n)_{n\in \mathbb{N}} & \to & 0,a_0 0 a_1 0 a_{2} 0 a_{3} 0 a_{4} \ldots
\end{array}
$$
Par exemple, à la suite constante égale à 9, on associe le réel 0,909090909 ...

> Le fait d'intercaler des 0 une décimale sur deux évite les problèmes liés aux répétitions infinies de 9 : par exemple, 0,35 et 0,349999... décrivent le même réel. Si l'on n'intercalait pas des 0 une décimale sur deux, on aurait donc deux suites ayant même image par $g$, et $g$ ne serait pas injective.

Ainsi, d'après le théorème de Cantor-Bernstein, il existe une bijection entre $[0,1[$ et $\mathbb{N}^\mathbb{N}$ : ces deux ensembles sont donc de même cardinal ! En d'autres termes :

<p style="text-align: center; font-weight: bold;">
Il existe "autant" de réels entre 0 et 1 que de suites d'entiers.
</p>

> Le théorème de Cantor-Bernstein joue un rôle crucial ici, car trouver directement une bijection explicite entre ces deux ensembles aurait été fort pénible. Remarquez qu'aucune des deux injections que nous avons définies plus haut ne sont bijectives : $f$ ne prend pas pour valeurs les suites constantes égales à 9 à partir d'un certain rang ; et $g$ ne prend clairement pas pour valeurs tous les nombres de $[0,1[$, vu sa définition. 

