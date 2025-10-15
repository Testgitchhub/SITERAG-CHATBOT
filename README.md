# SITERAG-CHATBOT
Chrome extension + FastAPI backend that allows users to ask questions about any website using Gemini AI. Built with Python (FastAPI) and JavaScript, it fetches webpage content and generates intelligent answers through Gemini integration
Root README.md
# 🧩 RAG Chrome Extension with Colab Backend

This project integrates a **Retrieval-Augmented Generation (RAG)** pipeline using an **LLM** with a **Chrome Extension frontend** and a **Google Colab backend**.

## ✨ Features
- Upload PDF/DOCX/TXT files.
- Query documents through a ChatGPT-based RAG backend.
- Uses FAISS for similarity search.
- Runs backend seamlessly in Colab using Flask + ngrok.
- Extension provides simple UI for file upload and Q&A.

## 🧱 Project Architecture

Chrome Extension (UI)
↓
Flask Backend in Colab (via ngrok)
↓
RAG Pipeline → Embeddings (Sentence Transformers) + LLM (OpenAI)


## ⚙️ Setup Guide

### 1️⃣ Backend (Colab)
1. Open `backend_colab/rag_colab_notebook.ipynb` in **Google Colab**.
2. Run all cells.
3. Set your API key:
   ```python
   import os
   os.environ['OPENAI_API_KEY'] = 'sk-...'


When the Flask app starts, note the ngrok URL (like https://abcd-1234.ngrok.io).

2️⃣ Frontend (Chrome Extension)

Go to chrome://extensions/ → enable Developer Mode.

Click Load unpacked → select chrome_extension/.

In popup → enter your backend ngrok URL.

Upload a document → Ask questions.

🧰 Requirements

See backend_colab/requirements.txt for dependencies:

flask-ngrok
flask
flask-cors
python-docx
pdfplumber
sentence-transformers
faiss-cpu
openai
werkzeug==2.2.3

📜 License

MITS License © 2025 Kanneluri Sravani
## 📁 backend_colab/

### `requirements.txt`


flask-ngrok
flask
flask-cors
python-docx
pdfplumber
sentence-transformers
faiss-cpu
openai
werkzeug==2.2.3


### `README.md`
```markdown
# 📘 Backend (Colab)

This folder contains the **Google Colab notebook** that hosts the Flask RAG API.

## 🧩 Components
- Text extraction: pdfplumber / python-docx
- Embedding: Sentence Transformers (`all-MiniLM-L6-v2`)
- Vector search: FAISS
- LLM query: OpenAI GPT-3.5-turbo
- Hosting: Flask + ngrok

## 🚀 How to Run
1. Open this notebook in Colab.
2. Install requirements (first cell).
3. Set your OpenAI key in an environment variable:
   ```python
   import os
   os.environ['OPENAI_API_KEY'] = 'sk-...'

Run the final cell. Copy the https://xxxx.ngrok.io URL.
Use this URL in the Chrome extension popup.


