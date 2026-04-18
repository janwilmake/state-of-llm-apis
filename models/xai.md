# xAI Grok Model Catalog

> **Source:** [xAI Models & Pricing](https://docs.x.ai/developers/models) · [xAI API](https://x.ai/api) · [OpenRouter](https://openrouter.ai/x-ai/grok-4.20) · **Verified:** 2026-04-18

---

## Current Models

### Grok 4.20 (Released 2026-03-31) — Current Flagship

xAI's newest flagship with 2 M token context, industry-leading speed, and agentic tool calling.

> **API name update (2026-04-17):** The official xAI API docs now surface `grok-4.20-0309-reasoning` and `grok-4.20-0309-non-reasoning` as the canonical dated model IDs. The alias `grok-4.20` remains valid. The `-0309` suffix pins to the March 9 training checkpoint.

| Metric | Value |
|---|---|
| API names | `grok-4.20-0309-reasoning` · `grok-4.20-0309-non-reasoning` · `grok-4.20` (alias) |
| Context window | 2,000,000 tokens |
| Input | **$2.00 / 1M** |
| Cached input | **$0.20 / 1M** |
| Output | **$6.00 / 1M** |
| Web search | $5.00 / 1K calls |
| Knowledge cutoff | November 2024 |

**Architecture:** 4-agent system (Grok + Harper + Benjamin + Lucas) for parallel reasoning and cross-verification. "Heavy" variant uses 16 agents for deeper analysis.

**Key capabilities:** Reasoning (can be toggled on/off), vision, X (Twitter) real-time data access, image generation.

**GPQA Diamond:** ~88%

---

### Grok 4 (Released 2025-07-09)

| Metric | Value |
|---|---|
| API name | `grok-4` |
| Context window | 256,000 tokens |
| Input | **$3.00 / 1M** |
| Cached input | $0.75 / 1M |
| Output | **$15.00 / 1M** |

Always-on reasoning model. No `reasoning_effort` parameter — reasoning cannot be disabled.  
`presencePenalty`, `frequencyPenalty`, and `stop` are not supported.

**GPQA Diamond:** 87.7% | **MMLU:** 86.6% | **LiveCodeBench:** 81.9%

---

### Grok 4 Fast / Grok 4.1 Fast (Recommended for most developers)

Near-frontier capability at a fraction of the flagship price. 2 M token context.

> **API name update (2026-04-15):** xAI's official API now surfaces these as `grok-4-fast-reasoning` and `grok-4-fast-non-reasoning`. `grok-4.1-fast` remains a valid alias. Both sets of names return identical pricing.

| Metric | Value |
|---|---|
| API names | `grok-4-fast-reasoning` · `grok-4-fast-non-reasoning` · `grok-4.1-fast` |
| Context window | 2,000,000 tokens |
| Input | **$0.20 / 1M** |
| Cached input | $0.05 / 1M |
| Output | **$0.50 / 1M** |
| Live search | $25.00 / 1K sources |

Available in reasoning and non-reasoning variants. 40% fewer thinking tokens than Grok 4 on average.

**Best for:** Long documents, large codebases, extended agent workflows, high-volume tasks.

---

### Grok 4.20 — Pricing via xAI Characters API

xAI also offers a **characters-based pricing** option at **$4.20 / 1M characters** with 10 rps for Grok 4.20.

---

### Grok Code Fast (Coding-Specialist)

Coding-focused model derived from the Grok 4.1 Fast architecture, optimized for programming tasks.

| Metric | Value |
|---|---|
| API name | `grok-code-fast-1` |
| Context window | 256,000 tokens |
| Input | **$0.20 / 1M** |
| Output | **$1.50 / 1M** |

**Best for:** Code generation, debugging, refactoring. Higher output price than Grok 4.1 Fast reflects longer code outputs. Vision not included.

---

### Grok 3 Beta (Legacy)

| Context | Input | Output |
|---|---|---|
| 131,072 tokens | $3.00 / 1M | $15.00 / 1M |

---

### Grok 3 Mini Beta

| Context | Input | Output |
|---|---|---|
| 131,072 tokens | $0.30 / 1M | $0.50 / 1M |

---

## Tools Pricing

| Tool | Price |
|---|---|
| Web search | $2.50–$5.00 / 1K calls (varies by model) |
| X (Twitter) search | Included with API access |
| Code execution | Per token |
| Collections search (RAG) | Per token |

---

## Subscription Plans (consumer)

| Plan | Price | Notes |
|---|---|---|
| Free | $0 | Grok 4.1 Fast, limited daily messages |
| SuperGrok | **$30/month** | Grok 4 + 2 M context, full usage |
| Grok Business | **$30/seat/month** | Team plan |
| X Premium+ | $16/month | Grok access through X platform |

---

## Grok 4.3 Beta (Early Access — Appeared 2026-04-17)

> ⚠️ **No API pricing or official announcement yet.** Consumer early access only.

On April 17, 2026, users discovered that Grok.com now lists **"Grok 4.3 (beta)"** as an "Early Access" option in the model selector. This was not announced via an official xAI blog post. Reported improvements include enhanced ultra-long context handling and native video analysis capabilities. The previous web version was Grok 4.20.

**What we know:**
- Visible in Grok.com model selector as "Grok 4.3 (beta)" with an "Early Access" label
- Expected improvements: better long-context processing, native multimodal video understanding
- No API model ID or pricing announced
- Available to SuperGrok Heavy ($300/month) subscribers

*Source: KuCoin Flash (2026-04-17), BlockBeats, multiple user reports — verified 2026-04-18*

---

## Grok 5 (Expected Q2 2026)

Grok 5 has been delayed past the original Q1 2026 target. xAI now points to **Q2 2026** as the likely window. Training on the 1 GW Colossus 2 supercluster in Memphis. Reported 6 trillion parameters with MoE architecture.

---

## Storage Billing (Effective 2026-04-20)

xAI Files and Collections (used for RAG/context storage) will begin incurring storage charges starting **April 20, 2026**. Developers using the Files or Collections APIs to persist data should review storage usage before this date. Visit the [xAI Console](https://console.x.ai/team/default/files) to view and manage stored files and collections.

## New Features (2026)

- **Batch API** (new) — async processing at reduced cost
- **Prompt Caching** (new) — automatic caching for repeated context
- **Provisioned Throughput** (new) — dedicated compute for enterprise
- **mTLS Authentication** (new) — enhanced security for API connections
- **Video input/output** (new capability)
- **Audio input/output** (new capability)

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
