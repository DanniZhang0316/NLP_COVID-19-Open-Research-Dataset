 Topic Clustering of COVID-19 Open Research
Overview

This project analyzes open-access COVID-19 research papers to identify, cluster, and track major research themes and their evolution across decades. Semantic embeddings and unsupervised clustering are used to group articles based on abstract content rather than keyword frequency.

Methods
Semantic Embeddings

Sentence-BERT (SBERT) was used to convert each abstract into a 384-dimensional semantic vector, capturing contextual meaning beyond keyword matching.

Dimensionality Reduction

Principal Component Analysis (PCA) was applied to reduce computational complexity while retaining 70% of the total variance (n_components = 0.7), reducing dimensions from 384 to 78.

Topic Clustering

Topics were identified using MiniBatchKMeans, selected for its efficiency on large datasets. The optimal number of clusters was set to k = 20 based on silhouette score analysis.

Topic Interpretation

TF-IDF was used to extract representative terms for each topic. Generic COVID-19 terms (e.g., covid, pandemic, sars-cov-2) were removed to improve topic clarity. Final topic labels were manually assigned with assistance from Claude Sonnet 4.5.

Results

20 distinct research topics identified

Word clouds used to visualize topic-specific keywords

Temporal analysis reveals shifts in research focus from 1970–2020

Representative papers extracted for each topic using cosine similarity

Tools

Sentence-BERT (SBERT)

PCA

MiniBatchKMeans

TF-IDF

Cosine similarity
