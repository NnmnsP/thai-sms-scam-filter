# Thai SMS Scam Filter

An NLP-based solution to detect and flag scam SMS messages in Thai, designed to protect vulnerable users such as the elderly and low-tech individuals.

---

## 📌 Problem Statement

Scam messages are increasingly common, especially in Thai. They often target elderly or non-technical users who may not recognize deceptive patterns. This project aims to filter and flag such messages in real time using machine learning.

---

## 🎯 Relevance

Due to the absence of Thai-language datasets and detection tools, this project provides a localized solution to reduce fraud and increase digital safety among Thai users.

---

## 🔁 Input and Output

- **Input**: Raw SMS text in Thai.
- **Output**: Original message tagged with scam likelihood (e.g., `Possible Scam`). Internally produces a binary classification and confidence score.

---

## 📊 Metrics

- **Primary Metric**: ROC-AUC  
  Chosen for its robustness in handling class imbalance. AUC > 0.85 is the initial target.

---

## 📦 Data

- No public Thai SMS scam dataset exists.
- Plan: Curate a small, anonymized dataset from volunteers.
- Messages: Avg. 10–25 words, labeled as scam or non-scam.
- Likely to be class-imbalanced initially.

---

## 📁 Links to Datasets

None available yet. A custom dataset will be created during development.

---

## ✅ Validation

- 80-10-10 train/validation/test split.
- 5-fold stratified cross-validation to reduce variance due to class imbalance.

---

## 🧪 Experiments

### 🔹 Baseline

- **Model**: Naive Bayes + TF-IDF
- **Preprocessing**: Thai tokenization, stopword removal, lowercasing
- **Regularization**: Laplace smoothing

**Expected Results (Mock Data)**:
- ROC-AUC: ~0.80  
- Precision: ~0.78  
- Recall: ~0.74

---

### 🔸 Main Model

- TF-IDF + Naive Bayes with PyThaiNLP for Thai processing
- Future upgrade: LSTM or Thai2Fit / multilingual BERT
- Add link/phone number features if helpful

**Target Metric**:
- ROC-AUC > 0.85

---

## 🧠 Related Tools

- [SMS Spam Collection Dataset (UCI)](https://archive.ics.uci.edu/ml/datasets/sms+spam+collection)
- [Thai2Fit: Transfer Learning for Thai NLP](https://github.com/cstorm125/thai2fit)
- [FastText for Text Classification](https://fasttext.cc/docs/en/supervised-tutorial.html)

---

## 📱 Usage

- The final product will be an Android app.
- Incoming SMS will be tagged with warnings like `Possible Scam`.
- Works offline using local text classification.
- Stores tagged messages locally for privacy.
