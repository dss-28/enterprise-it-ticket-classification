

# 📄 GitHub Project: Enterprise IT Support Ticket Classification

## **Project Title:**

**Enterprise IT Support Ticket Classification — Classical, DL & Embedding-based ML**

---

## **Project Summary**

This project classifies **IT support tickets** into operational categories using **full 45k dataset**.

* **Dataset:** 45,000 real-world tickets
* **Task:** `Hardware`, `Access`, `HR Support`, `Miscellaneous`
* **Goal:** Showcase staged experiments using classical ML, deep learning, and embeddings

**Highlights:**

* Phase 1: TF-IDF + classical ML
* Phase 2: Deep Learning (RNN, Stacked RNN, LSTM, GRU)
* Phase 3: Embedding-based ML (SBERT + SVM, Word2Vec + SVM)

---

## **Project Phases (Full 45k dataset)**

### **Phase 1 — Classical ML Baseline**

* **Models:** Logistic Regression, Linear SVM
* **Text Features:** TF-IDF (BoW tested)
* **Results:**

| Model               | Accuracy |
| ------------------- | -------- |
| Logistic Regression | 0.80     |
| Linear SVM          | 0.81     |

> CPU-friendly, strong baseline.

---

### **Phase 2 — Deep Learning Experiments**

* **Text Representation:** Sequences of tokenized tickets
* **Models & Results:**

| Model       | Accuracy |
| ----------- | -------- |
| Simple RNN  | 65%      |
| Stacked RNN | 70%      |
| LSTM        | 81%      |
| GRU         | 82%      |

> DL models capture sequential patterns; LSTM/GRU perform best.

---

### **Phase 3 — Embeddings-based ML**

* **Text Representation:** SBERT embeddings, Word2Vec embeddings
* **Model:** Linear SVM
* **Results:** ~79–80% accuracy
* **Status:**

  * SBERT + SVM → Done
  * Word2Vec + SVM → Pending (marked expected same accuracy as SBERT)

> Phase 3 demonstrates semantic embeddings for full 45k tickets, CPU-friendly.

---

## **Dataset**

* `Document`: Free-text ticket
* `Topic_group`: Ticket category
* **Size:** 45k rows, noisy, long, real-world text

---

## **Tech Stack**

* Python 3.x
* Libraries: pandas, scikit-learn, matplotlib, numpy, tensorflow/keras, sentence-transformers
* Models: Logistic Regression, Linear SVM, RNN, LSTM, GRU, SBERT + SVM, Word2Vec + SVM

---

## **Project Structure**

```
project/
│
├─ data/
│   └─ tickets_full.csv
│
├─ notebooks/
│   ├─ phase1_classical_ml.ipynb
│   ├─ phase2_dl_experiments.ipynb
│   └─ phase3_embeddings_svm.ipynb
│
├─ scripts/
│   ├─ preprocessing.py
│   ├─ train_phase1.py
│   └─ train_phase3_embeddings.py
│
├─ requirements.txt
└─ README.md
```

---

## **How to Run**

1. Clone repo:

```bash
git clone <repo_url>
cd project
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run notebooks in order:

   * Phase 1: TF-IDF + SVM / LR
   * Phase 2: DL experiments (RNN, LSTM, GRU)
   * Phase 3: Embeddings + SVM (SBERT done, Word2Vec pending)

---

## **Why This Project Stands Out**

* Full 45k dataset → industrial-scale
* Clear **phased methodology**: classical → deep learning → embeddings
* Phase 3 embeddings demonstrate semantic understanding
* CPU and GPU-friendly
* Strong portfolio / interview talking points

---

If you want, I can now **prepare the final GitHub README with all plots and tables for accuracies of each phase**, fully ready to push.

Do you want me to do that next?
