# E-commerce Product Assistant

An AI-powered product assistant that scrapes e-commerce data, processes it through RAG (Retrieval-Augmented Generation) workflows, and provides intelligent product recommendations and insights.

## Features

- **Web Scraping**: Automated Flipkart product and review scraping
- **Agentic RAG**: LangGraph-powered intelligent retrieval and generation
- **Vector Database**: AstraDB integration for semantic search
- **MCP Integration**: Model Context Protocol for enhanced workflows
- **Evaluation**: RAGAS-based response quality assessment
- **Web Interface**: Streamlit UI for scraping and FastAPI for chat

## Quick Start

### Installation

```bash
pip install -r requirements.txt
pip install -e .
```

### Environment Setup

Copy `.env.copy` to `.env` and configure:
- Database credentials (AstraDB)
- API keys (Google GenAI, Groq, OpenAI)

### Usage

**Scraping Interface:**
```bash
streamlit run scrapper_ui.py
```

**Chat API:**
```bash
uvicorn prod_assistant.router.main:app --reload
```

## Architecture

```
prod_assistant/
├── etl/           # Data scraping and ingestion
├── workflow/      # Agentic RAG workflows
├── retriever/     # Vector search components
├── mcp_servers/   # Model Context Protocol servers
├── evaluation/    # RAGAS evaluation metrics
└── router/        # FastAPI endpoints
```

## Deployment

- **Docker**: `docker build -t ecomm-assistant .`
- **Kubernetes**: Deploy using `k8/` manifests
- **AWS EKS**: Infrastructure in `infra/eks-with-ecr.yaml`

## Tech Stack

- **Backend**: FastAPI, LangChain, LangGraph
- **Frontend**: Streamlit, HTML/CSS
- **Database**: AstraDB (Vector), CSV (Raw data)
- **ML/AI**: Google GenAI, Groq, OpenAI
- **Deployment**: Docker, Kubernetes, AWS EKS
