# 📨 Spam Classification with NLP (BoW & TF-IDF)

This project demonstrates spam detection using classic **Natural Language Processing (NLP)** techniques:  
- **Bag of Words (BoW)** + Logistic Regression  
- **TF-IDF** (Term Frequency-Inverse Document Frequency) + Naive Bayes  

Both models classify SMS messages as **"spam"** or **"ham"** (not spam), and are trained on a cleaned and vectorized version of the original dataset.

---

## 🧠 Techniques Used

### 🔹 Bag of Words (BoW)
BoW converts text into numerical vectors based on **word frequency**:
- Builds a vocabulary of all unique words
- Represents each message as a vector of word counts
- Does **not** consider word order or semantics

### 🔸 TF-IDF (Term Frequency-Inverse Document Frequency)
TF-IDF improves BoW by:
- **Downweighting common words** (e.g., "the", "is", "on")
- **Highlighting rare but important words** in each document
- Gives more meaningful numerical representations for spam detection

---

## 🧼 Text Preprocessing

Before vectorization, messages are cleaned using:
- Lowercasing
- Removal of:
  - URLs
  - HTML tags
  - Punctuation
  - Numbers
  - Extra whitespace
  - Stopwords (for TF-IDF)

> This ensures high-quality features and reduced noise.

---

## 🛠️ Libraries Used

- `pandas` — data loading
- `sklearn` — model training, metrics, and vectorization
- `re` and `string` — for cleaning text
- `matplotlib`, `seaborn` — for visualizations

---

## 📂 Dataset

The dataset is a **collection of SMS messages** labeled as **spam** or **ham**, loaded from a CSV file using:
```python
pd.read_csv("spam.csv", encoding='ISO-8859-1")
The encoding ensures support for special characters.

📊 Results
✔️ Accuracy Scores
Model	Accuracy
BoW + Logistic Regression	✅ ~97%
TF-IDF + Naive Bayes	✅ ~96%

📈 Confusion Matrices & Classification Reports
Both models were evaluated using:

Accuracy

Precision

Recall

F1-score

Confusion Matrix

📉 Accuracy Comparison (Visualization)
python
Copy
Edit
plt.bar(['BoW + LR', 'TF-IDF + NB'], [acc_bow, acc_tfidf])
This visually compares the performance of both models.

📌 Future Improvements
Add stemming/lemmatization

Train with Word2Vec or BERT

Use ROC-AUC and precision-recall curves

Deploy as a web app with Flask/Streamlit

