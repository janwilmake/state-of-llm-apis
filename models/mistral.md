# Mistral AI Model Catalog

> **Source:** [Mistral API Pricing](https://mistral.ai/pricing) · [OpenRouter](https://openrouter.ai/mistralai/mistral-small-2603) · **Verified:** 2026-04-10

---

## Current Models

### Mistral Large 3

| Metric | Value |
|---|---|
| API name | `mistral-large-latest` |
| Context window | 131,072 tokens |
| Input | **$0.50 / 1M** |
| Output | **$2.00 / 1M** |
| Speed | ~44 tok/s |

**Best for:** Complex reasoning, instruction-following, multilingual tasks requiring large-model capability at low cost.  
> Note: Mistral Large 3 is a significant price reduction from Mistral Large 2411 (which was $2.00/$6.00).

---

### Mistral Small 4 (Released 2026-03-16)

A major update that unifies Magistral (reasoning), Pixtral (vision), and Devstral (coding) into one model.

| Metric | Value |
|---|---|
| API name | `mistral-small-2603` |
| Context window | 262,144 tokens |
| Input | **$0.15 / 1M** |
| Output | **$0.60 / 1M** |
| Weights | Open — [HuggingFace](https://huggingface.co/mistralai/Mistral-Small-4-119B-2603) |

**Best for:** Multimodal tasks, coding, reasoning on a budget. Capable of vision, tools, and complex analysis in a single model.

---

### Mistral Medium 3 (Released 2025-05-07)

| Metric | Value |
|---|---|
| API name | `mistral-medium-3` |
| Context window | 131,072 tokens |
| Input | **$0.40 / 1M** |
| Output | **$2.00 / 1M** |
| Speed | ~56 tok/s |

**Best for:** Coding, retrieval-augmented generation, agentic workflows at moderate cost.

---

### Devstral 2

Coding-specialist model optimized for agentic software development.

| Context | Input | Output |
|---|---|---|
| 128,000 tokens | **$0.40 / 1M** | **$2.00 / 1M** |

---

### Mistral Nemo

Ultra-cheap 12B model for simple, high-volume tasks.

| Context | Input | Output |
|---|---|---|
| 128,000 tokens | **$0.02 / 1M** | **$0.06 / 1M** |

Cheapest Mistral model. Good for classification, extraction, simple summaries.

---

### Codestral

Code completion model with FIM (fill-in-middle) support.

| Context | Pricing |
|---|---|
| 32,000 tokens | Varies (check [mistral.ai/pricing](https://mistral.ai/pricing)) |

---

### Mistral Large 2411 (Legacy)

| Input | Output |
|---|---|
| $2.00 / 1M | $6.00 / 1M |

Older Mistral Large version. Largely superseded by Mistral Large 3 at a quarter of the price.

---

## New: Voxtral TTS (Released 2026-03-26)

Open source text-to-speech model for enterprise voice agents.

- Supports 9 languages: English, French, German, Spanish, Dutch, Portuguese, Italian, Hindi, Arabic
- Optimized for edge devices (smartwatch, smartphone, laptop)
- Competing with ElevenLabs, Deepgram, OpenAI TTS
- Open source — self-hostable
- API pricing: TBD on la Plateforme

---

## Le Chat Subscription Plans

| Plan | Price | Notes |
|---|---|---|
| Free | $0 | ~25 messages/day on mid-tier models |
| Pro | **$14.99/month** | ~150 messages/day, all models, Mistral Vibe coding, 15 GB storage |
| Student | **$7.04/month** | Same as Pro, requires .edu email |
| Team | **$24.99/user/month** | 30 GB storage/user, domain verification, data export |
| Enterprise | Custom | SAML SSO, audit logs, white-label, admin API |

Cheapest premium AI chat subscription among major providers (vs. $20 for ChatGPT Plus or Claude Pro).

---

## API Free Tier

"Experiment" tier: rate-limited access for testing and prototyping. Add a payment method for production workloads.

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
