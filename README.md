# 🎈 Analyse de la rhétorique conspirationniste — Affaire des Chinese Balloons
### *Conspiratorial Rhetoric Analysis — Chinese Balloon Affair*

---

> 🇫🇷 **[Français](#français)** · 🇬🇧 **[English](#english)**

---

## Français

### 📌 Contexte du projet

Ce dépôt contient le code et les données associés à mon **mémoire de Master 2** en Information-Communication : Données et Société (Université Paris Nanterre, 2024).

**Sujet :** *Analyse de la rhétorique conspirationniste à l'ère de la post-vérité sur les médias sociaux*

Ce projet fait suite à un **mémoire de M1** portant sur les mécanismes psychologiques (biais cognitifs, heuristiques) à l'œuvre dans les groupes sectaires et conspirationnistes en ligne. Le M2 en constitue la **validation empirique**.

---

### 🎯 Problématique

> *Comment la rhétorique conspirationniste se structure-t-elle face à un fait divers controversé ? Comment évolue-t-elle au fil du temps en réponse aux phases de médiatisation ? Comment varie-t-elle selon les caractéristiques des plateformes sociales ?*

**Hypothèses :**
- H1 : Malgré la présentation de preuves contradictoires, la position conspirationniste reste résistante au changement — voire se renforce — avec le temps.
- H2 : La rhétorique conspirationniste varie selon la plateforme, avec des stratégies discursives spécifiques à chaque réseau social.

---

### 🎈 Étude de cas : L'affaire des "Chinese Balloons"

| Étape | Date |
|---|---|
| Début de l'observation | 28 janvier 2023 |
| Pic de l'attention médiatique | 4 février 2023 |
| Abattage des ballons | 11 février 2023 |
| Explications officielles du gouvernement américain | 1er septembre 2023 |

Un ballon-espion chinois est détecté dans l'espace aérien américain, provoquant une vague de réactions sur les réseaux sociaux oscillant entre explication officielle (déviation de trajectoire) et théories du complot (reconnaissance militaire, couverture gouvernementale).

---

### 🧪 Méthodologie

**Collecte des données**
- Scraping de **300 posts par plateforme** (Twitter/X, Facebook, Reddit)
- Période : janvier 2023 – septembre 2023
- Outil : Apify (scrapers dédiés par plateforme)

**Découpage temporel**
```
Before Event  →  Début du fait  →  Pic du fait  →  Fin du fait  →  Après débunkage
```

**Traitement (R)**
- Nettoyage et uniformisation des 3 corpus
- Harmonisation des colonnes (ID, posts, username, date, likes, comments, shares)
- Catégorisation temporelle par phases

**Analyses réalisées**
- 📊 Analyse univariée des réactions (likes, comments, shares) par phase et par plateforme
- 💬 Analyse de sentiment avec `sentimentr` (score moyen, catégorie : positif / neutre / négatif)
- 🔠 Préparation de corpus pour **IRaMuTeQ** (classification, analyse textuelle)
- 📐 Test du **Chi-deux** pour valider les différences inter-plateformes

---

### 📁 Structure du dépôt

```
📦 Memoire-M2-DES/
├── script_traitement_donnees.R   # Script principal R (nettoyage + analyses)
├── all_reactions.csv              # Réactions agrégées par phase et plateforme
├── all_reactions_long.csv         # Format long pour visualisation (Flourish)
├── sentiment_summary.csv          # Scores de sentiment par phase et plateforme
├── phase_counts.csv               # Nombre de posts par phase et plateforme
├── data/                          # Données brutes scrapées (non incluses)
├── graph/                         # Graphiques exportés
└── iramuteq/                      # Corpus formatés pour IRaMuTeQ
```

---

### 📊 Principaux résultats

| Plateforme | Ton dominant | Spécificité |
|---|---|---|
| **Twitter/X** | 🔴 Négatif (surtout au pic) | Réactions rapides, virales, focus géopolitique |
| **Facebook** | 🟡 Modéré → positif post-débunkage | Interactions locales, thématiques variées |
| **Reddit** | 🟢 Globalement positif | Débats analytiques approfondis, engagement communautaire |

**Conclusions :**
- ✅ H1 validée : la rhétorique conspirationniste **résiste voire se renforce** après la présentation de preuves contraires
- ✅ H2 validée : des **stratégies discursives distinctes** ont été observées selon chaque plateforme

---

### 🛠️ Stack technique

![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![tidyverse](https://img.shields.io/badge/tidyverse-1.3-blue)
![sentimentr](https://img.shields.io/badge/sentimentr-NLP-green)
![IRaMuTeQ](https://img.shields.io/badge/IRaMuTeQ-TextMining-purple)
![Flourish](https://img.shields.io/badge/Flourish-DataViz-orange)

**Librairies R :** `tidyverse`, `lubridate`, `highcharter`, `sentimentr`, `dplyr`

---

### 👩‍💻 Auteure

**Inès Amdjahed** — Master 2 Information-Communication : Données et Société  
Université Paris Nanterre · 2024  
📧 ines.amdjahed@email.com · 💼 [LinkedIn](https://linkedin.com/in/ines-amdjahed)

---
---

## English

### 📌 Project Overview

This repository contains the code and data associated with my **Master's thesis (M2)** in Information and Communication: Data and Society (Université Paris Nanterre, 2024).

**Topic:** *Analysis of Conspiratorial Rhetoric in the Post-Truth Era on Social Media*

This project is the empirical follow-up to an M1 thesis examining the psychological mechanisms (cognitive biases, heuristics) underlying conspiratorial and sectarian groups online.

---

### 🎯 Research Questions

> *How does conspiratorial rhetoric structure itself around a controversial news event? How does it evolve over time across different phases of media coverage? How does it vary depending on the specific characteristics of each social platform?*

**Hypotheses:**
- H1: Despite contradictory evidence, conspiratorial positions remain resistant to change — and may even intensify over time.
- H2: Conspiratorial rhetoric varies by platform, with specific discursive strategies for each social network.

---

### 🎈 Case Study: The Chinese Balloon Affair

| Phase | Date |
|---|---|
| Observation begins | January 28, 2023 |
| Peak media attention | February 4, 2023 |
| Balloons shot down | February 11, 2023 |
| Official U.S. government explanation | September 1, 2023 |

A Chinese surveillance balloon detected in U.S. airspace triggered a massive wave of social media reactions, ranging from acceptance of the official explanation (wind trajectory deviation) to conspiracy theories (military reconnaissance, government cover-up).

---

### 🧪 Methodology

**Data Collection**
- Scraping of **300 posts per platform** (Twitter/X, Facebook, Reddit)
- Period: January 2023 – September 2023

**Temporal segmentation**
```
Before Event  →  Event Start  →  Event Peak  →  Event End  →  Post-Debunking
```

**Processing (R)**
- Cleaning and standardization of 3 corpora
- Column harmonization across platforms
- Temporal phase categorization

**Analyses**
- 📊 Univariate analysis of reactions (likes, comments, shares) by phase and platform
- 💬 Sentiment analysis using `sentimentr` (mean score, categories: positive / neutral / negative)
- 🔠 Corpus preparation for **IRaMuTeQ** text analysis
- 📐 **Chi-square test** to validate cross-platform differences

---

### 📊 Key Findings

| Platform | Dominant Tone | Key Feature |
|---|---|---|
| **Twitter/X** | 🔴 Negative (especially at peak) | Fast, viral reactions; geopolitical focus |
| **Facebook** | 🟡 Moderate → positive post-debunking | Local interactions, varied topics |
| **Reddit** | 🟢 Consistently positive | Deep analytical debates, community engagement |

**Conclusions:**
- ✅ H1 confirmed: conspiratorial rhetoric **resists and sometimes intensifies** after debunking
- ✅ H2 confirmed: **platform-specific discursive strategies** were clearly observed

---

### 👩‍💻 Author

**Inès Amdjahed** — M2 Information & Communication: Data and Society  
Université Paris Nanterre · 2024  
📧 ines.amdjahed@email.com · 💼 [LinkedIn](https://linkedin.com/in/ines-amdjahed)
