## 📘 RAG-Style Question Answering over Machine Learning PDFs

This project demonstrates a document-grounded question-answering system built on two PDF files covering Supervised and Unsupervised Machine Learning, implemented entirely in a Jupyter Notebook.

While inspired by Retrieval-Augmented Generation (RAG) architectures, this implementation does not perform a retrieval (top-k search) step. Instead, it uses LangChain’s Runnable pipeline to pass document context directly to the language model.

## 🧠 Project Overview


+ PDFs are loaded and converted to text

+ Text is split into manageable chunks

+ Chunks are embedded and stored in a FAISS vector store

+ The full document context is passed directly to the LLM

+ Answers are generated using a Hugging Face model

  This setup focuses on document understanding and grounded generation, rather than similarity-based retrieval.


## ⚙️ Implementation Details
**Document Processing**

+ Load single or multiple PDF files related to:

   * Supervised Machine Learning
 
   * Unsupervised Machine Learning

+ Convert PDFs to raw text

+ Split text into smaller chunks to fit model context limits

# Embeddings and Storage

* Generate embeddings for text chunks

* Store embeddings using FAISS for efficient vector representation

**Note:** The vector store is used for structuring document embeddings, not for retrieval during inference.


## LLM Pipeline (No Retrieval Step)

* Uses LangChain Runnables:

    * RunnablePassthrough to forward document context

    * StrOutputParser to parse model outputs

* No similarity search or top-k chunk selection is applied

* Entire processed context is provided directly to the model

# Response Generation

* Language model: Hugging Face – flan-t5-base

* The prompt is formatted using the provided document context

* The model generates concise, context-aware answers

# ✨ Features

* PDF-based knowledge grounding

* Supports multiple documents

* Runnable-based LangChain pipeline

* Interactive question answering inside the notebook

* No external API dependency (runs locally with Hugging Face models)

# 📌 Notes

This project is best suited for:

* Learning LangChain Runnables

* Understanding document-aware generation pipelines

* Educational use cases with small, well-scoped document sets

For large document collections or scalable systems, a true retrieval step (top-k search) would be recommended.
