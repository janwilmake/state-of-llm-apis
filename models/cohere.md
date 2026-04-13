# Cohere Model Catalog

> **Source:** [Cohere Pricing](https://cohere.com/pricing) · [Cohere Docs](https://docs.cohere.com) · **Verified:** 2026-04-13

---

## Generative Models (Command Series)

### Command A (Released 2025-03-13) — Current Flagship

| Metric | Value |
|---|---|
| API name | `command-a-03-2025` |
| Context window | 256,000 tokens |
| Input | **$2.50 / 1M** |
| Output | **$10.00 / 1M** |
| Speed | ~49 tok/s |

**Best for:** Enterprise agents, advanced reasoning, long-context document processing, agentic workflows.  
MMLU: 71.2% | GPQA: 52.7%

---

### Command R+ (08-2024)

| Context | Input | Output |
|---|---|---|
| 128,000 tokens | **$2.50 / 1M** | **$10.00 / 1M** |

Legacy flagship. Same price as Command A but lower context (128K vs 256K) and lower benchmarks. Best for RAG with citation support.

---

### Command R (08-2024)

| Context | Input | Output |
|---|---|---|
| 128,000 tokens | **$0.15 / 1M** | **$0.60 / 1M** |

Balanced model. Good for production RAG workloads where Command R+ cost is prohibitive.

---

### Command R7B (Released 2024-12)

| Context | Input | Output |
|---|---|---|
| 128,000 tokens | **$0.0375 / 1M** | **$0.15 / 1M** |

Cheapest Command model. Good for high-volume simple tasks, classification, basic Q&A, development/testing.

---

## Retrieval & Embedding Models

### Rerank 3.5 / Rerank 4 Fast / Rerank 4 Pro

Available via Model Vault (dedicated deployment):
- Medium tier: **$5.00/hour** or **$3,250/month** per instance

### Embed 4

Multimodal embedding (text + images).

- Small tier: **$4.00/hour** or **$2,500/month** per instance (Model Vault)
- API: contact for pricing

---

## Free Tier

**1,000 API calls per month** across all models (Trial API key). No credit card required for trial access.

Production API key requires billing setup.

---

## Cohere's Positioning

Cohere focuses on **enterprise RAG and retrieval** use cases:
- Command R+ is purpose-built for retrieval-augmented generation with native citation support
- Embed 4 provides multimodal embeddings unavailable from most competitors
- Rerank models improve search quality significantly at low cost
- Model Vault offers private, dedicated deployment with SLA guarantees

**Honest benchmark note:** Command A benchmarks (GPQA 52.7%) trail Claude Opus 4.6 (91.3%) and GPT-5.4 considerably. Cohere's value is enterprise RAG tooling and specialized retrieval features, not frontier reasoning.

---

## Legacy Pricing (existing customers)

| Model | Input | Output |
|---|---|---|
| Command R+ 04-2024 | $3.00 / 1M | $15.00 / 1M |
| Command R 03-2024 | $0.50 / 1M | $1.50 / 1M |
| Command | $1.00 / 1M | $2.00 / 1M |
| Command-Light | $0.30 / 1M | $0.60 / 1M |
| Aya Expanse (8B/32B) | $0.50 / 1M | $1.50 / 1M |

## Retired Models (no longer accessible)

| Model | Retired | Replacement |
|---|---|---|
| `embed-english-v2.0` | **2026-04-04** | `embed-english-v3.0` or `embed-v4.0` |
| `embed-english-light-v2.0` | **2026-04-04** | `embed-english-v3.0` |
| `embed-multilingual-v2.0` | **2026-04-04** | `embed-multilingual-v3.0` or `embed-v4.0` |
| `c4ai-aya-expanse-8b` | **2026-04-04** | `command-r7b-12-2024` or `command-a-03-2025` |
| `c4ai-aya-vision-8b` | **2026-04-04** | `command-a-03-2025` |
| `command-r-03-2024` (alias `command-r`) | 2025-09-15 | `command-r-08-2024` |
| `command-r-plus-04-2024` (alias `command-r-plus`) | 2025-09-15 | `command-r-plus-08-2024` |
| `command-light` | 2025-09-15 | `command-r7b-12-2024` |
| `command` | 2025-09-15 | `command-a-03-2025` |

*See [deprecated.md](../deprecated.md) for full details.*

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
