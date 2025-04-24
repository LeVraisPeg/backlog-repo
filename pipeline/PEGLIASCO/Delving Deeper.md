# Approfondir les systèmes de recommandation : des bases à l’état de l’art

# ⌛Timeline
1990 - Basic CF (collaborative Filtering)
 - Le filtrage collaboratif repose sur l'idée que si deux utilisateurs ont aimé les mêmes choses dans le passé, ils aimeront probablement les mêmes choses à l’avenir.
 - User-Based Collaborative Filtering: Trouve utilisateur similaire / recommande
 - Item-Based Collaborative Filtering: Trouve obhets similaires à caux aimés / recommande
1990 - CB-Filtering (Content-Based Filtering)
   -Basé sur les comportements des users
   -ne regarde pas les objets
   -Utilise les notes/interactions
   
🔹 CF = "Les gens comme toi aiment ça"
🔹 CB = "Tu aimes ça, donc tu aimeras aussi ça"

2000 - Model hybrid 
  - Combine CF et CB

2000 - Deep learning debut
  -réseau de neurone
  -base mathématique

2010 - Context-aware / Knowledge-based
  - Tiennent compte de facteurs contextuels (temps, lieu appareil, etat émotionnel)
  - Applique un filtrage suivant le contexte avant d'appliquer un modèle puis un post filtrage contextuel
  - Utilisation explicite de connaissance sur les objets et besoin utilisateur
  - Utilise Ontologies, reglès logiques, bases de connaissance

2020 - Focus on RL and Explainable Recommenders
  -Reinforcement learning (RL) 
  -gestion de l'évolution des préférences
  -Interaction avec l'utilisateur
  -Approche séquentielle et interactive
  
# Type de Recommandation 🔍
- CF basé sur la mémoire:  intègre une BD, filtrage par élément utilisateur
- CF basé sur un moèle : réseau de neuronne, SVD (Singular Value Decomposition), facto matricielle
- Filtrage basé sur contenu: Utilise les attrivuts des éléments pour recommander des éléments similaire
- Modèles hybrides : Utilise filtrage collaboratif basé sur le contenue (Netflix)
- Apprentissage profond: Réseau de neurone, RNN (Recurrent Neural Network), ConvNets(CNN)
- Système de recommandation contextuels : temps, utilisateur ..
- Recommandation basé sur les connaissance : pour suggestion de produit de niche 
- Apprentissage par renforcement dans les recommandations: Multi-Armed Bandit
- Systèmes de recommandation explicables : Ajout d'une clarification de recommandation
- Recommandation multimodales : Utilisation d'élément visuel acoustique
- Evolution de la recommandation au fils du temps
- Recommandation préservant la confidentialité: Intégration de techniques (confidentialité différentielles) protection données

# Filtrage collaboratif avec ALS
L’hypothèse sous-jacente est que si une personne A a la même opinion qu’une personne B sur une question, A est plus susceptible d’avoir l’opinion de B sur une question différente.


# Definition: 

## SVD : 
Si tu as une matrice de notes R (utilisateurs × items), la SVD la décompose comme :
  R ≈ U⋅Σ⋅Vᵗ
- U = matrice des facteurs latents utilisateurs
- Σ = matrice diagonale des valeurs singulières
- Vᵗ = transpose de la matrice des facteurs latents des items

### SVD version recommandation:
Factorisation de Matrice:
$$
\hat{R}_{ui} = P_u^T Q_i
$$
R_ui = note prédite par l'utilisateur 𝑢 pour l'item 𝑖
P_u = vecteur latent de l'utilisateur u (préférences)
Q_i = vecteur latent de l’item i (caractéristiques)
Le produit scalaire donne la note prédite que u donnerait à i

### Apprentissage de P et Q:
$$
\min_{P, Q} \sum_{(u,i) \in K} \left( R_{ui} - P_u^T Q_i \right)^2 + \lambda \left( \lVert P_u \rVert^2 + \lVert Q_i \rVert^2 \right)
$$
K = ensemble des paires utilisateur-item connues (données d’entraînement)
R_ui = note réelle
λ = coefficient de régularisation

## RNN: 
Réseau de neurones pour traiter des séquences (texte, audio,clics, utilisation ...)
Possède une mémoire interne (utilise l'info précédente à chaque étape)
Gère les dépendances temporelles
Variantes plus puissante (LSTM,GRU)

À chaque instant \( t \), le RNN reçoit une entrée \( x_t \) et un état caché précédent \( h_{t-1} \), puis il calcule :

### 🧠 État caché :
$$
h_t = \tanh(W_h h_{t-1} + W_x x_t + b)
$$

### 🔮 Sortie (optionnelle) :
$$
y_t = \text{softmax}(W_y h_t + b_y)
$$

 Où :
- \( h_t \) = état caché (mémoire interne) à l’instant \( t \)
- \( x_t \) = entrée à l’instant \( t \)
- \( y_t \) = sortie prédite à l’instant \( t \)
- \( W_h, W_x, W_y \) = matrices de poids
- \( b, b_y \) = biais
- \( \tanh \) = fonction d’activation
- \( \text{softmax} \) = utilisée pour une prédiction de classe

## ConvNet (CNN)
Type de réseau de neurone profond 
Utilise des filtes convolutionnels pour apprend la hiérarchiques des données
- Convolution : applique un filtre sur l'image pour extraire des caractéristiques local
- Activation: apres caque convolution une fonction est applique pour introduire des non-linéarités
- pooling : Réduction de la taille de l'image
- Flattening : aplatie l'image
- Couches fully connected: applique des prédictions finales avec une extraction par des couches fully connected

## Multi-Armed Bandit
 Apprentissage par renforcement, maximisation des gains à long therme en appliquant une exploration large du domaine
 







