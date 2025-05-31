# 🧠 AI Support Ticket Classifier & Entity Extractor

This project is part of the **Vijayi WFH Internship Assignment**. It is an AI-powered system that classifies support tickets based on their **issue type** and **urgency level**, and also **extracts key entities** from the ticket text such as product names, complaint keywords, and dates.

---

## 📌 Features

✅ Predicts **Issue Type** (e.g., Billing Problem, Technical Support, Delivery Issue)  
✅ Predicts **Urgency Level** (Low, Medium, High)  
✅ Extracts **Product Names**, **Complaint Keywords**, and **Dates** from ticket text  
✅ Clean and Modular **NLP + ML Pipeline**  
✅ Interactive **Gradio Web Interface** for testing  
✅ Includes **cross-validation** for robust evaluation  

---

## 📁 Files in the Repository

- `support_ticket_classifier.ipynb`: Main Jupyter notebook with complete code
- `README.md`: This documentation file
- `requirements.txt`: (Optional) Python dependencies
- `sample_tickets.txt`: Test queries for live demo
- `trained_models.pkl`: (Optional) Pickled classifiers if saved

---

## 🧠 Approach Overview

### 🔹 Data Preprocessing:
- Lowercasing, punctuation removal, tokenization
- Stopword removal using NLTK
- Lemmatization using WordNet

### 🔹 Feature Engineering:
- TF-IDF Vectorization (`ngram_range=(1,2)`, max 1000 features)
- Sentiment Score using `TextBlob`
- Ticket Length (word count)
- Feature Normalization using `StandardScaler`

### 🔹 Model Training:
- Two separate classifiers using `RandomForestClassifier`:
  - `issue_type`
  - `urgency_level`
- Evaluation using **5-fold cross-validation** for each

### 🔹 Entity Extraction:
- Regex + rule-based logic to extract:
  - Dates
  - Complaint keywords (e.g., “not working”, “delayed”, “refund”)
  - Product names from a known list

### 🔹 Integration:
- All logic wrapped into `predict_ticket()` function
- Ready for batch processing or UI integration

---

## 🌐 Gradio Interface

An easy-to-use web interface is built using **Gradio**.

### 🔧 How to Use:
1. Run all cells in the notebook
2. Scroll to the bottom where `iface.launch()` appears
3. Paste any support ticket text
4. View predictions + extracted entities live

---

## 📊 Sample Input

