
# RAG Complaint Chatbot

A **Retrieval-Augmented Generation (RAG)** system designed to analyze and retrieve information from the **Consumer Financial Protection Bureau (CFPB) complaint dataset**.

---

## 📂 Project Structure

```text
rag-complaint-chatbot/
├── .github/
│   └── workflows/
│       └── unittests.yml
├── .vscode/
│   └── settings.json
├── data/
│   ├── raw/                       # Place complaints.csv here
│   └── processed/                 # filtered_complaints.csv saved here
├── notebooks/
│   ├── __init__.py
│   └── 01_eda_and_preproccess.ipynb     # Main execution notebook
├── src/
│   ├── __init__.py
│   ├── data_preprocessing.py      # Task 1: Cleaning logic
│   └── indexing.py                # Task 2: Embedding logic
├── tests/
│   ├── __init__.py
│   └── test_logic.py
├── vector_store/
│   └── faiss_index/               # Persisted vector database (ignored by git)
├── app.py                         # Chatbot interface
├── requirements.txt               # Project dependencies
├── README.md
└── .gitignore                     # Ignores data/ and vector_store/
````

---

## 🚀 Getting Started

### 1️⃣ Setup Environment

```bash
git clone https://github.com/zemicahel/rag-complaint-chatbot.git
cd rag-complaint-chatbot
pip install -r requirements.txt
```

---

### 2️⃣ Run Data Pipeline

You can run the full pipeline from the terminal.

#### Step 1: Data Preprocessing

```bash
python src/data_preprocessing.py
```

#### Step 2: Indexing & Embeddings

```bash
python src/indexing.py
```

---

## 🛠 Project Components

### ✅ Task 1: EDA & Preprocessing

* Removed redactions (e.g. `XXXX`)
* Cleaned boilerplate complaint text
* Filtered complaint categories:

  * Credit Card
  * Personal Loan
  * Savings Account
  * Money Transfers

---

### ✅ Task 2: Embedding & Vector Store

* **Sampling**: 15,000 records (stratified)
* **Chunking**: 500 characters with 50-character overlap
* **Embedding Model**: `all-MiniLM-L6-v2`
* **Vector Store**: FAISS

---

## 📋 Task Checklist

* [x] Task 1: EDA and Data Preprocessing
* [x] Task 2: Text Chunking, Embedding, and Indexing
* [ ] Task 3: RAG Retrieval Logic
* [ ] Task 4: UI Development

---

## 🧠 Notes

* `data/` and `vector_store/` directories are excluded from version control
* Vector indices are regenerated locally using the indexing pipeline
* This ensures reproducibility and a clean repository

---

## 📌 Repository

**Branch:** `task-1-2`
**Project:** `rag-complaint-chatbot`



