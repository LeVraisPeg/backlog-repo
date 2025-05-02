Page de l'article : [cliquer ici](https://linc.cnil.fr/on-a-teste-le-chiffrement-homomorphe)

# 🔐 Chiffrement homomorphe

## 🧪 On a testé le chiffrement homomorphe

Ce document est un résumé d'un article portant sur l’expérimentation du chiffrement homomorphe (FHE) dans un contexte d’apprentissage automatique.

## ✅ Avantages du chiffrement homomorphe (FHE)

Le FHE permet d'effectuer des calculs directement sur des données chiffrées, garantissant ainsi trois propriétés essentielles :

1. **Protection des données d’apprentissage** pendant l'entraînement.
2. **Protection des données en entrée** lors de l’utilisation d’un modèle.
3. **Protection des données en sortie**, même dans un environnement cloud.

Le serveur exécutant les calculs ne voit jamais les données en clair.  
L’entraînement de modèles sur données chiffrées est encore un défi, mais en progrès.

## ⚠️ Limites et défis du FHE

-   **Performances faibles** : calculs lents, forte consommation mémoire.
-   **Surcoût en stockage** : taille des données chiffrées jusqu’à 1000 fois supérieure.
-   **Difficultés mathématiques** : rétropropagation et fonctions d’activation difficilement compatibles avec le chiffrement.
-   **Perte de précision** due à l’encodage et à la difficulté de modéliser les non-linéarités.
-   **Temps d’inférence élevé** et besoin d’adaptations spécifiques des modèles.

## 🛠️ Resources pour implementer FHE

-   _SEAL_ (Microsoft)
-   _HElib_ (IBM)
-   _OpenFHE_ (Duality)
-   le framework **Concrete**.

Ce dernier simplifie le développement via un compilateur adapté. Il prend en charge plusieurs modèles standards (SVM, régressions, arbres...).  
Les réseaux de neurones personnalisés nécessitent des ajustements manuels.

## 📌 Recommandations

-   **Favoriser les modèles linéaires**, plus facilement compatibles avec le chiffrement.
-   **Modèles non-linéaires à éviter** en contexte FHE jusqu’à amélioration des techniques.

---
