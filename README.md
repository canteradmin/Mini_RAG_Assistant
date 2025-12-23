
## Mini RAG Assistant

A simple **Retrieval-Augmented Generation (RAG)** web application built with **Streamlit**.  
Ask questions about your documents — stored either **locally** (uploaded files) or in **Azure Blob Storage**.

### Features
- Toggle between **Local** and **Cloud (Azure Blob Storage)** data sources
- Upload PDF, DOCX, TXT files directly in the app (Local mode)
- Secure credential handling via `.env` 
- OpenAI embeddings (`text-embedding-3-small`) and LLM (`gpt-4o-mini`)
- Conversation memory (last 4 turns) - You can choose any turns based on your choice
- Retrieval quality metrics: Precision@3, Hit Rate@3, Faithfulness, Confidence Score
- Highlighted best-matching retrieved chunk
- Clean dark-themed UI

### Project Structure
mini-rag-assistant/
├── app.py                  # Main Streamlit app
├── prompts.py              # System prompt and message builder
├── .env                    # Environment variables (API keys) – NOT in git!
├── requirements.txt        # Dependencies
├── knowledge_base/         # Local uploaded documents (auto-created)
├── knowledge_base_vectorstore/  # FAISS vector store (auto-created)
└── docs/                   # Documentation (optional)


### Setup & Installation

#### Prerequisites
- Python 3.9+
- OpenAI API key[](https://platform.openai.com/account/api-keys)
- (Optional) Azure Storage Account + Blob container

#### Steps

1. **Clone or download** the project

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt

### .env 
OPENAI_API_KEY= 'your api key'

# Optional: Azure Blob Storage
AZURE_STORAGE_CONNECTION_STRING='your azure key'
AZURE_CONTAINER_NAME=' your container name '

### Run the app
streamlit run app.py

Choose Local or Cloud (Azure Blob Storage) in the sidebar
For Local:
Upload documents via the uploader
For Cloud:
Ensure .env has valid Azure credentials
App loads documents from your Azure container

Ask questions in the text input box
View answer, metrics, and retrieved chunks














IssueSolution"OPENAI_API_KEY not found"Check .env / RAG.env exists and has correct key401 Invalid API KeyGenerate a new key from https://platform.openai.com/account/api-keysNo documents loadedUpload files (Local) or check Azure container (Cloud)Azure load failsVerify connection string and container name
