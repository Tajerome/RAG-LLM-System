# RAG Pipeline with Guardrails

This repository contains an implementation of a **Retrieval-Augmented Generation (RAG) pipeline** that integrates the `llama-3.3-70b-versatile` model (via Groq), Pinecone for vector storage, LangChain utilities, and Google Custom Search for external knowledge retrieval. It also includes safety guardrails for filtering unsafe or irrelevant queries, and a Gradio interface for interaction.

## Features
- **Document ingestion**
  - Load PDFs from a folder (`FOLDER_PATH`) using `PyPDFLoader`.
  - Split documents into chunks with `RecursiveCharacterTextSplitter`.
- **Vector database (Pinecone)**
  - Store and query document embeddings.
  - Uses `SentenceTransformers` for embedding generation.
- **LLM integration**
  - Connects to the `llama-3.3-70b-versatile` model for completions.
- **Safety and relevance guardrails**
  - Filters unsafe or irrelevant queries before they reach the pipeline.
- **Web search augmentation**
  - Uses Google Custom Search API.
  - Re-ranks search results with cosine similarity against query embeddings.
- **Interactive UI**
  - Gradio interface for chat, including responses and sources.

## Installation

1. Clone the repository: 
   git clone https://github.com/Tajerome/RAG-LLM-System.git
   cd RAG-LLM-System

2. Create a virtual
   Create a virtual environment and install dependencies:
   python -m venv venv
source venv/bin/activate   # On macOS/Linux
venv\Scripts\activate      # On Windows

pip install -r requirements.txt


4. Create a .env file in the project root with the following variables:
GROQ_API_KEY=
FOLDER_PATH=
PINECONE_API_KEY=
PINECONE_ENVIRONMENT=
INDEX_NAME=
GOOGLE_API_KEY=
GOOGLE_SEARCH_ENGINE_ID=


## Usage
jupyter notebook groq.ipynb

   
