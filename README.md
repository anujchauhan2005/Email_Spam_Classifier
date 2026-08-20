# 📧 Email/SMS Spam Classifier

A machine learning web application that classifies SMS/Email messages as **Spam** or **Not Spam** in real time, built with Python, Scikit-learn, NLTK, and deployed using Streamlit.

## 🔗 Live Demo

**Try it here:** [https://emailspamclassifier-fcdn6ozjfpu78n7w4pyf2h.streamlit.app/](https://emailspamclassifier-fcdn6ozjfpu78n7w4pyf2h.streamlit.app/)

Just paste any message into the text box and hit **Predict** to see whether it's classified as spam or not.

---

## 📌 Overview

This project uses Natural Language Processing (NLP) techniques to analyze the text content of a message and predict whether it is spam or legitimate ("ham"). The model was trained on the classic SMS Spam Collection dataset and achieves high precision, making it reliable for filtering unwanted messages while minimizing false positives on genuine messages.

---

## 🚀 Features

- Real-time spam detection through a simple web interface
- Text preprocessing pipeline (lowercasing, tokenization, stopword removal, stemming)
- TF-IDF based feature extraction
- Multinomial Naive Bayes classifier optimized for high precision
- Clean, minimal Streamlit UI
- Fully deployed and publicly accessible

---

## 🛠️ Technologies & Libraries Used

| Category | Technology |
|---|---|
| Programming Language | Python |
| Web Framework / Deployment | Streamlit, Streamlit Community Cloud |
| Machine Learning | Scikit-learn |
| Natural Language Processing | NLTK (Natural Language Toolkit) |
| Data Handling | Pandas, NumPy |
| Data Visualization (EDA) | Matplotlib, Seaborn, WordCloud |
| Model Persistence | Pickle |
| Version Control | Git & GitHub |

---

## 🧠 Machine Learning Pipeline

1. **Data Cleaning**
   - Removed unnecessary columns and renamed columns for clarity
   - Removed duplicate entries
   - Encoded target labels (`ham` → 0, `spam` → 1) using `LabelEncoder`

2. **Exploratory Data Analysis (EDA)**
   - Analyzed character, word, and sentence counts across spam vs. ham messages
   - Visualized class distribution and word frequency using pie charts, histograms, and word clouds

3. **Text Preprocessing**
   - Lowercasing
   - Tokenization (`nltk.word_tokenize`)
   - Removal of special characters and punctuation
   - Removal of stopwords
   - Stemming using `PorterStemmer`

4. **Feature Extraction**
   - Text vectorized using **TF-IDF (Term Frequency–Inverse Document Frequency)** with a maximum of 3000 features

5. **Model Selection**
   - Multiple algorithms were trained and evaluated, including:
     - Multinomial Naive Bayes
     - Support Vector Machine (SVC)
     - Logistic Regression
     - Random Forest
     - Decision Tree
     - K-Nearest Neighbors
     - AdaBoost, Bagging, Extra Trees, Gradient Boosting, XGBoost
     - Voting Classifier & Stacking Classifier (ensemble methods)
   - Models were compared on **Accuracy** and **Precision**, with special emphasis on precision (to minimize misclassifying real messages as spam)

6. **Final Model**
   - **Multinomial Naive Bayes** with TF-IDF features was selected as the final production model due to its strong precision and simplicity
   - Serialized using `pickle` as `model.pkl` and `vectorizer.pkl`

---

## 📂 Project Structure

```
Email_Spam_Classifier/
│
├── app.py                     # Streamlit web application
├── model.pkl                  # Trained Multinomial Naive Bayes model
├── vectorizer.pkl             # Fitted TF-IDF vectorizer
├── spam.csv                   # Dataset used for training
├── SMS_Spam_Detection.ipynb   # Jupyter notebook with full EDA & model training
├── requirements.txt           # Python dependencies
└── README.md                  # Project documentation
```

---

## ⚙️ How It Works

1. User enters a message in the text box
2. The message is cleaned and preprocessed (lowercased, tokenized, stopwords removed, stemmed)
3. The cleaned text is converted into a TF-IDF vector using the saved vectorizer
4. The trained Naive Bayes model predicts the class (Spam / Not Spam)
5. The result is displayed instantly on the page

---

## 💻 Run Locally

**1. Clone the repository**
```bash
git clone https://github.com/anujchauhan2005/Email_Spam_Classifier.git
cd Email_Spam_Classifier
```

**2. Create and activate a virtual environment (recommended)**
```bash
python -m venv venv
venv\Scripts\activate      # Windows
source venv/bin/activate   # macOS/Linux
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Run the Streamlit app**
```bash
streamlit run app.py
```

The app will open automatically at `http://localhost:8501`

---

## 📊 Model Performance

The final Multinomial Naive Bayes model was selected for its strong balance of accuracy and precision on the test set, prioritizing precision to reduce the risk of flagging genuine messages as spam.

---

## 🌐 Deployment

This application is deployed on **Streamlit Community Cloud**, directly connected to this GitHub repository. Any updates pushed to the `main` branch are automatically reflected in the live app.

**Live App:** [https://emailspamclassifier-fcdn6ozjfpu78n7w4pyf2h.streamlit.app/](https://emailspamclassifier-fcdn6ozjfpu78n7w4pyf2h.streamlit.app/)

---

## 🔮 Future Improvements

- Experiment with deep learning approaches (LSTM, BERT) for improved accuracy
- Add support for detecting spam in multiple languages
- Build a browser extension / API endpoint for integration with email clients
- Add confidence score alongside the prediction

---

## 👤 Author

**Anuj Chauhan**
GitHub: [@anujchauhan2005](https://github.com/anujchauhan2005)

---

## 📄 License

This project is open source and available for educational and personal use.
