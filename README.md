# 🌾 Challenge Data — Agriculture & Microcrédit au Sénégal (2019–2023)

## 📌 Contexte

Ce projet s'inscrit dans le cadre d'un **challenge data** portant sur l'analyse de la performance agricole et financière de **50 planteurs** répartis dans **5 zones agroécologiques du Sénégal**, sur la période **2019–2023**.

Une ONG souhaitait évaluer l'impact d'un **programme de microcrédit agricole** sur la productivité et la résilience des exploitations agricoles dans les zones suivantes :

- 🌊 Vallée du Fleuve Sénégal
- 🌿 Zone des Niayes
- 🥜 Bassin Arachidier
- 🌳 Casamance
- ⛰️ Sénégal Oriental

---

## 🎯 Objectifs

### Analyse Agricole
- Identifier les cultures les plus productives selon les zones agroécologiques
- Comparer les rendements des planteurs sur 5 ans
- Évaluer l'impact de la surface cultivée sur la performance agricole
- Détecter les zones les plus dynamiques

### Analyse Financière
- Mesurer l'adoption du microcrédit par les planteurs
- Évaluer l'impact du crédit sur l'évolution des rendements
- Analyser les comportements de remboursement
- Identifier les profils les plus performants économiquement

### Analyse Géographique
- Cartographier les performances agricoles par région et par ville
- Comparer les dynamiques entre zones agroécologiques
- Identifier les zones prioritaires pour l'ONG

### Analyse Temporelle
- Étudier l'évolution des rendements entre 2019 et 2023
- Détecter les années de forte ou faible performance
- Comprendre les tendances par culture et par région

---

## 🗂️ Structure du Dataset

Le dataset est composé de **5 tables relationnelles** :

| Table | Description | Colonnes clés |
|---|---|---|
| `DimRegion` | Référentiel des régions agricoles | id_region, nom_region |
| `DimVille` | Liste des villes par région | id_ville, nom_ville, id_region |
| `DimCulture` | Liste des cultures | id_culture, nom_culture |
| `DimFermier` | Informations des planteurs | id_fermier, id_region, id_ville |
| `FaitAgriculture` | Table des faits (mesures annuelles) | id_fermier, annee, surface_km2, id_culture, rendement, montant_credit, montant_rembourse |

---

## 📊 Dashboard Power BI

Le rapport interactif est composé de **6 pages** :

###  Page 1 — Page d'acceuil

### 🌾 Page 2 — Analyse Agricole
- Rendement Moyen, Surface Totale, Productivité (KPI Cards)
- Rendement Moyen par Culture et par Région
- Impact de la Surface sur le Rendement (Nuage de points)
- Productivité par Région

### 💰 Page 3 — Analyse Financière
- Total Crédits, Taux de Remboursement, Taux d'Adoption (KPI Cards)
- Adoption du Microcrédit par Région
- Impact du Crédit sur le Rendement (Nuage de points)
- Comportement de Remboursement par Région
- Profils les plus performants (Table)

### 📈 Page 4 — Analyse Temporelle
- Rendement Moyen, Évolution Annuelle (KPI Cards)
- Évolution du Rendement par Année
- Évolution Annuelle en %
- Tendances par Culture
- Tendances par Région

### 🗺️ Page 5 — Analyse Géographique
- Rendement Moyen, Productivité (KPI Cards)
- Carte géographique des performances par ville
- Comparaison des zones agroécologiques
- Zones prioritaires pour l'ONG (Treemap)

  ### 🗺️ Page 6 — Synthèse
- Une synthèse pour chaque page
- Recommendations pour l'ONG

---

## 📐 Mesures DAX

| # | Mesure | Description |
|---|---|---|
| 1 | Rendement Moyen | Moyenne du rendement |
| 2 | Surface Totale (km²) | Somme des surfaces cultivées |
| 3 | Productivité (rendement/km²) | Rendement rapporté à la surface |
| 4 | Total Crédits Octroyés | Somme des montants de crédit |
| 5 | Total Remboursé | Somme des montants remboursés |
| 6 | Taux de Remboursement | Total remboursé / Total crédits |
| 7 | Taux d'Adoption Microcrédit | % de lignes avec crédit > 0 |
| 8 | Nombre Planteurs Actifs | Nombre de fermiers distincts |
| 9 | Rendement Année Précédente | Rendement de l'année N-1 |
| 10 | Évolution Annuelle Rendement | Variation % du rendement annuel |

---

## 💡 Insights Clés

- 📊 **Taux de remboursement : 77,77%** — encourageant mais 22% de défaut de paiement représente un risque pour l'ONG
- 📉 **Taux d'adoption : 53%** — près d'un planteur sur deux n'utilise pas le microcrédit
- 🌍 **La Casamance** est la zone la plus productive avec la meilleure efficacité par km²
- 📈 **2022 est la meilleure année** de rendement sur les 5 ans observés
- 💸 Les crédits élevés ne garantissent pas systématiquement de meilleurs rendements

---

## 🎯 Recommandations pour l'ONG

| Priorité | Recommandation |
|---|---|
| 🔴 Urgent | Intensifier le suivi des remboursements |
| 🔴 Urgent | Cibler la Vallée du Fleuve et le Sénégal Oriental pour le recouvrement |
| 🟡 Important | Augmenter le taux d'adoption du microcrédit (47% non couverts) |
| 🟡 Important | Sensibiliser le Bassin Arachidier et la Zone des Niayes |
| 🟢 Développement | Dupliquer le modèle de la Casamance dans les autres zones |
| 🟢 Développement | Encourager les cultures performantes : Arachide, Oignon, Haricot vert |

---

## 🛠️ Outils utilisés

- **Power BI Desktop** — Modélisation et visualisation
- **Power Query (M)** — Nettoyage et transformation des données
- **DAX** — Calcul des mesures et KPIs
- **Python / pandas** — Exploration préliminaire des données

---

## 📁 Structure du Repository

```
📦 challenge-data-agriculture-senegal
 ┣ 📂 datasets
 ┃ ┣ 📄 DimRegion.csv
 ┃ ┣ 📄 DimVille.csv
 ┃ ┣ 📄 DimCulture.csv
 ┃ ┣ 📄 DimFermier.csv
 ┃ ┗ 📄 FaitAgriculture.csv
 ┣ 📂 screenshots
 ┃ ┣ 🖼️ analyse_agricole.png
 ┃ ┣ 🖼️ analyse_financiere.png
 ┃ ┣ 🖼️ analyse_temporelle.png
 ┃ ┗ 🖼️ analyse_geographique.png
 ┣ 📄 README.md
 ┗ 📄 synthese_executive.md
```

---

## 👩‍💻 Auteur

Projet réalisé dans le cadre d'un challenge data sur l'agriculture et le microcrédit en Afrique de l'Ouest.

---

*Ce projet illustre l'utilisation de Power BI pour produire des insights à fort impact social dans un contexte agricole africain.*
