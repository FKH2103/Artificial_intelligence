# Amazon Fine Food Reviews Clustering

This repository contains an unsupervised machine learning project focused on clustering textual user reviews from the Amazon Fine Food Reviews dataset. Developed as Computer Assignment 5 for the Artificial Intelligence course at the University of Tehran, the project groups semantically similar reviews to uncover hidden patterns and topics.

## Project Overview
The pipeline processes raw, unstructured review strings into a clean dataset, extracts high-dimensional semantic embeddings, and applies clustering algorithms to segment the data visually and mathematically.

## Methodology
* **Data Parsing & Preprocessing:** Uses Regular Expressions to parse a raw text format into 9 structured features (including `Id`, `UserId`, `Score`, `Summary`, and `Text`). Text data is cleaned using NLTK via lowercasing, punctuation removal, stopword removal, and lemmatization.
* **Feature Extraction:** Converts processed text into 384-dimensional numerical vectors using the `sentence-transformers` library and the pre-trained `all-MiniLM-L6-v2` model.
* **Dimensionality Reduction:** Applies Principal Component Analysis (PCA) and t-SNE to reduce high-dimensional embeddings into 2D spaces for visual cluster analysis.
* **Clustering Algorithms:** Implements K-Means (optimized via the Elbow Method), DBSCAN, and Hierarchical Clustering to group the review data.
* **Evaluation:** Evaluates the quality and separation of the resulting clusters quantitatively using the Silhouette Score.

## Repository Contents
* `AI_CA5_Fall2025_amazon_reviews.csv`: The primary dataset containing user reviews, product scores, and timestamps.
* `AI_CA5_Fall2025.pdf`: The formal assignment description and requirement guidelines.
* `main_notebook.ipynb`: The Jupyter Notebook containing the data analysis, pipeline execution, markdown explanations, and result visualizations.

## Technologies & Libraries Used
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (K-Means, PCA, t-SNE)
* **Natural Language Processing:** NLTK, SentenceTransformers
* **Visualization:** Matplotlib, Seaborn

## Author
**Faezeh Khanmohamadi**
