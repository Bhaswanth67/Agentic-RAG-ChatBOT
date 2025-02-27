# Agentic RAG Chatbot

## Overview

The **Agentic RAG Chatbot** is a Retrieval-Augmented Generation (RAG) system designed to provide intelligent responses by leveraging both local document search and real-time web retrieval. Built with `crewai`, the chatbot utilizes **Synthesizer and Retriever Agents** for efficient data processing. It supports interaction with PDFs, Excel, and PowerPoint files while also integrating online search capabilities.

## Project Demo URL - https://drive.google.com/file/d/1pEXn6LGO1uSVFOJSPdYwx5Rn_eriM3A4/view?usp=sharing

## I'm still trying to increase the chatbot's response time. Soon, I will upload the code.

---

### Technologies Used

1. **CrewAI**:

   - **Agents**: Used to create specialized agents for information retrieval and response synthesis.
   - **Tasks**: Define specific tasks for agents to perform, such as retrieving information or synthesizing responses.
   - **Crew**: Manages the workflow between agents and tasks.

2. **SerperDevTool**:

   - A tool for performing web searches to retrieve information from the internet when the PDF does not contain the required data.

3. **DocumentSearchTool**:

   - A custom tool built using **Qdrant** and **Sentence Transformers** to search through uploaded PDF documents.
   - **Qdrant**: A vector search engine used to store and retrieve document chunks based on semantic similarity.
   - **Sentence Transformers**: Used to generate embeddings for text chunks and queries, enabling semantic search.

4. **MarkItDown**:

   - A library used to extract raw text from PDF documents.

5. **SemanticChunker**:

   - A tool for creating semantic chunks from raw text, ensuring that the text is divided into meaningful segments for better search results.

6. **Streamlit**:

   - A web framework used to create an interactive user interface for uploading PDFs and asking questions.
   - Provides a chat-like interface for users to interact with the system.

7. **Gemini LLM**:

   - A large language model used for generating responses based on the retrieved information.
   - The model is configured with a temperature of 0.5 to balance creativity and accuracy.

8. **Dotenv**:

   - Used to manage environment variables, such as API keys for Qdrant and SerperDev.

9. **Tempfile**:

   - Used to handle temporary files during PDF processing.

10. **Base64**:
    - Used to encode and display PDF files in the Streamlit interface.

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
### Key Features

1. **PDF Document Search**:

   - Users can upload PDF documents, which are processed and indexed for semantic search.
   - The system retrieves relevant chunks of text from the PDF based on the user's query.

2. **Web Search Integration**:

   - If the required information is not found in the PDF, the system performs a web search using SerperDevTool.
   - The results from the web search are combined with the PDF search results to provide a comprehensive response.

3. **Source Tracking**:

   - The system clearly indicates whether the information comes from the PDF or the web, ensuring transparency.

4. **Interactive Chat Interface**:

   - Built using Streamlit, the interface allows users to upload PDFs, ask questions, and receive responses in a chat-like format.

5. **Processing Time Monitoring**:
   - The system tracks the time taken to process each query, providing insights into performance.

---

### Workflow Overview

1. **PDF Upload and Indexing**:

   - The user uploads a PDF document, which is processed and indexed using Qdrant and Sentence Transformers.
   - The document is divided into semantic chunks, and embeddings are generated for each chunk.

2. **Query Processing**:

   - The user submits a query, which is first searched against the indexed PDF.
   - If the PDF does not contain relevant information, a web search is performed.

3. **Response Generation**:

   - The retrieved information is synthesized into a clear and concise response using the Gemini LLM.
   - The response includes source information (PDF or web) and processing time.

4. **Interactive Chat**:
   - The user can continue to ask questions in an interactive loop, with the system providing responses based on the uploaded PDF and web search results.
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
HUGGINGFACE_API_KEY=your_huggingface_api_key
SERPER_API_KEY=your_serper_api_key
QDRANT_API_KEY=your_qdrant_api_key
QDRANT_URL="your_qdrant_url"
GEMINI_API_KEY="your_gemini_api_key"
```

### Run the Application

```bash
streamlit run app.py
```




---

## Future Improvements

- Add support for more file formats (Word, CSV)
- Enhance UI with additional filters and settings
- Improve latency with optimized indexing
- Implement multi-modal support for images and audio

---
