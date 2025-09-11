# Fake or Real: The Impostor Hunt in Texts

##  Description du projet
Ce projet a été réalisé dans le cadre d’une compétition Kaggle : Fake or Real: The Impostor Hunt in Texts
L’objectif est de concevoir un modèle capable de différencier un faux texte (généré par des llm) et un vrai texte.

---

##  Données
- Jeu de données très léger, celui-ci contenait seulement 190 textes à analyser, ce qui peut être difficile pour entraîner un modèle robuste.
- Les textes n'étaient pas très longs, ce qui peut être un risque de surapprentissage.
---

##  Approche

### 1. Analyse exploratoire (EDA)
- Analyse des caractéristiques des différents textes
- Nombre de lettres en majuscule
- Nombre de caractères spéciaux
- Nombre d'identités normées (named entity recognition)
- Longueur des textes

Cela m'a permis d'identifier de nombreuses features qui seraient intéressantes, en effet, la distribution de ces features étaient très différente entre les vrais textes et les textes fabriqués.

### 2. Feature Engineering
- Les features dont j'ai parlé auparavant mais celles-ci ne suffisent pas pour entraîner un modèle robuste.
- J'ai décidé dans un premier temps d'utiliser un modèle basique de TF-ID pour convertir les textes en vecteurs numériques
- Les résultats n'étaient pas très prometteurs, j'ai donc décidé de passer à un modèle plus complexe pour extraire les embeddings, distilbert.
- Les embeddings extraits pour les 2 textes étaient donc des features importantes.
- La différence entre ces 2 embeddings était également une feature très intéressante
- Réduire les dimensions à l'aide de PCA pour éviter que le modèle ne fasse du surapprentissage

### 3. Modélisation
- Modèle choisi : **LightGBM (LGBM) + Random Forest**  
  - Etant donné que les données n'étaient pas très nombreuses, je me suis tourné vers random forest et lgbm et le modèle qui a le mieu performé était ...

---

##  Résultats
- **Score Kaggle (Leaderboard public) : 0.87**  
- Le modèle a montré de bonnes performances malgré un jeu de données très modeste

---


---
