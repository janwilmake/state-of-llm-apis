# DeepSeek Model Catalog

> **Source:** [DeepSeek API Docs](https://api-docs.deepseek.com/quick_start/pricing) · **Verified:** 2026-04-18

---

## Current Models

### DeepSeek V3.2 — Current Hosted API Model

The official DeepSeek hosted API (`api.deepseek.com`) runs **DeepSeek-V3.2** behind both endpoint names, per official API docs (verified 2026-04-18).

| Mode | API name | Context | Max output | Input (cache miss) | Input (cache hit) | Output |
|---|---|---|---|---|---|---|
| Chat (non-thinking) | `deepseek-chat` | 128,000 tokens | 8,000 tokens | **$0.28 / 1M** | $0.028 / 1M | **$0.42 / 1M** |
| Reasoner (thinking) | `deepseek-reasoner` | 128,000 tokens | 64,000 tokens | **$0.28 / 1M** | $0.028 / 1M | **$0.42 / 1M** |

> **Pricing correction (2026-04-18):** Official API docs confirm both `deepseek-chat` and `deepseek-reasoner` run **DeepSeek-V3.2** at **$0.28 input / $0.42 output** per 1M tokens (cache miss), with cache-hit input at **$0.028/1M** (90% discount). This corrects the 2026-04-14 entry that logged V3.1-Terminus at $0.56/$1.68 — DeepSeek's official page now clearly shows V3.2 and standard pricing. Always verify at the [official pricing page](https://api-docs.deepseek.com/quick_start/pricing).

**Cache hit discount:** 90% off input price for repeated context (cache read at $0.028 / 1M)

**New users:** 5 million free tokens upon registration (no credit card required)

---

## DeepSeek V4 — Imminent (Not Yet Released)

> ⚠️ **Not yet released as of 2026-04-18.** V4-Lite appeared on DeepSeek infrastructure from ~2026-03-09. Full launch targeted for late April 2026 per DeepSeek founder Liang Wenfeng.

**What we know (from Reuters/The Information/TechNode, verified 2026-04-03 to 2026-04-18):**
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

- `deepseek-chat` = DeepSeek-V3.2 non-thinking mode (per official API docs as of 2026-04-18): fast, general-purpose
- `deepseek-reasoner` = DeepSeek-V3.2 thinking mode: chain-of-thought reasoning for math/code; outputs thinking tokens separately
- FIM (fill-in-middle) completion available on `deepseek-chat` (beta)
- JSON output supported on both modes; function calling on `deepseek-chat` only (if tools param sent to `deepseek-reasoner`, request routes to `deepseek-chat` internally)
- Context caching is automatic

---

## Historical Models (for reference)

| Model | Notes |
|---|---|
| DeepSeek V3.2 | Currently behind official API endpoints; also available as open weights on HuggingFace at $0.18–$0.28/M input via third-party providers |
| DeepSeek V3.1 Terminus | Released 2025-08-21; was briefly listed as the model behind official endpoints (2026-04-14); current docs show V3.2 |
| DeepSeek V3 (0324) | Released 2025-03-24; $0.20 input / $0.77 output on hosted providers |
| DeepSeek R1 | Original reasoning model; $0.55 input / $2.19 output; open weights |

---

## Pricing Context

DeepSeek via the official hosted API (V3.2, cache miss):
- Chat mode ($0.28/$0.42) is ~11× cheaper than Claude Sonnet 4.6 ($3/$15) on input; ~36× cheaper on output
- ~9× cheaper than GPT-5.4 ($2.50/$15) on input; ~36× cheaper on output
- Similar input cost to Gemini 2.5 Flash ($0.30) but ~6× cheaper output ($0.42 vs $2.50)
- With cache hits ($0.028 input), input cost is extremely competitive (~107× cheaper than Claude Sonnet input)
- **Open weights allow self-hosting** — third-party providers (Fireworks AI, Together AI, etc.) offer V3.2 at $0.18–$0.28/M input
- For best pricing on DeepSeek models, compare official API vs. hosted providers (OpenRouter, Fireworks, Together, Groq)

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
