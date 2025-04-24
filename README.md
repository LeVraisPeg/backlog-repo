# 🔐 Moteur de Recommandations Respectueux de la Vie Privée

## 📌 Présentation
Ce projet a pour objectif de développer un moteur de recommandations respectueux de la vie privée des utilisateurs. Contrairement aux systèmes classiques qui exploitent massivement les données personnelles, notre moteur repose sur une approche centrée sur la minimisation de la collecte de données et l’intégration de techniques de confidentialité.

## 🎯 Objectifs
- Fournir des recommandations personnalisées tout en préservant la vie privée.
- Implémenter des techniques de **filtrage collaboratif** avec des garanties de confidentialité.
- Explorer des approches innovantes comme :
  - **La confidentialité différentielle**
  - **La cryptographie homomorphe**
  - **Le traitement local des données (edge computing)**

## 🛠️ Technologies Utilisées
- **Langage :** Python
- **Bibliothèques :** NumPy, Pandas, Scikit-learn, PySyft, TenSEAL
- **Environnement :** Jupyter Notebook, VSCode

## 📚 Lien systèmes de recommandation
- https://en.wikipedia.org/wiki/Collaborative_filtering
- https://medium.com/@eliasah/delving-deeper-into-recommender-systems-from-basics-to-state-of-the-art-d92ee8e277f2
- https://medium.com/@eliasah/deep-dive-into-matrix-factorization-for-recommender-systems-from-basics-to-implementation-79e4f1ea1660

## 📊 Lien BD
https://grouplens.org/datasets/movielens/

## 🚀 Installation
1. Cloner ce dépôt :
   ```bash
   git clone https://github.com/LeVraisPeg/PROJET-repo.git
   ```

2. Se déplacer dans le dossier du projet :
   ```bash
   cd PROJET-repo
   ```

3. Créer un environnement virtuel :
   ```bash
   python -m venv env
   source env/bin/activate  # Sur Windows : env\Scripts\activate
   ```

4. Installer les dépendances :
   ```bash
   pip install -r requirements.txt
   ```

## 📈 Fonctionnalités
- Recommandations via **filtrage collaboratif utilisateur-utilisateur** et **élément-élément**
- Mécanismes intégrés de **préservation de la confidentialité**
- Interface simple pour la génération de recommandations
- Options de test pour comparer recommandations classiques vs privées

## 🧪 Exemple d'utilisation
Lancer le moteur de recommandation :

```bash
python main.py
```

Suivre les instructions dans la console pour choisir un utilisateur et obtenir une liste personnalisée de recommandations respectueuses de la vie privée.

## ✅ Avantages
- Recommandations même sans connaissance explicite des contenus
- Préservation des préférences privées des utilisateurs
- Capacité à identifier des goûts non évidents grâce au comportement collectif

## ⚠️ Limites
- **Cold Start** : plus difficile avec de nouveaux utilisateurs/produits
- **Parcimonie des données** : peu d’interactions peuvent limiter la qualité
- **Complexité algorithmique** accrue avec l’ajout de protections de confidentialité

## 📄 Licence
Ce projet est distribué sous licence **MIT**.

## 📫 Contact
- Auteur principal : [LeVraisPeg](https://github.com/LeVraisPeg)
- Projet réalisé dans le cadre d’un module universitaire **SAE821** à l'Université de Toulon.
