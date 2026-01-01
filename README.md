# Topic Clustering of COVID-19 Open Research

## Overview
This project analyzes open-access COVID-19 research papers to identify, cluster, and track major research themes and their evolution across decades. It uses semantic embeddings and unsupervised learning to group papers based on abstract meaning rather than keyword frequency.

## Dataset Overview
The [CORD-19 Dataset](https://www.kaggle.com/datasets/allen-institute-for-ai/CORD-19-research-challenge) is a large open-access collection of scientific publications related to the COVID-19 pandemic. It is curated by the Allen Institute for natural language processing challenges on Kaggle. The file metadata.csv contains over one million records and includes 19 variables that describe essential article information, such as titles, abstracts, author names, publication dates, and source details.


## Methods
- **Semantic embeddings (SBERT):** Convert each abstract into a **384-dimensional** vector representation.
- **Dimensionality reduction (PCA):** Retain **70% variance** (`n_components=0.7`), reducing **384 → 78** dimensions.
- **Clustering (MiniBatchKMeans):** Cluster papers into **k = 20** topics (selected via **silhouette score**).
- **Topic labeling (TF-IDF + filtering):** Extract top terms per cluster, remove generic COVID terms (e.g., *covid*, *pandemic*, *sars-cov-2*), then **manually assign labels** with assistance from **Claude Sonnet 4.5**.

## Outputs
- **20 labeled topics**
- **Word clouds** for topic keywords
- **Topic frequency over time** (1970–2020)
- **Top 3 representative papers per topic** (cosine similarity to topic centroid)

