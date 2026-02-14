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

## Running the Project

### Open in Google Colab (recommended)

1. Upload or open `01_workflow.ipynb` in Google Colab.
2. Run all cells from top to bottom.

If running locally, install dependencies:

```bash
pip install gensim scikit-learn numpy matplotlib scipy
Data
Parallel English–French sentences (Tatoeba format)

MUSE bilingual dictionary (en-fr.txt) used for supervised alignment

Large datasets are not included in this repository.

Workflow
The notebook performs the following steps:

Load and preprocess the parallel corpus (tokenization & cleaning)

Train word embeddings (Word2Vec & FastText)

Load MUSE bilingual dictionary

Align English & French embeddings using Procrustes mapping

Analyze linguistic properties:

synonym vs antonym similarity

translation similarity

polysemy example (bank)

out-of-vocabulary (OOV) coverage

Visualize embedding spaces using PCA and t-SNE

Train a language identification classifier using aligned embeddings

Output
results_summary.json
Contains:

alignment metrics

synonym vs antonym similarity

common word similarity

polysemy analysis

OOV coverage

classifier performance

Methods & Tools
Embeddings: gensim (Word2Vec, FastText)

Alignment: Orthogonal Procrustes mapping

Analysis: Cosine similarity & linguistic evaluation

Visualization: PCA & t-SNE (matplotlib, scikit-learn)

Classifier: Logistic Regression on aligned sentence embeddings

Results Summary
Multilingual Alignment
Procrustes mapping successfully aligned English vectors into French space.

Cosine similarity indicates a meaningful shared semantic space.

Linguistic Analysis
Synonyms show moderate similarity.

Antonyms may appear similar due to distributional semantics.

FastText provides strong OOV handling.

Downstream Task Performance
Language identification using aligned embeddings:

Accuracy: ≈ 97%

Precision: ≈ 0.97

Recall: ≈ 0.97

F1-score: ≈ 0.97

These results confirm the aligned embeddings retain meaningful linguistic structure.

Key Insights
✔ FastText improves vocabulary coverage and robustness
✔ Procrustes alignment enables cross-lingual semantic mapping
✔ Distributional embeddings capture similarity but struggle with antonyms
✔ Visualization confirms successful alignment
✔ High classification accuracy validates embedding usefulness

Academic Context
Université Claude Bernard Lyon 1
Master: Data & Intelligence for Smart Systems (DISS)
