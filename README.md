# Veridian Atlas

Enterprise RAG engine that transforms raw documents into structured, queryable knowledge. Combines semantic embeddings with BM25 keyword search for hybrid retrieval, backed by ChromaDB vector storage and a React frontend.

## Architecture

- **Ingestion Pipeline** (`data_pipeline/`) - Document loaders, chunking strategies, and embedding generation with sentence-transformers
- **RAG Core** (`core/`) - Hybrid search combining dense vector retrieval (ChromaDB) with sparse keyword matching (BM25), plus cross-encoder reranking
- **API** (`api/server.py`) - FastAPI backend serving queries with source citations and confidence scores
- **Frontend** (`src/frontend/`) - React + Tailwind UI with conversation history, citation panels, and deal-level filtering

## Stack

Python 3.11 / FastAPI / ChromaDB / sentence-transformers / PyTorch / React / Tailwind / Docker

## Quick Start

```bash
docker-compose up --build
# API at localhost:8000, frontend at localhost:3000
```

## Key Features

- Hybrid search: dense embeddings + BM25 keyword matching
- Source attribution with clickable citations back to original documents
- Multi-deal document isolation - query across or within specific document sets
- Dockerized deployment with health checks and volume persistence
