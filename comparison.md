# LLM API Comparison Matrix

> **Last updated:** 2026-05-18. Prices per 1M tokens (USD), standard tier unless noted.

---

## Flagship Models (Best-in-class)

| Provider | Model | Context | Input | Output | GPQA | SWE-bench | Notes |
|---|---|---|---|---|---|---|---|
| [OpenAI](models/openai.md) | GPT-5.5 🆕 | 1 M | $5.00 | $30.00 | — | — | Latest flagship; ~40% fewer output tokens on agentic tasks |
| [OpenAI](models/openai.md) | GPT-5.4 | 1 M | $2.50 | $15.00 | 92.8% | 57.7% | Native computer-use; tokens >272K billed at 2× |
| [OpenAI](models/openai.md) | GPT-5.4 Pro / GPT-5.5 Pro | 1 M | $30.00 | $180.00 | — | — | Max capability |
| [Anthropic](models/anthropic.md) | Claude Opus 4.7 | 1 M | $5.00 | $25.00 | — | 70% (CursorBench) | Released 2026-04-16; cyber safeguards; no long-context premium |
| [Google](models/google.md) | Gemini 3.1 Pro Preview | 1 M | $2.00 | $12.00 | 94.3% | 80.6% | Preview (no GA SLA) |
| [xAI](models/xai.md) | Grok 4.3 🆕 | 1 M | $1.25 | $2.50 | — | — | xAI flagship; released 2026-04-30; 1M context; voice API |
| [xAI](models/xai.md) | Grok 4.20 | 2 M | $1.25 | $2.50 | ~88% | 75% | X data integration; matched Grok 4.3 price |
| [xAI](models/xai.md) | Grok 4 | 256 K | $3.00 | $15.00 | 87.7% | — | Always-on reasoning |

**Verdict:** For best reasoning accuracy, Gemini 3.1 Pro (94.3% GPQA) is currently top. For computer-use, GPT-5.4 is unmatched. For cost-efficiency at frontier level, Grok 4.3 ($1.25/$2.50) leads among flagship models. GPT-5.5 is the most capable OpenAI model but 2× the price of GPT-5.4.

---

## Mid-Range Models (Best price-performance)

| Provider | Model | Context | Input | Output | Notes |
|---|---|---|---|---|---|
| [OpenAI](models/openai.md) | GPT-5.3-Codex | 400 K | $1.75 | $14.00 | GPQA 91.5%; agentic coding specialist; powers Codex tasks |
| [OpenAI](models/openai.md) | GPT-5.4 Mini | 400 K | $0.75 | $4.50 | 54.38% SWE-bench; 6× cheaper than flagship |
| [OpenAI](models/openai.md) | GPT-4.1 | 1 M | $2.00 | $8.00 | 1 M context at lower price |
| [Anthropic](models/anthropic.md) | Claude Sonnet 4.6 | 1 M | $3.00 | $15.00 | Best production Claude model |
| [Google](models/google.md) | Gemini 2.5 Pro | 2 M | $1.25 | $10.00 | ⚠️ Retiring 2026-06-17 |
| [Google](models/google.md) | Gemini 3 Flash Preview | 1 M | $0.50 | $3.00 | Preview; fast |
| [Mistral](models/mistral.md) | Mistral Medium 3.5 🆕 | 256 K | $1.50 | $7.50 | 128B dense; vision + coding + agents; GA 2026-05-05 |
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
| [xAI](models/xai.md) | Grok 4.3 | 1 M | $1.25 | $2.50 | ✅ Recommended xAI default; replaces all Fast/grok-4 models |
| [DeepSeek](models/deepseek.md) | V4 Flash | 1 M | $0.14 | $0.28 | Open weights; cheapest frontier-class option |
| [DeepSeek](models/deepseek.md) | V4 Pro | 1 M | $0.435¹ | $0.87¹ | ¹75% promo until 2026-05-31; list $1.74/$3.48 |
| [Cohere](models/cohere.md) | Command R7B | 128 K | $0.0375 | $0.15 | Cheapest Cohere |
| [Meta](models/meta.md) | Llama 4 Scout | 10 M | ~$0.08 | ~$0.30 | Open weights; 10 M context |

---

## Reasoning Models

| Provider | Model | Context | Input | Output | Notes |
|---|---|---|---|---|---|
| [OpenAI](models/openai.md) | o3 | 200 K | $10.00 | $40.00 | Deep reasoning flagship |
| [OpenAI](models/openai.md) | o4-mini | 200 K | $1.10 | $4.40 | Best cost-efficient reasoning |
| [xAI](models/xai.md) | Grok 4 | 256 K | $3.00 | $15.00 | Always-on reasoning |
| [DeepSeek](models/deepseek.md) | V4 Flash (thinking) | 1 M | $0.14 | $0.28 | Use `deepseek-v4-flash` with thinking mode enabled |

---

## Context Window Comparison

| Model | Context window |
|---|---|
| Llama 4 Scout | **10,000,000 tokens** |
| Grok 4.20 / Grok 4.1 Fast | **2,000,000 tokens** |
| Gemini 2.5 Pro | **2,000,000 tokens** |
| GPT-5.4 Mini | **400,000 tokens** |
| GPT-5.4, Claude Opus 4.6, Claude Sonnet 4.6 | **1,000,000 tokens** |
| GPT-4.1, GPT-4.1 Mini, GPT-4.1 Nano | **1,000,000 tokens** |
| Gemini 2.5 Flash, 2.0 Flash | **1,000,000 tokens** |
| Gemini 3.1 Pro Preview | **1,000,000 tokens** |
| Mistral Large 3, Mistral Small 4, Devstral 2 | **262,144 tokens** |
| Grok 4 | **256,000 tokens** |
| Command A | **256,000 tokens** |
| Claude Haiku 4.5, o3, o4-mini | **200,000 tokens** |
| GPT-4o, GPT-4o Mini | **128,000 tokens** |
| Mistral Medium 3 | **131,072 tokens** |
| DeepSeek V4 Flash / V4 Pro | **1,000,000 tokens** |

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
| Coding agents (best) | Claude Opus 4.7 / GPT-5.3-Codex / GPT-5.4 | CursorBench 70% (Opus 4.7); GPQA 91.5% (GPT-5.3-Codex); SWE-bench 57.7% (GPT-5.4) |
| Long documents (>200K tokens) | Llama 4 Scout (10 M) or Gemini 2.5 Pro (2 M) | Largest context windows |
| Production chatbot (balanced) | Claude Sonnet 4.6 | Strong reasoning + cost |
| High-volume cheap tasks | Gemini 2.0 Flash-Lite ($0.075) or Mistral Nemo ($0.02) | Cheapest per-token |
| Cheapest open-weight option | Llama 4 Scout or DeepSeek V3.2 | Self-hostable |
| Enterprise RAG / retrieval | Cohere Command A | Built-in citation, Rerank/Embed tools |
| Real-time X/Twitter data | Grok 4.20 | Native X integration |
| Reasoning on a budget | o4-mini ($1.10/$4.40) or DeepSeek Reasoner ($0.56/$1.68 official API; cheaper via third-party hosts) | Cheap chain-of-thought |

---

## Action Items (As of 2026-05-16)

| Deadline | Action |
|---|---|
| **2026-05-12** ❌ PASSED | ❌ `dall-e-2` and `dall-e-3` **retired 2026-05-12** — calls now failing; migrate to `gpt-image-2` |
| **2026-05-15** ❌ PASSED | xAI `grok-4-fast-reasoning`, `grok-4-fast-non-reasoning`, `grok-4.1-fast`, `grok-4-0709`, `grok-code-fast-1`, `grok-3`, `grok-imagine-image-pro` **retired 2026-05-15 at 12pm PT** — slugs now **redirect silently to `grok-4.3`** (not errors). If you haven't updated your `model` field, you are being billed at 6× your old Fast model rates. Fix immediately. |
| **2026-05-19** 🔭 | Google I/O 2026 **TOMORROW** (10am PT keynote) — major Gemini model announcement confirmed. New Gemini model (variously "Gemini 3.5" or "Gemini 4.0" per leaks) expected; described as "roughly GPT-5.5 class." Watch for new API model IDs, pricing, and context window details post-keynote. |
| **2026-05-25** ⚠️ | Migrate `gemini-3.1-flash-lite-preview` → `gemini-3.1-flash-lite` (GA, same pricing, same model) |
| **2026-05-26** ⚠️ | Opt-in to new Gemini Interactions API schema (Python ≥2.0.0 / JS ≥2.0.0 SDKs do this automatically; raw HTTP users add `Api-Revision: 2026-05-26` header) |
| **2026-05-31** ⚠️ | ⏱️ DeepSeek V4 Pro 75%-off promo ends — prices revert to **$1.74/$3.48 per 1M tokens** (from $0.435/$0.87) |
| **2026-05-31** ⚠️ | Migrate `mistral-large-2411` → `mistral-large-latest` (Mistral Large 3) |
| **2026-05-31** ⚠️ | Retire `pixtral-large-2411` → `mistral-large-latest`; `devstral-medium-2507` → `mistral-medium-3-5`; `voxtral-mini-2507` → `voxtral-mini-transcribe-2` |
| **2026-06-01** | Migrate `gemini-2.0-flash` / `gemini-2.0-flash-lite` to 2.5 equivalents |
| **2026-06-05** | GPT-5.2 Thinking removed from ChatGPT legacy picker |
| **2026-06-08** | Gemini Interactions API legacy schema removed entirely — complete migration before this date |
| **2026-06-15** | Migrate `claude-sonnet-4-20250514` → `claude-sonnet-4-6`, `claude-opus-4-20250514` → `claude-opus-4-7` (shutdown June 15) |
| **2026-06-15** | ⚠️ **Anthropic Agent SDK billing split takes effect** — autonomous `claude -p`/SDK/GitHub Actions usage moves to per-API-rate credit pool ($20/$100/$200 for Pro/Max5x/Max20x). Review your workflows. See [anthropic.md](models/anthropic.md). |
| **2026-06-17** | Migrate `gemini-2.5-pro` → `gemini-3.1-pro-preview`, `gemini-2.5-flash` → `gemini-3-flash-preview` |
| **2026-07-22** | Migrate `gemini-2.5-flash-lite` → `gemini-3.1-flash-lite` (now GA) |
| **2026-07-24** | Migrate DeepSeek `deepseek-chat` / `deepseek-reasoner` → `deepseek-v4-flash` or `deepseek-v4-pro` (hard cutoff — no silent redirect) |
| **2026-07-31** | Migrate `mistral-small-2506`, `magistral-small-2509` → `mistral-small-2603` (Mistral Small 4) |

---

*See provider pages for full details: [OpenAI](models/openai.md) · [Anthropic](models/anthropic.md) · [Google](models/google.md) · [Mistral](models/mistral.md) · [xAI](models/xai.md) · [DeepSeek](models/deepseek.md) · [Cohere](models/cohere.md) · [Meta](models/meta.md)*
