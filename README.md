# 💊 Drug Review Intelligence: Deep Learning for Pharmacovigilance

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![HuggingFace](https://img.shields.io/badge/Transformers-DistilBERT-yellow)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📄 Project Overview
This project applies **Deep Learning** and **Natural Language Processing (NLP)** to automate the analysis of patient drug reviews. By processing unstructured text data, the system predicts:
1.  **Patient Satisfaction (Rating 1-10):** Using Regression.
2.  **Side Effect Severity:** Using Classification (e.g., Mild, Moderate, Severe).

The project evolves from simple Machine Learning baselines to advanced **Multi-Task Bi-Directional LSTMs** and finally to fine-tuned **BERT Transformers**.

---

## 📊 Key Results

| Model Architecture | Rating Error (MAE) ⬇ | Side Effect Accuracy ⬆ | Severe Class Recall ⬆ |
| :--- | :--- | :--- | :--- |
| **Baseline (TF-IDF + LR)** | 2.99 | 46.1% | 0.30 |
| **Deep Learning (Bi-LSTM)** | 2.09 | 33.0% | 0.22 |
| **Transformer (DistilBERT)** | **1.63** 🏆 | **42.0%** | **0.31** ✅ |

> **Key Insight:** The BERT model reduced the rating prediction error by **45%** compared to the baseline and successfully handled the class imbalance for "Severe" side effects using sample weighting.

---

## 🛠️ Methodology
1.  **Data Preprocessing:**
    * Text cleaning & concatenation of review segments.
    * Handling class imbalance using **Computed Sample Weights**.
    * Sub-word tokenization for Transformer models.
2.  **Model 1: Multi-Task Bi-LSTM**
    * Embedding Layer (64-dim).
    * Bi-Directional LSTM to capture sequential context.
    * Dual-head output (Linear for regression, Softmax for classification).
3.  **Model 2: DistilBERT (Fine-Tuned)**
    * Transfer learning using `distilbert-base-uncased`.
    * Fine-tuned for 3 epochs on the specific pharmacovigilance task.

---

## 📂 Repository Structure
```
├── data/
│   ├── drugLibTrain_raw.tsv  # Training Data
│   ├── drugLibTest_raw.tsv   # Testing Data
├── notebooks/
│   └── Drug_Review_Intelligence.ipynb  # Complete Colab Notebook
├── reports/
│   └── Project_Report.docx   # Detailed Business & Technical Report
└── README.md                 # Project Documentation
```

## 🚀 How to Run
1.  Clone the repository.
2.  Upload the `.ipynb` file to **Google Colab**.
3.  Upload the dataset files (`.tsv`) to the Colab session storage.
4.  Enable **GPU Runtime** (Runtime > Change runtime type > T4 GPU).
5.  Run all cells.

## 👤 Author
Sendhil Kumar 
Data Scientist / Deep Learning Engineer
Deep Learning Assignment

---
*Created as part of an academic portfolio project.*
