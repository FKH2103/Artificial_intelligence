# Snappfood Persian Sentiment Analysis using CNN

This repository contains a Convolutional Neural Network (CNN) built with PyTorch to perform sentiment analysis on Persian user reviews from Snappfood. Developed as Computer Assignment 4 for the Artificial Intelligence course, the model classifies customer comments into binary sentiment categories: HAPPY or SAD.

## Project Overview
The project pipeline ingests raw textual reviews, normalizes the Persian text, maps the vocabulary to pre-trained FastText embeddings, and trains a CNN to capture local semantic dependencies for accurate sentiment classification.

## Methodology
* **Text Preprocessing:** Cleans raw Persian text by removing URLs, mentions, and stopwords using the stopwords-iso repository. Standardizes characters (e.g., converting Arabic "ي" and "ك" to Persian "ی" and "ک") and converts English digits to Persian digits.
* **Feature Engineering:** Sequences are standardized to a fixed length of 50 tokens via padding and truncation. Words are mapped to 300-dimensional vectors using the pre-trained Persian FastText model (`cc.fa.300.vec`).
* **CNN Architecture:**
  * **Embedding Layer:** Frozen pre-trained FastText weights to prevent overfitting on the training vocabulary.
  * **Convolutional Layer:** `Conv1d` with 128 output channels, a kernel size of 3, and padding of 1 to extract local textual features (n-grams).
  * **Pooling Layer:** `MaxPool1d` with a kernel size of 2 to downsample feature maps.
  * **Regularization & Output:** A Dropout layer (`p=0.5`) feeds into a Fully Connected (`Linear`) layer mapping to the 2 target classes.
* **Training & Optimization:** Trained using the Adam optimizer with weight decay and CrossEntropyLoss. An Early Stopping mechanism monitors validation accuracy to save the optimal model weights.

## Results
Evaluated on an independent test set of 7,000 samples, the model achieved a 78.61% overall accuracy. The network demonstrates a high recall (0.84) for the SAD class, making it highly effective at detecting customer complaints in a real-world business context.

## Repository Contents
* `AI_CA4_Fall2025_snappfood.zip`: The dataset archive containing the train, dev, and test sets.
* `AI_CA4_Fall2025_2.pdf`: The formal assignment description and architectural guidelines.
* `AI_CA4_Fall2025.ipynb`: The Jupyter Notebook containing the data pipeline, PyTorch model definition, training loop, and evaluation visualizations (Classification Report & Confusion Matrix).

## Technologies & Libraries Used
* **Deep Learning Framework:** PyTorch (`torch.nn`, `torch.optim`)
* **Data Manipulation:** Pandas, NumPy
* **Natural Language Processing:** Regular Expressions (`re`), FastText
* **Evaluation & Visualization:** Scikit-learn, Matplotlib, Seaborn

## Author
**Faezeh Khanmohamadi**
