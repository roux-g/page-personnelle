---
title: Questions de sommabilité
ordre: 100
---

## Différents types de sommation



On considère la série $\displaystyle\sum_{n\geq 0} a_n$  de terme général $a_n$, où $(a_n)$ est une suite de réels (ou de complexes). Dans toute la suite, on notera $S_n$ la somme partielle d'ordre $n$ de cette série :
$$
S_n = \displaystyle \sum_{k=0}^{n} a_k.
$$
On fixe également $\ell \in \mathbb{C}$.

> [!def] Convergence "classique"
> On dit que la série $\displaystyle\sum_{n\geq 0} a_n$ *converge vers* $\ell$  si la suite de ses sommes partielles tend vers $\ell$, i.e. si :
> $$
> \sum_{k=0}^{n} a_k \ \underset{n\to +\infty}{\longrightarrow} \ \ell.
> $$




### Convergence au sens de Cesàro


> [!def] Convergence au sens de Cesàro
> On dit que la série $\displaystyle\sum_{n\geq 0} a_n$ *converge au sens de Cesàro vers* $\ell$  si :
> $$
> \dfrac{1}{n+1} \sum_{k=0}^{n} S_k \ \underset{n\to +\infty}{\longrightarrow} \ \ell.
> $$


Par exemple, considérons la série
$$
1-1+1-1+ \ldots
$$
Ses sommes partielles sont :
- $S_0 = 1$
- $S_1 = 1-1 =0$
- $S_2 = 1-1+1 =1$
- $S_3 = 1-1+1-1 =0$, etc.

donc la série ne converge pas au sens classique (car $(S_n)$ n'a pas de limite).

En revanche, en distinguant le cas $n$ pair ($n=2p$) et le cas $n$ impair ($n=2p+1$), on voit que :
$$
\dfrac{1}{2p+1} \sum_{k=0}^{2p} S_k = \dfrac{p+1}{2p+1} \ \underset{p\to +\infty}{\longrightarrow} \ \frac{1}{2} \quad \text{et} \quad \dfrac{1}{2p+2} \sum_{k=0}^{2p+1} S_k = \dfrac{p+1}{2p+2} \ \underset{p\to +\infty}{\longrightarrow} \ \frac{1}{2}
$$
et donc que $\displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} S_k \ \underset{n\to +\infty}{\longrightarrow} \ \dfrac{1}{2}$. Ainsi,
$$
\boxed{\text{La série }1-1+1-1+ \ldots \text{ converge au sens de Cesàro vers } \frac{1}{2}.}
$$

Ainsi, une série peut être convergente au sens de Cesàro, mais pas convergente au sens classique du terme. En revanche, l'implication réciproque est vraie :

> [!thm] Théorème de Cesàro (1821)
> Si une série converge vers $\ell$ au sens classique, alors elle converge aussi vers $\ell$ au sens de Cesàro.

> [!dem]- Démonstration
> Supposons que $S_n \ \underset{n\to +\infty}{\longrightarrow} \ \ell$, et montrons qu'alors $\displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} S_k \ \underset{n\to +\infty}{\longrightarrow} \ \ell.$
> 
> Soit $\varepsilon >0$. Par définition de la limite, il existe $N\in \mathbb{N}$ tel que :
> $$
> \forall n\geq N, \ |S_n - \ell| \leq \frac{\varepsilon}{2}. \quad (*)
> $$
> L'astuce consiste alors à déguiser la limite $\ell$ sous la forme :
> $$
> \ell = \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} \ell.
> $$
> Grâce à ce petit relooking, on peut alors écrire
> $$
> \left(\dfrac{1}{n+1} \sum_{k=0}^{n} S_k\right) - \ell = \left(\dfrac{1}{n+1} \sum_{k=0}^{n} S_k\right) - \left(\displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} \ell\right) = \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} (S_k - \ell).
> $$
> Reste à majorer tout cela à l'aide de $(*)$, en faisant bien attention au fait que cette inégalité ne peut s'appliquer qu'au-delà du rang $N$ :
> $$
> \begin{align*}
> \left| \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} (S_k - \ell) \right| &\leq \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} |S_k - \ell|\\
> &= \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{N-1} |S_k - \ell| + \displaystyle\dfrac{1}{n+1} \sum_{k=N}^{n} |S_k - \ell|\\
> &\leq \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{N-1} |S_k - \ell| + \displaystyle\dfrac{1}{n+1} \sum_{k=N}^{n} \frac{\varepsilon}{2}\\
> &= \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{N-1} |S_k - \ell| + \displaystyle\dfrac{n-N+1}{n+1} \frac{\varepsilon}{2}.
> \end{align*}
> $$
> Il reste alors à majorer convenablement chacun de ces deux termes :
> - le premier tend vers 0 quand $n$ tend vers $+\infty$ (car la somme ne dépend pas de $n$) ; il va donc être inférieur à $\frac{\varepsilon}{2}$ à partir d'un certain rang.
> - pour le second terme, on peut simplement remarquer que $\dfrac{n-N+1}{n+1} \leq 1$.
> 
> Ainsi, à partir d'un certain rang, on a :
> $$
> \left| \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} (S_k - \ell) \right| \leq \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon.
> $$
> On a donc montré que, pour tout $\varepsilon>0$, il existe un rang au-delà duquel
> $$
> \left| \left(\displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} S_k\right) - \ell \right| \leq \varepsilon.
> $$
> Par définition de la limite, cela prouve bien que $\displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} S_k \ \underset{n\to +\infty}{\longrightarrow} \ \ell$ !

### Convergence au sens d'Abel


> [!def] Convergence au sens d'Abel
> On dit que la série $\displaystyle\sum_{n\geq 0} a_n$ *converge au sens d'Abel vers* $\ell$  si la fonction $f(x)=\displaystyle\sum_{n= 0}^{+\infty} a_n x^n$ est bien définie pour tout $x\in ]-1,1[$, et si $f(x)\ \underset{x\to 1^-}{\longrightarrow} \ \ell$.


Par exemple, considérons la série
$$
1-2+3-4+ \ldots
$$
Cette série converge au sens d'Abel vers $1/4$ ; en effet, ici le terme général est $a_n = (-1)^n (n+1)$, et on a donc, en vertu de la formule des sommes géométriques dérivées  :
$$
\displaystyle\sum_{n=0}^{+\infty} a_n x^n = \displaystyle\sum_{n=0}^{+\infty}  (n+1) (-x)^n = \dfrac{1}{(1+x)^2} \ \underset{x\to 1^-}{\longrightarrow} \ \frac{1}{4}.
$$
En revanche, cette série ne converge ni au sens classique, ni au sens de Cesàro ! En effet, ses sommes partielles sont :
- $S_0 = 1$
- $S_1 = 1-2 =-1$
- $S_2 = 1-2+3 =2$
- $S_3 = 1-2+3-4 =-2$
- $S_4 = 1-2+3-4+5 =3$
- $S_5 = 1-2+3-4+5-6 =-3$, etc.

En posant $\sigma_n = \displaystyle\dfrac{1}{n+1} \sum_{k=0}^{n} S_k$, on a alors
- $\sigma_0 = S_0 =1$
- $\sigma_1 = \frac{1}{2}(S_0 +S_1) = 0$
- $\sigma_2 = \frac{1}{3}(S_0 + S_1 + S_2) = \frac{2}{3}$
- $\sigma_3 = \frac{1}{4}(S_0 + S_1 + S_2 + S_3) = 0$
- $\sigma_4 = \frac{1}{5}(S_0 + S_1 + S_2 + S_3 + S_4) = \frac{3}{5}$

et d'une manière générale, $\sigma_{2p+1}=0$ et $\sigma_{2p}=\dfrac{p+1}{2p+1}$. En particulier, $\sigma_{2p+1} \ \underset{p\to +\infty}{\longrightarrow} \ 0$ et $\sigma_{2p}\ \underset{p\to +\infty}{\longrightarrow} \ \dfrac{1}{2}$, donc $(\sigma_n)$ n'admet pas de limite : cette série ne converge donc pas au sens de Cesàro.


Ainsi, une série peut être convergente au sens d'Abel, mais pas convergente au sens de Cesàro. En revanche, l'implication réciproque est vraie :

> [!thm] Théorème de continuité de Frobenius (1880)
> Si une série converge vers $\ell$ au sens de Cesàro, alors elle converge aussi vers $\ell$ au sens d'Abel.

La preuve repose sur une formule très utile appelée *transformation d'Abel* (aussi appelée *formule de sommation par parties*, car il s'agit de l'équivalent pour les sommes de la formule d'intégration par parties pour les intégrales).

> [!thm] Transformation d'Abel
> $$
> \displaystyle \sum_{k=0}^{n} (u_{k+1}-u_k)v_k = (u_{n+1}v_{n+1}-u_0 v_0) - \displaystyle \sum_{k=0}^{n} u_{k+1}(v_{k+1}-v_k)
> $$

> [!dem]- Preuve de la formule d'Abel 
> C'est un petit tour de passe-passe : on va séparer la somme en deux morceaux, réindicer l'un des deux (mais pas l'autre), puis les réunir à nouveau.
> $$
> \begin{align*}
> \sum_{k=0}^{n}(u_{k+1}-u_k)v_k 
> &=\sum_{k=0}^{n}u_{k+1}v_k-\sum_{k=0}^{n}u_kv_k\\[1mm]
> &=\sum_{k=0}^{n}u_{k+1}v_k-\sum_{k=-1}^{n-1}u_{k+1}v_{k+1}\quad\text{(par réindiçage)}\\[1mm]
> \end{align*}
> $$
> Après ce réindiçage, on va chercher à réunir à nouveau ces deux morceaux, mais il y a un prix à payer pour cela : puisque les deux n'ont plus les mêmes bornes, il va falloir laisser certains termes de côté.
>  $$
> \begin{align*}
> \sum_{k=0}^{n}u_{k+1}v_k-\sum_{k=-1}^{n-1}u_{k+1}v_{k+1} &=\sum_{k=0}^{n}u_{k+1}v_k-\left( \sum_{k=0}^{n}u_{k+1}v_{k+1} + u_0v_0 -u_{n+1}v_{n+1} \right)\\[1mm]
> &=u_{n+1}v_{n+1}-u_0v_0-\sum_{k=0}^{n}u_{k+1}(v_{k+1}-v_k).
> \end{align*}
> $$

Équipés de cette formule, on peut à présent s'attaquer à la démonstration du Théorème de continuité de Frobenius. Commençons par planter le décor, en notant :
$$
S_n = \displaystyle \sum_{k=0}^{n} a_k, \quad T_n = \sum_{k=0}^{n} S_k \quad \text{et} \quad f(x)=\displaystyle\sum_{k= 0}^{+\infty} a_k x^k.
$$
Supposons que $\dfrac{T_n}{n+1} \ \underset{n\to +\infty}{\longrightarrow} \ \ell$. On va chercher à démontrer qu'alors :
-  $\displaystyle\sum_{k= 0}^{+\infty} a_k x^k$ converge pour tout $x\in ]-1,1[$ 
- $f(x)\ \underset{x\to 1^-}{\longrightarrow} \ \ell$.

Dans la suite, on fixe un réel $x\in ]-1,1[$. 

#### 1ere étape : faire le lien entre $S_n$, $T_n$ et $f(x)$

On va commencer par mettre en relation tous les protagonistes de notre histoire, en montrant à l'aide de la transformation d'Abel que :
$$
f(x)= \sum_{k=0}^{\infty} a_k x^k = (1-x) \sum_{k=0}^{\infty} S_k x^k = (1-x)^2 \sum_{k=0}^{\infty} T_k x^k.
$$

> [!dem]- Démonstration
> On va utiliser la transformation d'Abel à deux reprises. Déjà, commençons par remarquer que $a_k = S_k - S_{k-1}$ (on pose par commodité que $S_{-1} = 0$, ce qui permet de généraliser cette formule au cas $a_0 = S_0 - S_{-1}$). Cela permet d'écrire, par une première transformation d'Abel :
> $$
> \sum_{k=0}^{n}a_k x^k = \sum_{k=0}^{n}(S_{k} - S_{k-1}) x^k = (S_{n}x^{n+1} - S_{-1}) - \displaystyle \sum_{k=0}^{n}S_{k}(x^{k+1}-x^k)
> $$
> d'où, en écrivant $x^{k+1}-x^k = x^k(x-1)$,
> $$
> \sum_{k=0}^{n}a_k x^k =  S_{n}x^{n+1} + (1-x)\sum_{k=0}^{n}S_{k}x^k. \quad (*)
> $$
> Par une transformation similaire (en utilisant le fait que $S_k = T_{k} - T_{k-1}$), on montre que :
> $$
> \sum_{k=0}^{n}S_k x^k =  T_{n}x^{n+1} + (1-x)\sum_{k=0}^{n}T_{k}x^k. \quad (* *)
> $$
> Il reste à comprendre comment les quantités dans les deux relations que l'on vient d'obtenir se comportent lorsque $n\to +\infty$.
> 
> Pour cela, souvenons-nous que par hypothèse $\dfrac{T_n}{n+1} \ \underset{n\to +\infty}{\longrightarrow} \ \ell$. On en déduit par croissances comparées que $T_n x^{n+1} \ \underset{n\to +\infty}{\longrightarrow} \ 0$, en écrivant :
> $$
> T_n x^{n+1} = \underbrace{ \left(\frac{T_n}{n+1} \right) }_{ \ \underset{n\to +\infty}{\longrightarrow} \  \ell }\underbrace{ (n+1)x^{n+1} }_{ \ \underset{n\to +\infty}{\longrightarrow} \   0 }
> $$
> Et puisque $S_n = T_n - T_{n-1}$, on en déduit aussi que $S_n x^{n+1} =  \ \underset{n\to +\infty}{\longrightarrow} \ 0$.
> 
> De plus, puisque la suite $\left( \frac{T_n}{n+1} \right)$ converge, elle est bornée ; en notant $M$ une borne de cette suite, on peut alors écrire
> $$
> |T_k x^k| = \left| \left(\frac{T_k}{k+1} \right)(k+1)x^{k} \right| \leq M(k+1)|x|^k.
> $$
> Or la série de terme général $(k+1)|x|^k$ converge puisque $|x|<1$ (il s'agit d'une série géométrique dérivée), et donc par théorème de comparaison pour les séries à termes positifs, on en déduit que $\sum_{k\geq 0} T_{k}x^k$ converge absolument et donc converge. Par conséquent :
> - D'après $(**)$, et puisque $T_n x^{n+1} \ \underset{n\to +\infty}{\longrightarrow} \ 0$, la série $\sum_{k\geq 0} S_{k}x^k$ converge aussi ;
> - D'après $(*)$, et puisque $S_n x^{n+1} \ \underset{n\to +\infty}{\longrightarrow} \ 0$, la série $\sum_{k\geq 0} a_{k}x^k$ converge aussi.
> 
> Il reste à passer à la limite dans $(*)$ et dans $(**)$ pour obtenir
> $$
> \sum_{k=0}^{+\infty}a_k x^k =  (1-x)\sum_{k=0}^{+\infty}S_{k}x^k \quad \text{et} \quad \sum_{k=0}^{+\infty}S_k x^k =  (1-x)\sum_{k=0}^{+\infty}T_{k}x^k
> $$
> et donc, en mettant ces deux relations bout à bout :
> $$
> f(x)= \sum_{k=0}^{\infty} a_k x^k = (1-x) \sum_{k=0}^{\infty} S_k x^k = (1-x)^2 \sum_{k=0}^{\infty} T_k x^k.
> $$
 


#### 2ième étape : reformuler le problème

Grâce à la première étape, on a écrit $f(x)$ sous la forme
$$
f(x)= (1-x)^2 \sum_{k=0}^{\infty} T_k x^k.
$$
Montrons à présent que $f(x)\ \underset{x\to 1^-}{\longrightarrow} \ \ell$, *i.e.* que $f(x) - \ell \ \underset{x\to 1^-}{\longrightarrow} \ 0$ . 

Problème : on n'a a priori pas grand-chose à dire sur la quantité $f(x)-\ell$ ... les quantités $f(x)$ et $\ell$ sont trop différentes l'une de l'autre pour pouvoir les comparer facilement ! On va donc commencer par faire subir un petit relooking à ces deux quantités, afin de les faire ressembler autant que possible l'une à l'autre. Pour cela, souvenons-nous de la formule pour les séries géométriques dérivées :
$$
\sum_{k=0}^{\infty} (k+1)x^k = \dfrac{1}{(1-x)^2}, \quad \text{i.e.} \quad \sum_{k=0}^{\infty} (k+1)(1-x)^2x^k = 1.
$$
Ce $(1-x)^2$ est fort intéressant, car il est déjà présent dans $f(x)$ ... En revanche, il manque le $k+1$. Qu'à cela ne tienne, on va l'ajouter :
$$
\begin{align*}
f(x)=(1-x)^2 \sum_{k=0}^{\infty} T_k x^k&=\sum_{k=0}^{\infty}(k+1)(1-x)^2 x^k \times \frac{T_k}{k+1} \\
\text{et d'autre part, } \ \ell&=\sum_{k=0}^{\infty}(k+1)(1-x)^2 x^k \times \ell
\end{align*}.
$$
Le relooking est complet ! On peut à présent les soustraire l'une à l'autre sans encombres :
$$
f(x)-\ell = \sum_{k=0}^{\infty}(k+1)(1-x)^2 x^k \times \left(\frac{T_k}{k+1}-\ell\right).
$$
Plus qu'à établir que cette quantité tend vers 0 quand $x$ tend vers 1.

#### 3ième étape : majorer avec délicatesse

On va supposer à partir de maintenant, par commodité, que $x\in [0,1[$ (ce qui n'est pas gênant puisque l'on ne s'intéresse qu'à la limite en $1^-$).

Par inégalité triangulaire, on a :
$$
|f(x)-\ell| \leq \sum_{k=0}^{\infty}(k+1)(1-x)^2 x^k \times \left|\frac{T_k}{k+1}-\ell\right|.
$$
Soit $\varepsilon>0$. Par hypothèse, $\dfrac{T_n}{n+1} \ \underset{n\to +\infty}{\longrightarrow} \ \ell$ donc il existe un rang $N$ tel que :
$$
\forall k\geq N, \ \left|\frac{T_k}{k+1}-\ell\right|\leq \frac{\varepsilon}{2}.
$$
(On fixe un tel $N$ dans toute la suite.)

Pour tirer parti de cela, on va séparer notre somme en deux :
$$
\begin{align*}
\left|f(x)-\ell\right| &\leq \sum_{k=0}^N(k+1)(1-x)^2 x^k \times\left|\frac{T_k}{k+1}-\ell\right|\\
& \hspace{1cm} +\sum_{k=N+1}^{\infty}(k+1)(1-x)^2 x^k 
\times\left|\frac{T_k}{k+1}-\ell\right|
\end{align*}
$$
Puisque $\displaystyle\sum_{k=N+1}^{\infty}(k+1)(1-x)^2 x^k \leq \sum_{k=0}^{\infty}(k+1)(1-x)^2 x^k =1$, on en déduit :
$$
\begin{align*}
\left|f(x)-\ell\right| &\leq \sum_{k=0}^N(k+1)(1-x)^2 x^k \times\left|\frac{T_k}{k+1}-\ell\right| +  \sum_{k=N+1}^{\infty}(k+1)(1-x)^2 x^k \times \frac{\varepsilon}{2} \\
&\leq \sum_{k=0}^N(k+1)(1-x)^2 x^k \times\left|\frac{T_k}{k+1}-\ell\right| +  \frac{\varepsilon}{2}.
\end{align*}
$$
Il reste à remarquer que, la première somme étant finie, elle tend vers 0 quand $x$ tend vers 1, et que donc, pour $x$ suffisamment proche de 1, elle est inférieure à $\frac{\varepsilon}{2}$. On a alors, dès que $x$ est suffisamment proche de 1 :
$$
|f(x)-\ell|\leq \frac{\varepsilon}{2}+\frac{\varepsilon}{2} = \varepsilon.
$$
Cela prouve que $f(x)\ \underset{x\to 1^-}{\longrightarrow} \ \ell$, et conclut la preuve !


## Théorèmes Taubériens

Comme on l'a vu avec les exemples donnés plus haut, les réciproques aux deux théorèmes qui précèdent sont fausses en général ; cependant, on peut poser la question des hypothèses qu'il faudrait ajouter pour rendre ces réciproques vraies. En d'autres termes, on peut se demander s'il existe des "réciproques partielles" aux théorèmes ci-dessus. De telles réciproques partielles sont ce que l'on appelle des *théorèmes Taubériens*, en hommage à Alfred Tauber qui en 1897 fut le premier à énoncer un résultat de ce genre :

> [!thm] Théorème (Tauber, 1897)
> Si une série converge vers $\ell$ au sens d'Abel et que $n a_n \ \underset{n\to +\infty}{\longrightarrow} \ 0$, alors la série converge aussi vers $\ell$ au sens classique du terme.

Cette hypothèse supplémentaire sur $na_n$ est en réalité assez contraignante ; quelques années plus tard, John Edensor Littlewood prouva qu'il suffit en fait de supposer que $(na_n)$ est bornée :

> [!thm] Théorème (Littlewood, 1911)
> Si une série converge vers $\ell$ au sens d'Abel et que $(n a_n)$ est bornée, alors la série converge aussi vers $\ell$ au sens classique du terme.

La preuve donnée initialement par Littlewood de ce théorème était assez complexe ; tout au long du vingtième siècle, de nombreuses autres preuves ont été proposées, aidant à simplifier considérablement la démonstration. On va présenter ici une preuve due aux travaux de Karamata (1930), Wiener (1932) et Wielandt (1952).


*Avertissement : la preuve qui suit fait appel à certains résultats de topologie (théorème de Heine, théorème d'approximation de Weierstrass).*

On reprend les notations habituelles, en posant :
$$
S_n = \displaystyle \sum_{k=0}^{n} a_k \quad \text{et} \quad f(x)=\displaystyle\sum_{k= 0}^{+\infty} a_k x^k.
$$
Supposons que :
-  la série $\displaystyle\sum_{k\geq 0}^{} a_k x^k$ converge pour tout $x\in ]-1,1[$ 
- $f(x)\ \underset{x\to 1^-}{\longrightarrow} \ \ell$
- il existe $C\geq 0$ telle que, pour tout $n\in \mathbb{N}$, $n|a_n|\leq C$.

Le but est de démontrer qu'alors $S_n \ \underset{n\to +\infty}{\longrightarrow} \ \ell$.

On va procéder en trois grandes étapes.

#### Étape 1 : renforcement de l'hypothèse

Par hypothèse, on sait que $\displaystyle\sum_{k= 0}^{+\infty} a_k x^k \ \underset{x\to 1^-}{\longrightarrow} \ \ell$. On peut en déduire quelque chose d'apparence plus forte : pour tout polynôme $P$ tel que $P(0)=0$, on a
$$
\boxed{\sum_{k=0}^{\infty} a_k P\left(x^k\right) \underset{x \to 1^-}{\longrightarrow} \ell P(1). \quad (*)}
$$
^4cfb5c


> [!dem]- Démonstration
> Soit $P=\displaystyle \sum_{j=1}^{N}b_j X^j$ (le polynôme n'a pas de terme constant puisque $P(0)=0$).
> 
> Soit $j\in \llbracket 1, N \rrbracket$. Puisque $\displaystyle\sum_{k= 0}^{+\infty} a_k x^k \ \underset{x\to 1^-}{\longrightarrow} \ \ell$, et que $x^j \ \underset{x\to 1^-}{\longrightarrow} \ 1$, on en déduit par composition que
> $$
> \displaystyle\sum_{k= 0}^{+\infty} a_k (x^j)^k \ \underset{x\to 1^-}{\longrightarrow} \ \ell \quad \text{i.e.} \quad \displaystyle\sum_{k= 0}^{+\infty} a_k (x^k)^j \ \underset{x\to 1^-}{\longrightarrow} \ \ell
> $$
> Par linéarité, $\displaystyle\sum_{k=0}^{\infty} a_k P\left(x^k\right)$ converge donc, et :
> $$
> \sum_{k=0}^{\infty} a_k P\left(x^k\right) = \sum_{k=0}^{\infty} a_k \displaystyle \sum_{j=1}^{N} b_j\left(x^k\right)^j = \displaystyle \sum_{j=1}^{N} b_j\sum_{k=0}^{\infty} a_k \left(x^k\right)^j  \underset{x \to 1^-}{\longrightarrow} \sum_{j=1}^{N} b_j \ell = \ell P(1).
> $$
 



#### Étape 2 : reformulation du problème


Rappelons que notre objectif est de prouver que $\displaystyle \sum_{k=0}^{n} a_k\ \underset{x\to 1^-}{\longrightarrow} \ \ell$. On va commencer par reformuler ce résultat, pour le faire davantage ressembler à notre hypothèse $(*)$, ce qui aidera à passer de l'un à l'autre par la suite.

Il s'agit donc de "camoufler" cette somme finie en une somme infinie comme dans $(*)$. Pour cela, on va utiliser une fort jolie astuce : on écrit que
$$
\sum_{k=0}^{n} a_k = \sum_{k=0}^{\infty} a_k g\left(x_n^k\right)
$$
où $x_n=e^{-1 / n}$ et où $g$ est la fonction indicatrice de $\left[e^{-1}, 1\right]$, *i.e.*
$$
g(x)=\left\{\begin{array}{cl}
1 & \text { si } e^{-1} \leq x \leq 1 \\
0 & \text { sinon. }
\end{array}\right.
$$
L'objectif à démontrer peut ainsi se présenter sous la forme :
$$
\boxed{\displaystyle \sum_{k=0}^{\infty} a_k g\left(x_n^k\right) \ \underset{x\to 1^-}{\longrightarrow} \ \ell. \quad (**)}
$$

Tout l'enjeu de la démonstration est à présent de prouver que l'on peut passer de $(*)$, un résultat qui ne concerne que des fonctions polynômiales, à $(**)$, qui lui fait intervenir une fonction $g$ qui non seulement n'est pas polynômiale mais n'a même pas la décence d'être continue.


#### Étape 3 : on se ramène en 0

On va déjà effectuer une manœuvre courante en analyse, consistant à déplacer tout le problème pour se ramener à étudier des quantités tendant vers 0.

Pour cela, commençons par remarquer que l'hypothèse $(*)$ entraîne en particulier que pour tout polynôme $P$ tel que $P(0)=0$ et $P(1)=1$, on a :
$$
\sum_{k=0}^{\infty} a_k P\left(x^k\right) \underset{x \to 1^-}{\longrightarrow} \ell.
$$
 Mais alors, puisque par hypothèse,  $\displaystyle\sum_{k= 0}^{+\infty} a_k x^k \ \underset{x\to 1^-}{\longrightarrow} \ \ell$, on a par soustraction,
$$
\sum_{k=0}^{\infty} a_k (P\left(x^k\right)-x^k) \underset{x \to 1^-}{\longrightarrow} 0.
$$
Or on remarque que le polynôme $P(X)-X$ s'annule en 0 et en 1, et peut donc s'écrire sous la forme $P(X)-X=X(X-1)Q(X)$, où $Q$ est un polynôme quelconque. Cela invite à faire un changement de fonction : pour tout polynôme $Q$, en appliquant ce qui précède à $P(X)=X+X(X-1)Q(X)$, on a donc
$$
\sum_{k=1}^{\infty} a_k x^k\left(1-x^k\right) Q\left(x^k\right) \underset{x \to 1^-}{\longrightarrow} 0.
$$
Comparé à l'hypothèse initiale $(*)$, on a ici gagné deux gros avantages :
- la limite est à présent 0 au lieu de $\ell$.
- peut-être encore plus important, ceci est à présent vrai pour **tout** polynôme $Q$, alors que $(*)$ n'était vrai que pour les polynômes s'annulant en 0.


Enivrés par ces progrès, on décide de faire subir le même traitement au résultat $(**)$ que l'on cherche à prouver : on écrit
$$
g(x)=x+x(1-x) h(x)
$$
avec $h(x)=\dfrac{g(x)-x}{x(1-x)}$, et par un raisonnement analogue, $(**)$ se réécrit alors

%%
$$
h(x)=\left\{\begin{array}{cc}
-\frac{1}{1-x} & \text { si } 0 \leqslant x<e^{-1} \\
\frac{1}{x} & \text { si } e^{-1} \leqslant x \leqslant 1
\end{array}\right.
$$ %%
$$
\sum_{k=1}^{\infty} a_k x^k\left(1-x^k\right) h\left(x^k\right) \underset{x \to 1^-}{\longrightarrow} 0.
$$

#### Étape 4 : on majore avec finesse

Résumons la situation. On sait que  :
$$
\text {Pour tout polynôme } Q, \quad \sum_{k=1}^{\infty} a_k x^k\left(1-x^k\right) Q\left(x^k\right) \underset{x \to 1^-}{\longrightarrow} 0,
$$
et l'on cherche à prouver que
$$
\sum_{k=1}^{\infty} a_k x^k\left(1-x^k\right) h\left(x^k\right) \underset{x \to 1^-}{\longrightarrow} 0.
$$
Pour conclure, il reste donc à montrer que la différence des deux, à savoir
$$
E(x)=\sum_{k=1}^{\infty} a_k x^k\left(1-x^k\right)\left(h\left(x^k\right)-Q\left(x^k\right)\right)
$$
tend vers 0 quand $x\to 1^-$.

Dans la suite, on va supposer que $x\in [0,1[$ (pas gênant puisque l'on ne s'intéresse qu'à la limite en $1^-$). 

Or, la fonction $x\mapsto 1-x^k$ est concave sur $[0,1]$, donc reste en dessous de ses tangentes sur cet intervalle, et notamment :
$$
\forall x\in [0,1], \quad 1-x^k \leqslant k(1-x).
$$
![[puissance_tangente.png |center]]

Par conséquent,
$$
|E(x)| \leq \sum_{k=1}^{\infty} a_k x^k k(1-x)\left|h\left(x^k\right)-Q\left(x^k\right)\right|.
$$
L'intérêt de cette majoration est qu'elle permet (enfin !) d'utiliser notre hypothèse clé : le fait que la suite $(ka_k)$ est bornée. 
$$
|E(x)| \leq C \sum_{k=1}^{\infty} (x^k -x^{k+1})\left|h\left(x^k\right)-Q\left(x^k\right)\right|.
$$
On reconnait alors dans le membre de droite une somme de Riemann associée à la fonction continue par morceaux $|h-Q|$ et à la subdivision $(x^k)_{k\geq 1}$. Le pas maximal de cette subdivision est $1-x$ ; en effet :
$$
\forall k\geq 1, \quad x^k - x^{k+1} = x^k(1-x)\leq 1-x
$$
En particulier, le pas maximal de cette subdivision tend vers 0 lorsque $x\to 1^-$. Par conséquent :
$$
\sum_{k=1}^{\infty} (x^k -x^{k+1})\left|h\left(x^k\right)-Q\left(x^k\right)\right| \ \underset{x\to 1^-}{\longrightarrow} \  \int_0^1|h(t)-Q(t)| \mathrm{dt}.
$$

> [!dem]- Démonstration
> Plus généralement, on a le résultat suivant :
> 
> > [!thm] Lemme
> > 
> > Si $\phi:[0,1]\to \mathbb{R}$ est une fonction continue par morceaux, alors :
> > $$
> > \sum_{k=1}^{\infty} (x^k -x^{k+1})\phi(x^k) \ \underset{x\to 1^-}{\longrightarrow} \  \int_0^1 \phi(t) \mathrm{dt}.
> > $$
> 
> J'en inclus ici une démonstration car, même si cela ressemble à un résultat classique sur les intégrales de Riemann, le fait que la subdivision utilisée (les $x^k$) comporte un nombre infini de points rend les choses un peu moins conventionnelles. La preuve est ceci dit similaire au cas des subdivisions formées d'un nombre fini de points.
> 
> Déjà, commençons par remarquer que $\sum_{k\geq 1}^{} (x^k -x^{k+1})\phi(x^k)$ est bien une série convergente. En effet, $\phi$ étant continue par morceaux sur le segment $[a,b]$, elle y est bornée ; en notant $M$ tel que $|\phi|\leq M$, on a alors
> $$
> \left|(x^k -x^{k+1})\phi(x^k)\right| \leq M(x^k-x^{k+1})
> $$
> Or par télescopage, la série $\sum_{k\geq 1}^{} (x^k -x^{k+1})$ converge :
> $$
> \sum_{k= 1}^{n} (x^k -x^{k+1}) = x-x^{n+1} \ \underset{n\to +\infty}{\longrightarrow} \  x
> $$
> donc par théorème de comparaison pour les séries à termes positifs, $\sum_{k\geq 1}^{} (x^k -x^{k+1})\phi(x^k)$ est absolument convergente et donc convergente.
> 
> Passons à la démonstration à proprement parler. Remarquons déjà que l'on peut ajouter à la somme le terme pour $k=0$, ce qui ne change rien puisque ce terme (à savoir $(1-x)\phi(1)$) tend vers 0 quand $x\to 1$. On va donc chercher à prouver que :
> $$
> \sum_{k=0}^{\infty} (x^k -x^{k+1})\phi(x^k) \ \underset{x\to 1^-}{\longrightarrow} \  \int_0^1 \phi(t) \mathrm{dt}.
> $$
> 
> **1er cas :** si $\phi$ est continue
> 
> On écrit :
> $$
> \begin{align*}
> \sum_{k=0}^{\infty} (x^k -x^{k+1})\phi(x^k) -  \int_0^1 \phi(t) \mathrm{dt} &= \sum_{k=0}^{\infty} \int_{x^{k+1}}^{x^{k}} \phi(x^k) \mathrm{dt} -  \sum_{k=0}^{\infty} \int_{x^{k+1}}^{x^{k}}  \phi(t) \mathrm{dt}\\
> &= \sum_{k=0}^{\infty} \int_{x^{k+1}}^{x^{k}} \phi(x^k) - \phi(t) \mathrm{dt}
> \end{align*}
> $$
> 
> Or d'après le théorème de Heine, $\phi$ est uniformément continue sur le segment $[0,1]$. Soit $\varepsilon>0$ ; il existe donc $\delta>0$ tel que
> $$
> \forall t,t'\in [0,1], \ |t'-t|\leq \delta \implies |\phi(t')-\phi(t)|\leq \varepsilon.
> $$
> Par ailleurs, si $t\in [x^{k+1}, x^{k}]$, on a
> $$
> 0\leq x^k - t \leq x^k - x^{k+1} = x^k(1-x) \leq 1-x
> $$
> Considérons donc $x\in [1-\delta, 1[$. L'inégalité précédente entraîne que $|x^k - t| \leq \delta$, et donc que $|\phi(x^k)-\phi(t)|\leq \varepsilon$. Il reste à conclure par inégalité triangulaire :
> $$
> \begin{align*}
> \left|\sum_{k=0}^{\infty} (x^k -x^{k+1})\phi(x^k) -  \int_0^1 \phi(t) \mathrm{dt} \right| &= \left|\sum_{k=0}^{\infty} \int_{x^{k+1}}^{x^{k}} \phi(x^k) - \phi(t) \mathrm{dt}\right|\\
> &\leq \sum_{k=0}^{\infty} \int_{x^{k+1}}^{x^{k}} \left|\phi(x^k) - \phi(t)\right| \mathrm{dt}\\
> &\leq \sum_{k=0}^{\infty} \int_{x^{k+1}}^{x^{k}} \varepsilon\  \mathrm{dt}\\
> &= \sum_{k=0}^{\infty}  \varepsilon (x^k - x^{k+1}) \  \mathrm{dt}\\
> &=\varepsilon \text{   par télescopage.} 
> \end{align*}
> $$
> Ainsi, $\displaystyle\sum_{k=0}^{\infty} (x^k -x^{k+1})\phi(x^k) \ \underset{x\to 1^-}{\longrightarrow} \  \int_0^1 \phi(t) \mathrm{dt}$.
> 
> **2nd cas :** $\phi$ continue par morceaux
> 
> Notons $a_1, ..., a_p$  les points de discontinuité de $\phi$.
> 
> On adapte la subdivision des $(x^k)_{k\geq 1}$ en ajoutant les $a_i$ à cette famille de points. Bien sûr, cela change légèrement la somme de Riemann considérée ici : en l'occurrence, si $x^{k+1}<a_i\leq x^k$, alors le terme
> $$
> (x^k -x^{k+1})\phi(x^k)
> $$
> est remplacé par les deux termes
> $$
> (x^k-a_i)\phi(x^k)+(a_i-x^{k+1})\phi(a_i).
> $$
> Cependant, cela ne change rien sur la limite obtenue, car la différence entre ces deux quantités tend vers 0 quand $x\to 1$ , et ce indépendamment de $k$ :
> $$
> \begin{align*}
> \left| (x^k -x^{k+1})\phi(x^k)\right. & \left. \, - \, (x^k-a_i)\phi(x^k)-(a_i-x^{k+1})\phi(a_i) \right|\\
> &= \left|(a_i-x^{k+1})\phi(x^k)-(a_i-x^{k+1})\phi(a_i)\right|\\
> &\leq 2M(a_{i}-x^{k+1})\\
> &\leq 2M(x^k -x^{k+1})\\
> &\leq 2M(1-x) \ \underset{x\to 1^-}{\longrightarrow} \  0.
> \end{align*}
> $$
> Une fois que les $a_i$ font partie de la subdivision, il est alors aisé de découper la somme de Riemann et l'intégrale étudiées en plusieurs morceaux, et de se ramener à étudier $\phi$ sur chacun des intervalles sur lesquels elle est continue (ou en tout cas prolongeable en une fonction continue). On applique alors sur chacun de ces intervalles un raisonnement similaire à celui fait dans le premier cas.


Il reste alors pour conclure à justifier que cette intégrale peut être rendue aussi petite que l'on veut en choisissant un polynôme $Q$ judicieux.


> [!thm] Théorème
> Soit $h : [a,b]\to \mathbb{R}$ une fonction continue par morceaux.
> Pour tout $\varepsilon>0$, il existe un polynôme $Q$ tel que :
> $$
> \int_a^b|h(t)-Q(t)| \mathrm{dt} \leq \varepsilon.
> $$


> [!dem]- Démonstration
> On procède en deux temps :
> - On commence par approcher $h$ par une fonction continue $\tilde{h}$, en "raccommodant" les points de discontinuité à l'aide d'interpolations linéaires
> - Puis on approche la fonction $\tilde{h}$ par un polynôme à l'aide du théorème de Weierstrass.
> 
> **1ere étape**
> 
> Notons $x_1$, ..., $x_p$ les points de discontinuité de $h$. On va modifier $h$ seulement au voisinage de ces points de discontinuité.
> 
> Soit $\delta>0$ (que l'on choisira "très petit" dans la suite). On définit une fonction continue $\tilde{h}$ qui coïncide avec $h$ hors des intervalles $[x_{i}-\delta, x_{i}+\delta]$, et qui est définie comme une fonction affine sur chacun de ces intervalles. Alors, si $\delta$ est suffisamment petit, on a :
> $$
> \int_a^b|h(t)-\tilde{h}(t)| \mathrm{dt} \leq \frac{\varepsilon}{2}.
> $$
> 
> > [!dem]- Démonstration
> > 
> > La fonction $h$ est continue par morceaux sur le segment $[a,b]$, donc est bornée. Soit un réel $M$ tel que $|h(t)|\leq M$ sur $[a,b]$. Par construction de $\tilde{h}$, remarquons qu'on a également $|\tilde{h}(t)|\leq M$ sur $[a,b]$.
> > 
> > Alors, puisque $\tilde{h}$  coïncide avec $h$ hors des intervalles $[x_{i}-\delta, x_{i}+\delta]$,
> > $$
> > \begin{align*}
> > \int_a^b|h(t)-\tilde{h}(t)| \mathrm{dt} &= \displaystyle \sum_{i=1}^{p} \int_{x_i -\delta}^{x_i + \delta}|h(t)-\tilde{h}(t)| \mathrm{dt}\\
> > &\leq \displaystyle \sum_{i=1}^{p} \int_{x_i -\delta}^{x_i + \delta}|h(t)|+|\tilde{h}(t)| \mathrm{dt}\\
> > &\leq \displaystyle \sum_{i=1}^{p} \int_{x_i -\delta}^{x_i + \delta}2M \mathrm{dt} \\
> > &= \sum_{i=1}^{p} 4M\delta = 4M\delta p.
> > \end{align*} 
> > $$
> > Il suffit donc de prendre $\delta = \dfrac{\varepsilon}{8Mp}$ pour avoir l'inégalité souhaitée.
> 
> **2nde étape**
> 
> Puisque $\tilde{h}$ est continue sur le segment $[a,b]$, d'après la théorème d'approximation de Weierstrass, il existe un polynôme $Q$ tel que :
> $$
> \forall x\in [a,b], \ |\tilde{h}(x)-Q(x)|\leq \frac{\varepsilon}{2(b-a)}.
> $$
> Il reste alors à combiner cela avec la première étape, par inégalité triangulaire :
> $$
> \begin{align*}
> \int_a^b|h(t)-Q(t)| \mathrm{dt} &= \int_a^b|h(t)-\tilde{h}(t)+\tilde{h}(t)-Q(t)| \mathrm{dt}\\
> &\leq \int_a^b|h(t)-\tilde{h}(t)|+|\tilde{h}(t)-Q(t)| \mathrm{dt}\\
> &= \int_a^b|h(t)-\tilde{h}(t)|\mathrm{dt}+\int_a^b|\tilde{h}(t)-Q(t)| \mathrm{dt}\\
> &\leq \frac{\varepsilon}{2}+\int_a^b \frac{\varepsilon}{2(b-a)} \mathrm{dt} = \frac{\varepsilon}{2}+\frac{\varepsilon}{2} = \varepsilon.
> \end{align*}
> $$


**Conclusion :**

Soit $\varepsilon>0$. Fixons un polynôme $Q$ tel que  $\displaystyle\int_0^1|h(t)-Q(t)| \mathrm{dt} \leq \frac{\varepsilon}{2}$.

D'après ce que l'on a vu plus haut,
$$
|E(x)| \leq C \sum_{k=1}^{\infty} (x^k -x^{k+1})\left|h\left(x^k\right)-Q\left(x^k\right)\right| \ \underset{x\to 1^-}{\longrightarrow} \  \int_0^1|h(t)-Q(t)| \mathrm{dt} \leq \frac{\varepsilon}{2}
$$
et donc $|E(x)|\leq \varepsilon$ pour tout $x$ suffisamment proche de $1$. Cela prouve que $E(x)\ \underset{x\to 1^-}{\longrightarrow} \ 0$, et conclut la preuve.

## Bibliographie

- Choimet, D.; Queffélec, H. *Analyse mathématique - grands théorèmes du vingtième siècle*; Calvage & Mounet, 2009
- Korevaar, J. *Tauberian Theory : a Century of Developments*; Springer, 2004