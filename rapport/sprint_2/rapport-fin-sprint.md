# Rapport de fin du Sprint 2  

## Activités réalisées  

### 1. Mise en place du mécanisme de confidentialité différentielle  
Le **mécanisme de confidentialité différentielle** est désormais entièrement **opérationnel et prêt à être intégré**.  
- Les algorithmes de **bruitage (Laplace, Gaussien)** ont été développés et testés  
- Le mécanisme est **fonctionnel**, seul son **rattachement aux différents flux de données reste à finaliser**  

### 2. Chargement massif de données  
Le chargement des données a nécessité **plus de temps que prévu** en raison du **remaniement complet de la base de données** :  
- Reformatage et nettoyage des données  
- **Adaptation des scripts d’import** au nouveau schéma  
- Estimation : **+5 heures** de travail supplémentaires  

### 3. Mise en place du serveur Python  
Le **serveur Python a été mis en place avec succès** pour accueillir les futurs algorithmes de recommandation :  
- Infrastructure fonctionnelle  
- Connexion établie avec la base de données et l’environnement externe  

### 4. Algorithmes de recommandation  
Les travaux sur la recommandation ont considérablement progressé :  
- **Amélioration de l’algorithme SVD**, avec des résultats plus cohérents  
- **Début de l’intégration du Deep Learning**, accompagné d’un **long travail de préparation des données** pour qu’elles soient exploitables dans ce contexte  

### 5. Interface utilisateur (IHM)  
Le développement de l’interface utilisateur a avancé bien au-delà des prévisions :  
- **Quasi complétée**, avec affichage dynamique et interactions de base  
- Intégration des recommandations et des connexions utilisateurs  
- Estimation : **5 à 6 heures** de travail (contre 1-2h initialement prévues)  

---

## Tâches non réalisées  

Aucune tâche prévue pour ce sprint n’a été laissée de côté.  
**Toutes les fonctionnalités majeures ont été abordées et développées**, malgré certains dépassements de temps.

---

## Livrables du Sprint 2  
- **Mécanisme de confidentialité différentielle** prêt à l’emploi  
- **Serveur Python fonctionnel**  
- **Recommandation améliorée (SVD) + base pour le Deep Learning**  
- **Interface utilisateur complète** (avec pages connectées et récupération de recommandations)  
- **Base de données nettoyée et pleinement intégrée dans l’écosystème**

---

## Bilan du Sprint 2  
Ce Sprint a permis de **transformer l’architecture en une solution cohérente, intégrée et prête pour l’apprentissage avancé**.  
Les différents modules (Quarkus, Python, front-end, base de données) **communiquent efficacement**, et les premières **fondations du système de recommandation intelligent** sont posées.  
Bien que certaines tâches aient nécessité **plus de temps que prévu**, **aucun objectif n’a été abandonné**. Le sprint est donc une **réussite complète** sur le plan technique et organisationnel.
