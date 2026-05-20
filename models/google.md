# Google Gemini Model Catalog

> **Source:** [Gemini API Pricing](https://ai.google.dev/gemini-api/docs/pricing) · [Vertex AI Pricing](https://cloud.google.com/vertex-ai/generative-ai/pricing) · [Gemini Deprecations](https://ai.google.dev/gemini-api/docs/deprecations) · **Verified:** 2026-05-20

---

## Current Models (Gemini 3.5 — Latest Generation)

### Gemini 3.5 Flash (Released 2026-05-19 — Google I/O 2026) 🆕 NEW

Google's newest Gemini model, announced at Google I/O 2026. Optimized for **speed and complex agentic tasks**. Outperforms Gemini 3.1 Pro on key agentic/coding benchmarks at a fraction of the cost. Now the **default model** powering the Gemini app and AI Mode in Google Search globally.

> ⚠️ **Pricing correction (2026-05-20):** The pre-launch estimate of $1.50/$9.00 was incorrect. The official Google AI Developer API pricing page (last updated 2026-05-19 UTC) shows **$2.70 input / $16.20 output** per 1M tokens.

| Metric | Value |
|---|---|
| API name | `gemini-3.5-flash` |
| Context window | 1,000,000 tokens |
| Max output | 64,000 tokens |
| Input (standard) | **$2.70 / 1M** (text/image/video) |
| Output (standard, incl. thinking) | **$16.20 / 1M** |
| Context caching | $0.27 / 1M |
| Context caching (storage) | $1.00 / 1M tokens per hour |
| Free tier | ✅ (rate-limited) |

**Key facts:**
- Released at Google I/O 2026 keynote, **2026-05-19**; available immediately in Gemini API, Google AI Studio, Antigravity, and Vertex AI
- Outperforms Gemini 3.1 Pro on agentic/coding benchmarks: **Terminal-Bench 2.1: 76.2%**, GDPval-AA: 1656 Elo, MCP Atlas: 83.6%, CharXiv (multimodal): 84.2%
- ~4× faster output token generation compared to other frontier models
- Built for long-horizon agentic tasks, complex coding, and multi-step workflows
- Google Cloud positions it as "often at less than half the cost of comparable models" for agentic workloads
- Replaces Gemini 3.1 Pro as the recommended API model for production agentic use
- **Gemini 3.5 Pro**: Confirmed "coming next month" (June 2026) — currently in testing
- Grounding with Google Search: 5,000 prompts/month free (shared across Gemini 3 family), then **$14 / 1,000 queries**

*Source: [Google AI Developer API pricing](https://ai.google.dev/gemini-api/docs/pricing) · [Google Cloud Blog — Google I/O 2026](https://cloud.google.com/blog/products/ai-machine-learning/innovations-from-google-io-26-on-google-cloud) · [MacRumors I/O roundup](https://www.macrumors.com/2026/05/19/google-io-2026-roundup/) — verified 2026-05-20*

---

### Gemini Omni Flash (Released 2026-05-19 — Consumer) 🆕 NEW

Google's first "any-to-any" model: blends text, audio, image, and **video** inputs to produce video output. Designed for conversational video creation and editing. Announced at Google I/O 2026.

> ⚠️ **API not yet available.** As of 2026-05-20, Gemini Omni Flash is only accessible via the **Gemini app, Google Flow, and YouTube Shorts/Create** for AI Plus/Pro/Ultra subscribers. Developer and enterprise API access via Vertex AI is expected "in the coming weeks." No model ID, token pricing, or API endpoint has been announced yet. Do not include in production planning until the API ships.

**What's confirmed:**
- Produces dynamic video by combining text, audio, image, and video inputs
- Supports conversational editing (natural language edits on existing video)
- Rolling out to AI Plus ($7.99/mo), AI Pro ($19.99/mo), AI Ultra ($99.99/mo) subscribers

*Source: [VentureBeat — Gemini Omni enterprise breakdown](https://venturebeat.com/ai/google-unveils-gemini-omni-any-to-any-ai-model-what-enterprises-should-know) · [Google Cloud Blog](https://cloud.google.com/blog/products/ai-machine-learning/innovations-from-google-io-26-on-google-cloud) — 2026-05-19 · verified 2026-05-20*

---

## Previous Generation GA Models

### Gemini 2.5 Pro

Best reasoning model at GA. Large 2 M token context window.

| Metric | Value |
|---|---|
| API name | `gemini-2.5-pro` |
| Context window | 2,000,000 tokens |
| Input (≤200K) | **$1.25 / 1M** |
| Input (>200K) | $2.50 / 1M |
| Output (≤200K) | **$10.00 / 1M** |
| Output (>200K) | $15.00 / 1M |
| Cached input | $0.125 / 1M |
| Free tier | ✅ (rate-limited) |
| **Retirement date** | **2026-06-17** → migrate to `gemini-3-flash-preview` or `gemini-3.1-pro-preview` |

---

### Gemini 2.5 Flash 🏆 Best price-performance (GA)

| Metric | Value |
|---|---|
| API name | `gemini-2.5-flash` |
| Context window | 1,000,000 tokens |
| Input | **$0.30 / 1M** |
| Output | **$2.50 / 1M** |
| Cached input | $0.03 / 1M |
| Free tier | ✅ |
| **Retirement date** | **2026-06-17** → migrate to `gemini-3-flash-preview` |

---

### Gemini 2.5 Flash-Lite (GA)

| Metric | Value |
|---|---|
| API name | `gemini-2.5-flash-lite` |
| Context window | 1,000,000 tokens |
| Input | **$0.10 / 1M** |
| Output | **$0.40 / 1M** |
| Free tier | ✅ |
| **Retirement date** | **2026-07-22** |

---

### Gemini 2.0 Flash (GA – DEPRECATED)

> ⚠️ **Shutdown: 2026-06-01.** Migrate to `gemini-2.5-flash`.

| Input | Output | Cached input |
|---|---|---|
| $0.10 / 1M | $0.40 / 1M | $0.025 / 1M |

Audio input: $1.00/1M. Available on both Google AI Studio (paid) and Vertex AI.

---

### Gemini 2.0 Flash-Lite (GA – DEPRECATED)

> ⚠️ **Shutdown: 2026-06-01.** Migrate to `gemini-2.5-flash-lite`.

| Input | Output |
|---|---|
| $0.075 / 1M | $0.30 / 1M |

Cheapest billed model among all current-GA Gemini versions.

---

## Preview Models (Gemini 3.x generation)

> Preview models do not have GA stability guarantees. No shutdown date announced unless noted.

### Gemini 3.1 Pro Preview (Released 2026-02-19)

| Metric | Value |
|---|---|
| API name | `gemini-3.1-pro-preview` |
| Context window | 1,000,000 tokens |
| Input (≤200K) | **$2.00 / 1M** |
| Input (>200K) | $4.00 / 1M |
| Output (≤200K) | **$12.00 / 1M** |
| Output (>200K) | $18.00 / 1M |

Replaces `gemini-3-pro-preview` (retired 2026-03-09). Highest-capability Gemini model currently available.  
**GPQA Diamond:** 94.3% (highest of all major providers as of March 2026).

---

### Gemini 3.1 Flash-Lite (GA — Released 2026-05-07) 🆕

GA release. Graduated from preview on May 7, 2026.

| Metric | Value |
|---|---|
| API name | `gemini-3.1-flash-lite` |
| Input | **$0.25 / 1M** |
| Output | **$1.50 / 1M** |
| Free tier | ✅ (rate-limited) |

**Best for:** High-volume agentic tasks, translation, simple data processing — cheapest Gemini 3.x model at GA.

*Source: [Google Gemini API changelog](https://ai.google.dev/gemini-api/docs/changelog) — verified 2026-05-12*

---

### Gemini 3.1 Flash-Lite Preview (Released 2026-03-03)

> ⚠️ **DEPRECATED 2026-05-11. Shutdown: 2026-05-25.** Migrate to `gemini-3.1-flash-lite` (GA, same pricing, same model).

| Input | Output |
|---|---|
| $0.25 / 1M | $1.50 / 1M |

---

### Gemini 3 Flash Preview (Released 2025-12-17)

| Input | Output |
|---|---|
| $0.50 / 1M | $3.00 / 1M |

---

## Gemma 4 (Open Weights — Released 2026-04-02)

Google's latest open-weight model family. Released under **Apache 2.0** (first Gemma generation with fully permissive license). Built on Gemini 3 research.

| Model | Parameters | Context | License | Best for |
|---|---|---|---|---|
| Gemma 4 E2B | ~2B active | 128K | Apache 2.0 | Mobile / edge devices |
| Gemma 4 E4B | ~4B active | 128K | Apache 2.0 | Smartphones, NPUs |
| Gemma 4 26B MoE (A4B) | 26B total / 3.8B active | 256K | Apache 2.0 | Single GPU (H100), fast inference |
| Gemma 4 31B Dense | 31B | 256K | Apache 2.0 | Workstation, maximum quality |

**Key facts:**
- 31B: #3 on Arena AI open text leaderboard (April 2026); 26B MoE: #6
- All variants support text, image, video, audio inputs
- E2B/E4B also process audio input (speech recognition)
- 140+ languages
- Available via HuggingFace, Kaggle, Ollama, Google AI Studio
- License change from custom Gemma license to Apache 2.0 is significant for enterprise compliance

*Source: [Google Blog](https://blog.google/innovation-and-ai/technology/developers-tools/gemma-4/) — 2026-04-02*

---

## Free Tier

Google AI Studio usage is **completely free** in all regions — no API billing for Studio use.

**Changes effective 2026-04-01:**
- ⚠️ **Pro models now paid-only** on API free tier (previously free-tier accessible). Free-tier developers must use Flash or Flash-Lite models.
- Mandatory spending caps enforced by tier: Tier 1 ($250/month), Tier 2 ($2,000/month), Tier 3 ($20K–$100K+/month)
- New accounts may be required to use prepaid billing (buy credits upfront)
- Existing accounts not yet affected by prepaid requirement

API free tier provides rate-limited access to **Flash and Flash-Lite models only** (no credit card required for free tier).

Paid API pricing starts when you exceed free-tier rate limits.

---

## New Inference Tiers (April 2026)

Google updated its API to offer **Standard, Flex, Priority, Batch, and Caching** tiers (announced 2026-04-02):
- **Batch:** 50% off Standard pricing (async, for non-real-time workloads)
- **Flex / Priority:** TBD differentiated latency/throughput SLAs

---

## Tools Pricing

| Tool | Free tier | Paid |
|---|---|---|
| Google Search grounding (Gemini 3) | 5,000 RPD | $14 / 1,000 queries |
| Google Search grounding (Gemini 2.5 Flash/Pro) | 1,500 RPD | $35 / 1,000 queries |
| Google Maps grounding | 5,000 queries/month | $14 / 1,000 queries |
| Code execution | Free | Free |
| URL context | Free | Input tokens at model rate |
| File search (embeddings) | Free | $0.15 / 1M tokens |

---

## Vertex AI

Enterprise pricing matches Google AI Studio paid tiers for most models. Vertex AI adds:
- Data residency and CMEK
- Private VPC endpoints
- SLA guarantees
- Unified GCP billing
- Volume-based discounts (negotiated)

---

## ⚠️ Interactions API Breaking Changes (May–June 2026)

Google is changing the Interactions API (v1beta) request/response schema. Action required before **May 26, 2026**.

| Change | Detail |
|---|---|
| `outputs` array → `steps` | Each action (user_input, thought, tool_call, model_output, etc.) becomes its own `step` object |
| `response_format` consolidated | Image, audio, JSON schema all unified under a single `response_format` field |
| Legacy schema default removed | **May 26, 2026**: new schema becomes default |
| Legacy schema removed entirely | **June 8, 2026**: old schema no longer accepted |

**How to migrate:**
- **SDK users:** Upgrade to Python ≥2.0.0 or JavaScript ≥2.0.0 — SDKs automatically opt in to the new schema
- **Raw HTTP users:** Add header `Api-Revision: 2026-05-26` to opt in before the deadline
- Full migration guide: [Interactions API breaking changes (May 2026)](https://ai.google.dev/gemini-api/docs/interactions-breaking-changes-may-2026)

*Source: [Google Gemini API changelog](https://ai.google.dev/gemini-api/docs/changelog) — 2026-05-06 · verified 2026-05-12*

---

## Google AI Subscription Tiers (Updated 2026-05-20)

Announced at Google I/O 2026: Google dropped the top-tier Ultra price and added a mid-tier.

| Plan | Price | Key models |
|---|---|---|
| Free | $0 | Gemini 2.5 Flash (limited), Flash-Lite |
| AI Plus | $7.99/month | Gemini 2.5 Flash, limited Gemini 3 |
| AI Pro | $19.99/month | Gemini 3 Flash, Deep Research, Veo 3.1, Jules |
| AI Ultra (new) | **$99.99/month** 🆕 | 5× Pro limits, Gemini 3.5 Flash, priority Antigravity, 20 TB storage, YouTube Premium bundled, Gemini Spark (beta) |
| AI Ultra (premium) | **$199.99/month** ↓ (was $249.99) | All Ultra features + highest limits |

*Source: [Google I/O 2026 keynote](https://io.google/2026/) · [CNET live blog](https://www.cnet.com/news-live/google-io-2026-live-news-updates/) — 2026-05-19*

---

## Deprecation Summary

| Model | Shutdown date | Recommended migration |
|---|---|---|
| `gemini-3.1-flash-lite-preview` | **2026-05-25** 🚨 | `gemini-3.1-flash-lite` (GA, same pricing) |
| `gemini-2.0-flash` | **2026-06-01** | `gemini-2.5-flash` |
| `gemini-2.0-flash-lite` | **2026-06-01** | `gemini-2.5-flash-lite` |
| `gemini-2.5-pro` | **2026-06-17** | `gemini-3.1-pro-preview` or `gemini-3.5-flash` |
| `gemini-2.5-flash` | **2026-06-17** | `gemini-3-flash-preview` or `gemini-3.5-flash` |
| `gemini-2.5-flash-lite` | **2026-07-22** | `gemini-3.1-flash-lite` (now GA) |
| `gemini-3-pro-preview` | Retired 2026-03-09 | `gemini-3.1-pro-preview` |

*Full table: [deprecated.md](../deprecated.md)*

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md) · [deprecated.md](../deprecated.md)*
