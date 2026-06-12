# LLM API Comparison Matrix

> **Last updated:** 2026-06-12. Prices per 1M tokens (USD), standard tier unless noted.

---

## Flagship Models (Best-in-class)

| Provider | Model | Context | Input | Output | GPQA | SWE-bench | Notes |
|---|---|---|---|---|---|---|---|
| [Anthropic](models/anthropic.md) | **Claude Fable 5** 🆕 | 1 M | $10.00 | $50.00 | — | **80.3%** (Pro) | NEW 2026-06-09; Mythos-class; always-on adaptive thinking; 30-day data retention req |
| [OpenAI](models/openai.md) | GPT-5.5 | 1 M | $5.00 | $30.00 | — | — | Latest OpenAI flagship; ~40% fewer output tokens on agentic tasks |
| [OpenAI](models/openai.md) | GPT-5.4 | 1 M | $2.50 | $15.00 | 92.8% | 57.7% | Native computer-use; tokens >272K billed at 2× |
| [OpenAI](models/openai.md) | GPT-5.4 Pro / GPT-5.5 Pro | 1 M | $30.00 | $180.00 | — | — | Max capability |
| [Anthropic](models/anthropic.md) | Claude Opus 4.8 | 1 M | $5.00 | $25.00 | — | 69.2% (SWE-bench Pro) | Released 2026-05-28; Dynamic Workflows; Fast Mode $10/$50 |
| [Google](models/google.md) | Gemini 3.1 Pro Preview | 1 M | $2.00 | $12.00 | 94.3% | 80.6% | Preview (no GA SLA) |
| [xAI](models/xai.md) | Grok 4.3 🆕 | 1 M | $1.25 | $2.50 | — | — | xAI flagship; released 2026-04-30; 1M context; voice API |
| [xAI](models/xai.md) | Grok 4.20 | 2 M | $1.25 | $2.50 | ~88% | 75% | X data integration; matched Grok 4.3 price |
| [xAI](models/xai.md) | Grok 4 | 256 K | $3.00 | $15.00 | 87.7% | — | Always-on reasoning |

**Verdict:** **Claude Fable 5** is the new overall capability leader (80.3% SWE-bench Pro, released 2026-06-09) at $10/$50 — 2× the price of Opus 4.8. For best reasoning accuracy, Gemini 3.1 Pro (94.3% GPQA) remains top. For computer-use, GPT-5.4 is unmatched. For cost-efficiency at frontier level, Grok 4.3 ($1.25/$2.50) leads. GPT-5.5 is the most capable OpenAI model but 2× the price of GPT-5.4. Gemini 3.5 Flash ($1.50/$9.00 Standard) released 2026-05-19 outperforms Gemini 3.1 Pro on coding/agents at ~4× faster output speed and ~25% lower cost.

---

## Mid-Range Models (Best price-performance)

| Provider | Model | Context | Input | Output | Notes |
|---|---|---|---|---|---|
| [OpenAI](models/openai.md) | GPT-5.3-Codex | 400 K | $1.75 | $14.00 | GPQA 91.5%; agentic coding specialist; powers Codex tasks |
| [OpenAI](models/openai.md) | GPT-5.4 Mini | 400 K | $0.75 | $4.50 | 54.38% SWE-bench; 6× cheaper than flagship |
| [OpenAI](models/openai.md) | GPT-4.1 | 1 M | $2.00 | $8.00 | 1 M context at lower price |
| [Anthropic](models/anthropic.md) | Claude Sonnet 4.6 | 1 M | $3.00 | $15.00 | Best production Claude model |
| [Google](models/google.md) | Gemini 2.5 Pro | 2 M | $1.25 | $10.00 | ⚠️ Retiring 2026-06-17 |
| [Google](models/google.md) | Gemini 3.5 Flash | 1 M | $1.50 | $9.00 | ~4× token gen speed; strongest agentic/coding; default Gemini model; released 2026-05-19 (Priority: $2.70/$16.20) |
| [Google](models/google.md) | Gemini 3 Flash Preview | 1 M | $0.50 | $3.00 | Preview; fast |
| [Mistral](models/mistral.md) | Mistral Medium 3.5 🆕 | 256 K | $1.50 | $7.50 | 128B dense; vision + coding + agents; GA 2026-05-05 |
| [Mistral](models/mistral.md) | Mistral Medium 3 | 131 K | $0.40 | $2.00 | Good for coding/RAG |
| [xAI](models/xai.md) | Grok Build 0.1 🆕 | 256 K | $1.00 | $2.00 | NEW 2026-05-28; agentic coding specialist; powers Grok Build CLI |
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
| [DeepSeek](models/deepseek.md) | V4 Pro | 1 M | $0.435 | $0.87 | Permanent price (75% cut made permanent 2026-05-24) |
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
| Claude Fable 5 🆕 | **1,000,000 tokens** |
| Grok 4.20 / Grok 4.1 Fast | **2,000,000 tokens** |
| Gemini 2.5 Pro | **2,000,000 tokens** |
| GPT-5.4 Mini | **400,000 tokens** |
| GPT-5.4, Claude Opus 4.6, Claude Sonnet 4.6 | **1,000,000 tokens** |
| GPT-4.1, GPT-4.1 Mini, GPT-4.1 Nano | **1,000,000 tokens** |
| Gemini 3.5 Flash 🆕 | **1,000,000 tokens** |
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
| **Best overall capability** | **Claude Fable 5** 🆕 | 80.3% SWE-bench Pro (best available); Mythos-class; $10/$50 |
| Best general reasoning | Gemini 3.1 Pro Preview | Highest GPQA (94.3%) |
| Fastest token generation | Gemini 3.5 Flash | ~4× token gen speed vs other frontier models; $1.50/$9.00 Standard |
| Computer use / desktop agents | GPT-5.4 | 75% OSWorld (above human baseline) |
| Coding agents (best, frontier) | Claude Fable 5 / Claude Opus 4.8 | SWE-bench Pro 80.3% (Fable 5); 69.2% (Opus 4.8) — best on market |
| Coding agents (cost-efficient) | GPT-5.3-Codex / Grok Build 0.1 | GPQA 91.5% (Codex); $1.00/$2.00 (Grok Build 0.1) |
| Long documents (>200K tokens) | Llama 4 Scout (10 M) or Gemini 3.1 Pro Preview (1 M) | Largest context windows |
| Production chatbot (balanced) | Claude Sonnet 4.6 | Strong reasoning + cost ($3/$15) |
| High-volume cheap tasks | Gemini 3.1 Flash-Lite ($0.25/$1.50) or Mistral Nemo ($0.02/$0.06) | Cheapest current options |
| Cheapest frontier (open weight) | DeepSeek V4 Flash ($0.14/$0.28) | Open weights, 1M context, extremely cheap |
| Enterprise RAG / retrieval | Cohere Command A | Built-in citation, Rerank/Embed tools |
| Real-time X/Twitter data | Grok 4.3 + X Search | Native X integration |
| Reasoning on a budget | o4-mini ($1.10/$4.40) or DeepSeek V4 Flash (thinking mode, $0.14/$0.28) | Cheap chain-of-thought |

---

## Action Items (As of 2026-06-10)

| Deadline | Action |
|---|---|
| **2026-05-12** ❌ PASSED | ❌ `dall-e-2` and `dall-e-3` **retired 2026-05-12** — calls now failing; migrate to `gpt-image-2` |
| **2026-05-15** ❌ PASSED | xAI `grok-4-fast-reasoning`, `grok-4-fast-non-reasoning`, `grok-4.1-fast`, `grok-4-0709`, `grok-code-fast-1`, `grok-3`, `grok-imagine-image-pro` **retired 2026-05-15 at 12pm PT** — slugs now **redirect silently to `grok-4.3`** (not errors). If you haven't updated your `model` field, you are being billed at 6× your old Fast model rates. Fix immediately. |
| **2026-05-25** ❌ PASSED | `gemini-3.1-flash-lite-preview` — deprecated and shut down; use `gemini-3.1-flash-lite` (GA, same pricing) |
| **2026-06-01** ❌ PASSED | `gemini-2.0-flash` and `gemini-2.0-flash-lite` — shut down; migrate to `gemini-2.5-flash` / `gemini-2.5-flash-lite` |
| **2026-06-05** ❌ PASSED | GPT-5.2 Thinking removed from ChatGPT legacy picker |
| **2026-06-08** ❌ PASSED | Gemini Interactions API legacy schema removed entirely |
| **2026-06-09** ✅ DONE | 🆕 **Claude Fable 5** launched — `claude-fable-5`, $10/$50 per 1M, 1M context, SWE-bench Pro 80.3%. Now the best-in-class coding/reasoning model. Subscription users: free access through June 22, then usage credits required. See [Anthropic](models/anthropic.md). |
| **2026-06-09** ✅ DONE | 🆕 **xAI Grok Imagine 1.5 Preview** — `grok-imagine-video-1.5-preview` image-to-video model, up to 720p |
| **2026-06-15** | 🚨 **5 DAYS** — Migrate `claude-sonnet-4-20250514` → `claude-sonnet-4-6` and `claude-opus-4-20250514` → `claude-opus-4-7` (hard shutdown June 15) |
| **2026-06-15** | 🚨 **5 DAYS** — **Anthropic Agent SDK billing split takes effect** — autonomous `claude -p`/SDK/GitHub Actions usage moves to per-API-rate credit pool ($20/$100/$200 for Pro/Max5x/Max20x). Review your workflows. See [anthropic.md](models/anthropic.md). |
| **2026-06-17** | Migrate `gemini-2.5-pro` → `gemini-3.1-pro-preview` or `gemini-3.5-flash`; `gemini-2.5-flash` → `gemini-3-flash-preview` or `gemini-3.5-flash` |
| **2026-06-22** | Claude Fable 5 free access ends for subscription plan users — usage credits required |
| **2026-06-30** | Migrate Mistral `mistral-moderation-2411` → `mistral-moderation-2` |
| **2026-07-22** | Migrate `gemini-2.5-flash-lite` → `gemini-3.1-flash-lite` (now GA) |
| **2026-07-24** | ⚠️ Migrate DeepSeek `deepseek-chat` / `deepseek-reasoner` aliases → `deepseek-v4-flash` or `deepseek-v4-pro` (**hard cutoff — returns errors after this date, no redirect**) |
| **2026-07-31** | Migrate `mistral-small-2506`, `magistral-small-2509` → `mistral-small-2603` (Mistral Small 4) |

---

*See provider pages for full details: [OpenAI](models/openai.md) · [Anthropic](models/anthropic.md) · [Google](models/google.md) · [Mistral](models/mistral.md) · [xAI](models/xai.md) · [DeepSeek](models/deepseek.md) · [Cohere](models/cohere.md) · [Meta](models/meta.md)*
