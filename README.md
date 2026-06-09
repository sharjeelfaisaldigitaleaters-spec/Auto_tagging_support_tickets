# 🤖 Auto Tagging Support Tickets Using LLM

An NLP project that automatically classifies customer support tickets into predefined categories using:

1. Zero-Shot Prompting (LLaMA 3 via Groq)
2. Few-Shot Prompting (LLaMA 3 via Groq)
3. Fine-Tuned DistilBERT

The project compares prompt engineering approaches against supervised fine-tuning to determine the most effective solution for support ticket categorization.

---

## 🚀 Project Overview

Organizations receive thousands of support tickets daily.

Manually categorizing tickets is:

* Time-consuming
* Error-prone
* Expensive

This project automates ticket classification and returns the Top-3 most relevant categories for each support request.

---

## 🎯 Categories

The model classifies tickets into:

* Billing and Payments
* Customer Service
* IT Support
* Product Support
* Technical Support

---

## 📊 Dataset

Dataset:

```text
Tobi-Bueck/customer-support-tickets
```

### Original Dataset

* Total Records: 61,765
* English Tickets: 28,261

### Project Dataset

Balanced sampling was performed:

* 10 tickets per category
* Total tickets: 50

---

## 🛠 Technologies Used

* Python
* Groq API
* LLaMA 3.1 8B Instant
* DistilBERT
* Hugging Face Transformers
* Hugging Face Datasets
* PyTorch
* Scikit-Learn
* Matplotlib
* Seaborn

---

## ⚙️ Methodology

### 1. Zero-Shot Classification

The LLM receives:

* Ticket text
* Category definitions
* Output formatting instructions

No examples are provided.

### Results

| Metric   | Score  |
| -------- | ------ |
| Accuracy | 36.00% |
| F1 Score | 0.3225 |

---

### 2. Few-Shot Classification

The LLM receives:

* Five labeled examples
* Classification instructions
* Category descriptions

### Results

| Metric   | Score  |
| -------- | ------ |
| Accuracy | 52.00% |
| F1 Score | 0.4768 |

---

### 3. Fine-Tuned DistilBERT

A DistilBERT model was fine-tuned on the ticket dataset.

Configuration:

* Epochs: 10
* Learning Rate: 3e-5
* Max Length: 128
* Train/Test Split: 80/20

### Results

| Metric   | Score  |
| -------- | ------ |
| Accuracy | 70.00% |
| F1 Score | 0.6333 |

---

## 📈 Performance Comparison

| Approach              | Accuracy | F1 Score |
| --------------------- | -------- | -------- |
| Zero-Shot (LLaMA 3)   | 36.0%    | 0.3225   |
| Few-Shot (LLaMA 3)    | 52.0%    | 0.4768   |
| Fine-Tuned DistilBERT | 70.0%    | 0.6333   |

🏆 Best Performing Approach: Fine-Tuned DistilBERT

---

## 📊 Visualizations

Generated visualizations include:

* Ticket Category Distribution
* Ticket Length Distribution
* Accuracy Comparison Charts
* F1 Score Comparison Charts
* Confusion Matrices

---

## 🔍 Top-3 Tag Prediction

For each ticket, the system returns:

```json
{
  "top1": {
    "tag": "IT Support",
    "confidence": 0.85
  },
  "top2": {
    "tag": "Product Support",
    "confidence": 0.12
  },
  "top3": {
    "tag": "Customer Service",
    "confidence": 0.03
  }
}
```

This provides more flexibility than a single-label prediction.

---

## 📂 Project Structure

```text
├── notebook.ipynb
├── eda.png
├── comparison_chart.png
├── confusion_matrices.png
├── distilbert-tickets/
├── requirements.txt
└── README.md
```

---

## 🎯 Key Learnings

* Prompt Engineering
* Zero-Shot Learning
* Few-Shot Learning
* Large Language Models
* DistilBERT Fine-Tuning
* Text Classification
* Model Evaluation
* Comparative NLP Experiments

---

## Future Improvements

* Increase training data size
* Use larger instruction-tuned LLMs
* Deploy as REST API
* Add active learning workflow
* Integrate into helpdesk systems

---

## 👨‍💻 Author

Muhammad Sharjeel Faisal

AI/ML Engineering Internship Project
