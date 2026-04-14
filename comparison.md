# LLM API Comparison Matrix

> **Last updated:** 2026-04-14. Prices per 1M tokens (USD), standard tier unless noted.

---

## Flagship Models (Best-in-class)

| Provider | Model | Context | Input | Output | GPQA | SWE-bench | Notes |
|---|---|---|---|---|---|---|---|
| [OpenAI](models/openai.md) | GPT-5.4 | 1 M | $2.50 | $15.00 | 92.8% | 57.7% | Native computer-use; tokens >272K billed at 2× |
| [OpenAI](models/openai.md) | GPT-5.4 Pro | 1 M | $30.00 | $180.00 | — | — | Max capability |
| [Anthropic](models/anthropic.md) | Claude Opus 4.6 | 1 M | $5.00 | $25.00 | 91.3% | 74%+ | No long-context premium |
| [Google](models/google.md) | Gemini 3.1 Pro Preview | 1 M | $2.00 | $12.00 | 94.3% | 80.6% | Preview (no GA SLA) |
| [xAI](models/xai.md) | Grok 4.20 | 2 M | $2.00 | $6.00 | ~88% | 75% | X data integration |
| [xAI](models/xai.md) | Grok 4 | 256 K | $3.00 | $15.00 | 87.7% | — | Always-on reasoning |

**Verdict:** For best reasoning accuracy, Gemini 3.1 Pro (94.3% GPQA) is currently top. For computer-use, GPT-5.4 is unmatched. For cost-efficiency at frontier level, Grok 4.20 ($2/$6) leads.

---

## Mid-Range Models (Best price-performance)

| Provider | Model | Context | Input | Output | Notes |
|---|---|---|---|---|---|
| [OpenAI](models/openai.md) | GPT-5.4 Mini | 1 M | $0.75 | $4.50 | 54.38% SWE-bench; 6× cheaper than flagship |
| [OpenAI](models/openai.md) | GPT-4.1 | 1 M | $2.00 | $8.00 | 1 M context at lower price |
| [Anthropic](models/anthropic.md) | Claude Sonnet 4.6 | 1 M | $3.00 | $15.00 | Best production Claude model |
| [Google](models/google.md) | Gemini 2.5 Pro | 2 M | $1.25 | $10.00 | ⚠️ Retiring 2026-06-17 |
| [Google](models/google.md) | Gemini 3 Flash Preview | 1 M | $0.50 | $3.00 | Preview; fast |
| [Mistral](models/mistral.md) | Mistral Medium 3 | 131 K | $0.40 | $2.00 | Good for coding/RAG |
| [Cohere](models/cohere.md) | Command A | 256 K | $2.50 | $10.00 | Enterprise RAG; citation support |
| [Meta](models/meta.md) | Llama 4 Maverick | 1 M | ~$0.15 | ~$0.60 | Open weights; self-hostable |

---

## Budget / High-Volume Models

| Provider | Model | Context | Input | Output | Notes |
|---|---|---|---|---|---|
| [OpenAI](models/openai.md) | GPT-5.4 Nano | 1 M | $0.20 | $1.25 | Newest cheapest OpenAI |
| [OpenAI](models/openai.md) | GPT-4.1 Nano | 1 M | $0.10 | $0.40 | Very cheap; 1 M context |
| [OpenAI](models/openai.md) | GPT-4o Mini | 128 K | $0.15 | $0.60 | Legacy; still widely used |
| [Anthropic](models/anthropic.md) | Claude Haiku 4.5 | 200 K | $1.00 | $5.00 | Fastest Claude |
| [Google](models/google.md) | Gemini 2.5 Flash 🏆 | 1 M | $0.30 | $2.50 | Best GA balance ⚠️ retires 2026-06-17 |
| [Google](models/google.md) | Gemini 2.5 Flash-Lite | 1 M | $0.10 | $0.40 | ⚠️ retires 2026-07-22 |
| [Google](models/google.md) | Gemini 2.0 Flash-Lite | 1 M | $0.075 | $0.30 | Absolute cheapest billed option ⚠️ retires 2026-06-01 |
| [Mistral](models/mistral.md) | Mistral Small 4 | 262 K | $0.15 | $0.60 | Vision + coding + reasoning unified |
| [Mistral](models/mistral.md) | Mistral Nemo | 128 K | $0.02 | $0.06 | Cheapest Mistral |
| [xAI](models/xai.md) | Grok 4.1 Fast | 2 M | $0.20 | $0.50 | Near-frontier at budget price |
| [xAI](models/xai.md) | Grok Code Fast | 256 K | $0.20 | $1.50 | Coding-specialist |
| [DeepSeek](models/deepseek.md) | V3.1-Terminus Chat | 128 K | $0.56¹ | $1.68¹ | Open weights; ¹official API cache-miss rate |
| [Cohere](models/cohere.md) | Command R7B | 128 K | $0.0375 | $0.15 | Cheapest Cohere |
| [Meta](models/meta.md) | Llama 4 Scout | 10 M | ~$0.08 | ~$0.30 | Open weights; 10 M context |

---

## Reasoning Models

| Provider | Model | Context | Input | Output | Notes |
|---|---|---|---|---|---|
| [OpenAI](models/openai.md) | o3 | 200 K | $10.00 | $40.00 | Deep reasoning flagship |
| [OpenAI](models/openai.md) | o4-mini | 200 K | $1.10 | $4.40 | Best cost-efficient reasoning |
| [xAI](models/xai.md) | Grok 4 | 256 K | $3.00 | $15.00 | Always-on reasoning |
| [DeepSeek](models/deepseek.md) | V3.1-Terminus Reasoner | 128 K | $0.56¹ | $1.68¹ | Chain-of-thought; ¹official API cache-miss rate |

---

## Context Window Comparison

| Model | Context window |
|---|---|
| Llama 4 Scout | **10,000,000 tokens** |
| Grok 4.20 / Grok 4.1 Fast | **2,000,000 tokens** |
| Gemini 2.5 Pro | **2,000,000 tokens** |
| GPT-5.4, Claude Opus 4.6, Claude Sonnet 4.6 | **1,000,000 tokens** |
| GPT-4.1, GPT-4.1 Mini, GPT-4.1 Nano | **1,000,000 tokens** |
| Gemini 2.5 Flash, 2.0 Flash | **1,000,000 tokens** |
| Gemini 3.1 Pro Preview | **1,000,000 tokens** |
| Mistral Small 4 | **262,144 tokens** |
| Grok 4 | **256,000 tokens** |
| Command A | **256,000 tokens** |
| Claude Haiku 4.5, o3, o4-mini | **200,000 tokens** |
| GPT-4o, GPT-4o Mini | **128,000 tokens** |
| Mistral Large 3, Mistral Medium 3 | **131,072 tokens** |
| DeepSeek V3.2 Chat | **128,000 tokens** |

---

## Feature Matrix

| Feature | OpenAI | Anthropic | Google | Mistral | xAI | DeepSeek | Cohere |
|---|---|---|---|---|---|---|---|
| Vision/Multimodal | ✅ | ✅ | ✅ | ✅ (Small 4) | ✅ | ❌ | ❌ |
| Function calling / tools | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Prompt caching | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ❌ |
| Batch API (50% off) | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ |
| Streaming | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Fine-tuning | ✅ | ❌ | ✅ (2.0 Flash) | ❌ | ❌ | ❌ | ❌ |
| Web search (built-in) | ✅ ($10/1K) | ❌ | ✅ ($14–35/1K) | ❌ | ✅ ($2.5–5/1K) | ❌ | ❌ |
| Computer use | ✅ (GPT-5.4) | ✅ | ✅ (Computer Use Preview) | ❌ | ❌ | ❌ | ❌ |
| Open weights | ❌ | ❌ | ✅ (Gemma 4 – Apache 2.0) | ✅ (some) | ❌ | ✅ | ❌ |
| Free API tier | ✅ (trial) | ❌ | ✅ | ✅ (experiment) | ❌ | ✅ (5 M tokens) | ✅ (1K calls/mo) |

---

## Pricing Tiers Available

| Provider | Standard | Batch (50% off) | Cached input | Priority queue |
|---|---|---|---|---|
| OpenAI | ✅ | ✅ | ✅ (~10%) | ✅ (2× price) |
| Anthropic | ✅ | ✅ | ✅ (~10%) | ❌ |
| Google | ✅ | ✅ | ✅ (~10%) | ✅ (new) |
| Mistral | ✅ | ❌ | ❌ | ❌ |
| xAI | ✅ | ✅ (new) | ✅ | ✅ (Provisioned Throughput) |
| DeepSeek | ✅ | ❌ | ✅ (~5%) | ❌ |
| Cohere | ✅ | ❌ | ❌ | ❌ |

---

## Decision Guide

| Use case | Recommended model | Rationale |
|---|---|---|
| Best general reasoning | Gemini 3.1 Pro Preview | Highest GPQA (94.3%) |
| Computer use / desktop agents | GPT-5.4 | 75% OSWorld (above human baseline) |
| Coding agents (best) | Claude Opus 4.6 / GPT-5.4 | SWE-bench 74%+ / 57.7% |
| Long documents (>200K tokens) | Llama 4 Scout (10 M) or Gemini 2.5 Pro (2 M) | Largest context windows |
| Production chatbot (balanced) | Claude Sonnet 4.6 | Strong reasoning + cost |
| High-volume cheap tasks | Gemini 2.0 Flash-Lite ($0.075) or Mistral Nemo ($0.02) | Cheapest per-token |
| Cheapest open-weight option | Llama 4 Scout or DeepSeek V3.2 | Self-hostable |
| Enterprise RAG / retrieval | Cohere Command A | Built-in citation, Rerank/Embed tools |
| Real-time X/Twitter data | Grok 4.20 | Native X integration |
| Reasoning on a budget | o4-mini ($1.10/$4.40) or DeepSeek Reasoner ($0.56/$1.68 official API; cheaper via third-party hosts) | Cheap chain-of-thought |

---

## Action Items (As of 2026-04-12)

| Deadline | Action |
|---|---|
| **2026-04-20** 🚨 | Migrate `claude-3-haiku-20240307` → `claude-haiku-4-5-20251001` (Claude 3 Haiku retiring in **6 days** — 2026-04-20) |
| **2026-06-01** | Migrate `gemini-2.0-flash` / `gemini-2.0-flash-lite` to 2.5 equivalents |
| **2026-06-05** | GPT-5.2 Thinking removed from ChatGPT legacy picker |
| **2026-06-17** | Migrate `gemini-2.5-pro` → `gemini-3.1-pro-preview`, `gemini-2.5-flash` → `gemini-3-flash-preview` |
| **2026-07-22** | Migrate `gemini-2.5-flash-lite` → `gemini-3.1-flash-lite-preview` |
| **Late April 2026** | 🔥 Watch for **DeepSeek V4** launch — Founder Liang Wenfeng confirmed late April target (2026-04-10); Vision/Expert/Lite modes confirmed in grey test UI. 3 variants: V4 Lite, V4 Expert, V4 Vision |

---

*See provider pages for full details: [OpenAI](models/openai.md) · [Anthropic](models/anthropic.md) · [Google](models/google.md) · [Mistral](models/mistral.md) · [xAI](models/xai.md) · [DeepSeek](models/deepseek.md) · [Cohere](models/cohere.md) · [Meta](models/meta.md)*
