# PDF RAG Assistant

An interactive, AI-powered PDF Question Answering Assistant built using **Retrieval-Augmented Generation (RAG)**. Upload a PDF, ask questions in natural language, and receive context-aware answers with relevant source-page references.

## Features

- **PDF Upload:** Upload PDF documents through a simple Gradio interface.
- **Document Processing:** Extract PDF content and split it into manageable text chunks.
- **Semantic Retrieval:** Generate embeddings using Hugginface Embedding and retrieve relevant content using FAISS.
- **LLM-Powered Answers:** Use  qwen/qwen3.8-27b  to generate responses based on retrieved document content.
- **Source-Page References:** Display the PDF page numbers associated with retrieved source documents.
- **Interactive Interface:** Upload, process, and query documents through Gradio.

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core application |
| Gradio | User interface |
| LangChain | RAG pipeline orchestration |
| PyPDF | PDF document loading |
| Hugginface Embeddings | Text vectorization |
| FAISS | Vector similarity search |
|qwen/qwen3.8-27b | Answer generation |

## Architecture

PDF Upload → Document Loading → Text Chunking → Embeddings → FAISS Vector Store → Relevant Document Retrieval → GPT-4o-mini → Answer with Source Pages

## Project Structure

```text
├── requirements.txt
├── README.md
├── .gitignore
├── screenshots/
└── ragpdfassistance.ipynb
```

The notebook and screenshots are optional. Include them only if they are cleaned and relevant to the final project.

## Prerequisites

- Python 3.10 or a compatible Python version
- An OpenAI API key with access to the required API models
- Internet connectivity for API calls and initial package installation

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR-USERNAME/pdf-rag-assistant.git
   cd pdf-rag-assistant
   ```

2. Create a virtual environment:

   ```bash
   python -m venv .venv
   ```

3. Activate the environment.

   Windows:

   ```bash
   .venv\Scripts\activate
   ```

4. Install dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

5. Configure your GROQ API key.

   PowerShell:

   ```powershell
   $env:GROQ_API_KEY="YOUR_GROQ_API_KEY"
   ```

   Replace the placeholder with your own key. Do not commit API keys to GitHub.

## Run the Application



Open the local Gradio URL displayed in your terminal.

## How to Use

1. Launch the application.
2. Upload a PDF document.
3. Click **Process PDF** and wait for processing to complete.
4. Enter a question about the uploaded document.
5. Click **Ask PDF** or press Enter.
6. Read the generated answer and review the referenced source pages.

## Retrieval Pipeline

The application splits the document into chunks of 1,000 characters with a 200-character overlap. HuggingFaceEmbeddings  and retrieves up to five relevant chunks through FAISS. qwen/qwen3.8-27b generates the response, and the interface displays available source-page references.

## Current Limitations

- The application processes one uploaded PDF per active session.
- The vector index is created in memory and is not persisted between application restarts.
- OpenAI API access and usage charges may apply.
- Response quality depends on PDF text extraction, retrieval relevance, and the source document.
- Source-page references indicate retrieved source pages; they do not guarantee that every generated claim is fully supported.

## Future Enhancements

- Persistent vector storage and document indexing
- Support for multiple PDFs
- Improved retrieval and reranking
- Better error handling and input validation
- Evaluation of retrieval relevance and answer quality
- Deployment with secure API-key management

## Learning Outcomes

This project demonstrates hands-on implementation of document ingestion, text chunking, embeddings, vector similarity search, RAG pipeline orchestration, LLM integration, and interactive GenAI application development.

## License

This project is available for learning and portfolio demonstration. Add a suitable open-source license before granting others explicit reuse permissions.

---

**Built with Python, LangChain, FAISS, OpenAI, and Gradio.**
