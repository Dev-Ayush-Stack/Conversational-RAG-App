# 🧠 Conversational RAG Application using LangChain

## 📌 Overview

This project is a **Conversational Retrieval-Augmented Generation (RAG) system** built using **LangChain, vector databases, and Large Language Models (LLMs)**.

It allows users to ask **context-aware questions over multiple documents (PDF, TXT, HTML)** while maintaining **chat history**, enabling intelligent follow-up conversations.

The system leverages a **history-aware retriever** and **session-based memory**, making it suitable for real-world AI chatbot applications.

---

## 🚀 Features

* 💬 **Conversational Question Answering**
* 🧠 **History-Aware Query Rewriting**
* 🔍 **Semantic Search using Embeddings**
* 📄 **Multi-format Document Support (PDF, TXT, HTML)**
* 🧩 **Vector Storage using Chroma DB**
* 🔗 **LangChain RAG Pipeline**
* 🗂️ **Session-based Chat Memory**
* ⚡ **Efficient Retrieval + LLM Response Generation**

---

## 🛠️ Tech Stack

* Python
* LangChain (LCEL)
* Chroma (Vector Database)
* HuggingFace / OpenAI Embeddings
* LLM (Groq / OpenAI / others)
* Jupyter Notebook
* Poetry (Dependency Management)
* dotenv

---

## 📂 Project Structure

```bash
Conversational-RAG-App/
│── data/                          # Input documents
│   ├── 5pages.pdf
│   ├── 100-startups.html
│   ├── be-good-and-how.html
│   ├── be-good.txt
│   ├── como_podemos_*.pdf
│   ├── good.txt
│   ├── SAMPLE-OF-ENV-FILE
│   ├── state_of_the_union.txt
│
│── Conversational-Rag-App.ipynb   # Main RAG pipeline
│── basic-schema.ipynb             # Supporting schema / experiments
│── .env                           # API keys
│── .gitignore
│── pyproject.toml                 # Poetry config
│── poetry.lock
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/conversational-rag-app.git
cd conversational-rag-app
```

---

### 2️⃣ Install Dependencies (Poetry)

```bash
poetry install
poetry shell
```

---

### 3️⃣ Setup Environment Variables

Create a `.env` file:

```env
OPENAI_API_KEY=your_api_key
# or
GROQ_API_KEY=your_api_key
```

---

## ▶️ Usage

Run the notebook:

```bash
jupyter notebook
```

Open:

```
Conversational-Rag-App.ipynb
```

---

### 💬 Example Usage

```python
response = conversational_rag_chain.invoke(
    {"input": "What is this article about?"},
    config={"configurable": {"session_id": "user1"}}
)

print(response["answer"])
```

---

## 📊 Example Conversation

### 🧑 User:

```
What is this article about?
```

### 🤖 AI:

```
This article discusses artificial intelligence and machine learning.
```

---

### 🧑 Follow-up:

```
What was my previous question about?
```

### ✅ AI (Context-Aware):

```
Your previous question was about the topic of the article.
```

---

## 🧠 How It Works

### 🔹 1. Document Loading

Documents are loaded from multiple formats:

* PDF
* HTML
* TXT

---

### 🔹 2. Embedding & Storage

* Documents are converted into embeddings
* Stored in **Chroma vector database**

---

### 🔹 3. History-Aware Retrieval

* Uses `create_history_aware_retriever`
* Converts follow-up questions into standalone queries

---

### 🔹 4. Conversational Memory

* Managed using `RunnableWithMessageHistory`
* Tracks conversation using `session_id`

---

### 🔹 5. Answer Generation

* Retrieved documents are passed to LLM
* Final answer is generated contextually

---

## 🔄 Pipeline

```
User Query + Chat History
        ↓
Contextual Prompt (Query Rewriting)
        ↓
LLM (Standalone Query)
        ↓
Retriever (Chroma DB)
        ↓
Relevant Documents
        ↓
LLM Answer Generation
        ↓
Final Response
```

---

## 🧩 Key Concepts

### ✅ MessagesPlaceholder

Injects chat history dynamically into prompts

### ✅ History-Aware Retriever

Improves retrieval by rewriting ambiguous queries

### ✅ RunnableWithMessageHistory

Automatically manages chat sessions and memory

---

## 🔒 Security Note

* Store API keys in `.env`
* Never push `.env` to GitHub

---

## 🚀 Future Improvements

* 🌐 Streamlit / Web UI
* 📂 Upload custom documents
* 🧠 Hybrid Search (BM25 + Vector)
* ☁️ Deployment (Vercel / AWS)
* 👥 Multi-user authentication

---

## 👨‍💻 Author

**Ayush Pandey**
B.Tech CSE | AI Engineer

---

## ⭐ If you like this project

Give it a ⭐ on GitHub and share it!
