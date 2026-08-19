# Generative AI & RAG Architectures

This repository walks through the fundamental technologies and techniques behind Generative AI, focusing on building, evaluating, and optimizing **Retrieval-Augmented Generation (RAG)** systems for document Question & Answering (Q&A).

---

## 📚 Dataset / Knowledge Base

The applications use **5 PDF documents** from Kaggle's 5-day intensive Generative AI course as the primary knowledge base. These documents cover core Large Language Model (LLM) concepts:
* **Transformer Architecture**: Attention mechanisms, Encoders, and Decoders.
* **Fine-Tuning Techniques**: Supervised Fine-Tuning (SFT), RLHF, and PEFT/LoRA.
* **Inference Optimization**: Acceleration methods and efficient LLM deployment.

---

## 🧪 Notebooks & Applications

### 1. `RAG_app_LangChain.ipynb` — Standard LangChain RAG
A step-by-step guide to building a traditional document Q&A pipeline using the **LangChain** ecosystem.
* **LLM & Embeddings**: `ChatGoogleGenerativeAI` (`gemini-2.0-flash-001`) and `GoogleGenerativeAIEmbeddings`.
* **Vector Store**: Integration via `langchain-chroma` using `RecursiveCharacterTextSplitter`.
* **Pipeline**: Orchestrated using LangChain retrieval chains (`create_retrieval_chain`) for direct vector search and answer synthesis.

### 2. `RAG_app_custom.ipynb` — Step-by-Step Custom RAG
A hands-on implementation explaining how RAG components interact without relying on high-level abstractions.
* **Retrieval**: Queries the vector database directly using a custom embedding function.
* **Augmented Generation**: Explicitly constructs structured prompts incorporating the user query, retrieved passages, and document source context before sending them to the Gemini model.

### 3. `Agentic_RAG_app.ipynb` — Agentic-RAG Pipeline
Solves the scalability limitation of standard RAG when working with large volumes of documents—where massive chunk counts increase retrieval latency and degrade response accuracy.
* **Agent Filtering**: Automatically generates individual document summaries using a *map-reduce* strategy. An agent inspects these summaries to determine which files have the highest probability of containing the answer before executing vector retrieval.
* **Technologies**: `GoogleGenerativeAI`, `text-embedding-004`, custom `ChromaDB` setup, and `PyPDFLoader`.

---

## 🛠️ Tech Stack & Tools

* **LLMs**: Gemini 2.0 Flash (`gemini-2.0-flash-001` / `ChatGoogleGenerativeAI`)
* **Embeddings**: `text-embedding-004` / `GoogleGenerativeAIEmbeddings`
* **Vector Database**: ChromaDB
* **Frameworks & Data Loaders**: LangChain, PyPDFLoader
