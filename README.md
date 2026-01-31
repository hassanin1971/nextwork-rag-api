# RAG-API: INTELLIGENT KUBERNETES KNOWLEDGE BASE

## PROJECT OVERVIEW
This project implements a high-performance **Retrieval-Augmented Generation (RAG)** system. It transforms static documentation into an interactive intelligence layer, allowing users to query Kubernetes data using natural language.

## CORE TECHNOLOGIES & TOOLS
* **FastAPI**: High-performance web framework for building the API.
* **ChromaDB**: AI-native open-source vector database for persistent storage.
* **Ollama**: Local engine for running large language models (TinyLlama).
* **Docker**: Containerization for seamless and isolated deployment.
* **Python**: The core programming language for logic and data processing.

## EXECUTION WORKFLOW

### 1. DOCUMENT PROCESSING (k8s.txt)
The system starts by consuming the **k8s.txt** file, which serves as the primary source of truth. This text document contains the technical knowledge required to answer Kubernetes-related questions.

### 2. VECTOR EMBEDDINGS (ChromaDB)
Using \`embed.py\`, the system performs the following:
* It reads the content of **k8s.txt**.
* It converts text chunks into high-dimensional **Vector Embeddings**.
* These embeddings are stored persistently in the **ChromaDB** (\`/db\`) directory, allowing for lightning-fast semantic searches.

### 3. API DEVELOPMENT (FastAPI)
The **FastAPI** layer (\`app.py\`) acts as the brain of the operation:
* It manages the \`/query\` endpoint to receive user input.
* It retrieves the most relevant text segments from ChromaDB based on semantic similarity.

### 4. INTELLIGENT GENERATION (Ollama)
The retrieved context is passed to **Ollama**:
* The system utilizes a local LLM to generate precise and human-like answers.
* It ensures that the model only answers based on the provided Kubernetes context.

## DOCKER HUB REPOSITORY
The official Docker image for this project is available on my Docker Hub profile:
👉 [**hassanin1971/rag-app:latest**](https://hub.docker.com/r/hassanin1971/rag-app

