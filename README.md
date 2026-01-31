# # RAG-API: INTELLIGENT KUBERNETES KNOWLEDGE BASE

## ## PROJECT OVERVIEW
This project implements a high-performance **Retrieval-Augmented Generation (RAG)** system. It transforms static documentation into an interactive intelligence layer, allowing users to query Kubernetes data using natural language.

---

## ## CORE TECHNOLOGIES & TOOLS
* **FastAPI**: High-performance web framework for building the API [cite: 2026-01-19].
* **ChromaDB**: AI-native open-source vector database for persistent storage [cite: 2026-01-19].
* **Ollama**: Local engine for running large language models (TinyLlama) [cite: 2026-01-19].
* **Docker**: Containerization for seamless and isolated deployment [cite: 2026-01-19].
* **Python**: The core programming language for logic and data processing [cite: 2026-01-19].

---

## ## EXECUTION WORKFLOW

### ### 1. DOCUMENT PROCESSING (k8s.txt)
The system starts by consuming the **k8s.txt** file, which serves as the primary source of truth [cite: 2026-01-19]. This text document contains the technical knowledge required to answer Kubernetes-related questions [cite: 2026-01-19].

### ### 2. VECTOR EMBEDDINGS (ChromaDB)
Using `embed.py`, the system performs the following:
* It reads the content of **k8s.txt** [cite: 2026-01-19].
* It converts text chunks into high-dimensional **Vector Embeddings** [cite: 2026-01-19].
* These embeddings are stored persistently in the **ChromaDB** (`/db`) directory, allowing for lightning-fast semantic searches [cite: 2026-01-19].

### ### 3. API DEVELOPMENT (FastAPI)
The **FastAPI** layer (`app.py`) acts as the brain of the operation:
* It manages the `/query` endpoint to receive user input [cite: 2026-01-19].
* It retrieves the most relevant text segments from ChromaDB based on semantic similarity [cite: 2026-01-19].

### ### 4. INTELLIGENT GENERATION (Ollama)
The retrieved context is passed to **Ollama**:
* The system utilizes a local LLM to generate precise and human-like answers [cite: 2026-01-19].
* It ensures that the model only answers based on the provided Kubernetes context [cite: 2026-01-19].

---

## ## DOCKER HUB REPOSITORY
The official Docker image for this project is available on my Docker Hub profile. You can pull the latest version using the following link:

👉 **[hassanin1971/rag-app:latest](https://hub.docker.com/r/hassanin1971/rag-app)**

---

## ## QUICK START
To run the container and connect it to your local Ollama instance:
```bash
docker run -d -p 8000:8000 -e OLLAMA_HOST=[http://host.docker.internal:11434](http://host.docker.internal:11434) --name rag-app-final hassanin1971/rag-app