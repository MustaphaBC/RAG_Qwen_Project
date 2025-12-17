# 📚 RAG-based Question Answering System (Qwen2.5 + ChromaDB)

## 🧠 Project Overview
This project implements a **Retrieval-Augmented Generation (RAG)** pipeline for question answering over course materials (PDF, DOCX, TXT). It combines:
- A document ingestion & embedding pipeline
- A vector database (ChromaDB) for semantic search
- A large language model (Qwen2.5-7B-Instruct) for answer generation

The system retrieves the most relevant document chunks and injects them into the LLM prompt to generate **accurate answers in French**.

---

## 🏗️ Architecture
The project consists of **two main pipelines**:

### 1️⃣ Data Ingestion Pipeline (Offline)
- Load PDF, DOCX, TXT files
- Extract raw text
- Split text into chunks (900 tokens, overlap 150)
- Generate embeddings (all-MiniLM-L6-v2)
- Store vectors in ChromaDB

### 2️⃣ Retrieval & Generation Pipeline (Online)
- Embed user question
- Retrieve top-k relevant chunks
- Inject context into prompt
- Generate final answer using Qwen2.5-7B-Instruct

---

## 📂 Project Structure
```
project/
│── data/
│── rag_architecture_diagram.png
│── RAG_Qwen.ipynb
│── requirements.txt
│── README.md
```

---

## ⚙️ Technologies
- LangChain
- ChromaDB
- Sentence-Transformers
- Qwen2.5-7B-Instruct
- PyPDF, python-docx
- Python 3.9+

---

## 🚀 Run
```bash
pip install -r requirements.txt
```

Place documents in `data/course_materials/`  
Run `RAG_Qwen.ipynb`

---

## 👤 Author
Mustapha Ben Cheikh
