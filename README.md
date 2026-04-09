# AI Customer Service Agent

A full-stack conversational AI customer service agent combining NLP, RAG, and tool calling into one unified pipeline. Built with HuggingFace Transformers, LangChain, and Groq.

## What it does

Every customer query goes through a 3-stage pipeline:

1. **NLP Analysis** — extracts sentiment, intent, and named entities
2. **RAG Retrieval** — pulls relevant policy chunks from a document
3. **Agent Response** — uses policy context + NLP insights + tools to respond

## Pipeline Flow

Customer Query → NLP Analysis → RAG Retrieval → Agent Response

## Tech Stack

| Component | Tool |
|---|---|
| LLM | Groq (llama-3.3-70b-versatile) |
| NLP | HuggingFace Transformers |
| Embeddings | sentence-transformers/all-MiniLM-L6-v2 |
| Vector Store | ChromaDB |
| Framework | LangChain |

## Models Used

| Task | Model |
|---|---|
| Sentiment Analysis | distilbert-base-uncased-finetuned-sst-2-english |
| Intent Classification | facebook/bart-large-mnli (zero-shot) |
| Named Entity Recognition | dbmdz/bert-large-cased-finetuned-conll03-english |

## Tools Available

- `check_refund_status` — looks up refund status by transaction ID
- `get_account_status` — looks up account status by account ID

## Setup

```bash
pip install langchain langchain-groq langchain-community langchain-chroma langchain-huggingface langchain-text-splitters chromadb sentence-transformers transformers torch
```

Add your Groq API key. Get a free key at https://console.groq.com

```bash
python agent.py
```

## Sample Output
