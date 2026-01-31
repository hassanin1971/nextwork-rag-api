# RAG-API: Kubernetes Intelligent Knowledge Base

This project implements a complete **Retrieval-Augmented Generation (RAG)** system. It is designed to provide intelligent, context-aware answers regarding Kubernetes documentation by integrating a Vector Database with a local Large Language Model (LLM).

---

## System Architecture

The project follows a modular design to ensure high performance and scalability:

* **Ingestion Layer (embed.py):** Converts raw text from documentation into numerical vector representations for the database.
* **Storage Layer (ChromaDB):** A persistent vector database that stores the semantic meaning of data within the db directory.
* **API Layer (app.py):** A robust FastAPI interface that handles user queries and orchestrates the RAG workflow.
* **Inference Layer (Ollama):** The local generative engine that crafts final responses based on retrieved context.

---

## Technical Key Features

* **Local LLM Integration:** Uses Ollama to run models locally, ensuring data privacy and reducing latency.
* **Persistent Vector Search:** Utilizes ChromaDB to maintain a long-term knowledge base that survives container restarts.
* **Dockerized Environment:** Fully containerized for consistent deployment across different environments.
* **Cross-Platform Networking:** Configured to bridge the gap between Docker containers and host-managed services using specialized network routing.

---

## Installation and Setup

### 1. Build the Docker Image
Execute the following command in the project root to build the application:
```bash
docker build -t hassanin1971/rag-app .

