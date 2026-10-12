<div align="center">

# 👋 Bonjour, je suis Benoist Légal

### Data Engineering · Architecture des données · IA & Analytics

*De la compréhension des besoins à l'industrialisation de solutions data.*

[![GitHub](https://img.shields.io/badge/GitHub-benstL-181717?style=for-the-badge&logo=github)](https://github.com/benstL)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Me%20contacter-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/)
![Profile views](https://komarev.com/ghpvc/?username=benstL&style=for-the-badge&color=28647B)

</div>

---

## 👨‍💻 À propos

🎓 Diplômé du **Master Ingénierie de la Donnée — Mines Paris – PSL Executive Education × Liora**.

🏗️ **Trois années à l'INA**, à l'interface entre équipes métiers et techniques : architecture applicative, documentation technique, traitements de données et industrialisation de projets.

🔎 J'aime comprendre les systèmes dans leur ensemble : flux, données, contraintes, usages, et même faire de la rétro-ingénierie quand c'est nécessaire.

🌱 Je poursuis ma montée en compétences en **Data Engineering, DataOps, Machine Learning et architectures data**.

> Mon fil conducteur : construire des solutions compréhensibles, maintenables et utiles.

---

## 🍽️ YUMMY — Mon projet Data & IA

![Statut](https://img.shields.io/badge/Statut-En%20%C3%A9volution-2EA44F?style=flat-square)
![Projet](https://img.shields.io/badge/Type-Projet%20personnel%20%26%20acad%C3%A9mique-28647B?style=flat-square)
![Architecture](https://img.shields.io/badge/Architecture-Medallion-8A63D2?style=flat-square)

**YUMMY** est une plateforme expérimentale de **recommandation de recettes fondée sur les données**. Elle rapproche des recettes et avis utilisateurs, des informations sur la saisonnalité et des indicateurs de disponibilité alimentaire pour proposer des recommandations contextualisées.

L'utilisateur peut explorer des recettes selon son **pays**, le **mois** et les **ingrédients** qui l'intéressent. L'objectif n'est pas seulement de classer les recettes, mais aussi **d'expliquer les critères utilisés** et de signaler les limites des données.

### 🎯 Ce que j'explore avec YUMMY

- **Data Engineering** : ingestion, nettoyage, standardisation et enrichissement des données.
- **Architecture** : séparation Bronze / Silver / Gold et stockage analytique.
- **Data Science** : analyse de sentiment, regroupement de recettes et scoring multicritère.
- **API & produit** : exposition des recommandations et interface de consultation.
- **Qualité & transparence** : distinction entre saisonnalité documentée et disponibilité estimée.

### 🏗️ Architecture conceptuelle

```mermaid
flowchart TD
    A[Food.com<br/>Recettes et avis] --> B[Bronze<br/>Données brutes]
    E[EUFIC<br/>Saisonnalité européenne] --> B
    F[FAOSTAT<br/>Production annuelle] --> B
    B --> C[Silver<br/>Nettoyage et standardisation]
    C --> D[Gold<br/>Enrichissement et scores]
    D --> G[Recommandations<br/>YUMMY Score]
    G --> H[FastAPI<br/>Services de recommandation]
    G --> I[Streamlit<br/>Interface MVP]
    D -. Stockage / synchronisation .-> J[(MinIO / Parquet)]
    K[Airflow<br/>Orchestration des traitements] -.-> C
    K -.-> D
```

> **Note d'architecture :** le MVP Streamlit peut lire les données Gold locales ; MinIO n'est pas nécessairement interrogé à chaque consultation. Ce schéma présente les principaux composants du projet, pas une infrastructure cloud déjà déployée.

### 🧪 Sources de données

| Source | Rôle dans le projet | Limite à connaître |
|---|---|---|
| **Food.com** | Recettes, ingrédients et avis | Données historiques et qualité variable |
| **EUFIC** | Références de saisonnalité en Europe | Couverture principalement européenne |
| **FAOSTAT** | Indicateurs de production par pays | La production annuelle **ne mesure pas** directement la saisonnalité mensuelle |

### 🧰 Stack du projet

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-FFF000?logo=duckdb&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)
![Apache Airflow](https://img.shields.io/badge/Airflow-017CEE?logo=apacheairflow&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?logo=dbt&logoColor=white)
![MinIO](https://img.shields.io/badge/MinIO-C72E49?logo=minio&logoColor=white)

### 🚧 Un projet en évolution continue

**MVP et travaux déjà engagés**

- [x] Collecte et préparation des données de recettes
- [x] Structuration Bronze / Silver / Gold
- [x] Premiers traitements NLP, clustering et scoring
- [x] Première API FastAPI et interface Streamlit
- [x] Expérimentation d'une orchestration Airflow et du stockage MinIO

**Prochaines améliorations**

- [ ] Renforcer les tests automatiques et les contrôles qualité
- [ ] Consolider les modèles dbt et les contrats de données
- [ ] Uniformiser l'exécution avec Docker Compose
- [ ] Ajouter une observabilité plus complète (Prometheus / Grafana)
- [ ] Améliorer l'explicabilité et le niveau de confiance des recommandations
- [ ] Étudier la traduction FR / EN et un déploiement cloud

<details>
<summary><strong>🔍 Comment fonctionne le YUMMY Score ?</strong></summary>

Le score expérimental combine plusieurs dimensions : appréciation des recettes, cohérence des ingrédients, temps de préparation et indicateurs de saisonnalité ou de disponibilité. Les pondérations et leur validation restent des axes d'amélioration.

La disponibilité estimée à partir de FAOSTAT ne doit pas être présentée comme une preuve de saisonnalité locale.

</details>

<details>
<summary><strong>🧭 Pourquoi ce projet ?</strong></summary>

YUMMY est mon terrain d'expérimentation de bout en bout : partir de données hétérogènes, concevoir des transformations reproductibles, construire un produit consultable et documenter honnêtement les limites des indicateurs.

</details>

➡️ **Retrouver le projet :** [mes dépôts GitHub](https://github.com/benstL?tab=repositories) — rechercher **YUMMY**.

---

## 🛠️ Technologies & pratiques

| Domaine | Technologies / sujets |
|---|---|
| **Traitement & analyse** | Python, SQL, Pandas, DuckDB, Parquet |
| **Orchestration & DataOps** | Airflow, Dagster, Docker, Jenkins, GitHub Actions |
| **Stockage & modélisation** | MongoDB, MinIO, dbt, architectures Medallion |
| **Applications** | FastAPI, Streamlit, APIs REST |
| **IA & NLP** | Classification, analyse de sentiment, clustering, BERT |
| **Architecture & collaboration** | DAT, schémas de flux, documentation, interfaces métier/technique |

<details>
<summary><strong>⚙️ Ce que j'aime approfondir</strong></summary>

- La fiabilité des pipelines : reprise sur erreur, idempotence, qualité et traçabilité.
- Le passage du prototype à un système industrialisable.
- L'observabilité, les tests et les pratiques CI/CD.
- La compréhension des systèmes existants et leur évolution progressive.

</details>

---

## 📈 GitHub en un coup d'œil

<div align="center">

![Statistiques GitHub](https://github-readme-stats.vercel.app/api?username=benstL&show_icons=true&hide_border=true&theme=github_dark)

![Langages](https://github-readme-stats.vercel.app/api/top-langs/?username=benstL&layout=compact&hide_border=true&theme=github_dark)

</div>

> Ces cartes proviennent d'un service externe et peuvent être momentanément indisponibles. Elles reflètent l'activité GitHub publique, pas l'ensemble de mon expérience professionnelle.

---

<div align="center">

### 🤝 Échangeons

Je suis ouvert aux échanges techniques, aux collaborations et aux opportunités autour de la data et de l'IA.

**Merci de votre visite !**

</div>
