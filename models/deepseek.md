# DeepSeek Model Catalog

> **Source:** [DeepSeek API Docs](https://api-docs.deepseek.com/quick_start/pricing) · **Verified:** 2026-04-13

---

## Current Models

### DeepSeek V3.2 — Current (Released 2025-12-01)

Unified model that handles both chat and reasoning at the same price. Replaces both V3 and R1 in the hosted API.

| Mode | API name | Context | Max output | Input (cache miss) | Input (cache hit) | Output |
|---|---|---|---|---|---|---|
| Chat (non-thinking) | `deepseek-chat` | 128,000 tokens | 8,000 tokens | **$0.28 / 1M** | $0.028 / 1M | **$0.42 / 1M** |
| Reasoner (thinking) | `deepseek-reasoner` | 128,000 tokens | 64,000 tokens | **$0.28 / 1M** | $0.028 / 1M | **$0.42 / 1M** |

> **Pricing update 2026-04-13:** Both `deepseek-chat` and `deepseek-reasoner` are now priced identically at **$0.28 input / $0.42 output** per 1M tokens (cache miss), with a 90% cache discount. The previous file listed differing rates ($0.27/$1.10 chat; $0.55/$2.19 reasoner) — those were inaccurate. The official DeepSeek API docs confirm the current unified rates. Always check the [official pricing page](https://api-docs.deepseek.com/quick_start/pricing) for current rates.

**Cache hit discount:** ~90% off input price for repeated context (cache read at $0.028–$0.14 / 1M)

**New users:** 5 million free tokens upon registration (no credit card required)

---

## DeepSeek V4 — Imminent (Not Yet Released)

> ⚠️ **Not yet released as of 2026-04-12.** V4-Lite is in limited grey testing on some DeepSeek infrastructure nodes (early April 2026), suggesting full launch is close.

**What we know (from Reuters/The Information, verified 2026-04-03 to 2026-04-12):**
- Expected launch: **late April 2026** (missed at least two earlier targets)
- Architecture: ~1 trillion total parameters, ~32–37B active per token (MoE)
- Context window: **1 million tokens** (widely reported, not officially confirmed)
- Modalities: Multimodal — text, images, video
- Hardware: First frontier model trained on **Huawei Ascend chips** (no NVIDIA/AMD early access given)
- Variants: Three V4 variants in development, each optimized for different capabilities
- Pricing: Not announced

**Impact:** If V4 delivers frontier-class performance at DeepSeek's typical aggressive pricing, it will significantly pressure the market again (similar to V3/R1's impact in January 2025).

*Source: Reuters (2026-04-03), Taipei Times (2026-04-11), Gizchina (2026-04-11)*

---

## Open Weights

All DeepSeek models are released under permissive open-source licenses:
- Self-host on your own infrastructure to eliminate per-token costs
- Popular options: Together AI, Fireworks AI, Groq, Nebius AI, Hyperbolic

**Best for:** Cost-sensitive production workloads, high-volume batch processing, teams who want to self-host, privacy-conscious deployments.

---

## Model Architecture Notes

- `deepseek-chat` = V3.2 non-thinking mode: fast, general-purpose
- `deepseek-reasoner` = V3.2 thinking mode: chain-of-thought reasoning for math/code; outputs thinking tokens separately
- FIM (fill-in-middle) completion available on `deepseek-chat` (beta)
- JSON output and tool calls supported on both modes
- Context caching is automatic

---

## Historical Models (for reference)

| Model | Notes |
|---|---|
| DeepSeek V3 (0324) | Released 2025-03-24; $0.20 input / $0.77 output on hosted providers |
| DeepSeek R1 | Original reasoning model; $0.55 input / $2.19 output; open weights |
| DeepSeek V3.1 Terminus | Released 2025-08-21; stronger than V3.0324 |

---

## Pricing Context

DeepSeek V3.2 remains one of the most cost-competitive hosted models available:
- Chat mode (~$0.28/$0.42) is ~10× cheaper than Claude Sonnet 4.6 ($3/$15) on input; ~35× cheaper on output
- ~9× cheaper than GPT-5.4 ($2.50/$15) on input; ~36× cheaper on output
- Slightly cheaper than Gemini 2.5 Flash ($0.30/$2.50) on input; ~6× cheaper on output
- Open weights allow self-hosting to eliminate API costs entirely

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
