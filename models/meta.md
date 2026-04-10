# Meta Llama Model Catalog

> **Source:** [Meta AI](https://ai.meta.com) · [OpenRouter](https://openrouter.ai) · [Together AI](https://together.ai) · **Verified:** 2026-04-10

---

## Overview

Meta releases Llama models as **open weights** under the [Meta Llama Community License](https://llama.meta.com/license). There is no official Meta-hosted API with per-token billing — you access Llama models through:
1. **Third-party API providers** (Together AI, Groq, Fireworks AI, AWS Bedrock, Azure AI, etc.)
2. **Self-hosting** (on your own infrastructure using vLLM, Ollama, llama.cpp, etc.)
3. **Meta's own apps** (Meta AI on WhatsApp/Messenger/Instagram — consumer product, not API)

Pricing below reflects typical third-party provider rates as of April 2026.

---

## Current Models

### Llama 4 Scout (Released 2025-04)

Meta's current frontier open-weight model. Mixture-of-Experts architecture.

| Metric | Value |
|---|---|
| Parameters | 109B active (17B per expert × 16 experts) |
| Context window | 10,000,000 tokens (10 M — extraordinary) |
| Modalities | Text + Images |
| Typical API price (input) | ~$0.11 / 1M tokens |
| Typical API price (output) | ~$0.34 / 1M tokens |
| Weights | Open — [HuggingFace](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E-Instruct) |

**Best for:** Long-document reasoning, multimodal tasks, cost-sensitive production at frontier quality.

---

### Llama 4 Maverick (Released 2025-04)

Larger MoE model in the Llama 4 family.

| Parameters | Context | Input (typical) | Output (typical) |
|---|---|---|---|
| 400B active (17B × 128E) | 1,000,000 tokens | ~$0.27 / 1M | ~$0.85 / 1M |

---

### Llama 3.3 70B Instruct (Released 2024-12)

Previous-generation flagship. Still widely used and supported.

| Context | Typical input | Typical output |
|---|---|---|
| 128,000 tokens | ~$0.59 / 1M | ~$0.79 / 1M |

---

### Llama 3.1 405B Instruct

Largest dense Llama model. Higher cost than MoE variants.

| Context | Typical input | Typical output |
|---|---|---|
| 128,000 tokens | ~$3.50 / 1M | ~$3.50 / 1M |

---

## Key Provider Options for Llama

| Provider | Notable features |
|---|---|
| **Together AI** | Broadest Llama selection, fine-tuning, competitive pricing |
| **Groq** | Fastest inference (LPU hardware), limited models |
| **Fireworks AI** | Low latency, strong uptime SLAs |
| **AWS Bedrock** | Enterprise compliance, managed service |
| **Azure AI** | Enterprise compliance, integrated with Azure ecosystem |
| **Cloudflare Workers AI** | Edge inference, generous free tier |
| **Nebius AI** | European data residency option |
| **Ollama** | Local/self-hosted, free |

---

## Self-Hosting Guidance

For >10M tokens/month, self-hosting on cloud GPUs typically becomes cost-competitive with managed APIs:
- 70B model requires 2× A100 80GB or 4× A10G
- 8B model runs on single A10G or consumer 4090

Use [vLLM](https://github.com/vllm-project/vllm) for production inference or [Ollama](https://ollama.ai) for local development.

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
