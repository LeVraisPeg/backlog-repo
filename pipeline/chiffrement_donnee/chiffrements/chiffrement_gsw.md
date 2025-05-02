Page de l'article : [cliquer ici](https://www.utc.fr/~wschon/sr06/tx_chiffrement_homomorphe/pages/vecteurs_propres_approx.html)

# 🔐 Chiffrement GSW (Gentry–Sahai–Waters)

## 📌 Introduction

Le chiffrement GSW est un schéma symétrique "somewhat" homomorphe, c’est-à-dire qu’il permet un nombre limité d’opérations homomorphes.  
Il repose sur la notion de **vecteurs propres approximés** :

$s \cdot C = s \cdot m + e$

où \( s \) est un vecteur privé, \( C \) une matrice chiffrée, \( m \) le message, et \( e \) un vecteur non nul choisi.

---

## 🔧 Fonctionnement

### 🔐 Chiffrement

-   **Clé privée** : un vecteur \( s \)
-   **Clé publique** : une matrice \( A \) construite à partir de \( s \) et d’un bruit \( e \), ie $A.s = e$
-   **Chiffrement** : pour un message $ m,C = A \cdot r + m \cdot G$

où \( r \) est un vecteur aléatoire et \( G \) une matrice gadget, ie la matrice tel que $G.bits(C) = C$.

### 🔓 Déchiffrement

On calcule :

$s \cdot C \cdot G^{-1} = e \cdot G^{-1} + m \cdot s$

Le message \( m \) est extrait en analysant ce résultat.

---

## ➕➗ Propriétés homomorphes

Le schéma GSW permet :

-   **Addition homomorphe** :  
    $ C\_{\text{add}} = C_1 + C_2 $

-   **Multiplication homomorphe** :  
    $C\_{\text{mult}} = C_1 \cdot G^{-1}(C_2) $

⚠️ Le bruit augmente à chaque opération.
En effet, G dépend de C qui dépend elle même du bruit e.

---

## 🧩 Sécurité basée sur le problème LWE

La sécurité repose sur le problème **LWE (Learning With Errors)** :

-   Il s’agit de retrouver un vecteur secret à partir d’équations bruitées.
-   Le bruit garantit la difficulté du problème, même pour des ordinateurs quantiques.

---

## ⚙️ Optimisations : matrice gadget et décomposition binaire

-   **Matrice gadget \( G \)** : facilite le déchiffrement.
-   **Décomposition binaire** : rend les opérations plus efficaces et contrôle le bruit.

---

## 📘 Ressources

-   Article original : [eprint.iacr.org/2013/340](https://eprint.iacr.org/2013/340.pdf)
-   Présentation : [Zvika Brakerski sur YouTube](https://www.youtube.com/watch?v=O8IvJAIvGJo)
