# Digital Habits & Cultural Practices: A Multivariate Data Analysis 

Ce projet présente une étude statistique approfondie sur les **usages du numérique** et les **pratiques culturelles** au sein d'une population sondée via Google Forms. 

À l'aide de méthodes d'**analyse de données multivariées sous R**, ce travail met en évidence les facteurs sous-jacents qui façonnent les comportements numériques/culturels et identifie des profils homogènes d'individus.

---

## 📄 Rapport Complet & R Markdown
> 💡 **Remarque** : Le script complet et le traitement des données sont documentés dans le fichier R Markdown (`Projet.Rmd`). **Le rapport scientifique final au format PDF (`Projet.pdf` / `Rapport_Analyse_Donnees.pdf`) sera importé directement dans le dépôt.** Il contient l'ensemble des graphiques, des matrices de corrélation, ainsi que les interprétations détaillées.

---

## 📌 Présentation des Données
Les données ont été collectées via un questionnaire composé de 43 variables couvrant trois grandes dimensions :
- **Profil sociodémographique** : `Âge`, `Sexe`, `CSP`, `Région`.
- **Usages & perceptions du numérique** : Temps d'écran, utilisation des réseaux sociaux (`Instagram`, `TikTok`), utilité d'Internet, confiance envers l'IA et le paiement en ligne, dépendance numérique, etc.
- **Pratiques culturelles & style de vie** : Sorties (cinéma, musées), lecture, streaming, fréquentation de salles de sport, bénévolat, voyages à l'étranger, etc.

Le fichier brut (`Form_realiste_bruit.xlsx`) a été nettoyé et recodé (échelles de Likert converties en valeurs numériques 1 à 5) pour générer le jeu de données d'analyse (`Form_normalise.csv`).

---

## 🎯 Méthodologie & Démarche Scientifique

Le pipeline d'analyse s'articule autour de quatre étapes majeures :

1. **Nettoyage & Normalisation des Données** :
   - Suppression des métadonnées (horodatage).
   - Mapping des échelles de Likert (*Pas du tout d'accord* ➡️ 1, ..., *Tout à fait d'accord* ➡️ 5).
   - Création de tranches d'âge (*Jeunes*, *Adultes*, *Matures*, *Seniors*).
2. **Statistiques Descriptives & Exploration** :
   - Graphiques de répartition (camemberts / diagrammes en barres) pour caractériser l'échantillon selon le sexe, la région, la CSP et l'âge.
3. **Analyses Factorielles (Multivariées)** :
   - **ACP (Analyse en Composantes Principales)** sur les variables numériques/Likert liées aux usages digitaux :
     - *Axe 1* : Intensité et intégration de l'usage du numérique.
     - *Axe 2* : Confiance vs. rapport critique vis-à-vis des technologies (IA, sécurité, dépendance).
   - **ACM (Analyse des Correspondances Multiples)** sur les variables qualitatives (pratiques culturelles, réseaux utilisés, équipement) pour identifier les proximités de styles de vie.
4. **Classification Automatique (Typologie d'Individus)** :
   - **CAH (Classification Ascendante Hiérarchique)** selon la méthode de Ward sur les coordonnées factorielles de l'ACP.
   - Segmentation de la population en **4 clusters homogènes**.

---

## 🧩 Typologie des Profils Identifiés (Clusters)
L'analyse de la classification hiérarchique a permis de dégager 4 grands profils :
- 🟢 **Cluster 1 – Utilisateurs intensifs et confiants** : Forte adhésion au numérique, temps d'écran élevé et grande confiance dans les technologies.
- 🟡 **Cluster 2 – Profils intermédiaires et polyvalents** : Usages réguliers mais modérés, attitudes nuancées.
- 🔵 **Cluster 3 – Utilisateurs sélectifs et pragmatiques** : Utilisation ciblée du numérique sans dépendance ni rejet.
- 🔴 **Cluster 4 – Profils distants ou critiques** : Usage limité, méfiance accrue et sensibilité aux risques numériques.

---

## 🛠️ Stack Technique & Package R
- **Langage** : R
- **Manipulation de données** : `dplyr`, `readxl`
- **Visualisation & Graphiques** : `ggplot2`, `corrplot`
- **Analyse Multivariée & Clustering** : `FactoMineR`, `factoextra`

---

## 📁 Structure du Dépôt

```text
.
├── Form_realiste_bruit.xlsx        # Fichier de données brut (issues de Google Forms)
├── Form_normalise.csv              # Dataset nettoyé et normalisé
├── Projet.Rmd                      # Code source R Markdown de l'analyse
├── Rapport_Analyse_Donnees.pdf     # Rapport complet généré au format PDF (à venir)
└── README.md                       # Présentation du projet
