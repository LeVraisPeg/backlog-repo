# Rapport de fin du Sprint 1 

## Activités réalisées

### 1. Implémentation de la confidentialité différentielle  
Nous avons finalisé et validé un **mécanisme de bruitage** conforme aux principes de la **confidentialité différentielle** :  
- Implémentation d’algorithmes de **bruitage (Laplace et Gaussienne)** applicables aux données sensibles  
- **Étude des techniques de chiffrement** (notamment TFHE et crypto homomorphes) pour évaluer leur compatibilité avec l’algorithme de recommandation  
- **Abandon des solutions homomorphes (TFHE)**, jugées inadaptées au contexte de la recommandation (incompatibilités techniques et performances insuffisantes)

### 2. Mise en place de l’environnement Quarkus & Base de données  
L’infrastructure serveur a été finalisée avec :  
- **Mise en production d’un serveur Quarkus** pleinement opérationnel  
- **Conception complète de la base de données** et mise en œuvre de la structure relationnelle  
- Intégration et validation des échanges entre l’application Quarkus et la base de données (CRUD opérationnels)

---

## Tâches non réalisées

### 1. Mise en place du serveur Python  
La **mise en place du serveur Python** (prévu pour l’exécution d’algorithmes de recommandation avancés) n’a pas pu être réalisée durant ce sprint. Cette tâche est **reportée au Sprint 2**.

---

## Livrables du Sprint 1  
À l’issue du Sprint 1, les éléments suivants ont été produits :  
- **Mécanisme de confidentialité différentielle** fonctionnel (bruitage)  
- **Infrastructure Quarkus** déployée avec base de données opérationnelle  
- **Documentation technique** des choix et implémentations

---

## Bilan du Sprint 1  
Ce sprint a permis de **poser des fondations techniques solides** avec la mise en place d’un mécanisme de protection des données conforme et d’une infrastructure applicative prête à supporter les développements futurs. Bien que certaines tâches aient été reportées (serveur Python), l’avancement global est conforme aux attentes pour engager sereinement le Sprint 2.
