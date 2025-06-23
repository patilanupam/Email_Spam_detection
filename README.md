
## 📧 Email Spam Classifier with Logistic Regression

This project is a **text-based spam classifier** that uses classic NLP techniques like **TF-IDF** vectorization and **Logistic Regression** to detect whether an email is spam or not. A simple web interface is provided using **Gradio**, and the project runs in **Google Colab**.

---

### 🔧 Features

* Preprocessing: Lowercasing, punctuation & stopword removal
* Text vectorization using TF-IDF
* Classifier: Logistic Regression
* Output: Label with confidence score
* Gradio UI to test your own emails in real time

---

### 🗂️ Dataset

The dataset used should be a `.csv` file with two columns:


* 'dataset link': https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset?resource=download
* `text` — raw email text
* `label` — binary label (1 = spam, 0 = not spam)

Example structure:

```csv
text,label
"Subject: Hello, your invoice is attached...",0
"Subject: WIN $1000 Walmart Gift Card NOW!",1
```

---

### ▶️ How to Run

1. **Open the Colab Notebook** (or upload your own).
2. Mount your Google Drive:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
3. Load the dataset:

   ```python
   import pandas as pd
   data = pd.read_csv('/content/drive/My Drive/emails.csv', header=None, names=['text', 'label'])
   ```
4. Preprocess text and build classifier (already in notebook).
5. Launch the Gradio interface:

   ```python
   interface.launch()
   ```

---

### 🧠 Model Pipeline

* `clean_text()` — basic text cleaning and stopword removal using NLTK
* `TfidfVectorizer` — feature extraction
* `LogisticRegression()` — model training
* `Gradio Interface` — for user input and live testing

---

### 🛠️ Dependencies

Install with:

```bash
pip install -q gradio nltk scikit-learn pandas
```

You may also need:

```python
import nltk
nltk.download('stopwords')
```

---

### 🌐 Web Interface Preview

Paste or type your email content:

```
Dear user, you've won a $1000 reward! Click here to claim: http://spam.link
```

The model will return:

```
Spam (Confidence: 92.3%)
```

---

### 📁 File Structure (in Colab)

```
/content/drive/My Drive/emails.csv
📦 Email Spam Classifier.ipynb
📄 README.md
```

---

### ✅ Future Enhancements

* Add deep learning models (LSTM or BERT)
* Use email headers as features
* Host interface permanently on Hugging Face Spaces

