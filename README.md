# AgenticAI - Document Q&A System

A RAG (Retrieval-Augmented Generation) system that allows users to upload documents, process them into chunks, store embeddings in a vector database, and query them using LLMs.


This project is currently in active development. Core RAG functionality is implemented and testable.


## Prerequisites

- Python 3.13+
- OpenAI API key

## Installation

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install langchain
pip install langchain-openai
pip install chromadb
pip install pypdf
pip install python-docx
```

## Configuration

Set your OpenAI API key:

```python
import os
os.environ["OPENAI_API_KEY"] = "your-api-key-here"
```

Or use a `.env` file (recommended):

```bash
OPENAI_API_KEY=your-api-key-here
```

## Project Structure

```
AgenticAi/
├── llms.ipynb           # Main Jupyter notebook for testing
├── chroma_db/           # Vector database storage (gitignored)
├── .env                 # Environment variables (gitignored)
├── .gitignore
└── README.md
```

## How It Works

1. **Document Loading**: User selects a file (PDF, text, etc.)
2. **Chunking**: Document is split into manageable chunks with overlap
3. **Embedding**: Each chunk is converted to vector embeddings
4. **Storage**: Embeddings are stored in ChromaDB vector database
5. **Query**: User asks a question
6. **Retrieval**: Most relevant chunks are retrieved via similarity search
7. **Generation**: LLM generates answer based on retrieved context

## Current Limitations

- Only supports PDF and text files
- No user interface yet (Jupyter notebook only)
- Vector database is local (not cloud-based)
- Single document processing at a time


