---
ordre: 30
title: La série exponentielle
---

$$
1+ x + \dfrac{x^2}{2!}+\dfrac{x^3}{3!} + \dfrac{x^4}{4!} + \ldots = e^x
$$
> [!thm] Théorème
> $$
> \sum_{k=0}^{+\infty} \dfrac{x^{k}}{k!} = e^x, \qquad \text{i.e.} \qquad \sum_{k=0}^{n} \dfrac{x^{k}}{k!} \underset{n\to +\infty}{\longrightarrow} e^x.
> $$


## Une première justification ... peu rigoureuse

Commençons par un argument un peu faux : si l'on note $f(x)=\displaystyle \sum_{k=0}^{+\infty} \dfrac{x^{k}}{k!}$ , alors
$$
f'(x)= \sum_{k=1}^{+\infty} \dfrac{kx^{k-1}}{k!} = \sum_{k=1}^{+\infty} \dfrac{x^{k-1}}{(k-1)!} = \sum_{k=0}^{+\infty} \dfrac{x^{k}}{k!} = f(x).
$$
(où l'on est passé de la seconde à la troisième somme par changement d'indice)

De plus, $f(0)=1+0+0+0+\ldots = 1$ (rappelons que $0^0=1$ par définition).

Or l'exponentielle est l'unique fonction de $\mathbb{R}$ dans $\mathbb{R}$ vérifiant $f'=f$ et $f(0)=1$ ; par conséquent, pour tout $x\in \mathbb{R}$, $f(x)=e^x$ !

Cet argument est très rapide ... mais passe sous le tapis deux points cruciaux :
- Qu'est-ce qui garantit que la fonction $f$ est **bien définie** ? Rappelons en effet que ces sommes infinies sont par définition des limites : pourquoi la quantité $\displaystyle \sum_{k=0}^{n} \dfrac{x^{k}}{k!}$ aurait-elle une limite lorsque $n$ tend vers $+\infty$ ?
- Qu'est-ce qui garantit que $f$ est **dérivable** ? A priori, rien n'autorise à dériver comme nous l'avons fait sous un symbole de somme infinie ...

Plusieurs voies sont possibles pour pallier ces problèmes. La première, la plus directe, consiste à établir rigoureusement les deux points ci-dessus. Cela fait intervenir des arguments d'analyse assez techniques, en lien avec les *séries entières*, qui sont les objets du type de la fonction $f$ étudiée dans cette section.\
A la place, on va présenter un argument plus élémentaire consistant, plutôt qu'à affronter les obstacles présentés plus haut, à contourner ceux-ci.

## Corrigeons le tir

Tous les problèmes rencontrés dans la preuve précédente sont dus au fait que nous avons voulu raisonner avec des sommes infinies. Qu'à cela ne tienne : on va raisonner avec des sommes finies à la place, et tenter de mettre en place le même argument !

Pour $n\in \mathbb{N}^\ast$, posons donc $f_n(x)=\displaystyle \sum_{k=0}^{n} \dfrac{x^{k}}{k!}$ . Notre but est de prouver que $f_n(x) \ \underset{n\to +\infty}{\longrightarrow} \ e^x$.\
On va faire comme précédemment, en commençant par dériver $f_n$ :
$$
f_n'(x)= \sum_{k=1}^{n} \dfrac{kx^{k-1}}{k!} = \sum_{k=1}^{n} \dfrac{x^{k-1}}{(k-1)!} = \sum_{k=0}^{n-1} \dfrac{x^{k}}{k!} = f_n(x) - \frac{x^n}{n!}.
$$
(où l'on est passé de la seconde à la troisième somme par changement d'indice)

Comparé à notre première tentative de preuve, on observe que cette fois $f_n'$ n'est pas exactement égale à $f_n$ : il y a un petit terme d'erreur $\dfrac{x^n}{n!}$ qui est apparu. C'est normal, puisque la fonction $f_n$ n'est pas exactement égale à la fonction $f$ définie plus haut (la somme infinie), elle ne fait qu'approcher cette fonction lorsque $n\to +\infty$. D'ailleurs, le terme $\dfrac{x^n}{n!}$ tend vers 0 quand $n\to +\infty$, ce qui est cohérent avec l'idée que l'erreur commise en approchant une somme infinie par une somme finie s'amenuise à mesure que l'on augmente le nombre de termes dans la somme.


Voyons ce que cela entraîne sur $f_n$. Rappelons que le but est de prouver que $f_n(x) \ \underset{n\to +\infty}{\longrightarrow} \ e^x$ ; dit de manière un peu moins formelle, on veut montrer que si $n$ est grand, alors $f_n(x) \approx e^x$. Autrement dit, on souhaite établir que la fonction $g_n : x\mapsto f_n(x)e^{-x}$ est "à peu près constante" ... il y a une manière simple de vérifier cela : regarder sa dérivée !
$$
\begin{align*}
g_n'(x)&= f_n'(x)e^{-x}-f_n(x)e^{-x} \\
&=  \left( f_n(x) - \frac{x^n}{n!} \right)e^{-x}-f_n(x)e^{-x} \\
&= - \dfrac{x^n}{n!}e^{-x}.
\end{align*}
$$
(remarque : si $n$ est très grand, cette dérivée est très proche de 0, et donc $g_n$ est bien "environ constante" comme prévu)

On va alors se servir de cette dérivée pour reconstruire $g_n$, puis $f_n$ :
- déjà, on récupère $g_n(x)$ en intégrant l'égalité $g_n'(t)=- \dfrac{t^n}{n!}e^{-t}$ :
$$
\begin{align*}
\int_0^x g_n'(t)dt &= -\int_0^x \dfrac{t^n}{n!}e^{-t} dt\\
\text{i.e.}  \quad g_n(x)-g_n(0) &= -\int_0^x \dfrac{t^n}{n!}e^{-t} dt.
\end{align*}
$$
Puisque $g_n(0)=f_n(0)e^{-0} = 1$, on a donc :
$$
g_n(x) = 1-\int_0^x \dfrac{t^n}{n!}e^{-t} dt.
$$
- puis on en déduit $f_n(x)$ :
$$
f_n(x)=e^x g_n(x) = e^x - e^x \int_0^x \dfrac{t^n}{n!}e^{-t} dt. \qquad (*)
$$


> [!rem]- Remarque
> L'égalité que l'on vient d'établir se réécrit aussi :
> $$
> \begin{align*}
> e^x &= f_n(x) + e^x \int_0^x \dfrac{t^n}{n!}e^{-t} dt \\[10pt]
> \text{i.e.} \quad e^x &= \displaystyle \sum_{k=0}^{n} \dfrac{x^{k}}{k!} + \int_0^x \dfrac{t^n}{n!}e^{x-t} dt.
> \end{align*}
> $$
> On vient donc d'approcher $e^x$ par un polynôme, $\displaystyle \sum_{k=0}^{n} \dfrac{x^{k}}{k!}$, et l'erreur commise dans cette approximation est donnée par l'intégrale $\displaystyle \int_0^x \dfrac{t^n}{n!}e^{x-t} dt$.
> 
> Cette formule est en réalité un cas particulier d'une célèbre formule appelée la *formule de Taylor-Lagrange avec reste intégral*, qui permet de faire exactement cela avec n'importe quelle fonction suffisamment régulière ! Une de ses versions s'énonce ainsi :
> > [!thm] Formule de Taylor-Lagrange avec reste intégral
> > Soit $f$ une fonction de classe $C^{n+1}$ sur un intervalle $I$, et $a,x\in I$. Alors :
> > $$
> > f(x)=\sum_{k=0}^n \frac{f^{(k)}(a)}{k!}(x-a)^k+\int_0^{x-a} \frac{t^n}{n!} f^{(n+1)}(x-t) \mathrm{d} t.
> > $$
> 
> En particulier, pour $a=0$, on a :
> $$
> f(x)=\sum_{k=0}^n \frac{f^{(k)}(0)}{k!}x^k+\int_0^{x} \frac{t^n}{n!} f^{(n+1)}(x-t) \mathrm{d} t,
> $$
> et on retrouve bien la formule obtenue plus haut avec l'exponentielle (puisque toutes les dérivées successives de l'exponentielle sont égales à elle-même).
> 
> La formule de Taylor-Lagrange avec reste intégral se démontre par exemple en raisonnant par récurrence, et en utilisant une intégration par parties pour obtenir l'hérédité.


<!--
 $$
> > f(x)=\sum_{k=0}^n \frac{f^{(k)}(a)}{k!}(x-a)^k+\int_a^x \frac{(x-t)^n}{n!} f^{(n+1)}(t) \mathrm{d} t
> > $$
-->


Pour conclure, il ne reste donc plus qu'à justifier que l'intégrale dans l'égalité $(*)$ tend vers 0 :

> [!thm] Lemme
> $$
> \int_0^x \dfrac{t^n}{n!}e^{-t} dt \ \underset{n\to +\infty}{\longrightarrow} \ 0.
> $$

C'est intuitivement vrai puisque, par croissances comparées, pour tout $t\in \mathbb{R}$, $\dfrac{t^n}{n!} \ \underset{n\to +\infty}{\longrightarrow} \ 0$ ("la factorielle l'emporte sur les suites géométriques"). Cependant, rien n'autorise *a priori* à passer ainsi à la limite sous l'intégrale ; pour justifier cela plus rigoureusement, on va suivre la stratégie classique pour les intégrales à paramètre comme celle-ci, en cherchant à encadrer l'intégrale entre deux quantités qui tendent vers 0.

> [!dem]-
> L'encadrement est un peu pénible à faire, car on ne sait pas quel est le signe de $x$, et les théorèmes permettant d'établir des inégalités sur les intégrales requièrent tous que les bornes des intégrales considérées soient rangées dans le bon ordre. Il faut donc distinguer le cas $x\geq 0$ du cas $x<0$.
> 
> Dans la suite, on va détailler le cas $x\geq 0$ (l'autre cas est relativement similaire - on peut faire se ramener à un cas très proche du premier, en faisant le changement de variable $u=-t$ et en sortant un facteur $(-1)^n$ de l'intégrale). Dans ce cas, pour $t\in [0,x]$, on peut écrire :
> $$
> 0 \leq \dfrac{t^n}{n!}e^{-t} \leq \dfrac{x^n}{n!}e^{-t}
> $$
> et par croissance de l'intégrale (puisque $0\leq x$),
> $$
> 0 \leq \int_0^x \dfrac{t^n}{n!}e^{-t} dt \leq \int_0^x \dfrac{x^n}{n!}e^{-t} dt
> $$
> Pour montrer que $\displaystyle \int_0^x \dfrac{t^n}{n!}e^{-t} dt \ \underset{n\to +\infty}{\longrightarrow} \ 0$, il suffit donc, par encadrement, de montrer que le membre de droite ci-dessus tend vers 0. Or ce membre se calcule très bien :
> $$
> \int_0^x \dfrac{x^n}{n!}e^{-t} dt =  \dfrac{x^n}{n!} \int_0^x e^{-t} dt = \dfrac{x^n}{n!} \left( 1-e^{-x} \right) \ \underset{n\to +\infty}{\longrightarrow} \  0.
> $$
> (par croissances comparées, la suite factorielle l'emportant sur les suites géométriques.)
> 
> Ainsi, par encadrement, cela établit la limite souhaitée.

Conclusion : au vu de l'égalité $(*)$ établie plus haut et du lemme que l'on vient de prouver, on a donc bien
$$
\sum_{k=0}^{n} \dfrac{x^{k}}{k!} = f_n(x) =  e^x - e^x \int_0^x \dfrac{t^n}{n!}e^{-t} dt \ \underset{n\to +\infty}{\longrightarrow} \  e^x.
$$
CQFD !