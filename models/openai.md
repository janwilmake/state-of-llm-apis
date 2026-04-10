# OpenAI Model Catalog

> **Source:** [OpenAI API Pricing](https://developers.openai.com/api/docs/pricing) · [OpenAI Models](https://platform.openai.com/docs/models) · **Verified:** 2026-04-10

---

## Current Recommended Models

### GPT-5.4 Family (Flagship – Released 2026-03-05)

OpenAI's most capable general-purpose model family. First mainline model with **native computer-use** capabilities. Absorbs frontier coding from GPT-5.3-Codex into a single unified model.

| Model | API name | Context | Max output | Input (std) | Cached input | Output (std) | Input (long >272K) | Output (long >272K) |
|---|---|---|---|---|---|---|---|---|
| GPT-5.4 | `gpt-5.4` | 1 M tokens | 128 K | $2.50 | $0.25 | $15.00 | $5.00 | $22.50 |
| GPT-5.4 Pro | `gpt-5.4-pro` | 1 M tokens | 128 K | $30.00 | — | $180.00 | $60.00 | $270.00 |

**GPT-5.4 Mini** (Released 2026-03-17)

| Model | API name | Context | Input | Cached input | Output |
|---|---|---|---|---|---|
| GPT-5.4 Mini | `gpt-5.4-mini` | 1 M tokens | $0.75 | $0.075 | $4.50 |

**GPT-5.4 Nano** (Released 2026-03-17)

| Model | API name | Context | Input | Cached input | Output |
|---|---|---|---|---|---|
| GPT-5.4 Nano | `gpt-5.4-nano` | 1 M tokens | $0.20 | $0.02 | $1.25 |

**Key facts:**
- Standard context window: **272K tokens**; tokens beyond 272K billed at 2× rate (long-context pricing)
- Native computer-use: **75% OSWorld-Verified** (surpasses human expert baseline of 72.4%)
- SWE-bench Pro: **57.7%** (GPT-5.4), **54.38%** (Mini)
- GPT-5.2 Thinking retires **2026-06-05**; GPT-5.4 Thinking is the replacement in ChatGPT
- Regional processing (data residency) adds **+10% uplift** on all gpt-5.4 models

**Pricing tiers available:** Standard, Batch (50% off), Flex (50% off, async), Priority (2× standard, fast queuing)

---

### GPT-4.1 Family (Released 2025-04-14)

Long-context workhorses with 1 M token context at lower price than GPT-5.4.

| Model | API name | Context | Input | Cached input | Output |
|---|---|---|---|---|---|
| GPT-4.1 | `gpt-4.1` | 1 M tokens | $2.00 | $0.50 | $8.00 |
| GPT-4.1 Mini | `gpt-4.1-mini` | 1 M tokens | $0.40 | $0.10 | $1.60 |
| GPT-4.1 Nano | `gpt-4.1-nano` | 1 M tokens | $0.10 | $0.025 | $0.40 |

Available for fine-tuning: `gpt-4.1`, `gpt-4.1-mini`

---

### Reasoning Models

| Model | API name | Context | Input | Cached input | Output | Notes |
|---|---|---|---|---|---|---|
| o3 | `o3` | 200 K | $10.00 | $2.50 | $40.00 | Deep reasoning; released 2025-04-16 |
| o4-mini | `o4-mini` | 200 K | $1.10 | $0.275 | $4.40 | Cost-efficient reasoning; released 2025-04-16 |
| o3 Deep Research | `o3-deep-research` | 200 K | $10.00 | — | $40.00 | Research agent |
| o4-mini Deep Research | `o4-mini-deep-research` | 200 K | $2.00 | — | $8.00 | Budget research agent |

---

### Legacy / Still Active

| Model | API name | Context | Input | Cached input | Output | Notes |
|---|---|---|---|---|---|---|
| GPT-4o | `gpt-4o` | 128 K | $2.50 | $1.25 | $10.00 | GA; older flagship |
| GPT-4o Mini | `gpt-4o-mini` | 128 K | $0.15 | $0.075 | $0.60 | GA |
| GPT-4.5 Preview | `gpt-4.5-preview` | 128 K | — | — | — | **Deprecated** – see [deprecated.md](../deprecated.md) |

---

## Batch API Pricing

Batch processing offers **50% off** standard prices for all models (asynchronous, up to 24 h turnaround). Use the `v1/batches` endpoint.

## Prompt Caching

Cached input tokens are charged at **10% of standard input price** for most models. Caching kicks in automatically after the first 1 024 tokens of a repeated prefix.

## Codex (Agentic Coding)

- **Pay-as-you-go** for teams via `codex-mini-latest` and Codex CLI (available April 2026)
- Enterprise: new **Codex seat** type at flexible token-based pricing (announced 2026-04-02)
- ChatGPT Business price reduced to **$20/seat/month** (down from $25) with Codex rollout

## Notes for Developers

- `gpt-5.4` is the best single model for agentic, computer-use, and coding tasks as of April 2026
- `gpt-5.4-mini` is recommended for high-volume latency-sensitive workloads
- `gpt-4.1-nano` / `gpt-5.4-nano` are the cheapest OpenAI options ($0.10–$0.20 input)
- `o4-mini` is the best cost-to-performance reasoning choice
- All prices **per 1M tokens** (USD)

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md) · [deprecated.md](../deprecated.md)*
