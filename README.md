🚀 RAGForge AI — 

RAGForge AI is a modern Retrieval-Augmented Generation (RAG) chatbot built with Spring Boot, LangChain4j, Google Gemini, and Pinecone.
It allows users to upload PDF documents, index them into a vector database, and ask intelligent questions grounded in the document content.

✨ Features

📄 PDF Upload & Indexing — Automatically parse, chunk, embed, and store PDFs in Pinecone

💬 RAG Chat — Ask questions and receive answers based on your uploaded documents

⚡ Reactive UI — Built with HTMX + Alpine.js for a smooth, dynamic experience

🔧 Clean Architecture — Clear separation between controller, service, and configuration layers

🔒 Secure Environment Config — API keys loaded from .env using spring-dotenv

🏗️ Architecture Overview

Code

User (Browser)

    │
    ▼
    
ChatController

    │
    ▼
    
ChatService ───────────────────────────────► RagAssistant (LangChain4j)

    │                                            │
    │                                            ├── Google Gemini (LLM)
    │                                            └── EmbeddingStoreContentRetriever
    │                                                    │
    ▼                                                    ▼
    
Thymeleaf UI                                      Pinecone Vector DB


🛠️ Tech Stack

Layer	Technology
Backend	Spring Boot 3.2, Java 17
AI Orchestration	LangChain4j 0.36.2
LLM	Google Gemini 2.5 Pro
Embedding Model	AllMiniLM-L6-v2
Vector Store	Pinecone Serverless
PDF Parsing	Apache PDFBox
Frontend	Thymeleaf, HTMX, Alpine.js, Tailwind CSS
Config	spring-dotenv
Testing	JUnit 5, Mockito, Spring MockMvc


🚀 Getting Started

Prerequisites

Java 17+

Maven 3.8+

Google Gemini API key

Pinecone API key + serverless index (dimension 384, metric cosine)

1. Clone the repository
bash
git clone https://github.com/badouchmohamed/RAGForgeAI.git
cd spring-boot-rag-chatbot

3. Create your .env file
env
GEMINI_API_KEY=your-google-gemini-api-key
PINECONE_API_KEY=your-pinecone-api-key
PINECONE_INDEX=your-index-name

4. Run the application
bash
mvn spring-boot:run

The app will be available at:
👉 http://localhost:8080

💡 How It Works
Upload a PDF from the UI

The document is parsed and split into small chunks

Embeddings are generated using AllMiniLM-L6-v2

Chunks are stored in Pinecone

You ask a question → Gemini answers using RAG retrieval


📜 License
MIT License — free to use, modify, and contribute.
