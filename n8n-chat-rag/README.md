# n8n RAG Chatbot 🤖

> Intelligent document chat system powered by RAG (Retrieval-Augmented Generation), vector search, and AI




## 📖 Overview

An n8n workflow that enables intelligent conversations with your documents using RAG technology. Upload documents to Google Drive, and the system automatically processes them into a vector database, allowing you to ask questions and receive AI-generated answers based on your document content.

## ✨ Features

- 🔄 **Automatic Document Processing** - Monitors Google Drive for new documents
- 🧠 **Vector Embeddings** - Uses Ollama for local embedding generation
- 💾 **Supabase Vector Store** - Stores and retrieves document embeddings
- 💬 **Intelligent Chat** - Powered by OpenAI GPT for natural conversations
- 🔍 **Semantic Search** - Finds relevant context from your documents
- 📄 **Multi-Format Support** - Handles various document types

## 🏗️ Architecture

### Workflow Components

**Document Processing Pipeline:**
1. Google Drive Trigger → Monitors for new files
2. Download File → Retrieves document content
3. Data Loader → Parses document structure
4. Text Splitter → Chunks text for processing
5. Embeddings (Ollama) → Generates vector representations
6. Supabase Vector Store → Stores embeddings with metadata

**Chat Pipeline:**
1. Chat Trigger → Receives user queries
2. AI Agent → Orchestrates response generation
3. Query Embeddings → Converts query to vectors
4. Vector Search → Finds relevant document chunks
5. OpenAI Chat Model → Generates contextual responses
6. Response Output → Returns answer to user

## 🚀 Getting Started

### Prerequisites

- Docker installed on your system
- Google Drive account with API credentials
- Supabase account and project
- OpenAI API key
- Ollama running locally or accessible endpoint


Installation

**Import the workflow:**
   - Download `rag-chatbot-workflow.json` from this repository
   - In n8n: Click "Add workflow" → "Import from File"
   - Select the downloaded JSON file

4. **Configure credentials:**
   - Go to Settings → Credentials
   - Add the following credentials:
     - Google Drive OAuth2
     - Supabase API
     - OpenAI API
     - Ollama endpoint (if remote)

### Quick Start

1. **Set up Google Drive folder:**
   - Create a folder in Google Drive for documents
   - Configure the Google Drive Trigger node with folder ID

2. **Configure Supabase:**
   - Create a Supabase project
   - Enable `pgvector` extension
   - Create a table for vector storage
   - Add connection details to Supabase Vector Store nodes

3. **Set up OpenAI:**
   - Get API key from OpenAI
   - Add to OpenAI Chat Model node

4. **Configure Ollama:**
   - Install Ollama: `curl https://ollama.ai/install.sh | sh`
   - Pull embedding model: `ollama pull nomic-embed-text`
   - Configure endpoint in Embeddings nodes

5. **Activate the workflow:**
   - Save all node configurations
   - Click "Active" toggle to enable

## 💡 Usage

### Processing Documents

1. Upload a document to your configured Google Drive folder
2. n8n automatically detects the new file
3. Document is processed and stored in vector database
4. You can now chat about the document content

### Chatting with Documents

1. Send a message through the chat interface
2. System searches for relevant document context
3. AI generates a response using retrieved information
4. Response includes information from your documents

### Example Queries

```
"What are the main points in the uploaded document?"
"Summarize the key findings about [topic]"
"Find all references to [keyword] in my documents"
"What does the report say about [specific subject]?"
```




## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Workflow Engine** | n8n (Docker) |
| **Vector Database** | Supabase (pgvector) |
| **Embeddings** | Ollama (nomic-embed-text) |
| **Chat Model** | OpenAI GPT |
| **Document Source** | Google Drive |
| **Text Processing** | Recursive Character Splitter |
| **AI Orchestration** | n8n AI Agent |



## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Contact

For questions or feedback, please open an issue on GitHub.

---

**Built with ❤️ using n8n, AI, and vector search**
