# Q1 Labs — RAG Workshop with IBM Granite

A hands-on workshop series that walks through building a Retrieval-Augmented Generation (RAG) pipeline using IBM Granite models. Uses the [Basic Fantasy RPG](https://www.basicfantasy.org/) rulebook as a real-world test document to demonstrate how grounding LLMs with retrieved context dramatically improves answer quality.

## Structure

| Section | Topic | Description |
|---------|-------|-------------|
| `02/` | Setup & Baseline | Configure API access, test model connectivity, and establish baseline responses to reveal knowledge gaps |
| `03/` | Document Ingestion | Convert PDF documents to Markdown using [Docling](https://github.com/DS4SD/docling) |
| `04/` | Tokens, Context & RAG | Token counting, context window management, chunking strategies, embeddings with Granite Embedding, vector search with ChromaDB, and full RAG pipeline |
| `05/` | Evaluation | Compare baseline vs. RAG answers using manual review and automated LLM-as-judge scoring |
| `06/` | Production Pipeline | Scale ingestion to multiple documents with source attribution and corpus-level evaluation |
| `07/` | Conclusion | Earning the right to escalate to fine-tuning — diagnosing failures, synthetic data, and field positioning |

## Getting Started

### Prerequisites

- Python 3.12+
- JupyterLab
- API key and endpoint for a MaaS (Model as a Service) instance running Granite models

### Setup

1. Create a `.env` file in the project root:

   ```
   API_KEY=your-api-key
   ENDPOINT_BASE=https://your-maas-endpoint/v1
   ```

2. Install dependencies within the notebooks as needed (each notebook installs its own requirements).

3. Work through the notebooks in order, starting with `02/01_SetupAndModelTest.ipynb`.

## Key Technologies

- **IBM Granite 3.2 8B Instruct** — Language model for generation
- **Granite Embedding 30M English** — Local embedding model for semantic search
- **ChromaDB** — In-process vector store
- **Docling** — PDF-to-Markdown document conversion
- **sentence-transformers** — Embedding model runtime

## Project Layout

```
Q1ETX/
├── config.py          # Loads .env and exposes API_KEY / ENDPOINT_BASE
├── .env               # API credentials (not tracked in git)
├── docs/              # Source documents (PDFs, including 3rd Edition variants)
├── models/            # Pre-downloaded embedding models (e.g. granite-embedding-30m-english)
├── utils/             # Utility notebooks (e.g. GPU diagnostics)
├── 02/                # Section 2 — Setup & Baseline
├── 03/                # Section 3 — Document Ingestion
├── 04/                # Section 4 — Tokens, Context & RAG
├── 05/                # Section 5 — Evaluation
├── 06/                # Section 6 — Production Pipeline
└── 07/                # Section 7 — Conclusion
```
