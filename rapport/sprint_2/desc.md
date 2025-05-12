# Description du Sprint 2 – Confidentialité & Optimisation des Données

## Objectif du Sprint 2  
L’objectif de ce sprint était de **renforcer la protection des données** via des techniques avancées de confidentialité différentielle, d’**optimiser le traitement des grandes quantités de données**, et de **poursuivre l’amélioration de l’algorithme de recommandation**.  
Ce sprint a également permis de mettre en place un serveur Python dédié aux calculs et d’amorcer une interface utilisateur simplifiée.

## Durée  
32 heures

---

## Activités réalisées

### 1. Mécanisme exponentiel (Confidentialité différentielle)  
Pour améliorer la protection des données tout en maintenant la pertinence des résultats, un **mécanisme exponentiel** a été intégré :  
- Compréhension théorique du mécanisme exponentiel et de ses cas d’usage  
- Implémentation d’un module permettant la sélection de sorties qualitatives sous confidentialité différentielle  
- Tests de combinaison avec les autres mécanismes de bruitage (Laplace et Gaussien) pour validation de l’utilité

> Temps estimé : 12 heures

---

### 2. Serveur Python  
Un **backend Python** a été mis en place pour traiter les calculs complexes, notamment liés à la recommandation :  
- Initialisation du projet Python avec **FastAPI** et installation des dépendances  
- Développement d’une API REST exposant les algorithmes de traitement  
- Connexion à la base de données pour manipulation directe des jeux de données  
- Tests des endpoints pour assurer la fiabilité des échanges

> Temps estimé : 2 heures

---

### 3. Chargement massif de données  
Pour optimiser l’intégration de grandes quantités de données, une **méthodologie de chargement rapide** a été développée :  
- Étude des techniques d’insertion massive (bulk insert, COPY, LOAD DATA INFILE selon le SGBD)  
- Développement d’un pipeline d’import automatisé compatible avec les formats CSV volumineux  
- Mise en place d’un système de **validation et nettoyage de données** avant insertion  
- Tests de performances pour s’assurer de la rapidité et fiabilité du processus

> Temps estimé : 8 heures

---

### 4. Algorithme de recommandation  
Poursuite de l’**amélioration du système de recommandation personnalisé** :  
- Optimisation du modèle existant basé sur la **Singular Value Decomposition (SVD)**  
- Début d’intégration de techniques de **deep learning** pour capter des relations complexes entre utilisateurs et contenus  
- Entraînement de modèles hybrides et ajustements des hyperparamètres  
- Évaluation de la précision du modèle et itérations successives pour amélioration continue

> Temps estimé : 10 heures

---

### 5. Interface Homme-Machine (IHM)  (OPTIONNEL)  
Afin de permettre une **interaction simple** avec l’application :  
- Conception d’une maquette basique de l’interface (recherche, visualisation de recommandations)  
- Connexion de l’IHM aux APIs backend (Quarkus & Python) pour afficher les résultats et tester les fonctionnalités

> Temps estimé : 1-2 heures

---
