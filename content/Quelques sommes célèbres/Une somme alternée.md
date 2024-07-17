---
ordre: 20
---
$$
1-\dfrac{1}{2}+\dfrac{1}{3}-\dfrac{1}{4}+\ldots = \ln(2), \qquad \text{i.e.} \qquad \sum_{k=1}^{+\infty} \dfrac{(-1)^{k-1}}{k} = \ln(2)
$$
> [!thm] Théorème
> $$
> \sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k} \underset{n\to +\infty}{\longrightarrow} \ln(2)
> $$

> [!dem]- Démonstration
> Il est parfois utile, en maths, de réaliser que le problème que l'on étude n'est en fait qu'un cas particulier d'un problème certes plus général, mais plus facile à étudier. Ici, par exemple, au lieu de s'intéresser seulement à la somme mentionnée dans le théorème ci-dessus, on va élargir nos ambitions et considérer plutôt la **fonction** $f_n$ définie par :
> $$
> f_n(x)=\sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k}x^k.
> $$
> La somme qui nous intéresse n'est alors autre que $f_n(1)$.
> 
> Mais quel est l'intérêt de complexifier ainsi le problème en introduisant une fonction ? Eh bien, cela permet d'enrichir l'éventail des outils à notre disposition : parler de fonctions, cela débloque toute la puissance de l'Analyse ! On est ainsi face à un objet certes plus compliqué, mais on dispose de beaucoup plus d'armes pour le combattre.
> En l'occurrence, parmi les nombreuses choses que l'on peut faire avec les fonction, il y a ... la **dérivation**.
> $$
> f_n'(x) = \sum_{k=1}^{n} \dfrac{(-1)^{k-1}}{k}kx^{k-1} = \sum_{k=1}^n  (-x)^{k-1} = \sum_{k=0}^{n-1}  (-x)^{k}
> $$
> 

