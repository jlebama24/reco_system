# reco_system


# 🎬 Système de Recommandation de Films

Ce projet a pour objectif de proposer un moteur de recommandations personnalisées basé sur des données issues de la plateforme [Kaggle - The Movies Dataset](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset). Il a été réalisé dans le cadre de la Majeure Big Data 2025.

## 📁 Structure du projet

```
.
├── data/                       # Fichiers prétraités et objets picklés
│   ├── ratings_sample.csv
│   ├── movies.csv
│   ├── matrice_filtrée.pkl
│   └── similarité_filtrée.pkl
├── notebooks/                 # Explorations et EDA
│   └── eda_recommandation.ipynb
├── app.py                     # Interface principale Streamlit (modèle 1)
├── app_svd.py                 # Interface Streamlit du second modèle (SVD)
├── requirements.txt           # Dépendances
└── README.md
```

## 🚀 Lancement du projet

### 1. Cloner le dépôt

```bash
git clone https://github.com/ton-pseudo/reco-films.git
cd reco-films
```

### 2. Installer les dépendances

Crée un environnement virtuel si tu veux :

```bash
python -m venv venv
source venv/bin/activate  # ou .\venv\Scripts\activate sous Windows
pip install -r requirements.txt
```

> ⚠️ Pense à créer un fichier `.env` à la racine avec ta clé TMDb :

```
TMDB_API_KEY=ta_clé_tmdb
```

### 3. Lancer l'application principale

```bash
streamlit run app.py
```

### 4. Lancer l’interface alternative (modèle SVD)

```bash
streamlit run app_svd.py
```

## 📊 Fonctionnalités

- Recommandation par film (filtrage collaboratif item-item)
- Recommandation personnalisée par utilisateur
- Téléchargement des suggestions
- Affichage des métriques : RMSE, MAE, distribution des erreurs
- Visualisation : histogrammes, heatmaps, overview des films
- Deux modèles comparés (Collaboratif & SVD)

## 🧠 Modèles implémentés

- ✅ **Filtrage collaboratif basé sur la similarité entre items**
- ✅ **Factorisation matricielle (SVD via Surprise)**
- 🚧 (optionnel) Modèle hybride ou deep learning

## ⚠️ Limitations rencontrées

- Données initiales massives → échantillonnage à 10 000 ratings
- Modèle lent à évaluer sur l'ensemble des utilisateurs
- Premiers pas avec certaines technologies : TMDb API, Streamlit avancé

## 📚 Sources

- Kaggle : [The Movies Dataset](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset)
- [Surprise library](http://surpriselib.com/)
- [TMDb API](https://www.themoviedb.org/documentation/api)
- Tutoriel : [Getting Started with a Movie Recommendation System](https://www.kaggle.com/code/rounakbanik/movie-recommender-systems)
