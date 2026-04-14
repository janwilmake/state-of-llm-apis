# DeepSeek Model Catalog

> **Source:** [DeepSeek API Docs](https://api-docs.deepseek.com/quick_start/pricing) · **Verified:** 2026-04-14

---

## Current Models

### DeepSeek V3.1-Terminus — Current Hosted API Model

The official DeepSeek hosted API (`api.deepseek.com`) now runs **DeepSeek-V3.1-Terminus** behind both endpoint names. Note: the public platform (chat.deepseek.com) may run a different version.

| Mode | API name | Context | Max output | Input (cache miss) | Input (cache hit) | Output |
|---|---|---|---|---|---|---|
| Chat (non-thinking) | `deepseek-chat` | 128,000 tokens | 8,000 tokens | **$0.56 / 1M** | $0.07 / 1M | **$1.68 / 1M** |
| Reasoner (thinking) | `deepseek-reasoner` | 128,000 tokens | 64,000 tokens | **$0.56 / 1M** | $0.07 / 1M | **$1.68 / 1M** |

> **⚠️ Pricing update 2026-04-14:** The official DeepSeek API docs now list the model behind both endpoints as **DeepSeek-V3.1-Terminus**, priced at **$0.56 input / $1.68 output** per 1M tokens (cache miss), with cache-hit input at $0.07/1M. This is significantly higher than third-party aggregator rates ($0.14–$0.28) which reflect older pricing or reseller discounts. Always verify at the [official pricing page](https://api-docs.deepseek.com/quick_start/pricing).
>
> **Note on model naming:** There is a discrepancy between official API docs (which say `deepseek-chat` = V3.1-Terminus) and multiple third-party sources that still refer to "V3.2" being behind these endpoints. DeepSeek's versioning and naming has been inconsistent. The API docs are authoritative for billing purposes.

**Cache hit discount:** ~87% off input price for repeated context (cache read at $0.07 / 1M)

**New users:** 5 million free tokens upon registration (no credit card required)

---

## DeepSeek V4 — Imminent (Not Yet Released)

> ⚠️ **Not yet released as of 2026-04-14.** V4-Lite appeared on DeepSeek infrastructure from ~2026-03-09. Full launch targeted for late April 2026 per DeepSeek founder Liang Wenfeng.

**What we know (from Reuters/The Information/TechNode, verified 2026-04-03 to 2026-04-14):**
- Expected launch: **late April 2026** per DeepSeek founder Liang Wenfeng (internal comms via ITHome, 2026-04-10); has missed at least two earlier targets (mid-February, early April)
- Architecture: ~1 trillion total parameters, ~32–37B active per token (MoE)
- Context window: **1 million tokens** (widely reported, not officially confirmed)
- Modalities: Confirmed multimodal — **Vision** (image) mode confirmed in grey test interface (TechNode, 2026-04-08)
- Hardware: First frontier model trained on **Huawei Ascend chips** (no NVIDIA/AMD early access given)
- Variants: **3 versions visible in grey test UI** — V4 Lite (Fast), V4 Expert (flagship), V4 Vision
- V4-Lite (also called "Sealion-lite", ~200B parameters) has been on API infrastructure since ~2026-03-09
- Pricing: Not announced; expected to follow DeepSeek's aggressive pricing model

**Impact:** V4 arriving on Huawei chips at frontier performance would validate China's domestic AI hardware stack and likely trigger another market pricing shockwave.

*Source: Reuters (2026-04-03), ITHome via Reddit (2026-04-10), TechNode (2026-04-08), Gizchina (2026-04-11)*

---

## Open Weights

All DeepSeek models are released under permissive open-source licenses:
- Self-host on your own infrastructure to eliminate per-token costs
- Popular options: Together AI, Fireworks AI, Groq, Nebius AI, Hyperbolic

**Best for:** Cost-sensitive production workloads, high-volume batch processing, teams who want to self-host, privacy-conscious deployments.

---

## Model Architecture Notes

- `deepseek-chat` = V3.1-Terminus non-thinking mode (per official API docs as of 2026-04-14): fast, general-purpose
- `deepseek-reasoner` = V3.1-Terminus thinking mode: chain-of-thought reasoning for math/code; outputs thinking tokens separately
- FIM (fill-in-middle) completion available on `deepseek-chat` (beta)
- JSON output supported on both modes; function calling on `deepseek-chat` only (if tools param sent to `deepseek-reasoner`, request routes to `deepseek-chat` internally)
- Context caching is automatic

---

## Historical Models (for reference)

| Model | Notes |
|---|---|
| DeepSeek V3.2 | Open weights on HuggingFace; available via third-party providers at $0.18–$0.28/M input; currently **not** behind the official DeepSeek API per docs (which show V3.1-Terminus) |
| DeepSeek V3.1 Terminus | Released 2025-08-21; currently the model behind official `deepseek-chat` / `deepseek-reasoner` API endpoints |
| DeepSeek V3 (0324) | Released 2025-03-24; $0.20 input / $0.77 output on hosted providers |
| DeepSeek R1 | Original reasoning model; $0.55 input / $2.19 output; open weights |

---

## Pricing Context

DeepSeek via the official hosted API (V3.1-Terminus, cache miss):
- Chat mode ($0.56/$1.68) is ~5× cheaper than Claude Sonnet 4.6 ($3/$15) on input; ~9× cheaper on output
- ~4.5× cheaper than GPT-5.4 ($2.50/$15) on input; ~9× cheaper on output
- More expensive than Gemini 2.5 Flash ($0.30/$2.50) on input; ~1.5× cheaper on output on cache miss
- With cache hits ($0.07 input), input cost is still very competitive (~43× cheaper than Claude Sonnet input)
- **Open weights allow self-hosting** — third-party providers (Fireworks AI, Together AI, etc.) offer V3.2 at $0.18–$0.28/M input, reflecting lower-cost inference outside the official API
- For best pricing on DeepSeek models, compare official API vs. hosted providers (OpenRouter, Fireworks, Together, Groq)

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
