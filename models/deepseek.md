# DeepSeek Model Catalog

> **Source:** [DeepSeek API Docs](https://api-docs.deepseek.com/quick_start/pricing) · **Verified:** 2026-05-10

---

## Current Models

### DeepSeek V4 (Released 2026-04-24) 🆕 NEW

DeepSeek's latest generation. Two variants with 1M context, both open-weight. Both support OpenAI-compatible and Anthropic-compatible APIs. Both support thinking mode and non-thinking mode.

> ⚠️ **`deepseek-chat` and `deepseek-reasoner` will be retired on 2026-07-24 15:59 UTC.** They currently route to `deepseek-v4-flash` (non-thinking and thinking respectively). Migrate explicitly to V4 model IDs.

| Model | API name | Context | Max output | Input (cache miss) | Input (cache hit) | Output |
|---|---|---|---|---|---|---|
| V4 Flash | `deepseek-v4-flash` | 1,000,000 tokens | 384,000 tokens | **$0.14 / 1M** | $0.0028 / 1M | **$0.28 / 1M** |
| V4 Pro | `deepseek-v4-pro` | 1,000,000 tokens | 384,000 tokens | **$0.435 / 1M** ¹ | $0.003625 / 1M | **$0.87 / 1M** ¹ |

¹ **V4 Pro is offered at 75% discount until 2026-05-31 15:59 UTC.** List (post-discount) price is **$1.74 input / $3.48 output** per 1M. Verify at [official pricing page](https://api-docs.deepseek.com/quick_start/pricing) before large top-ups.

**Architecture:**
- **V4 Pro:** 1.6T total parameters / 49B active parameters — "performance rivaling the world's top closed-source models"
- **V4 Flash:** 284B total / 13B active parameters — fast, efficient, economical

**V4 Pro benchmarks:** Strong performance on AIME 2025, GPQA Diamond, SWE-bench, HumanEval; tech report on HuggingFace.

**Cache hit discount (from 2026-04-26):** Reduced to 1/50 of cache-miss input price (2% for Flash, 0.83% for Pro).

*Source: [DeepSeek V4 Preview Release](https://api-docs.deepseek.com/news/news260424) · [Official Pricing](https://api-docs.deepseek.com/quick_start/pricing) — verified 2026-05-10*

---

### DeepSeek V3.2 (Legacy — Now Routed to V4 Flash via `deepseek-chat`)

| Mode | API name | Context | Max output | Input (cache miss) | Input (cache hit) | Output |
|---|---|---|---|---|---|---|
| Chat (non-thinking) | `deepseek-chat` ⚠️ | 128,000 tokens | 8,000 tokens | **$0.14 / 1M** ² | $0.0028 / 1M ² | **$0.28 / 1M** ² |
| Reasoner (thinking) | `deepseek-reasoner` ⚠️ | 128,000 tokens | 64,000 tokens | **$0.14 / 1M** ² | $0.0028 / 1M ² | **$0.28 / 1M** ² |

² Since 2026-04-24, `deepseek-chat` routes to **V4 Flash non-thinking** and `deepseek-reasoner` routes to **V4 Flash thinking** mode. Billed at V4 Flash rates. These aliases retire **2026-07-24 15:59 UTC**.

**New users:** 5 million free tokens upon registration (no credit card required)

---



---

## Open Weights

All DeepSeek models are released under permissive open-source licenses:
- Self-host on your own infrastructure to eliminate per-token costs
- Popular options: Together AI, Fireworks AI, Groq, Nebius AI, Hyperbolic

**Best for:** Cost-sensitive production workloads, high-volume batch processing, teams who want to self-host, privacy-conscious deployments.

---

## Model Architecture Notes

- `deepseek-v4-flash` = DeepSeek-V4-Flash, non-thinking by default (switch via API param); fast, general-purpose
- `deepseek-v4-pro` = DeepSeek-V4-Pro, higher capability, thinking by default
- `deepseek-chat` = currently routes to V4-Flash non-thinking mode (legacy alias, retires 2026-07-24)
- `deepseek-reasoner` = currently routes to V4-Flash thinking mode (legacy alias, retires 2026-07-24)
- FIM (fill-in-middle) completion available on `deepseek-chat` (beta)
- JSON output supported on both modes; function calling on `deepseek-chat` only (if tools param sent to `deepseek-reasoner`, request routes to `deepseek-chat` internally)
- Context caching is automatic

---

## Historical Models (for reference)

| Model | Notes |
|---|---|
| DeepSeek V3.2 | Open weights on HuggingFace; available at $0.18–$0.28/M input via third-party providers (Fireworks, Together, etc.) |
| DeepSeek V3.1 Terminus | Released 2025-08-21; was briefly listed as the official endpoint model (2026-04-14); superseded by V4 |
| DeepSeek V3 (0324) | Released 2025-03-24; $0.20 input / $0.77 output on hosted providers |
| DeepSeek R1 | Original reasoning model; $0.55 input / $2.19 output; open weights |

---

## Pricing Context

DeepSeek V4 Flash via official API (cache miss, at current list price):
- V4 Flash ($0.14/$0.28) is ~21× cheaper than Claude Sonnet 4.6 ($3/$15) on input; ~54× cheaper on output
- ~18× cheaper than GPT-5.4 ($2.50/$15) on input; ~54× cheaper on output
- Cheaper than Gemini 2.5 Flash ($0.30/$2.50) on both input and output
- V4 Pro at promotional price ($0.435/$0.87 until 2026-05-31) is still 7× cheaper than Claude Sonnet 4.6 on input
- V4 Pro post-promotion list price ($1.74/$3.48) is ~60% cheaper than GPT-5.5 ($5/$30) on output
- **Open weights allow self-hosting** — third-party providers offer V4 Pro at ~$1.74/$3.48/M (DeepInfra, Fireworks, Together)
- For best pricing, compare official API vs. hosted providers (OpenRouter, Fireworks, Together, DeepInfra)

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
