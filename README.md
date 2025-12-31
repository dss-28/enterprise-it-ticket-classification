
# 📄 Enterprise IT Support Ticket Classification

## **Project Title**

**Enterprise IT Support Ticket Classification — Classical, Deep Learning & Embedding-based Approaches**

---

## **Project Summary**

Enterprise IT systems generate large volumes of **free-text support tickets** that must be manually routed to the correct operational teams (hardware, access, HR, etc.). This process is time-consuming, error-prone, and does not scale well with growing ticket volumes.

This project builds an **automated multi-class ticket classification system** using a **45,000-record real-world dataset**, systematically comparing **classical machine learning, deep learning, and embedding-based methods** under a unified experimental setup.

**Key Details**

* **Dataset:** 45,000 real-world IT support tickets
* **Task:** Multi-class text classification
  (`Hardware`, `Access`, `HR Support`, `Miscellaneous`)
* **Objective:** Benchmark NLP modeling approaches for enterprise-scale ticket triaging

---

## **Methodology Overview**

The project follows a **progressive modeling strategy**:

* **Phase 1:** Classical ML with sparse representations
* **Phase 2:** Sequence-based deep learning models
* **Phase 3:** Semantic embedding-based machine learning

This phased design enables **clear, fair comparison across NLP paradigms** on the same dataset.
Perfect — here’s exactly where and how to **add your class imbalance sentence** in that section:

---

### **Methodology Overview**

The project follows a **progressive modeling strategy**:

> **Note: There was significant class imbalance among the 8 categories, which we resolved using class weights in both classical ML and deep learning models.**

* **Phase 1:** Classical ML with sparse representations
* **Phase 2:** Sequence-based deep learning models
* **Phase 3:** Semantic embedding-based machine learning

This phased design enables **clear, fair comparison across NLP paradigms** on the same dataset.

---

## **Dataset Description**

* **Document:** Free-text IT support ticket description
* **Label:** `Topic_group` (ticket category)
* **Characteristics:** Noisy, unstructured, variable-length enterprise text
* **Number of samples:** 45,000 samples
* * **Number of classes:** 8

---

## **Text Preprocessing**

Text preprocessing was **fully implemented and model-specific**, ensuring compatibility with each NLP approach:

* **Common steps (all models):**

  * Lowercasing
  * Whitespace normalization
  * Removal of null and extremely short samples

* **Classical ML & Deep Learning models:**

  * Tokenization using Keras tokenizer
  * Vocabulary size control
  * Padding and truncation for sequence models

* **Embedding-based models:**

  * **Word2Vec:**
    Preprocessing performed using **Gensim’s `simple_preprocess`**, which includes:

    * Lowercasing
    * Tokenization
    * Removal of punctuation and short tokens
  * **SBERT:**
    Raw cleaned text passed directly to the transformer encoder (no manual tokenization required)

This preprocessing pipeline ensures **clean separation between feature engineering and modeling logic**.

---

## **Project Phases (Full 45k Dataset)**

### **Phase 1 — Classical Machine Learning Baseline**

* **Text Representation:** TF-IDF
* **Models:** Logistic Regression, Linear SVM

| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | ~80%     |
| Linear SVM          | ~81%     |

> Establishes a strong, CPU-efficient baseline for enterprise-scale text classification.

---

### **Phase 2 — Deep Learning Models**

* **Text Representation:** Tokenized and padded sequences
* **Models Evaluated:**

| Model       | Accuracy |
| ----------- | -------- |
| Simple RNN  | ~65%     |
| Stacked RNN | ~70%     |
| LSTM        | ~81%     |
| GRU         | ~82%     |

> LSTM and GRU effectively capture sequential dependencies, significantly outperforming vanilla RNNs.

---

### **Phase 3 — Embedding-Based Machine Learning**

* **Text Representation:** Dense semantic embeddings (SBERT using MiniLM and Word2Vec)
* **Classifier:** Linear SVM

| Embedding Method | Accuracy |
| ---------------- | -------- |
| Word2Vec + SVM   | ~82%     |
| SBERT + SVM      | ~80–81%  |

> Embedding-based approaches introduce semantic understanding while remaining efficient for production inference.
Hence,this approach is better than TF-IDF or dl models in real word applicabilty, due to comparable accuracy, and computationally less expensive.
---
Confusion Matrix — Final Model

The confusion matrix below shows performance across all 8 classes:

Classification Report — Final Model
Class	Precision	Recall	F1-Score	Support
Access	0.85	0.86	0.85	1412
Administrative rights	0.86	0.64	0.73	350
HR Support	0.79	0.79	0.79	2171
Hardware	0.76	0.80	0.78	2708
Internal Project	0.85	0.78	0.81	423
Miscellaneous	0.73	0.73	0.73	1408
Purchase	0.94	0.85	0.89	492
Storage	0.83	0.82	0.83	554
Accuracy			0.79	9518
Macro Avg	0.83	0.78	0.80	9518
Weighted Avg	0.80	0.79	0.79	9518
You should paste the **Classification Report table** **right after the confusion matrix section** in your README.

Here’s the **ideal flow for that part of the README**:

---

### Phase 3 — Embedding-Based Machine Learning

*(SBERT + SVM, Word2Vec + SVM, MiniLM for SBERT)*

* Text Representation: Dense semantic embeddings
* Classifier: Linear SVM

| Embedding Method | Accuracy |
| ---------------- | -------- |
| Word2Vec + SVM   | ~82%     |
| SBERT + SVM      | ~80–81%  |

> Embeddings capture context better than TF-IDF or sequence models, achieve comparable accuracy, and are less computationally expensive.

---

## Confusion Matrix — Final Model

The confusion matrix below shows performance across all 8 classes:

---

## Classification Report — Final Model

| Class                 | Precision | Recall | F1-Score | Support |
| --------------------- | --------- | ------ | -------- | ------- |
| Access                | 0.85      | 0.86   | 0.85     | 1412    |
| Administrative rights | 0.86      | 0.64   | 0.73     | 350     |
| HR Support            | 0.79      | 0.79   | 0.79     | 2171    |
| Hardware              | 0.76      | 0.80   | 0.78     | 2708    |
| Internal Project      | 0.85      | 0.78   | 0.81     | 423     |
| Miscellaneous         | 0.73      | 0.73   | 0.73     | 1408    |
| Purchase              | 0.94      | 0.85   | 0.89     | 492     |
| Storage               | 0.83      | 0.82   | 0.83     | 554     |
| **Accuracy**          |           |        | 0.79     | 9518    |
| **Macro Avg**         | 0.83      | 0.78   | 0.80     | 9518    |
| **Weighted Avg**      | 0.80      | 0.79   | 0.79     | 9518    |

---


## **Evaluation Setup**

* **Metric:** Accuracy (multi-class classification)
* **Dataset Usage:** Full 45k dataset used consistently across all phases
* **Comparison Strategy:** Same labels, same splits, same evaluation metric

---

## **Tech Stack**

* **Language:** Python 3.x

* **Libraries:**
  `pandas`, `numpy`, `scikit-learn`,
  `tensorflow / keras`, `gensim`,
  `sentence-transformers`, `matplotlib`

* **Models:**
  Logistic Regression, Linear SVM, RNN, LSTM, GRU, Word2Vec + SVM, SBERT + SVM

---

## **Project Structure**

```
project/
│
├─ data/
│   └─ tickets.csv
│
├─ notebooks/
│   ├─ phase1_classical_ml.ipynb
│   ├─ phase2_dl_models.ipynb
│   └─ phase3_embeddings_svm.ipynb
│
├─ README.md
```

---

## **Why This Project Stands Out**

* Uses a **large real-world enterprise dataset**
* Structured **phase-wise comparison** across NLP paradigms
* Covers **classical ML, deep learning, and semantic embeddings**
* Clean preprocessing-to-model separation
* Strong **portfolio and interview discussion value**

---

## **Future Enhancements**

* Hyperparameter tuning
* Few Shot Learning
* Online Learning
* Deployment-ready API

---

If you want, next I can:

* 🔥 tighten this further for **recruiter skim-read**
* 🔁 align README + LinkedIn post wording 1:1
* 🧠 add a **“Key Learnings”** section (very interview-friendly)

Just say the word.
