---
title: Autour de l'exponentielle complexe
prérequis: Complexes
draft: true
---
The following conditions are equivalent:

1. $f$  is real analytic on an open set $D$.
2. There is a complex analytic extension of $f$  to an open set $G\subset \mathbb{C}$ which contains $D$.
3. $f$  is smooth and for every compact set $K ⊂ D$  there exists a constant  $C$  such that for every $x \in K$ and every non-negative integer $k$  the following bound holds :
$$
\left|\frac{d^k f}{d x^k}(x)\right| \leq C^{k+1} k!
$$

[preuve de la dérivabilité d'une série entière](https://math.stackexchange.com/questions/186922/how-to-show-that-power-series-is-analytic-inside-the-radius-of-convergence)

[preuve qu'une série entière est analytique](https://math.stackexchange.com/questions/3161105/analytic-function-and-power-series-expansion)

## Histoire

### Séries entières

D'abord en Inde (13e-16e), par des astronomes de l'école du Kerala (école de Maths et d'astronomie), notamment **Madhava** (le fondateur de l'école, dit-on), pour faciliter les calculs d'astronomie - mais ces connaissances n'ont pas atteint l'europe

Puis redécouvert indépendamment au 17e en Europe, pour faciliter les calculs d'astronomie, de cartographie, de navigation, faisant intervenir des fonction trigo, expo, ou log.

Newton (1669) : usage systématique de séries entières pour résoudre des problèmes d'analyse (calculs d'aires, calculs de valeurs de fonctions, résolution d'EDs)

Gregory (1671) : formule de la série de Taylor d'une fonction en un point

Some power series, like the geometric progression were indeed encountered since the ancient times, but **the first person who used them systematically was Isaac Newton**. Actually Newton considered this his main mathematical discovery: that any equation (algebraic, differential, etc.) can be solved by substituting a power series with undetermined coefficients, and then the coefficients can be found successively. This is the essential message of his two coded sentences which he sent to Leibniz via Oldenburg. You may read here a discussion about these coded messages: [https://mathoverflow.net/questions/140327/arnold-on-newtons-anagram](https://mathoverflow.net/questions/140327/arnold-on-newtons-anagram) It is clear from Newton's mathematical papers, that for him "calculus" was essentially the use of power series. Mathematicians of 18s century started immediately using them for all sorts of problems. However they mostly did formal manipulations. The rigorous theory of convergence goes back to Cauchy and Abel. After that the theory essentially merged to the theory of analytic functions.

## Logarithme

**XVIIe siècle**

Motivation historique : faciliter les calculs de produits. Avant l'apparition du logarithme, on utilisait à la place des tables trigonométriques et les formules d'addition de trigo pour convertir des sommes en produits.

- début 17e : tables logarithmiques introduites, en lien avec les suites géométriques, pour faciliter la conversion somme $\leftrightarrow$ produit. Puis développé par **Neper** qui prend un point de vue en lien avec ce que l'on appellerait aujourd'hui des équations différentielles.
- milieu 17e : comportement logarithmique rencontré une seconde fois par les matheux dans le cadre de la recherche de l'aire sous la courbe de la fonction inverse
- seconde moitié 17e : DSE de $\ln$ et $\exp$ (Mercator, Newton, Leibniz)
	- DSE de $\exp$ en 1665 par Newton (démo non rigoureuse ?)
- fin du 17e : introduction de la fonction exponentielle (Bernoulli, Leibniz) :
	- d'abord comme généralisation progressive des puissances entières, puis fractionnaires
	- puis comprise par Leibinz comme réciproque de $\ln$.
	- Bernoulli : lien fait aussi avec ce qui se produit quand on chercher à rendre continus des intérêts annuels, en les divisant en des intérêts $n$ fois plus petits toutes les $1/n$ années : cela fait apparaître la formule $\left(  1+ \frac{x}{n}  \right)^n$.