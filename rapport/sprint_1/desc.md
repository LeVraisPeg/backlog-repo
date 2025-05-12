# Description du Sprint 1 – Serveur & Chiffrement

## Objectif du Sprint 1  
L’objectif de ce sprint était de **développer l’ossature technique du projet**, en mettant en place les serveurs backend et en intégrant des mécanismes de sécurisation des données.  
Ce sprint a également amorcé l’implémentation de l’algorithme de recommandation et préparé une première interface utilisateur rudimentaire.

## Durée  
48 heures

---

## Activités réalisées

### 1. Serveur Quarkus  
Mise en place d’un **backend Java** basé sur Quarkus. Cette étape a consisté à :  
- Initialiser le projet Quarkus et configurer le système de build (Maven/Gradle)  
- Configurer la connexion à la base de données avec les entités JPA  
- Créer les **endpoints REST** pour réaliser les opérations CRUD (GET, POST, etc.)  
- Tester et valider les endpoints via Postman ou curl  

> Temps estimé : 5 heures

---

### 2. Serveur Python  
En parallèle, un **backend Python** a été développé avec un framework web (FastAPI ou Flask) afin d’expérimenter une architecture alternative ou complémentaire.  
Les tâches menées :  
- Initialisation du projet Python et installation des dépendances nécessaires  
- Implémentation des routes REST (CRUD)  
- Connexion à la base de données avec SQLAlchemy ou un autre ORM  
- Tests de l’API pour s’assurer de sa fiabilité  

> Temps estimé : 5 heures

---

### 3. Chiffrement des données  
Un **travail approfondi de sécurisation** des données a été réalisé :  
- Sélection de l’algorithme de chiffrement approprié (AES, RSA, etc.)  
- Intégration du chiffrement/déchiffrement dans les flux de données côté serveur  
- Mise en place d’un mécanisme sécurisé de **gestion des clés** (ex : Vault, KMS)  
- Application du chiffrement sur les colonnes sensibles de la base de données  
- Réalisation de tests de sécurité et audit des échanges pour valider la robustesse du système  

> Temps estimé : 12 heures

---

### 4. Algorithme de recommandation  
Début de l’implémentation du **système de recommandations personnalisées** :  
- Collecte et nettoyage du dataset destiné à l’apprentissage du modèle  
- Choix de l’approche algorithmique (filtrage collaboratif, content-based ou hybride)  
- Exploration et prototypage du modèle (entraînement initial, ajustement des hyperparamètres)  
- Intégration de l’algorithme dans l’application backend  
- Évaluation du modèle (précision, rappel) et ajustements successifs  
- Tests finaux et validation de la solution proposée  

> Temps estimé : 25 heures

---

### 5. Interface Homme-Machine (IHM)  (OPTIONNEL)
Pour permettre une **interaction basique** avec l’application :  
- Conception rapide d’une maquette d’IHM (formulaires, tableaux de visualisation)  
- Connexion de l’interface à l’API backend pour afficher les données et interagir avec le système  

> Temps estimé : 1 heure

---
