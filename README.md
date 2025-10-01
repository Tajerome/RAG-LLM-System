# RAG Pipeline with Guardrails

This repository implements a **Retrieval-Augmented Generation (RAG) system** using Groq LLMs, Pinecone, and LangChain, with optional Google Custom Search for external knowledge retrieval.  
It also includes **safety guardrails** for filtering unsafe or irrelevant queries and a **Gradio interface** for interaction.

---

## Features

- **Document ingestion**
  - Load PDFs from a local folder (`FOLDER_PATH`) using `PyPDFLoader`.
  - Split documents into chunks with `RecursiveCharacterTextSplitter`.

- **Vector database (Pinecone)**
  - Store and query document embeddings.
  - Embeddings generated with `SentenceTransformers` (`all-mpnet-base-v2`).

- **LLM integration**
  - Query Groq’s `llama-3.3-70b-versatile` model for completions.
  - Strict context-based responses with citations.

- **Safety and relevance guardrails**
  - Block unsafe queries before reaching the pipeline.
  - Enforce context-only answers.

- **Web search augmentation (optional)**
  - Integrates Google Custom Search API.
  - Re-ranks results against query embeddings.

- **Interactive UI**
  - Gradio interface for chat.
  - Returns answers and their sources.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Tajerome/RAG-LLM-System.git
   cd RAG-LLM-System



python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows


pip install -r requirements.txt


GROQ_API_KEY=
FOLDER_PATH= # Path to your local PDF Data folder
PINECONE_API_KEY=
PINECONE_ENVIRONMENT=
INDEX_NAME=
GOOGLE_API_KEY=
GOOGLE_SEARCH_ENGINE_ID=
