# 📊 Pipeline ETL Big Data — Transport & Open Data

**Master 2 Calcul Scientifique (M2 CS)**  
Université de Reims Champagne-Ardenne

Ce projet consiste à développer un pipeline complet de Data Engineering permettant la collecte, le stockage, la transformation et l’analyse de données issues de différentes APIs publiques.

---

## 👥 Auteurs

- Moulouka Mohamed
- Mohamed Daher
- Traoré Yannick Quentin

---

## 🎯 Objectifs du projet

Le but du projet est de construire une architecture de traitement de données similaire à celle utilisée en entreprise :

- Collecter automatiquement des données ouvertes
- Les stocker dans un Data Lake
- Les nettoyer et les structurer
- Les charger dans un Data Warehouse
- Produire des indicateurs analytiques

---

## 🧭 Architecture du pipeline

Le pipeline suit une **Medallion Architecture** en trois couches.

### 🥉 Bronze — Data Lake (Google Cloud Storage)
Stockage des données brutes récupérées depuis les APIs publiques.  
Aucune transformation n’est appliquée.

### 🥈 Silver — Data Warehouse brut (BigQuery)
Données nettoyées et structurées :
- suppression des valeurs manquantes
- typage des colonnes
- normalisation

### 🥇 Gold — Couche analytique
Données agrégées et prêtes pour l’analyse métier :
- indicateurs statistiques
- tables analytiques
- exploitation décisionnelle

---

## 🧭 Schéma d’architecture

![Architecture du projet](images/architecture.png)

---

## 📂 Structure du projet

```
bigdata-etl-sncf-gcp/
│
├── notebooks/
│   ├── 0_test_connection.ipynb
│   ├── 1_ingest_to_gcs.ipynb
│   ├── 2_load_to_bigquery.ipynb
│   └── 3_analyze_for_gold.ipynb
│
├── src/
│   ├── gcs_utils.py
│   └── bq_utils.py
│
├── data/
├── report/
├── images/
├── requirements.txt
└── README.md
```

---

## 🧰 Technologies utilisées

- Python 3.11
- Pandas
- Google Cloud Platform
- Google Cloud Storage (GCS)
- BigQuery
- APIs Open Data

---

## 🔗 Sources de données

- Île-de-France Mobilités Open Data
- Open-Meteo API
- API Gouvernement (jours fériés)
- GeoAPI (communes)

---

## ⚙️ Installation

Cloner le projet :

```bash
git clone https://github.com/<votre-repo>.git
cd bigdata-etl-sncf-gcp
```

Créer un environnement virtuel :

```bash
python -m venv venv
```

Activer l’environnement :

### Windows
```bash
venv\Scripts\activate
```

### Linux / Mac
```bash
source venv/bin/activate
```

Installer les dépendances :

```bash
pip install -r requirements.txt
```

---

## 🔐 Configuration

Créer un fichier `.env` à la racine du projet :

```
PROJECT_ID=your-gcp-project-id
GOOGLE_APPLICATION_CREDENTIALS=secrets/service-account.json
BUCKET_NAME=your-gcs-bucket-name
```

---

## ▶️ Exécution du pipeline

Lancer Jupyter Notebook :

```bash
jupyter notebook
```

Puis exécuter les notebooks dans l’ordre :

1. 0_test_connection
2. 1_ingest_to_gcs
3. 2_load_to_bigquery
4. 3_analyze_for_gold

---

## 📊 Résultats attendus

À la fin du pipeline :

- les données sont stockées dans BigQuery
- les tables sont nettoyées
- les indicateurs sont calculés
- la base est prête pour l’analyse métier

---

## 📑 Rapport

Le rapport détaillé du projet est disponible ici :

[📄 Télécharger le rapport](report/rapport.pdf)

---

## 📜 Licence

Projet réalisé uniquement dans un cadre pédagogique universitaire.
