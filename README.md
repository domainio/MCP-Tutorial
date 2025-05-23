# MCP Practical Guide

This repository contains code samples and exercises for the MCP Workshop, demonstrating how to build AI applications using the MCP for standardized communication between AI apps and tools.

## Prerequisites

- Python 3.11 or higher
- Git
- An OpenAI API key for working with the AI models
- Alternatively, run a Local Model with Ollama:
  - Install Ollama: 
    ```curl -fsSL https://ollama.com/install.sh | sh```
  - Pull a Model: 
    ```ollama pull llama3.2```
  - Run the Model: 
    ```ollama run llama3.2```
  - Set env vars:
    ```
    OPENAI_API_BASE_URL=http://localhost:11434/v1
    OPENAI_API_KEY=ollama-key
    ```
  - Set OpenAI base url in code: ```openai.api_base = os.getenv("OPENAI_API_BASE_URL")```
  - Use local Ollama model in every LLM call: ```model="llama3.2"```  
  

## Setup Instructions

1. **Clone the repository**

```bash
git clone https://github.com/domainio/MCP-Practical-Guide.git
```

2. **Install uv**

If you don't have uv installed, you can install it with:

```bash
curl -sSf https://astral.sh/uv/install.sh | bash
```

Or on Windows:

```bash
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

3. **Create and activate a virtual environment with uv**

```bash
uv venv
source .venv/bin/activate  # On Windows, use .venv\Scripts\activate
```

4. **Install the dependencies with uv**

Since this project has a pyproject.toml file, you can install all dependencies with:

```bash
uv pip install -e .
```

5. **Set up environment variables**

Create a `.env` file in the project root with the following content:

```
OPENAI_API_KEY=your_openai_api_key
```

## Get Started

### * [Colab Notebook](https://colab.research.google.com/drive/1fM355sy66MQK-t5-jOHlYH5j4YxBI5o4?usp=sharing)

---

### * Run section 1 locally

Run the MCP Server

```bash
python src/1-mcp-simple-client-server/mcp_simple_server.py
```


Run the MCP Inspector

```bash
mcp dev src/1-mcp-simple-client-server/mcp_simple_server.py
```
Browse `http://127.0.0.1:6274`


Run the MCP Client

```bash
python src/1-mcp-simple-client-server/mcp_simple_client.py
```

---

### * Run section 4-Resources locally

Run MinIO with initial Resources

```bash
docker compose -f src/4-mcp-resource/resources/docker-compose.minio.yml up
```
Browse MinIO `http://127.0.0.1:9001/`

---

### * Run section 6 Multi Clients - Browser Use

```bash
npx playwright install
npx playwright install chromium

python src/6-mcp-multi-clients/browser_use.py
```

---

### * Run section 6 Multi Clients - Multi Clients

Set `GITLAB_PERSONAL_ACCESS_TOKEN` in `.env`

