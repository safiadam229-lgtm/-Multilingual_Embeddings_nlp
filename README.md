# NLP Assignment: Multilingual Word Embeddings

## **Author:** ADAM Muhammad Safi Ullah | p2516297

Exploration and comparison of word embeddings for English and French, including alignment, analysis, and a downstream language identification task.
---

## Project Overview

This project builds and aligns English and French word embeddings into a shared semantic space. The aligned embeddings are analyzed linguistically and evaluated through a downstream classification task.

---

## Data

- **Parallel corpus**: `data/Sentence pairs in English-French - 2026-02-12.tsv` https://tatoeba.org/en/downloads (Tatoeba format: id_en, english, id_fr, french)
- **GloVe**: Download [glove.6B.zip](https://nlp.stanford.edu/projects/glove/) and place in `data/`. If missing, the code falls back to Word2Vec.
- **Bilingual dictionary**:  MUSE English–French dictionary (en-fr.txt) used as supervised translation pairs for alignment. Filtered to retain only word pairs present in both embedding vocabularies.
 
## Repository Structure

```
project/
├── 01_workflow.ipynb            # Main Colab notebook (run all cells)
├── results_summary.json         # Alignment, analysis & classifier metrics
├── en-fr.txt                    # MUSE bilingual dictionary used for alignment
├── NLP_Assignment1_Report.pdf   # Final report (main deliverable)
└── README.md                    # Project documentation
```


## ⭐ Open in Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]
(https://colab.research.google.com/drive/1Zu4ONhRJNYLT-nkaqwmy9aUBVmjPfLkH?usp=sharing)

---

## ▶️ How to Run (Google Colab)

1. Open the notebook in Colab.
2. Run all cells sequentially.

The notebook workflow:

  ## step_1: Load & preprocess corpus
    details:
      - load English–French parallel sentences - (source: https://tatoeba.org/en/downloads)
      - lowercase and clean text
      - tokenize sentences

  ## step_2: Train word embeddings
    details:
      - Word2Vec embeddings
      - FastText embeddings (subword-aware)
      - Loaded pretrained GloVe vectors (6B) and used them as global semantic embeddings.
      - OOV Handling
      - Visualization
    FastText was used for alignment due to its robustness to rare/OOV words.


  ## step_3: Load bilingual dictionary &  Multilingual alignment
    details:
      - load MUSE English–French dictionary (en-fr.txt)
      - filter usable word pairs present in vocabularies
      - learn orthogonal Procrustes mapping
      - map English vectors into French embedding space
      - evaluate alignment with cosine similarity

  ## step_4: Linguistic analysis
    details:
      - synonyms vs antonyms similarity
      - translation (common word) similarity
      - polysemy example analysis (bank)
      - out-of-vocabulary (OOV) coverage

  ## step_5: Visualization
    details:
      - PCA projection of embeddings
      - t-SNE visualization of semantic clusters
      - multilingual PCA to inspect alignment quality

 ## step_6: Downstream task
    details:
      - build sentence embeddings by averaging word vectors
      - map English sentences into shared space
      - train Logistic Regression classifier  for EN–FR language identification
      - evaluate language identification performance using accuracy and F1-score
---

## 🔬 Methods Used

### 🔹 Embeddings
- One-Hot encoding
- TF-iDF
- Word2Vec  
- FastText (subword-aware; used for alignment)
- GloVe
- GloVe embeddings: Loaded pretrained 100-dimensional GloVe vectors (glove.6B.100d.txt) extracted from the GloVe 6B dataset to provide globally learned semantic representations based on word co-occurrence statistics.
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




