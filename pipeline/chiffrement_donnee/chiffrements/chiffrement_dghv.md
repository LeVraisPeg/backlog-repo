Page de l'article : [cliquer ici](https://www.utc.fr/~wschon/sr06/tx_chiffrement_homomorphe/pages/dghv.html)

# 🔐 Chiffrement DGHV (Dijk-Gentry-Halevi-Vaikuntanathan)

## 📌 Introduction

Le chiffrement DGHV est une version simplifiée du premier chiffrement totalement homomorphe de Craig Gentry (2009).  
Il permet d'effectuer des opérations arithmétiques (additions et multiplications) directement sur des données chiffrées.

Ce cryptosystème repose sur deux problèmes mathématiques réputés difficiles :

-   **PGCD approché (Approximate Greatest Common Divisor)** : utilisé pour la génération de la clé publique.
-   **Problème de la somme de sous-ensembles clairsemée (Sparse Subset Sum Problem)** : assure la sécurité du chiffrement avec la clé publique.

Il ne permet que de chiffrer des elements compris entre 0 et 1.
Ainsi, pour chiffrer un nombre, il est necessaire de l'écrire sous sa représentation binaire et conserver l'ordre des bianaires au cours des opérations.

---

## 🔧 Fonctionnement

### 🔐 Version symétrique

-   **Clé privée** : un entier impair \( p \), généré aléatoirement.
-   **Chiffrement** : pour un bit \( $m \in \{0,1\}$ \), on calcule  
    \( $c = p \cdot q + 2r + m$ \),  
    où \( q \) et \( r \) sont des entiers aléatoires.
-   **Déchiffrement** :  
    \( $m = (c \mod p) \mod 2 $\).

Ce chiffrement est probabiliste (le même bit peut donner différents chiffrés).

### 🔐 Version asymétrique

Pour le chiffrement asymétrique, la sécurité est prrouvé si : $\lambda < \rho < \eta < \mu < \theta$, avec :

-   $\lambda$ : le degré de sécurité.
-   $\eta (=\lambda^2)$ : la taille de la clé privée p.
-   $\theta$ le nombre de composant $x_i$ composant la clef publique
-   $\rho$ : la taille du bruit

Ainsi, pour générer les différents composants, on a:

-   **Clé privée** : un entier impair \( p \) aléatoire dans $[2^{\eta-1}, 2^{\eta}]$.
-   **Clé publique** : une liste de valeurs \($ x_i = p \cdot q_i + 2r_i $\), qui sont des chiffrés de 0 avec $x_0$ le maximum impaire des $x_i$ .
-   **Chiffrement** : consiste à additionner un sous-ensemble aléatoire de ces \( $x_i$ \), ajouter le message et un petit bruit.
-   **Déchiffrement** : même que dans la version symétrique.

---

## ➕➗ Propriétés homomorphes

Le schéma DGHV est totalement homomorphe, c’est-à-dire qu’il permet :

-   **Addition homomorphe** :  
    \( $\text{Enc}(m_1) + \text{Enc}(m_2) = \text{Enc}(m_1 + m_2) $\).
-   **Multiplication homomorphe** :  
    \( $\text{Enc}(m_1) \times \text{Enc}(m_2) = \text{Enc}(m_1 \cdot m_2)$ \).

⚠️ Chaque opération augmente le bruit. Trop de bruit empêche le déchiffrement.  
En effet, par exemple si le bruit est $3$ et $p=5$, on a : $2\times3 [5] = 1 = 1[2]$

---

## ⚙️ Circuits binaires

Les opérations sur les entiers sont construites avec des circuits logiques :

-   **Additionneur complet** :
    -   \( $\text{Somme} = a \oplus b \oplus r$ \)
    -   \($ \text{Retenue} = (a \land b) \lor ((a \oplus b) \land r) $\)
-   **Multiplication** :
    -   Basée sur la multiplication binaire classique (produit de bits + additions avec décalage).

---

## 📘 Ressources

-   Implémentation en SageMath : [coron/fhe](https://github.com/coron/fhe)
-   Article original : _"Fully Homomorphic Encryption over the Integers"_, Dijk, Gentry, Halevi, Vaikuntanathan
