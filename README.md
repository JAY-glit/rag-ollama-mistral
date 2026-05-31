<h1 align="center">🧠 RAG System — Ollama Mistral + AuraDB</h1>
<p align="center"><b>Context-Aware AI Responses using Knowledge Graphs + Vector Search</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Completed-1D9E75?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/LLM-Ollama_Mistral-000000?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Framework-LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white"/>
  <img src="https://img.shields.io/badge/Graph_DB-Neo4j_AuraDB-008CC1?style=for-the-badge&logo=neo4j&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
</p>

---

## 📌 Overview

A **Retrieval-Augmented Generation (RAG)** system that combines a local LLM (Ollama Mistral) with a Neo4j AuraDB knowledge graph to deliver context-aware, structured AI responses. Instead of relying on LLM memory alone, this system retrieves relevant facts from a **triplet-based knowledge graph** and feeds them into the model for grounded, accurate answers.

---

## ✨ Features

- 🦙 **Local LLM inference** — Ollama + Mistral runs fully offline, no API key needed
- 🗺 **Knowledge graph** — Triplet-based Neo4j AuraDB for structured data representation
- 🔍 **Semantic retrieval** — Embedding generation + vector search for relevant context
- 🤝 **Hybrid retrieval** — Combines vector similarity search with graph traversal
- 📄 **Document ingestion** — Automated pipeline for loading and embedding documents
- 🎯 **Improved relevance** — Graph-aware context improves response accuracy

---

## 🏗 Architecture

```
  Documents
      │
      ▼
┌─────────────────┐
│  Ingestion      │ → Chunk → Embed → Store
│  Pipeline       │
└────────┬────────┘
         │
    ┌────▼──────────────────────────────┐
    │         Neo4j AuraDB              │
    │  Knowledge Graph (Triplets)       │
    │  + Vector Index (Embeddings)      │
    └────┬──────────────────────────────┘
         │  Query: vector search + graph traversal
         ▼
┌─────────────────┐
│  LangChain      │ → Build prompt with retrieved context
│  RAG Chain      │
└────────┬────────┘
         │
    ┌────▼────────┐
    │ Ollama      │ → Generate grounded response
    │ Mistral LLM │
    └─────────────┘
```

---

## 🚀 Getting Started

```bash
git clone https://github.com/JAY-glit/rag-ollama-mistral.git
cd rag-ollama-mistral
pip install -r requirements.txt
ollama pull mistral
cp .env.example .env   # Add your Neo4j AuraDB credentials
python ingest.py       # Load and embed documents
python query.py        # Start asking questions
```

---

## 👨‍💻 Author

**JAY (Alladi Jaydurga)**
📧 jaydurga1290@gmail.com · LinkedIn: https://www.linkedin.com/in/jaydurga · GitHub: https://github.com/JAY-glit