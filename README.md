# docReader

A Retrieval-Augmented Generation (RAG) system using **LangChain** and **ChromaDB** to read and process online PDFs. The system integrates with **Ollama** for running LLaMA-based models and is containerized with Docker for easy deployment.

---

## Features
- Fetch and process PDFs from URLs.
- Store and query embeddings using **ChromaDB**.
- Use **LangChain** for orchestration.
- Run LLaMA models via **Ollama**.
- Dockerized for reproducibility and portability.

---

## Docker Setup

### 1. Build the Docker image
```bash
docker build -t docreader .
```
### 2. Run the container
The container uses an initialization script (init.sh) to manage Ollama and run the app.
Development Mode (pull model only)
```bash
docker run --rm -it docreader pull
```

This will:
- Start Ollama if not running.
- Pull the llama3.2:1b model.

Production Mode (run the app)
```bash
docker run --rm -it docreader run url/to/pdf
```
This will:
- Start Ollama if not running.
- Execute main.py with the provided PDF URL.

## Example Usage

```bash
# Local
python3 main.py https://example.com/sample.pdf

# Docker
docker run --rm -it docreader run https://example.com/sample.pdf
```
