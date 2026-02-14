# NLP Assignment: Multilingual Word Embeddings

**Author:** ADAM Muhammad Safi Ullah | p2516297

Exploration and comparison of word embeddings for English and French, including alignment, analysis, and a downstream language identification task.
---

## Project Overview

This project builds and aligns English and French word embeddings into a shared semantic space. The aligned embeddings are analyzed linguistically and evaluated through a downstream classification task.

---

repository_structure:

  project:
    - 01_workflow.ipynb: "Main Colab notebook (run all cells)"
    - results_summary.json: "Alignment, analysis & classifier metrics"
    - en-fr.txt: "MUSE bilingual dictionary used for alignment"
    - NLP_Assignment1_Report.pdf: "Final report (main deliverable)"
    - README.md: "Project documentation"


---

## ▶️ How to Run (Google Colab)

1. Open the notebook in Colab.
2. Run all cells sequentially.

The notebook workflow:
  step_1:
    name: Load & preprocess corpus
    details:
      - load English–French parallel sentences
      - lowercase and clean text
      - tokenize sentences

  step_2:
    name: Train word embeddings
    details:
      - train Word2Vec embeddings
      - train FastText embeddings (subword-aware)

  step_3:
    name: Load bilingual dictionary
    details:
      - load MUSE English–French dictionary (en-fr.txt)
      - filter usable word pairs present in vocabularies

  step_4:
    name: Multilingual alignment
    details:
      - learn orthogonal Procrustes mapping
      - map English vectors into French embedding space
      - evaluate alignment with cosine similarity

  step_5:
    name: Linguistic analysis
    details:
      - synonyms vs antonyms similarity
      - translation (common word) similarity
      - polysemy example analysis (bank)
      - out-of-vocabulary (OOV) coverage

  step_6:
    name: Visualization
    details:
      - PCA projection of embeddings
      - t-SNE visualization of semantic clusters
      - multilingual PCA to inspect alignment quality

  step_7:
    name: Downstream task
    details:
      - build sentence embeddings by averaging word vectors
      - map English sentences into shared space
      - train Logistic Regression classifier
      - evaluate language identification performance
---

## 🔬 Methods Used

### 🔹 Embeddings
- One-Hot encoding
- TF-iDF
- Word2Vec  
- FastText (subword-aware; used for alignment)
- GloVe

### 🔹 Multilingual Alignment
- MUSE bilingual dictionary (~113k pairs)
- Orthogonal Procrustes mapping
- English vectors mapped into French space

### 🔹 Linguistic Analysis
- Synonyms vs antonyms similarity
- Translation similarity (common words)
- Polysemy example (*bank*)
- OOV coverage evaluation

### 🔹 Visualization
- PCA projection of embeddings
- t-SNE semantic clustering
- Multilingual PCA showing alignment

### 🔹 Downstream Task
Language identification using aligned sentence embeddings.

---

## 📊 Results

### Multilingual Alignment
- Alignment achieved using Procrustes mapping
- Cosine similarities indicate meaningful shared space

### Linguistic Insights
- Synonyms show moderate similarity
- Antonyms may appear similar (distributional semantics effect)
- FastText provides strong OOV handling

### Downstream Classification
Using aligned embeddings:

- **Accuracy:** ≈ 97%  
- **Precision:** ≈ 0.97  
- **Recall:** ≈ 0.97  
- **F1-score:** ≈ 0.97  

This confirms aligned embeddings retain meaningful linguistic structure.

---

## 📂 Output File

### `results_summary.json`
Contains:

- alignment metrics  
- synonym vs antonym similarity  
- common word similarity  
- polysemy analysis  
- OOV coverage  
- classifier performance  

---

## 🧠 Key Takeaways

✔ FastText improves vocabulary coverage and robustness  
✔ Procrustes alignment enables cross-lingual semantic mapping  
✔ Distributional embeddings capture similarity but struggle with antonyms  
✔ Visualization confirms successful alignment  
✔ High classification accuracy validates embedding usefulness  

---

## 🛠 Libraries Used

- gensim  
- scikit-learn  
- numpy  
- matplotlib  
- scipy  

---

## 🎓 Academic Context

Université Claude Bernard Lyon 1  
Master: Data & Intelligence for Smart Systems (DISS)

---

## ⭐ Open in Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]
(https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO/blob/main/01_workflow.ipynb)


