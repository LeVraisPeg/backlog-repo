# 📖 Filtrage collaboratif : Description détaillée et processus général

Le **filtrage collaboratif** est une technique de recommandation reposant sur l’idée que si deux utilisateurs ont aimé des éléments similaires par le passé, ils sont susceptibles d’apprécier d’autres éléments similaires à l’avenir. Cette approche s’appuie sur les interactions passées (notes, clics, achats, etc.) entre les utilisateurs et les objets à recommander.

## 🔍 Types de filtrage collaboratif

### 1. Filtrage collaboratif actif
- Les utilisateurs expriment explicitement leurs préférences (notes, avis).
- Ces données servent à prédire les préférences d'autres utilisateurs.

### 2. Filtrage collaboratif passif
- Les préférences sont déduites implicitement à partir du comportement de l'utilisateur (clics, historique, temps de consultation).

### 3. Filtrage basé sur le contenu
- Recommande des éléments similaires à ceux qu’un utilisateur a déjà appréciés.
- Basé sur les caractéristiques des objets, pas sur d'autres utilisateurs.

## 🧠 Méthodes principales

### 👤 Filtrage collaboratif basé sur l'utilisateur

Le **filtrage collaboratif utilisateur-utilisateur** recommande des éléments à un utilisateur cible en se basant sur les comportements d'autres utilisateurs similaires.

#### 🔄 Fonctionnement général

1. **Comparaison des comportements** :
   - Le système analyse les interactions passées de l’utilisateur cible (ex : notes, achats, clics).
   - Il les compare à celles des autres utilisateurs.

2. **Calcul de similarité** :
   - Chaque utilisateur reçoit un **poids de similarité** par rapport à l'utilisateur cible.
   - Ces poids déterminent les **voisins les plus proches** (utilisateurs les plus similaires).

3. **Sélection des voisins** :
   - Le système choisit les *n* utilisateurs ayant les poids les plus élevés (plus grande similarité).

4. **Prédiction du comportement** :
   - Les préférences du groupe de voisins sont combinées via une **moyenne pondérée**.
   - Cela permet d’estimer la probabilité que l’utilisateur cible aime un nouvel élément.

5. **Génération de recommandations** :
   - Sur la base des prédictions, des éléments sont proposés à l’utilisateur.
   - Hypothèse : *"Si vous avez aimé ce que vos voisins ont aimé, vous aimerez probablement aussi le reste."*

#### 📌 Remarques techniques

- Les **fonctions de similarité** (ex. : cosinus, Pearson) sont calculées **entre les lignes de la matrice utilisateur-élément**.


### 🎯 Filtrage collaboratif basé sur les éléments (item-item)

Le **filtrage collaboratif item-item** recommande des éléments à un utilisateur cible en se basant sur ses interactions avec des **éléments similaires**, et non sur des utilisateurs similaires.

#### 🔄 Fonctionnement général

1. **Analyse du comportement utilisateur** :
   - Le système observe les éléments que l’utilisateur a appréciés, notés ou utilisés.

2. **Calcul de similarité entre éléments** :
   - Contrairement au filtrage basé sur le contenu, on ne regarde **pas les caractéristiques intrinsèques** des éléments.
   - Le système compare les éléments **en fonction des comportements d’autres utilisateurs**.
   - Par exemple, deux films sont considérés comme similaires si **les mêmes utilisateurs les ont appréciés de façon comparable**.

3. **Corrélation des notes** :
   - Les similarités sont souvent déterminées par des **corrélations** entre les notes attribuées aux différents éléments (corrigées de la moyenne des utilisateurs).

4. **Prédiction d’intérêt** :
   - Si un utilisateur a fortement noté les films *a* et *b*, et que d'autres utilisateurs qui aiment *a* et *b* ont aussi aimé *c*, alors on prédit que cet utilisateur pourrait aimer *c*.

5. **Génération de recommandations** :
   - Le système propose à l’utilisateur des éléments **similaires à ceux qu’il a déjà aimés**, sur la base de similarités comportementales.

#### 📌 Remarques techniques

- Les **fonctions de similarité** (cosinus, corrélation, etc.) sont calculées **entre les colonnes** de la **matrice utilisateur-élément**.


## 🔗 Mesures de similarité dans le filtrage collaboratif

Pour générer des recommandations, les systèmes de filtrage collaboratif ont besoin d’estimer la **similarité** entre les utilisateurs ou les objets. Cette similarité est calculée à partir des évaluations présentes dans la **matrice utilisateur-élément**. Deux méthodes couramment utilisées sont :

---

### 📐 1. Similarité cosinus

La **similarité cosinus** mesure l’**angle** entre deux vecteurs dans un espace vectoriel. Plus cet angle est petit (le cosinus proche de 1), plus les deux vecteurs sont considérés comme **similaires**. Dans le contexte du filtrage collaboratif :

- Les **vecteurs** représentent les notes qu’un utilisateur a données à différents objets, ou vice versa.
- La **similarité cosinus** est utile même quand les utilisateurs n'ont pas évalué exactement les mêmes éléments, tant que leur orientation globale est proche.

#### 🧮 Formule

$$
\text{Sim}_{\cos}(x, y) = \frac{x \cdot y}{\|x\| \cdot \|y\|}
$$

Où :
- $x$ et $y$ sont des vecteurs représentant deux utilisateurs ou deux objets.
- $\cdot$ désigne le produit scalaire.
- $\|x\|$ est la norme (longueur) du vecteur.

#### ✅ Avantages
- Fonctionne bien dans des espaces de grande dimension.
- Rapide à calculer.

#### ⚠️ Limites
- Ne prend pas en compte les **différences d’échelle** ou de **notation moyenne** entre utilisateurs.

---

### 📊 2. Coefficient de corrélation de Pearson (PCC)

Le **PCC** mesure la **corrélation linéaire** entre les évaluations de deux utilisateurs (ou objets). Contrairement à la similarité cosinus, il **centre les données** autour de la moyenne de chaque vecteur, ce qui permet de comparer les **tendances de notation**, indépendamment de l'échelle personnelle.

#### 🧮 Formule

$$
\text{PCC}(a, b) = \frac{\sum_i (r_{ai} - \bar{r}_a)(r_{bi} - \bar{r}_b)}{\sqrt{\sum_i (r_{ai} - \bar{r}_a)^2} \cdot \sqrt{\sum_i (r_{bi} - \bar{r}_b)^2}}
$$

Où :
- $r_{ai}$ et $r_{bi}$ sont les notes données à l’élément $i$ par les utilisateurs $a$ et $b$,
- $\bar{r}_a$ et $\bar{r}_b$ sont les moyennes des notes données par les utilisateurs $a$ et $b$.

#### ✅ Avantages
- Prend en compte les **différences de style de notation**.
- Réduit les biais dus aux utilisateurs plus sévères ou indulgents.

#### ⚠️ Limites
- Moins fiable si peu de notes sont en commun entre deux utilisateurs ou objets.

---

### 📋 Comparatif

| Critère                     | Similarité Cosinus                | Corrélation de Pearson (PCC)       |
|----------------------------|-----------------------------------|------------------------------------|
| Type de mesure              | Angle entre vecteurs             | Corrélation centrée sur la moyenne |
| Sensible aux styles de notation | ❌ Non                          | ✅ Oui                              |
| Efficace pour données clairsemées | ✅ Oui                      | ⚠️ Moins fiable                    |
| Échelle des valeurs         | -1 à 1 (avec ajustements)         | -1 à 1                              |
| Cas d’usage                 | Systèmes simples, large dimension | Comparaison de tendances           |

---

### 🧠 À retenir

- Le **choix** entre Cosinus et PCC dépend du **contexte**, des **données disponibles** et du **comportement des utilisateurs**.
- Dans certains systèmes hybrides, les deux mesures peuvent être combinées ou utilisées de manière complémentaire pour améliorer la précision.


## ⚙️ Processus général du filtrage collaboratif

Le filtrage collaboratif suit en général les étapes suivantes :

### 1. **Collecte de données**
- Récupération des interactions entre utilisateurs et objets (films, livres, produits...).
- Données explicites : notes, avis.
- Données implicites : clics, temps passé, historique de navigation.

### 2. **Construction de la matrice utilisateur-objet**
- Création d’une matrice où :
  - Les lignes représentent les **utilisateurs**.
  - Les colonnes représentent les **objets** (films, produits…).
  - Les cellules contiennent les **interactions** (note, présence ou absence d'interaction).

### 3. **Mesure de similarité**
- Calcul de la similarité entre :
  - **Utilisateurs** : pour identifier ceux qui partagent des goûts similaires.
  - **Objets** : pour trouver des objets qui plaisent aux mêmes utilisateurs.
- Méthodes fréquentes : cosinus de similarité, corrélation de Pearson, distance euclidienne.

### 4. **Prédiction**
- Utilisation des similarités pour **prédire la note** ou la préférence d’un utilisateur pour un objet non encore évalué.
- Deux approches principales :
  - **User-based** : recommande ce qu'ont aimé les utilisateurs similaires.
  - **Item-based** : recommande des objets similaires à ceux déjà appréciés.

### 5. **Génération de recommandations**
- Sélection des objets ayant les meilleures prédictions.
- Présentation d’une liste personnalisée à l'utilisateur.

## 📊 Exemple simple

|       | Film A | Film B | Film C | Film D |
|-------|--------|--------|--------|--------|
| User1 |   5    |   ?    |   4    |   2    |
| User2 |   4    |   3    |   5    |   1    |
| User3 |   2    |   4    |   1    |   5    |

> Grâce aux notes des autres utilisateurs, on peut estimer que User1 pourrait aimer **Film B**, en analysant les préférences des utilisateurs similaires.

## ✅ Avantages du filtrage collaboratif

- Le filtrage collaboratif **excelle à découvrir des éléments inattendus** ou non liés directement à ceux déjà consultés, en s’appuyant sur des **modèles de comportements partagés** entre utilisateurs.
- Il **ne nécessite pas de connaissance explicite des contenus** des objets à recommander.
- Les systèmes peuvent **s’adapter aux goûts émergents** d’un utilisateur en observant simplement les préférences de groupes similaires.
- Cela permet de recommander des éléments qu’un utilisateur n’aurait **pas forcément envisagés**, mais qui pourraient fortement lui plaire, grâce à la similarité comportementale.

🧠 *Exemple concret* : même si un film ne partage aucune caractéristique avec ceux qu’un utilisateur a aimés, il peut lui être recommandé si d'autres utilisateurs aux goûts proches l'ont apprécié.

---

## ⚠️ Inconvénients du filtrage collaboratif

### 1. 🎬 **Problème du démarrage à froid (Cold Start)**
- Lorsqu’un **nouvel utilisateur** ou un **nouvel objet** entre dans le système, **aucune donnée d’interaction** n’est disponible.
- Sans historique, il est **difficile de calculer des similarités** ou de faire des recommandations précises.
- Les systèmes basés sur le contenu gèrent mieux les nouveaux objets, mais ont aussi des limites pour les nouveaux utilisateurs.

### 2. 📉 **Parcimonie des données**
- La matrice utilisateur-objet est souvent **très clairsemée**, avec peu d'interactions remplies.
- Cette **sparsité réduit l’efficacité** des modèles prédictifs : il devient difficile de repérer des schémas fiables dans les données.
- Les points vectoriels sont alors trop dissemblables pour produire des recommandations pertinentes.

🧩 *Solution* : l’usage de **techniques de factorisation matricielle** (ex. : **décomposition en valeurs singulières – SVD**) ou d’**approches à facteurs latents** permet de **réduire les dimensions** et d’améliorer les prédictions malgré la sparsité.

### 3. 🗣️ **Nécessité d'informations utilisateur**
- Pour pallier ces faiblesses, certains systèmes demandent aux utilisateurs de **remplir un profil initial** ou de **fournir des intérêts**, afin d'amorcer le processus de recommandation.

---

### 📌 Résumé comparatif

| Aspect                  | Avantage                                                            | Limite                                                         |
|------------------------|---------------------------------------------------------------------|----------------------------------------------------------------|
| Découverte d’éléments  | Propose des recommandations originales et variées                   | Peut recommander des objets inappropriés sans contexte         |
| Données requises       | Se base uniquement sur les interactions passées                     | Inefficace avec utilisateurs/objets sans historique (cold start)|
| Volume de données      | Plus la base croît, plus le système devient pertinent               | Moins performant avec matrices trop clairsemées                |



## 🧩 Applications concrètes

### 🎬 Divertissement
- **Netflix, YouTube, Spotify**
  Recommandation de films, vidéos, séries, musiques

### 🛒 E-commerce
- **Amazon, Cdiscount**
  Produits recommandés selon ce que des utilisateurs similaires ont acheté ou noté

### 📚 Education
- **MOOC, plateformes d'apprentissage**
  Cours ou ressources suggérés selon les préférences d'étudiants similaires

### 💼 Recrutement
- **LinkedIn, Welcome to the Jungle**
  Propositions d’emplois basées sur les profils similaires

### 📲 Réseaux sociaux
- **Facebook, Twitter, TikTok**
  Suggestions d’amis, de contenus ou de groupes

### 🚗 Mobilité
- **Applications de covoiturage ou transports**
  Recommandation d’itinéraires ou de partenaires de trajet

### 💊 Santé
- **Applications médicales**
  Recommandation de régimes, d’activités ou de traitements sur la base de profils proches

## 🔬 Innovations et évolutions

- **Deep Learning** (ex. : auto-encodeurs, RNN, transformers)
- **Recommandation en temps réel**
- **Filtrage collaboratif avec préservation de la vie privée**
  - Confidentialité différentielle
  - Cryptographie homomorphe
- **Recommandation contextuelle**
  - En fonction de la localisation, de l'heure, du device, etc.

## 🔗 Référence
- [Filtrage collaboratif — Wikipédia](https://fr.wikipedia.org/wiki/Filtrage_collaboratif)
- Recommender Systems Handbook (Ricci et al.)
- Netflix Prize dataset & research
