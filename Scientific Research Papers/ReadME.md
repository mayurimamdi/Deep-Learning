# 📚 arXiv Scientific Paper Classification (NLP + Deep Learning)

This project focuses on classifying scientific papers from the arXiv dataset into major research categories using both traditional Natural Language Processing (NLP) techniques and Deep Learning models.

---

## 🚀 Project Overview

The goal of this project is to build and compare two approaches for text classification:

1. **Machine Learning (TF-IDF + Logistic Regression)**
2. **Deep Learning (LSTM-based Neural Network)**

The dataset consists of scientific paper metadata, including titles and summaries, which are used to predict their respective categories.

---

## 📂 Dataset

* Source: arXiv scientific dataset
* Records used: **100,000 (sampled)**
* Final filtered dataset: **86,660 entries**
* Categories filtered to those with at least **5,000 samples**

### Final Classes:

* Artificial Intelligence
* Computer Vision and Pattern Recognition
* Machine Learning
* Machine Learning (Statistics)

---

## ⚙️ Data Preprocessing

Steps performed:

* Removed non-alphabet characters using regex
* Converted text to lowercase
* Tokenization
* Stopword removal (NLTK)
* Stemming using Porter Stemmer
* Combined **title + summary** into a single feature

---

## 🧠 Approach 1: Traditional NLP

### Feature Engineering

* **TF-IDF Vectorization**

  * Max features: 5000

### Model

* Logistic Regression

  * `max_iter=1000`
  * `class_weight='balanced'`

### 📊 Results

* **Accuracy:** 75.9%

#### Classification Report (Summary)

* Strong performance on:

  * Computer Vision (~91% F1)
* Moderate performance:

  * Artificial Intelligence (~78% F1)
* Weak performance:

  * Machine Learning (Statistics) (~53% F1)

---

## 🤖 Approach 2: Deep Learning (LSTM)

### Text Processing

* Tokenization with Keras Tokenizer
* Vocabulary size: 10,000
* Sequence padding: 150 tokens

### Model Architecture

* Embedding Layer (128 dimensions)
* LSTM Layer (128 units)
* Dropout (0.5)
* Dense Layer (64 units, ReLU)
* Output Layer (Softmax, 4 classes)

### Training

* Epochs: 5
* Batch size: 64

### 📊 Results

* **Test Accuracy:** 79.16%

| Epoch | Training Accuracy | Validation Accuracy |
| ----- | ----------------- | ------------------- |
| 1     | 74.6%             | 77.8%               |
| 2     | 79.7%             | 78.9%               |
| 3     | 81.4%             | 79.4%               |
| 4     | 83.4%             | 79.1%               |
| 5     | 84.7%             | 79.1%               |

---

## 📈 Key Insights

* Deep Learning (LSTM) outperforms traditional TF-IDF + Logistic Regression.
* Class imbalance affects performance, especially for:

  * Machine Learning (Statistics)
* LSTM captures sequential context better than bag-of-words methods.

---

## 🛠️ Tech Stack

* Python
* Pandas, NumPy
* NLTK
* Scikit-learn
* TensorFlow / Keras

---

## 📌 Future Improvements

* Use **pre-trained embeddings** (e.g., GloVe, Word2Vec)
* Try **Bidirectional LSTM**
* Implement **Transformer models (BERT)**
* Perform **hyperparameter tuning**
* Handle class imbalance with advanced techniques (SMOTE, focal loss)

---

## ▶️ How to Run

1. Clone the repository:

```bash
git clone <your-repo-url>
cd <repo-folder>
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the notebook or script:

```bash
jupyter notebook
```

---

## 📬 Contact

Feel free to reach out if you'd like to collaborate or discuss improvements!

---
