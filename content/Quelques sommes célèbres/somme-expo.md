---
ordre: 30
title: La série exponentielle
---
La fonction exponentielle apparait à la fin du XVIIe siècle, à travers les travaux de Newton, Jean Bernoulli et Leibniz, suite notamment à un volonté d'étendre la notion de puissance aux puissances non-entières (i.e. de donner un sens à $x^y$, pour $y$ un réel quelconque). Elle sera ensuite mise en relation avec d'autres concepts, Leibniz explicitant par exemple son lien avec le logarithme.

C'est Newton, en 1665, qui est le premier à énoncer ce que l'on appelle de nos jours le *développement en série entière* de l'exponentielle :
$$
e^x = 1+ x + \dfrac{x^2}{2!}+\dfrac{x^3}{3!} + \dfrac{x^4}{4!} + \ldots
$$
Dit plus formellement :

> [!thm] Théorème (développement en série entière de l'exponentielle)
> $$
> \sum_{k=0}^{+\infty} \dfrac{x^{k}}{k!} = e^x, \qquad \text{i.e.} \qquad \sum_{k=0}^{n} \dfrac{x^{k}}{k!} \underset{n\to +\infty}{\longrightarrow} e^x.
> $$

^7e582b

Dans cette page, on va présenter une démonstration de ce théorème. Surtout, on verra ensuite que la méthode de démonstration adoptée peut en fait se généraliser à de nombreuses autres fonctions, permettant par exemple d'obtenir des écritures similaires pour $\cos$ et $\sin$ ! 

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


<!--
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
-->

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

> [!dem]- Démonstration
> L'encadrement est un peu pénible à faire, car on ne sait pas quel est le signe de $x$, et les théorèmes permettant d'établir des inégalités sur les intégrales requièrent tous que les bornes des intégrales considérées soient rangées dans le bon ordre. Il faut donc distinguer le cas $x\geq 0$ du cas $x<0$.
> 
> Dans un souci de simplicité, on va seulement détailler ici le cas $x\geq 0$ (l'autre cas est relativement similaire, bien qu'un chouïa plus compliqué). Dans ce cas, pour $t\in [0,x]$, on a $e^{-t}\leq 1$, et donc  :
> $$
> 0 \leq \dfrac{t^n}{n!}e^{-t} \leq \dfrac{x^n}{n!}
> $$
> d'où par croissance de l'intégrale (puisque $0\leq x$),
> $$
> 0 \leq \int_0^x \dfrac{t^n}{n!}e^{-t} dt \leq \int_0^x \dfrac{x^n}{n!} dt = \dfrac{x^{n+1}}{n!}.
> $$
> Or par croissances comparées, $\dfrac{x^{n+1}}{n!} \ \underset{n\to +\infty}{\longrightarrow} \ 0$ (la suite factorielle l'emportant sur les suites géométriques). Par conséquent, par encadrement :
> $$
> \displaystyle \int_0^x \dfrac{t^n}{n!}e^{-t} dt \ \underset{n\to +\infty}{\longrightarrow} \ 0.
> $$


Conclusion : au vu de l'égalité $(*)$ établie plus haut et du lemme que l'on vient de prouver, on a donc bien
$$
\sum_{k=0}^{n} \dfrac{x^{k}}{k!} = f_n(x) =  e^x - e^x \int_0^x \dfrac{t^n}{n!}e^{-t} dt \ \underset{n\to +\infty}{\longrightarrow} \  e^x.
$$
CQFD !

## Généralisation : les séries de Taylor


Prenons un peu de recul sur le chemin parcouru. Pour arriver à nos fins, nous avons essentiellement raisonné en deux temps :

1. D'abord, on a obtenu l'égalité $(*)$ :
$$
f_n(x)=e^x g_n(x) = e^x - e^x \int_0^x \dfrac{t^n}{n!}e^{-t} dt. \qquad (*)
$$
En passant l'intégrale de l'autre côté de l'égalité, cela revient à dire :
$$
\begin{align*}
&e^x = f_n(x) + e^x \int_0^x \dfrac{t^n}{n!}e^{-t} dt \\[10pt]
\text{i.e.} \quad & \boxed{e^x = \displaystyle \sum_{k=0}^{n} \dfrac{x^{k}}{k!} + \int_0^x \dfrac{t^n}{n!}e^{x-t} dt.} \qquad (\ast \ast)
\end{align*}
$$
En bref, **on a approché $e^x$ par un polynôme**, $\displaystyle \sum_{k=0}^{n} \dfrac{x^{k}}{k!}$, et **l'erreur commise dans cette approximation est donnée par une intégrale**, $\displaystyle \int_0^x \dfrac{t^n}{n!}e^{x-t} dt$.

2. Puis on a montré que **l'intégrale tendait vers 0**. Cela venait essentiellement du fait que :
	- le terme en $\frac{t^n}{n!}$ devient très petit quand $n$ tend vers l'infini ;
	- le terme en $e^{x-t}$ n'avait pas d'impact (car on peut l'encadrer entre des quantités ne dépendant ni de $n$ ni de $t$).


Ce qui est remarquable, c'est que toute cette démarche n'est absolument pas spécifique de l'exponentielle : on peut en fait généraliser tous ces résultats pour produire des formules similaires à la pelle !

1. Toute fonction suffisamment régulière peut être écrite comme la somme d'un polynôme et d'une intégrale, de façon similaire à $(**)$. En fait, $(**)$ est un cas particulier d'une célèbre formule appelée la *formule de Taylor-Lagrange avec reste intégral*, dont une version s'énonce ainsi :

> [!thm] Formule de Taylor-Lagrange avec reste intégral
> Soit $f$ une fonction de classe $C^{n+1}$ sur un intervalle $I$, et $a,x\in I$. Alors :
> $$
> f(x)=\sum_{k=0}^n \frac{f^{(k)}(a)}{k!}(x-a)^k+\int_0^{x-a} \frac{t^n}{n!} f^{(n+1)}(x-t) \mathrm{d} t.
> $$
 
> En particulier, pour $a=0$, on a :
>$$
>f(x)=\sum_{k=0}^n \frac{f^{(k)}(0)}{k!}x^k+\int_0^{x} \frac{t^n}{n!} f^{(n+1)}(x-t) \mathrm{d} t,
>$$
> et l'on retrouve bien la formule $(**)$ obtenue plus haut avec l'exponentielle (puisque toutes les dérivées successives de l'exponentielle sont égales à elle-même).
> 
> La formule de Taylor-Lagrange avec reste intégral se démontre par exemple en raisonnant par récurrence, et en utilisant une intégration par parties pour obtenir l'hérédité (laissé en exercice pour le lecteur !)

2. Si, à $x$ fixé, on peut majorer $|f^{(n+1)}(x-t)|$ par une constante (ne dépendant ni de $n$, ni de $t$), alors de façon similaire à ce que l'on a fait plus haut avec l'exponentielle, on peut montrer par encadrement que
$$
\int_0^x  \frac{t^n}{n!} f^{(n+1)}(x-t) \mathrm{d} t \ \underset{n\to +\infty}{\longrightarrow} \  0
$$
ce qui entraîne au vu de la formule de Taylor-Lagrange que :
$$
\sum_{k=0}^n \frac{f^{(k)}(0)}{k!}x^k \ \underset{n\to +\infty}{\longrightarrow} \  f(x).
$$


Cela justifie donc le résultat suivant :

> [!thm] Théorème
> Soit $f:\mathbb{R}\to \mathbb{R}$. On suppose que :
> 1. $f$ est de classe $C^{\infty}$ sur $\mathbb{R}$.
> 2. Il existe un $r>0$ tel que les dérivées successives de $f$ sont uniformément bornées sur $[-r,r]$, i.e. :
> $$
> \exists M>0 \text{ tq } \forall n\in \mathbb{N},\  \forall x\in [-r,r], \ |f^{(n)}(x)|\leq M.
> $$
> (notez bien que la constante $M$ est **indépendante de n**.)
> 
> Alors :
> $$
> \forall x \in [-r,r], \quad \sum_{k=0}^{n} \dfrac{f^{(k)}(0)}{k!}x^k \ \underset{n\to +\infty}{\longrightarrow} \ f(x),
> $$
> ou autrement dit, la fonction $f$ peut se *développer en série entière* sous la forme :
> $$
> \forall x \in [-r,r], \quad f(x)= \sum_{k=0}^{+\infty} \dfrac{f^{(k)}(0)}{k!}x^k.
> $$

^thm-condition-DSE

**Exemples**\
Si $f=\cos$, alors $f'=-\sin$, $f''=-\cos$, $f^{(3)}=\sin$, $f^{(4)}=\cos$, et ainsi de suite, les dérivées successives se répétant avec une période 4. Par conséquent :
- Toutes les dérivées successives de $f$ sont majorées par 1 en valeur absolue, les hypothèses du théorème précédent sont donc vérifiées, quel que soit le $r>0$ considéré.
- Les valeurs successives de ces dérivées en 0 sont :
$$
\begin{align*}
f(0) &= 1\\
f'(0) &= 0\\
f''(0) &= -1\\
f^{(3)}(0) &= 0\\
\vdots & 
\end{align*}
$$
et ainsi de suite, en répétant ce motif.

Par conséquent, le théorème précédent donne :

> [!thm] Développement en série entière du cosinus
> $$
> \forall x\in \mathbb{R}, \quad \cos(x) = 1-\frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \ldots = \sum_{k=0}^{+\infty} \dfrac{(-1)^k x^{2k}}{(2k)!}
> $$

^thm-DSE-cos

Et de même, on trouve une formule similaire pour la fonction sinus :

> [!thm] Développement en série entière du sinus
> $$
> \forall x\in \mathbb{R}, \quad \sin(x) = x-\frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \ldots = \sum_{k=0}^{+\infty} \dfrac{(-1)^k x^{2k+1}}{(2k+1)!}
> $$

Comme pour le développement en série entière de l'exponentielle, ces deux formules ont été énoncées par Newton dans la seconde moitié du XVIIe siècle. Cependant, leur première apparition est en réalité bien plus ancienne : on attribue leur paternité au mathématicien indien Madhava de Sangamagrama, vers 1400, fondateur de l'école mathématique et astronomique du Kerala. En son hommage, les séries $1-\frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \ldots$  et $x-\frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \ldots$ sont parfois appelées *séries de Madhava*.

Madhava décrivait le développement en série entière du sinus en ces termes (traduits en anglais) :

> "Multiply the arc by the square of the arc, and take the result of repeating that (any number of times). Divide by the squares of the successive even numbers (such that current is multiplied by previous) increased by that number and multiplied by the square of the radius. Place the arc and the successive results so obtained one below the other, and subtract each from the one above. These together give the [jiva](https://en.wikipedia.org/wiki/Jy%C4%81,_koti-jy%C4%81_and_utkrama-jy%C4%81 "Jyā, koti-jyā and utkrama-jyā") [sine]"

Les travaux de Madhava n'ont vraisemblablement jamais atteint l'Europe ; il aura fallu attendre le XVIIe siècle pour que les mathématiciens européens redécouvrent indépendamment cette même formule, et l'énoncent avec le formalisme que l'on connaît aujourd'hui.

Pour plus de détails, vous pouvez consulter le très intéressant [premier chapitre](https://assets.cambridge.org/97805211/14707/excerpt/9780521114707_excerpt.pdf) de *Sources in the Development of Mathematics : Infinite Series and Products from the Fifteenth to the Twenty-first Century*, par Ranjan Roy.


