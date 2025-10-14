
# 🧠 AI Risk RAG Chat Agent (n8n + Supabase + OpenAI)

This n8n workflow builds a **Retrieval-Augmented Generation (RAG) chat agent** that retrieves insights on **AI risk** from a stored knowledge base.
It integrates **Google Drive**, **Supabase**, **Postgres**, and **OpenAI** to create a full-stack, self-updating RAG pipeline — all orchestrated visually in n8n.

---

## 🚀 Features

* **Automated document ingestion** from Google Drive
* **Embedding generation** with OpenAI (GPT-4o-mini)
* **Vector storage** in Supabase for semantic retrieval
* **Persistent chat memory** with Postgres
* **Interactive chat interface** with real-time responses

---

## 🧩 Workflow Overview

### 1️⃣ Trigger & File Download

* **Manual Trigger** → starts the workflow
* **Google Drive Node** → downloads a specific PDF (e.g. *AI Risk Chat - Sheet1.pdf*)

### 2️⃣ Data Loading & Embedding

* **LangChain Data Loader** → processes binary PDF data
* **OpenAI Embeddings Node** → converts text into vector embeddings

### 3️⃣ Vector Storage

* **Supabase Vector Store** → stores embeddings in the `documents` table
* Enables semantic retrieval for related documents or facts

### 4️⃣ Agent Composition

* **LangChain Agent Node** → orchestrates tool usage and query flow
* **Supabase Vector Tool** → retrieves relevant context
* **Postgres Memory** → retains conversational context
* **OpenAI Language Model (GPT-4o-mini)** → generates responses

### 5️⃣ Chat Interface

* **Chat Trigger Node** → enables real-time interaction
* The agent dynamically references past messages + vector data to generate context-aware answers.

---

## 🧠 Example Use Case

> **“Summarize the most recent AI risk reports from the uploaded document.”**
> The agent retrieves context from Supabase, uses embeddings to locate relevant passages, and answers conversationally — all within your n8n interface.

---

## ⚙️ Tech Stack

| Component                | Purpose                       |
| ------------------------ | ----------------------------- |
| **n8n**                  | Workflow orchestration        |
| **LangChain**            | AI agent and tool integration |
| **Supabase**             | Vector database               |
| **Postgres**             | Chat memory                   |
| **Google Drive**         | Document source               |
| **OpenAI (GPT-4o-mini)** | Embeddings & LLM responses    |

---

## 🧩 How to Use

1. Import the workflow JSON into n8n.
2. Add your credentials:
   * **Google Drive OAuth2**
   * **Supabase API**
   * **OpenAI API Key**
   * **Postgres DB connection**
3. Run the workflow manually to ingest documents into the RAG repository.
4. Trigger the **Chat Node** to interact with your RAG Agent.

---

## 📚 Output

A dynamic AI chat interface that:
✅ Remembers past messages
✅ Pulls verified info from Supabase
✅ Generates natural language summaries
✅ Can be extended with tools like news scrapers or compliance datasets


---

## 💡 Author

**Debasmita**

> Building autonomous workflows with n8n + LLMs.
> [Substack](https://substack.com/@aiwatch101)

---

