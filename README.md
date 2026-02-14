# NLP Assignment 1: Multilingual Word Embeddings

**Author:** ADAM Muhammad Safi Ullah | p2516297

Exploration and alignment of word embeddings for English and French, including linguistic analysis and a downstream language identification task.

---

## Project Overview

This project builds and aligns English and French word embeddings into a shared semantic space. The aligned embeddings are analyzed linguistically and evaluated through a downstream classification task.

---

## Repository Structure

project/
├── 01_workflow.ipynb # Main Colab notebook (run all cells)
├── results_summary.json # Alignment, analysis & classifier metrics
├── en-fr.txt # MUSE bilingual dictionary used for alignment
├── NLP_Assignment1_Report.pdf # Final report (main deliverable)
└── README.md # Project documentation

---

## ▶️ How to Run (Google Colab)

1. Open the notebook in Colab.
2. Run all cells sequentially.

The notebook will:

1. Load and preprocess the EN–FR parallel corpus  
2. Train word embeddings (Word2Vec & FastText)  
3. Load MUSE bilingual dictionary  
4. Align embeddings using **Procrustes mapping**  
5. Analyze semantic properties  
6. Visualise embedding spaces  
7. Train a language identification classifier  

---

## 🔬 Methods Used

### 🔹 Embeddings
- Word2Vec  
- FastText (subword-aware; used for alignment)

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

*(optional — add your Colab link here)*

