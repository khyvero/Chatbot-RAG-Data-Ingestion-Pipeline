# 🤖 Chatbot RAG Data Ingestion Pipeline

## Overview
A data pipeline that ingests PDF documents, chunks the text, converts them into vector embeddings, and stores them in a vector database. This serves as the foundational data layer for a Retrieval-Augmented Generation (RAG) AI application.

## Tech Stack
*   **Data Pipeline:** Python, LangChain, PyPDF2
*   **Embedding Model:** OpenAI API (or local Ollama / DeepSeek if running locally)
*   **Vector Database:** pgvector (PostgreSQL) or ChromaDB
*   **Infrastructure:** Docker Compose

## Features
*   **Document Processing:** Reads local PDF files from a designated `/data` directory.
*   **Chunking Logic:** Splits large texts into manageable 500-token chunks with 50-token overlaps to preserve context.
*   **Vectorization:** Calls an embedding model to convert the chunks into mathematical vectors.
*   **Storage:** Persists the vectors and original metadata into the database for future querying.

## Development Tasks (To-Do)
- [ ] Write the Python script to read and chunk the PDFs.
- [ ] Integrate the embedding model to generate vectors.
- [ ] Configure the database schema to accept vector data.
- [ ] Write the ingestion logic to save chunks and vectors to the database.
- [ ] Create a `Dockerfile` to run the ingestion script as a standalone container job.
- [ ] Set up the `docker-compose.yml` to provision the database and trigger the ingestion job.

## Getting Started
Place your PDF files in the `./data` folder and run:
`docker-compose up --build`
