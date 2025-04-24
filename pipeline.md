# Projet : Développement d’un moteur de recommandations respectueux de la vie privée

## Contexte
- Les moteurs de recommandations analysent des données pour suggérer des contenus pertinents, tout en soulevant des préoccupations liées à la confidentialité.
- Deux approches pour préserver la vie privée sont proposées : **Differential Privacy (DP)** ou **cryptographie homomorphe**.

## Objectifs
1. Implémenter un moteur de recommandations basé sur le **filtrage collaboratif** et utilisant des techniques modernes de machine learning.
2. Intégrer une méthode pour protéger la vie privée (**DP ou cryptographie homomorphe**).
3. Utiliser une **architecture microservices** avec une **modélisation UML** et une **gestion agile**.
4. Comparer les performances, la précision et la protection des données avec des solutions standards.

## Travail demandé
1. **Recherche théorique** : état de l'art sur les systèmes de recommandation et les techniques de préservation de la vie privée.
2. **Conception UML** : diagrammes pour modéliser les fonctionnalités et interactions du système.
3. **Développement technique** : moteur de recommandation et architecture microservices incluant **Java (backend)** et **Python (IA)**.
4. **Analyse comparative** des solutions avec ou sans préservation de la vie privée.

## Livrables
- Code source
- Modélisation UML
- Rapport technique
- Présentation orale

## Critères d’évaluation
- Analyse théorique
- Conception UML
- Qualité technique de l’implémentation
- Présentation finale

---

## 1. Confidentialité différentielle

La **confidentialité différentielle** est une méthode mathématique conçue pour protéger la vie privée des individus dans les bases de données. Elle garantit que la présence ou l'absence d'une personne dans une base de données n'affecte pas significativement les résultats obtenus lors de l'analyse des données.

### Comment cela fonctionne :
- **Ajout de bruit** : Elle introduit un bruit aléatoire dans les données ou les résultats des requêtes. Ce bruit est soigneusement calibré pour préserver les tendances générales tout en masquant les informations spécifiques des individus.
- **Budget de confidentialité** : Un paramètre appelé *budget de confidentialité* limite la quantité d'informations pouvant être divulguées sur un individu. Cela permet de trouver un équilibre entre l'utilité des données et la protection de la vie privée.

### Applications
Utilisée dans des domaines comme :
- Les statistiques
- Les systèmes de recommandation
- L’intelligence artificielle  
Elle permet d'exploiter des données sensibles tout en minimisant les risques d'identification des individus.

---

## 2. Cryptographie homomorphe

La **cryptographie homomorphe** est une technique avancée de chiffrement qui permet d'effectuer des calculs directement sur des données chiffrées, sans avoir besoin de les déchiffrer. Cela garantit que les données restent protégées tout au long du processus de traitement.

### Fonctionnement :
1. **Chiffrement des données** : Les données sont d'abord chiffrées à l'aide d'une clé publique.
2. **Calculs sur les données chiffrées** : Les opérations mathématiques (comme l'addition ou la multiplication) sont effectuées directement sur les données chiffrées. Ces calculs produisent des résultats également chiffrés.
3. **Déchiffrement des résultats** : Une fois les calculs terminés, le détenteur de la clé privée peut déchiffrer les résultats pour obtenir les données en clair.

### Types de cryptographie homomorphe :
- **Partiellement homomorphe** : Permet uniquement un type d'opération (*addition* ou *multiplication*) sur les données chiffrées.
- **Quelque peu homomorphe** : Autorise un nombre limité d'opérations, mais avec des contraintes liées au bruit généré.
- **Totalement homomorphe** : Permet un nombre illimité d'opérations sur les données chiffrées, mais reste complexe et coûteux en termes de calcul.

### Applications :
- **Cloud computing** : Permet de traiter des données sensibles sur des serveurs distants sans compromettre leur confidentialité.
- **Analyse de données** : Utilisé dans des secteurs comme la santé ou la finance pour analyser des données sensibles tout en respectant les réglementations sur la vie privée.
- **Blockchain** : Renforce la sécurité et la confidentialité des transactions.
