Articles
------

source : [wikipedia](https://fr.wikipedia.org/wiki/K-anonymisation)

>K-anonymisation

Le principe est de cacher des éléments de quasi identification d'un individu en les regroupant dans des representation plus large tout en conservant la visibilité des informations visées à être partagée.  
Par exemple : 
$$
[Emilie, 24 ans, Femme] \rightarrow [*, 10 <Age \leq 30, Femme]
$$

-------

source : [revue de psychologie](https://www.persee.fr/doc/bupsy_0007-4403_1979_num_33_343_1128)

L'objectif, ici, est de brouiller les données récupérer en remplaçant les données réelles par des données aléatoire.  
En connaissant la probabilité d'avoir une valeur aléatoire, il est alors possible de déterminer la proportion de donnée réelle ainsi que la variance au sein des données.  

**Remarque:** dans cet article, le système de données étudié est un sytème de réponse booléenne.  
Une adaptation sur des données réelles pourrait être réalisées en considérant des plages de valeurs et en étudiant la probabilité et l'espérance d'une valeur à apartenir à une plage de valeur specifique.

-------

source : [wikipedia](https://en.wikipedia.org/wiki/Additive_noise_differential_privacy_mechanisms)

> Mechanisme de Laplace

On construist notre fonction de bruitage a partir de la fonction de la fonction de distribution cumulée : 
$$
F(x) =
\begin{cases}
\frac{1}{2} \exp\left( \frac{x - \mu}{b} \right) & \text{si } x < \mu \\
1 - \frac{1}{2} \exp\left( -\frac{x - \mu}{b} \right) & \text{si } x \geq \mu
\end{cases}
$$
à partir de la fonction  de la densité de probabilité:
$$
f(x, (\mu,\epsilon)) = \frac{1}{2b}e^{-\frac{|x-\mu|}{b}}
$$ 
, où :
- $\mu$ est la médiane de la distribution.
- $b$ est le paramètre qui contrôle la dispersion. Plus $b$ est grand, plus le bruit est important.  

En posant $u$ la variable aléatroire tel que $u=F(x)$,
on a alors que : 
$$
x =
\begin{cases}
\mu + b \times ln(2u)& \text{si } x < \mu \\
\mu - b\times ln(2(1-u))& \text{si } x \geq \mu
\end{cases}
$$

Pour générer du bruit, on prend $\mu=0$ et $b=\frac{M_f}{\epsilon}$, où $M_f$ la valeur définie sur  un ensemble $D$ tel que : $M_f = max_{(x,y) \in D^2}\{|f(x)-f(y)|\}$.  
A partir de ces paramètres, plus $\epsilon$ est faible, plus le bruit généré sera important et inversement.

> Méchanisme Gaussien

On construist notre fonction de bruitage a partir de la fonction de la fonction de distribution cumulée : 
$$
F(x) =\frac{1}{2}[1 + erf(\frac{x-\mu}{\rho})]
$$
,avec $erf(x) := \int_0^xe^{-t^2}dt$.

Cette distribution cumulée est obtenue à partir de la fonction  de la densité de probabilité:
$$
f(x, (\mu,\rho))= \frac{1}{\sqrt{2\pi\rho^2}}e^{\frac{-(x-\mu)^2}{2\rho^2}}
$$ 
, où :
- $\mu$ est la médiane de la distribution.
- $\rho^2$ est la variance.

En posant $u$ la variable aléatroire tel que $u=F(x)$,
on a alors que : 
$$
x =\mu + \rho \times erf^{-1}(2u-1)
$$

Pour générer du bruit, on prend $\mu =0$ et $\rho^2 = \frac{2ln(1.25/ \delta)\times M_f^2}{\epsilon^2}$.  
Ici, $\delta$ et $\epsilon$ apprartiennent à $]0,1[$

**Remarque:** si $f:D\rightarrow \mathbb{R}^d$, il est possible de générer du bruit

-----------------------------
source : [ Abounded-noise mechanism for differential privacy](https://proceedings.mlr.press/v178/dagan22a/dagan22a.pdf)

> Mise en place de bruits bornés

L'article présente un méchanisme de bruitage avec u bruit borné afin de répondre au problème d'erreur lié à l'utilisation du méchanisme gaussien dans le cadre d'un modèle intéractif.
En effet, la génération du bruit va s'adapter en fonction du nombre de requetes d'informations.

L'article met en avant deux résultats:
- Génération d'erreur maximale par rapport à $k$ (le nombre de requêtes) est de l'odre de $O(M\sqrt{klog(1/\delta)}/\epsilon)$, avec $M$ la sensibilité de la fonction.

- Amélioration du mecanisme gaussien, car l'augmentation de la génération de bruit est plus faible. 

L'algorithme utilisé est l'algorithme 2 présent dans la section E.

--------------
source : [Pufferfish](https://www.nature.com/articles/s41598-024-84084-x)

L'article présente un algorithme de confidentialité Pufferfish basé sur le model de mélange Gaussien.

**Définition :** On dit que $X$ est un modèle de mélange gaussien si la fonction de densité de $X$ vérifie :
$$
p(x) = \sum_{i=1}^M w_iN(x|\mu_i,\Epsilon_i)
$$
,où $w_i$ vérifie : $\sum_{i=1}^M w_i = 1$ et $(\mu_i,\Epsilon_i)\in\mathbb{R}^d\times \mathbb{R}^{d\times d}$, d la dimension de l'ensemble de données, sont la moyenne et le paramètre de covariance de la i-ème composante.  
$N$ est une loi normal.

-----------------------------
source : [National library of medecine](https://pmc.ncbi.nlm.nih.gov/articles/PMC3904646/#R1)

> Calcul de variance via ensemble connu

On considère deux jeux de données : $\mathbb{E}$ (publique) et $\mathbb{D}$ (privé).  
Ici, l'objectif est de connaitre l'esperance d'une fonction $b$ sur la loi de distribution $p_D(.)$ tiré de l'ensemble $\mathbb{D}$ en utilisant la loi de distribution sur $\mathbb{E}$, noté $p_E(.)$ ainsi que les donnée de $ 

On cherche utiliser $\mathbb{E}$ pour estimer l'esperance de $\mathbb{D}$.

L'objectif est donc de trouver une fonction poids $w(.)$ pour chaque $x$ de $\mathbb{E}$ tel que pour toute fonction $b(.)$ on ait approximativement :
$$
E_{x \sim p_D}[b(x)] = \frac{1}{N_E}\sum_{x\in \mathbb{E} }b(x)w(x)
$$
avec $N_E$ (resp. $N_D$) la cardinalité de  $\mathbb{E}$ (resp.  $\mathbb{D}$).  
 $\mathbb{E}$ étant publique, en publiant les poids $(w(x))_{x\in\mathbb{ \mathbb{E}}}$ de manière à conserver la confidentialité différentielle, les personnes exterieur peuvent déterminer $E_D[b(x)]$ sans violer la confidentialité.

 L'algorithme 1 permet de générer ces poids.
 Il est alors possible de déterminer l'espérance d'en semble d'élément partir d'un ensemble de référence sans fournir de données privée.

----------

> Mecanisme exponentiel

Le mécanisme exponentiel est un algorithme qui permet de faire un choix parmi plusieurs sorties possibles tout en garantissant la confidentialité différentielle des données.

Pour cela, on défini une fonction d'utilité $u(.,.)$ qui mesure l'interet/qualité de la donnée choisie $r$ par rapport à aux données $D$.
le mécanisme choisit une sortie r avec une probabilité qui est en fonction de cette utilité grâce à :
$$
P(r) = e^{\frac{\epsilon u(D,r)}{2M_u}}
$$
,où :
- $M_u$ est la sensibilité de $u$. 
- $\epsilon$ le budget de confidentialité.

Par exemple:  
Dans une base de donnée de films, m films possèdent les meilleures note, noté $(n_i)_{i\in [0,m-1]}$, on note $n$ la meilleure note et on définie $u$ par : 
$$
u(D,r) = min_{d\in D} distance(d,r)
$$
On cherche donc les films les plus proches de r.

On détermine alors $M_u:= max_{x}|u(D,x) - u(D',x)|$, où D et D' sont deux bases voisines.

Pour chaque film $r\in Recommandation$ on détermine : 
$$
P(r)=e^{\epsilon. u(D,r)/2M_u}
$$
et on normalise les résultats obtenus.

Une fois cetrte distribution obtenue, on tire alors au hasard, un film parmi les recommandations.

----

FrameWork
----
source : [Differential Privacy](https://flower.ai/docs/framework/explanation-differential-privacy.html)

Présentation de framework pour la mise en place de confidentialité privée avec une mise en place de central differntial privacy avec le machanisme gaussien