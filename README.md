# RAG-Based QA System

A simple Retrieval-Augmented Generation (RAG) application that answers questions based on my own text documents using Google's Gemini API. Built as a learning project to understand the fundamentals of RAG: document chunking, embeddings, semantic search, and AI-generated answers.

## What is RAG?

Retrieval-Augmented Generation (RAG) combines information retrieval with AI text generation. Instead of relying solely on what an AI model was trained on, RAG retrieves relevant information from documents and uses that as context to generate accurate, grounded answers.

## How It Works

1. **Load Documents** — Reads all `.txt` files from the `documents/` folder
2. **Split Text** — Breaks documents into smaller chunks for processing
3. **Create Embeddings** — Converts each chunk into a numerical vector using Gemini's embedding model
4. **Store Vectors** — Keeps embeddings in memory for similarity search
5. **Query** — When a question is asked, finds the most relevant chunks via cosine similarity
6. **Generate** — Uses Gemini to generate an answer based on the retrieved chunks

## Tech Stack

- Python 3.8+
- Google Gemini API (`google-generativeai`) — embeddings via `gemini-embedding-001`, generation via `gemini-2.5-flash-lite`
- `python-dotenv` for environment variable management

## What I Learned

- How to chunk text documents for embedding
- Creating and comparing vector embeddings using cosine similarity
- Building a basic retrieval pipeline before passing context to an LLM
- Working with the Gemini API for both embeddings and text generation
- Setting up environment variables and keeping API keys out of version control

## Project Structure

```
RAG-Based-QA-System/
├── rag_app.py          # Main application code
├── requirements.txt    # Python dependencies
├── documents/          # Text files used as the knowledge base
├── .env                # API key (not committed)
└── .gitignore
```

## Future Ideas

- Persist embeddings instead of recomputing them on every run
- Support PDFs and other file types
- Add a simple web UI
