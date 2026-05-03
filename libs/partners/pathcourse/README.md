# langchain-pathcourse

PathCourse Health integration for LangChain — autonomous agent inference with USDC billing on Base L2.

## Installation

```bash
pip install langchain-pathcourse
```

## Quick Start — Chat Model

```python
from langchain_pathcourse import ChatPathCourse

llm = ChatPathCourse(
    model="pch-fast",
    pch_api_key="pch_prod_b_...",  # or set PCH_API_KEY env var
)

response = llm.invoke("Explain x402 in one sentence.")
print(response.content)
```

## Quick Start — Embeddings

```python
from langchain_pathcourse import PathCourseEmbeddings

embeddings = PathCourseEmbeddings()
vector = embeddings.embed_query("What is Path Score?")
vectors = embeddings.embed_documents(["doc1", "doc2"])
```

## Available Models

| Model | Description |
|-------|-------------|
| `pch-fast` | Fast reasoning, classification, routing — $0.44/M tokens |
| `pch-pro` | Deep reasoning, multi-step planning — $1.96/M tokens (Bronze+) |
| `pch-coder` | Code generation, debugging — $3.50/M tokens |
| `pch-embed` | Text embeddings for semantic search/RAG — $0.015/M tokens |
| `claude-haiku` | Anthropic Claude Haiku — common rate (Silver+) |
| `claude-sonnet` | Anthropic Claude Sonnet — common rate (Gold) |

```python
# List all models programmatically
from langchain_pathcourse import ChatPathCourse
print(ChatPathCourse.list_models())
```

## Configuration

| Parameter | Description | Default |
|-----------|-------------|---------|
| `model` | PCH model name | `pch-fast` |
| `pch_api_key` | PCH API key — falls back to `PCH_API_KEY` env var | `None` |

Get an API key at [pathcoursehealth.com](https://pathcoursehealth.com).

## Working Examples

[pch-integration-examples](https://github.com/pathcourse-health/pch-integration-examples)

## License

MIT — PathCourse Health
