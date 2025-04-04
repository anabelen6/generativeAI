# Generative AI

This repository walks through the foundamental technologies and techniques behing Generative AI.

## RAG: Retrieval Augmented Generation

1. RAG_app_LangChain.ipynb: step-by-step guide on how to build a document Q&A application using a RAG pipeline. It will be used:
    * Gemini AI models for embedding and generating answers
    * ChromaDB as the vector database
    * LangChain for managing the retrieval process

2. RAG_app.ipynb: using LangChain for the RAG chain, we missed the real understanding of building a RAG module. Thus, in this notebook we will see how to do it manually:
    * Gemini AI embedding model for embedding queries and documents (custom embedding function created)
    * ChromaDB as the vector database
    * RAG chain:
        * Retrieval: query to database using the custom embedding function
        * Augmented generation answer: create a proper prompt specifying the question, the passage (retrieved document) and the context (source of the info, pdf), and finally generating the answer with the gemini model
