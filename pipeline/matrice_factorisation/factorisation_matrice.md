Factorisation de matrice:
---

Factorisation de la matrice de donnée en produit de deux matrice représentant les caractéristique « cachée » qui influence les préférences des utilisateurs.
Pour générer ce produit, on peut combiner l’algorithme des moindres carrés alternés (ALS) et la descente de gradient stochastique (SGD).


En alternant jusqu’à obtenir une convergence avec ALS, on : 
- on corrige la matrice « utilisateur » et on optimise la matrice « caractéristique cachée »
- on corrige la matrice « item » et on optimise la matrice « caractéristique cachée »

Avantages :
- approche utile pour des problèmes de factorisation de matrices à grande échelle et peut gérer les retours explicites et implicites.
---
SGD permet de mettre à jour le modèle après chaque entraînement.

Avantages : 
- plus rapide et plus adapté aux grands ensembles de données
- adaptation facile aux nouvelles donnée (bien pour les scénario d’apprentissage en ligne (il faut vérifier les donnée d’apprentissage)).
---
données synthétique :
- contrôle la complexité et les caractéristiques des données, permet l’apprentissage sans le bruit des données.
- reproductible : le code obtiendra les même données et résultat
- confidentialité et accessibilité
- illustration facile de comment les changements dans les données affectent les performances du modèle

Existence de bibliothèque python pour la factorisation matricielle et le filtrage collaboratif qui sont optimisée, et évolutives (adaptées aux environnement de production) : Surprise, LightFM et implicit.

comment recommander ?
→ recommander les éléments ayant la note prédites les plus élevées pour chaque utilisateur.
→ Il existe  différentes mesures d’évaluation des systèmes de recommandation pour différent scénario (check autre article)

Avantages de la factorisation de matrice au filtrage collaboratif :
- Évolutivité : adaptation aux grands ensembles de données par rapport au (fc)
- Sparsité : gère les données clairsemée
- Démarrage à froid : peut mieux gérer les problèmes de démarrage à froid en utilisant des fonctionnalité latentes.
- Flexibité : peut être étendu pour intégrer des informations supplémentaires (rétroaction implicites/dynamique temporelle)
- Interprétabilité : les caractéristiques latentes peuvent fournir des informations sur les préférences des utilisateurs et sur les caractéristiques des éléments.


Avantages globaux : 
- Effectue une réduction de dimensionnalité
- Peut fournir des facteurs latents interprétables
- Effectue une réduction de dimensionnalité

Défis :
- démarrage à froid pour les nouveaux utilisateurs ou élément.
- réglage minutieux des hyperparamètres.
- beaucoup de calculs pour de très grands ensembles de données

Recommandation :
- problèmes démarrage à froid : modèle hybride pour les nouveaux utilisateurs
- réglage des hyperparamètres : utilisation de techniques comme la validation croisée ou l’optimisation baysiènne pour trouver éfficacement les paramètres optimaux.