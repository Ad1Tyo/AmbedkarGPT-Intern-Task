# AmbedkarGPT-Intern-Task
A simple command-line Q&amp;A system. The system will ingest the text from a provided short speech by Dr. B.R. Ambedkar and answer questions based solely on that content.
Features

Document Chunking: Automatically splits large texts into overlapping chunks for better context preservation
Vector Storage: Uses ChromaDB for efficient similarity search
Local LLM: Powered by Ollama (Mistral) for privacy and offline operation
Interactive CLI: Simple command-line interface for querying documents
Source Attribution: View the exact chunks used to generate answers

Prerequisites

Python 3.8 or higher
Ollama installed and running
Required Ollama models downloaded:

mistral:latest (LLM)
all-minilm:l6-v2 (Embeddings)



Installation

Clone the repository

bashgit clone <your-repo-url>
cd rag-speech-analyzer

Install Python dependencies

bashpip install -r requirements.txt

Install and configure Ollama
Download Ollama from https://ollama.ai/
Pull the required models:

bash   ollama pull mistral:latest
   ollama pull all-minilm:l6-v2

Prepare your document
Place your text file (e.g., speech.txt) in an accessible location and update the FILE_PATH in the script.

Configuration
Edit the configuration variables at the top of the script:
pythonFILE_PATH = r"C:\Users\LENOVO\Desktop\Python\speech.txt"  # Your text file path
DB_LOCATION = "./chroma_langchain_db"  # Vector database location
COLLECTION_NAME = "dbr_text"  # Collection name in ChromaDB
MODEL_NAME = "mistral:latest"  # Ollama LLM model
EMBEDDING_MODEL = "all-minilm:l6-v2"  # Embedding model
Usage

Run the script

bashpython rag_system.py

First Run: The system will:

Load your text file
Split it into chunks
Create embeddings
Store them in ChromaDB (this may take a few minutes)


Subsequent Runs: The system will load the existing vector store (much faster)
Ask Questions:

Type your question and press Enter
View the generated answer
Optionally view source chunks used for the answer
Type q to quit
