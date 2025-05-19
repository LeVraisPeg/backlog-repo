# Description du Sprint 3 – Recommandation à froid, Deep Learning & Sécurité des données

## Objectif du Sprint 3  
Ce sprint visait à **étendre les capacités du moteur de recommandation** en introduisant un **système de recommandation à froid** (cold-start) pour les nouveaux utilisateurs, à **renforcer la confidentialité des données** avec une couverture complète du bruitage, et à **poursuivre les améliorations du modèle de deep learning**.  
Des optimisations de l’IHM et de la base de données ont également été entreprises afin de préparer un système plus fluide et maintenable.

## Durée  
75 heures

---

## Activités réalisées

### 1. Recommandation à froid  
Mise en place d’un **système de recommandation à froid**, permettant de suggérer des contenus même en l’absence d’historique utilisateur :  
- **Étude des approches basées sur le contenu** pour le cold-start  
- Mise en place d’un algorithme de suggestion initiale à partir de données générales (popularité, similarité de contenu, etc.)  
- Tests d'intégration et vérification de la cohérence des recommandations pour les nouveaux utilisateurs

> Temps estimé : 20 heures

---

### 2. Implémentation complète du bruitage des données  
Dans le cadre du renforcement de la **confidentialité différentielle**, les mécanismes de bruitage (Laplace, Gaussien, Exponentiel) ont été **étendus à l’ensemble des flux de données** :  
- Identification des points critiques à protéger dans la base  
- Application automatisée du bruitage à tous les jeux de données sensibles  
- Vérifications que les résultats restent exploitables après perturbation

> Temps estimé : 15 heures

---

### 3. Amélioration de l’Interface Homme-Machine (IHM)  
Des améliorations ont été apportées à l’interface web pour renforcer l’expérience utilisateur :  
- Ajout de nouvelles vues et d’une meilleure navigation  
- Amélioration de la **gestion des comptes et de la connexion utilisateur**  
- Préparation de l’affichage dynamique des recommandations personnalisées

> Temps estimé : 10h heures

---

### 4. Amélioration de la base de données  
Dans une optique de **scalabilité et de cohérence des données**, la base a été revue et optimisée :  
- Nettoyage et refactorisation des schémas  
- Meilleure organisation des relations entre films, tags et utilisateurs  
- Intégration de données enrichies pour la phase de deep learning

> Temps estimé : 10h heures

---

### 5. Optimisation de l’algorithme de recommandation  
Le moteur de recommandation a été **ajusté et consolidé** sur plusieurs aspects :  
- Réduction de la redondance dans les résultats  
- Meilleur équilibrage entre popularité, préférences individuelles et diversité  
- Préparation de l’interfaçage avec les modules de deep learning

> Temps estimé : 10h heures

---

### 6. Deep Learning – Approfondissement  
Le développement du module de deep learning a continué :  
- Préparation des données pour l’entraînement (formatage, encodage)  
- Choix des premières architectures de réseaux (dense, embedding, etc.)  
- Premiers entraînements exploratoires sur jeux réduits

> Temps estimé : 10h heures

---
