# Description du Sprint 0 – Recherche, Choix technologiques & Conception

## Objectif du Sprint 0  
Le **Sprint 0** avait pour principal objectif de **poser les bases du projet** en réalisant toutes les activités préparatoires nécessaires avant le démarrage effectif du développement.  
Ce sprint préparatoire a permis de :  
- Comprendre le périmètre fonctionnel et technique du projet  
- Effectuer les **recherches exploratoires** nécessaires  
- Prendre les **décisions stratégiques** sur les technologies à utiliser  
- Concevoir l’**architecture logicielle** via la modélisation UML

---

## Activités réalisées

### 1. Analyse des besoins et cadrage du projet  
Nous avons commencé par identifier les **besoins fonctionnels** et les **contraintes techniques** du système. Cette phase a permis de :  
- Définir les **principales fonctionnalités** attendues  
- Identifier les **acteurs** du système et leurs interactions  
- Clarifier les **objectifs de confidentialité** et de sécurité des données  

### 2. Recherches exploratoires  
Afin de garantir la faisabilité technique, nous avons mené plusieurs **recherches** sur les outils et techniques pertinents :  
- Étude des frameworks back-end (choix de **Quarkus** pour sa légèreté et compatibilité cloud)  
- Exploration des **méthodes de chiffrement** : chiffrement homomorphe (TFHE) et confidentialité différentielle  
- Analyse des **outils de gestion de bases de données** et d’import de données (fichiers CSV)

### 3. Choix technologiques  
À l’issue des recherches, plusieurs **décisions technologiques** ont été prises :  
- **Quarkus** sera utilisé comme framework applicatif  
- Les données sensibles seront protégées par des **mécanismes de confidentialité différentielle** (ajout de bruit via distributions de Laplace et Gaussienne)  
- Abandon de TFHE après expérimentation (peu adapté au contexte)  
- Mise en place d’un **pipeline d’import de données** automatisé à partir de CSV

### 4. Conception UML  
Une **conception UML complète** a été réalisée afin de structurer le système :  
- **Diagrammes de cas d’utilisation** : identification des acteurs et fonctionnalités  
- **Diagramme de classes** : modélisation des entités métier (`Film`, `Avis`, `Utilisateur`, etc.) et relations  
- **Diagrammes de séquence** : description des interactions entre utilisateur, application et base de données pour les scénarios clés  
- **Diagramme de déploiement** : représentation de l’architecture matérielle et logicielle du système  

---
