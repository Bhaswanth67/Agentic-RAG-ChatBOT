# Agentic RAG Chatbot

## Overview

The **Agentic RAG Chatbot** is a Retrieval-Augmented Generation (RAG) system designed to provide intelligent responses by leveraging both local document search and real-time web retrieval. Built with `crewai`, the chatbot utilizes **Synthesizer and Retriever Agents** for efficient data processing. It supports interaction with PDFs, Excel, and PowerPoint files while also integrating online search capabilities.

## Features

- **Multi-Source Search**: Searches both uploaded documents and the web using `SerperDevTool`.
- **Vector Database**: Uses **Qdrant Cloud** for efficient document storage and retrieval.
- **Agentic Processing**:
  - **Retriever Agent**: Searches relevant information from local and web sources.
  - **Synthesizer Agent**: Processes and generates well-structured responses.
- **LLM-Powered Responses**: Utilizes `llama-3.3-70b-versatile` for generating answers.
- **Embedding and Parsing**:
  - Embeddings: `nomic-ai/modernbert-embed-base`
  - Parsing: `llama-parse`
- **Chatbot UI**: Built using `Streamlit` for an interactive experience.
- **Chat History Management**: Saves conversation history for future reference.
- **Configurable Search Scope**: Allows users to choose between local vector database or online search when needed.
- **Upload and Process Files**: Supports PDFs, Excel, and PowerPoint for document-based Q&A.

---

## Tech Stack

- **Frontend**: Streamlit
- **Backend**: Python (FastAPI for API integration)
- **LLM**: `llama-3.3-70b-versatile`
- **Embeddings**: `nomic-ai/modernbert-embed-base`
- **Vector Database**: Qdrant Cloud
- **Parsing**: `llama-parse`
- **Search Integration**: `SerperDevTool`, DuckDuckGo, Wikipedia, and ArXiv

---

## Installation & Setup

### Prerequisites

Ensure you have the following installed:

- Python 3.8+
- `pip` package manager

### Clone the Repository

```bash
git clone https://github.com/your-username/agentic-rag-chatbot.git
cd agentic-rag-chatbot
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Set Up Environment Variables

Create a `.env` file and add the required API keys:

```
GROQ_API_KEY=your_groq_api_key
HUGGINGFACE_API_KEY=your_huggingface_api_key
SERPER_API_KEY=your_serper_api_key
QDRANT_API_KEY=your_qdrant_api_key
```

### Run the Application

```bash
streamlit run app.py
```

---

## Project Structure

```
agentic-rag-chatbot/
│── app.py              # Main Streamlit application
│── app.ipynb           # Jupyter notebook for testing
│── tools.py            # Retrieval and processing logic
│── requirements.txt    # Dependencies
│── .env                # API keys (not included in repo)
│── README.md           # Project documentation
```

---

## Usage Guide

1. **Upload Documents**: Upload PDFs, Excel, or PowerPoint files for local retrieval.
2. **Ask Questions**: Type queries based on uploaded documents or general knowledge.
3. **Choose Search Mode**: Select between vector database search and online search.
4. **View Responses**: The chatbot will display generated answers with source tracking.
5. **Save or Clear Chat History**: Save conversations for later use or reset chat.

---

## Future Improvements

- Add support for more file formats (Word, CSV)
- Enhance UI with additional filters and settings
- Improve latency with optimized indexing
- Implement multi-modal support for images and audio

---
