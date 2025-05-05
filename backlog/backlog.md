## Sprint 1 : Serveur et Chiffrement
### Objectif : Développer un serveur backend et sécuriser les données
### Durée : 48h

### 1️⃣ Serveur Quarkus (5h)
> Mise en place d’un backend en Quarkus

- 📦 Initialisation projet Quarkus (1h)  
  Créer la structure du projet, configurer le build (Maven/Gradle)
- 🔌 Connexion base de données (1h)  
  Configurer le datasource et les entités JPA
- 🌐 Création endpoints REST (CRUD) (2h)  
  Implémenter les ressources de base (GET, POST…)
- 🧪 Tests et validation (1h)  
  Tester les endpoints avec Postman ou curl

---

### 2️⃣ Serveur Python (5h)
> Développement d’un service backend (FastAPI, Flask…)

- 🛠️ Initialisation projet Python + dépendances (1h)  
  Créer l’environnement virtuel, installer librairies (FastAPI/Flask)
- 🌐 Implémentation endpoints REST (CRUD) (2h)  
  Routes basiques (GET, POST…)
- 🔗 Connexion base de données (1h)  
  SQLAlchemy ou autre ORM + config DB
- 🧪 Tests et validation (1h)  
  Tester API (Postman, curl)

---

### 3️⃣ Chiffrement des données (12h)
> Sécurisation des données sensibles

- 🔑 Choix de l’algorithme de chiffrement (1h)  
  AES, RSA, ou autre selon le besoin
- 🔗 Intégration chiffrement côté serveur (5h)  
  Implémenter chiffrement/déchiffrement dans les flux de données
- 🗝️ Gestion des clés (stockage sécurisé) (2h)  
  Vault, KMS ou solution maison sécurisée
- 🛡️ Chiffrement des données en base (3h)  
  Chiffrer les colonnes sensibles à l’enregistrement
- 🧪 Tests et audit sécurité (1h)

---

### 4️⃣ Algorithme de recommandation (25h)
> Système de recommandations personnalisées

- 📊 Collecte et nettoyage des données (3h)  
  Préparer dataset pour apprentissage
- 🧩 Choix de l’approche algorithmique (3h)  
  Collaborative filtering, content-based, hybrid ?
- 🔍 Exploration et prototypage modèle (5h)  
  Entraînement initial, tuning hyperparamètres
- ⚙️ Implémentation algorithme (7h)  
  Intégration dans l’app backend
- 📈 Évaluation et amélioration (itérations) (5h)  
  Mesurer précision/rappel, ajustements
- 🧪 Tests finaux et validation (2h)

---

### 5️⃣ IHM (Interface Homme-Machine) (1h)
> Intégration finale

- 🎨 Maquettage rapide de l’IHM (0.5h)  
  Interface simple (formulaires, tableaux)
- 🔗 Connexion à l’API backend (0.5h)  
  Intégration appels API et affichage

---