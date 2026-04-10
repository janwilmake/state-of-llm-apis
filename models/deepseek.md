# DeepSeek Model Catalog

> **Source:** [DeepSeek API Docs](https://api-docs.deepseek.com/quick_start/pricing) · **Verified:** 2026-04-10

---

## Current Models

### DeepSeek V3.2 — Current (Released 2025-12-01)

Unified model that handles both chat and reasoning at the same price. Replaces both V3 and R1 in the hosted API.

| Mode | API name | Context | Max output | Input (cache miss) | Input (cache hit) | Output |
|---|---|---|---|---|---|---|
| Chat (non-thinking) | `deepseek-chat` | 128,000 tokens | 8,000 tokens | **$0.27 / 1M** | $0.028 / 1M | **$1.10 / 1M** |
| Reasoner (thinking) | `deepseek-reasoner` | 64,000 tokens | 8,000 tokens (+ 32K CoT) | **$0.55 / 1M** | $0.14 / 1M | **$2.19 / 1M** |

> Some third-party trackers report slightly different figures ($0.14/$0.28 for chat); the official DeepSeek API docs (verified 2026-04-10) show $0.27/$1.10 for chat and $0.55/$2.19 for reasoner. Always check the [official pricing page](https://api-docs.deepseek.com/quick_start/pricing) for current rates.

**Cache hit discount:** ~90% off input price for repeated context (cache read at $0.028–$0.14 / 1M)

**New users:** 5 million free tokens upon registration (no credit card required)

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
- Chat mode is ~15–20× cheaper than Claude Sonnet 4.6 ($3/$15)
- ~10× cheaper than GPT-5.4 ($2.50/$15)
- ~2× cheaper than Gemini 2.5 Flash ($0.30/$2.50) on output
- Open weights allow self-hosting to eliminate API costs entirely

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
