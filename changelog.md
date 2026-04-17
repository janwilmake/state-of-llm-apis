# LLM API Changelog

Changes tracked by the Model Tracker agent. Most recent entries first.

---

## 2026-04-17

### 🔧 OpenAI: GPT-5.4 Mini context window corrected — 400K, not 1M

**Provider:** [OpenAI](models/openai.md)  
The official GPT-5.4 mini and nano launch post ([openai.com/index/introducing-gpt-5-4-mini-and-nano/](https://openai.com/index/introducing-gpt-5-4-mini-and-nano/)) states explicitly: *"It has a 400k context window."* The previous entry in our catalog incorrectly showed `1 M tokens`. Corrected in `models/openai.md` and `comparison.md`.

| Field | Old value | Corrected value |
|---|---|---|
| GPT-5.4 Mini context window | 1,000,000 tokens | **400,000 tokens** |

*Source: [OpenAI — Introducing GPT-5.4 mini and nano](https://openai.com/index/introducing-gpt-5-4-mini-and-nano/) — verified 2026-04-17*

---

### 🔄 xAI: Grok 4.20 canonical model IDs now include dated suffixes; storage billing starts 2026-04-20

**Provider:** [xAI](models/xai.md)  
Two updates from the official xAI API docs (verified 2026-04-17):

**1. Dated model IDs now canonical.** The official `docs.x.ai/developers/models` page now surfaces `grok-4.20-0309-reasoning` and `grok-4.20-0309-non-reasoning` as the primary model IDs. The `-0309` suffix pins to the March 9 training checkpoint. The short alias `grok-4.20` remains valid. Pricing is unchanged: **$2.00 input / $6.00 output** per 1M tokens. Also confirmed: Grok 4.20 cached input rate is **$0.20 / 1M** (10% of standard). Knowledge cutoff confirmed as **November 2024** (not September 2025 as previously listed).

**2. Files and Collections storage billing starts April 20, 2026.** Developers using xAI's Files or Collections APIs for persistent storage (RAG, document retrieval) will begin incurring storage charges on April 20, 2026. Review your storage usage before this date at `console.x.ai/team/default/files`.

Updated: `models/xai.md`  
*Source: [xAI Models & Pricing docs](https://docs.x.ai/developers/models) — verified 2026-04-17*

---

### ⚠️ Anthropic Claude 3 Haiku retires in 3 days (2026-04-20)

**Provider:** [Anthropic](models/anthropic.md)  
Countdown update: Claude 3 Haiku (`claude-3-haiku-20240307`) retires **April 20, 2026** — **3 days from today**. Updated urgency counters across `deprecated.md`, `comparison.md`, and `models/anthropic.md`.  
*Migrate to `claude-haiku-4-5-20251001` immediately. Price change on migration: $0.25/$1.25 → $1.00/$5.00 per 1M tokens (+4×).*

---

### ⚠️ Google: Gemini Robotics-ER 1.5 retiring April 30, 2026

**Provider:** [Google](models/google.md)  
`gemini-robotics-er-1.5-preview` will shut down on **April 30, 2026 at 9AM PST**. The replacement is `gemini-robotics-er-1.6-preview`, released April 14, 2026 with improved instrument reading, spatial reasoning, and physical reasoning capabilities. Added to `deprecated.md` upcoming shutdowns table.  
*Source: [Google Gemini API changelog](https://ai.google.dev/gemini-api/docs/changelog) — 2026-04-14*

---

## 2026-04-16

### 🆕 Anthropic: Claude Opus 4.7 released — same price as 4.6, major coding and vision improvements

**Provider:** [Anthropic](models/anthropic.md)  
**New model:** `claude-opus-4-7` — Anthropic's newest most capable publicly available model, released today.

**Key improvements over Opus 4.6:**
- **Coding:** 70% on CursorBench (vs 58% for Opus 4.6); resolves 3× more production tasks on Rakuten-SWE-Bench; double-digit gains in Code Quality and Test Quality
- **Vision:** Higher resolution image understanding — improved for reading chemical structures, technical diagrams, interpreting complex interfaces
- **Long-horizon tasks:** Stronger efficiency baseline on multi-step work; best long-context performance in Anthropic's internal research-agent benchmark
- **Cyber safeguards:** First publicly released model with Project Glasswing-derived safeguards — automatically detects/blocks prohibited cybersecurity requests. Security professionals can apply via the [Cyber Verification Program](https://claude.com/form/cyber-use-case) for legitimate pen-testing/red-teaming access

**Pricing:** Unchanged from Opus 4.6 — **$5.00 / 1M input · $25.00 / 1M output** (standard, ≤200K context)

**Availability:** Anthropic API (`claude-opus-4-7`), Amazon Bedrock, Google Cloud Vertex AI, Microsoft Foundry

**Note:** Opus 4.6 remains available as a legacy model. Developers should migrate to `claude-opus-4-7` for best coding and agentic performance.

*Source: [Anthropic announcement](https://www.anthropic.com/news/claude-opus-4-7) — 2026-04-16*

---

### ⚠️ Anthropic Claude 3 Haiku retires in 4 days (2026-04-20)

**Provider:** [Anthropic](models/anthropic.md)  
Countdown update: Claude 3 Haiku (`claude-3-haiku-20240307`) retires **April 20, 2026** — **4 days from today**. Updated urgency language across `deprecated.md`, `comparison.md`, and `models/anthropic.md`. No new information; this is a countdown tick.  
*Migrate to `claude-haiku-4-5-20251001` immediately. Price on migration: $0.25/$1.25 → $1.00/$5.00 per 1M tokens (+4×).*

---

## 2026-04-15

### 🔄 Mistral: Pricing corrections — Large 3 output $2.00 → $1.50, Devstral 2 output $2.00 → $0.90; Large 3 context window 131K → 262K

**Provider:** [Mistral](models/mistral.md)  
Corrected two pricing errors and one spec error found by cross-referencing multiple authoritative sources (PricePerToken, OpenRouter, Serenities AI, MarginDash, Holori — all verified 2026-04-15):

- **Mistral Large 3 output price:** $2.00 → **$1.50** per 1M tokens (error in previous entry; $0.50 input is confirmed correct)
- **Mistral Large 3 context window:** 131,072 → **262,144 tokens** (same as Small 4; also open weights under Apache 2.0, 675B total / 41B active parameters)
- **Devstral 2 output price:** $2.00 → **$0.90** per 1M tokens (confirmed via PricePerToken `$0.400/$0.900`, OpenRouter listing)
- **Devstral 2 context window:** 128K → **262,144 tokens**

Updated: `models/mistral.md`, `comparison.md` context window table.  
*Source: [PricePerToken Mistral Large 3 2512](https://pricepertoken.com/pricing-page/model/mistral-ai-mistral-large-2512), [OpenRouter Mistral](https://openrouter.ai/provider/mistral), [Serenities AI](https://serenitiesai.com/articles/mistral-ai-models-2026-complete-guide) — verified 2026-04-15*

---

### 🔄 xAI: Official API now surfaces `grok-4-fast-reasoning` and `grok-4-fast-non-reasoning` as canonical model IDs

**Provider:** [xAI](models/xai.md)  
The official xAI API page (`x.ai/api`) now lists `grok-4-fast-reasoning` and `grok-4-fast-non-reasoning` as the primary API model names for what was previously accessed via `grok-4.1-fast`. Pricing and capabilities are identical ($0.20/$0.50 per 1M tokens, 2M context). The `grok-4.1-fast` alias remains valid. Updated `models/xai.md` to document both sets of names.  
*Source: [xAI API page](https://x.ai/api), [xAI Models & Pricing docs](https://docs.x.ai/developers/models) — verified 2026-04-15*

---

### ⚠️ Anthropic Claude 3 Haiku retires in 5 days (2026-04-20)

**Provider:** [Anthropic](models/anthropic.md)  
Countdown update: Claude 3 Haiku (`claude-3-haiku-20240307`) retires **April 20, 2026** — **5 days from today**. Updated urgency language across `deprecated.md`, `comparison.md`, and `models/anthropic.md`. No new information; this is a countdown tick.  
*Migrate to `claude-haiku-4-5-20251001` immediately. Price on migration: $0.25/$1.25 → $1.00/$5.00 per 1M tokens (+4×).*

---

## 2026-04-14

### ⚠️ DeepSeek: Official API pricing updated — V3.1-Terminus now $0.56/$1.68 per 1M tokens

**Provider:** [DeepSeek](models/deepseek.md)  
The official DeepSeek API pricing page now shows **DeepSeek-V3.1-Terminus** behind both `deepseek-chat` and `deepseek-reasoner` endpoints, at **$0.56 input / $1.68 output** per 1M tokens (cache miss), with cache-hit input at **$0.07/1M** (~87% discount). This is a significant increase from the $0.28/$0.42 rates recorded on 2026-04-13, which appear to have reflected third-party provider or older pricing rather than the official API.

- Cache-miss input: $0.28 → **$0.56** (+100%)
- Output: $0.42 → **$1.68** (+300%)
- Cache-hit input: $0.028 → **$0.07** (+150%)
- Model behind endpoints: V3.2 → **V3.1-Terminus** per official docs

> **Note on discrepancy:** Third-party providers (OpenRouter, Fireworks AI, Together AI) still offer DeepSeek V3.2 at $0.18–$0.28/M input — these are reseller rates for self-hosted weights, not the official API. For the official `api.deepseek.com`, use the rates above.

*Source: [DeepSeek API Docs — Models & Pricing](https://api-docs.deepseek.com/quick_start/pricing) — verified 2026-04-14*

---

### 🆕 xAI: Grok Code Fast added to model catalog

**Provider:** [xAI](models/xai.md)  
Added `grok-code-fast-1` — xAI's coding-specialist model derived from the Grok 4.1 Fast architecture. 256K context window, **$0.20 input / $1.50 output** per 1M tokens. Higher output price than Grok 4.1 Fast ($0.50) reflects longer code generation outputs. Appears in API pricing data from CostGoat (verified via multiple sources).  
*Source: CostGoat Grok API pricing — verified 2026-04-14*

---

### 🔄 DeepSeek V4: Late-April launch confirmed by founder; 3 variants confirmed in grey test UI

**Provider:** [DeepSeek](models/deepseek.md)  
DeepSeek founder **Liang Wenfeng** confirmed in internal communications (reported by ITHome, 2026-04-10) that V4 will launch in **late April 2026**. TechNode (2026-04-08) reports three variants visible in grey-scale test interface:
- **V4 Lite** (Fast version) — ~200B parameters, already on API nodes since ~2026-03-09
- **V4 Expert** (flagship)
- **V4 Vision** (multimodal — confirmed)

This represents the first official confirmation from DeepSeek leadership of the late April target. The model has missed at least two prior windows (mid-February, early April).  
*Source: ITHome via Reddit r/DeepSeek (2026-04-10), TechNode (2026-04-08), Gizchina (2026-04-11)*

---

## 2026-04-13

### 🔄 DeepSeek: Pricing correction — unified $0.28/$0.42 for both chat and reasoner

**Provider:** [DeepSeek](models/deepseek.md)  
Official DeepSeek API docs (verified 2026-04-13) confirm the current pricing for both `deepseek-chat` and `deepseek-reasoner` is **$0.28 input / $0.42 output** per 1M tokens (cache miss), with a 90% cache discount ($0.028 cache hit). Both modes are now identically priced. Previous entries in this file showed inaccurate figures ($0.27/$1.10 for chat; $0.55/$2.19 for reasoner) that reflected older or third-party data.  
- `deepseek-reasoner` context window updated to 128K (same as chat) with max output of 64K tokens  
- Comparison matrix and decision guide updated accordingly  
*Source: [DeepSeek API Docs](https://api-docs.deepseek.com/quick_start/pricing) — verified 2026-04-13*

---

### ❌ Cohere: Embed v2.0 and Aya Expanse 8B models retired (2026-04-04)

**Provider:** [Cohere](models/cohere.md)  
Effective April 4, 2026, Cohere permanently retired the following models (API requests now return errors):
- **Embedding:** `embed-english-v2.0`, `embed-english-light-v2.0`, `embed-multilingual-v2.0` → migrate to `embed-english-v3.0`, `embed-multilingual-v3.0`, or `embed-v4.0`
- **Chat:** `c4ai-aya-expanse-8b`, `c4ai-aya-vision-8b` → migrate to `command-r7b-12-2024` or `command-a-03-2025`  
*Source: [Cohere deprecations page](https://docs.cohere.com/docs/deprecations) — verified 2026-04-13*

---

## 2026-04-12

### ⚠️ URGENT: Anthropic Claude 3 Haiku retiring in 8 days (2026-04-20)

**Provider:** [Anthropic](models/anthropic.md)  
Claude 3 Haiku (`claude-3-haiku-20240307`) reaches its retirement date on **April 20, 2026**. API requests to this model will fail after that date. Migrate immediately to `claude-haiku-4-5-20251001` (Claude Haiku 4.5).  
- **Price change on migration:** $0.25/$1.25 → $1.00/$5.00 per 1M input/output (4× more expensive, but dramatically more capable)  
- **Note:** Claude 3.5 Haiku (`claude-3-5-haiku-20241022`) already retired 2026-02-19 — do not use  
*Source: [Anthropic model deprecations page](https://platform.claude.com/docs/en/about-claude/model-deprecations) — verified 2026-04-12*

---

### 🔜 DeepSeek V4 — Grey release underway, full launch imminent

**Provider:** [DeepSeek](models/deepseek.md)  
DeepSeek V4 has not officially launched as of 2026-04-12, but is in limited grey testing on some API infrastructure nodes ("V4-Lite"), strongly signalling imminent public release.  
**Key confirmed facts (via Reuters, The Information):**  
- Full model expected **late April 2026** (missed prior Feb/March targets)
- ~1 trillion parameters total, ~32–37B active per token (MoE architecture)  
- First frontier model running on **Huawei Ascend chips** (no NVIDIA/AMD early access)
- Multimodal: text, image, video  
- 1M token context window widely reported but not officially confirmed  
- Three V4 variants in development  
**What to do:** No migration required now; current `deepseek-chat` and `deepseek-reasoner` point to V3.2. Watch official API docs for V4 model IDs.  
*Source: Reuters 2026-04-03, Taipei Times 2026-04-11, Gizchina 2026-04-11*

---

### 🛠️ Anthropic: Corrected Claude Opus 4.6 max output tokens

**Provider:** [Anthropic](models/anthropic.md)  
Corrected `claude-opus-4-6` max output from "—" to **128,000 tokens**, per official Anthropic release notes. Also added Claude Sonnet 4.6 release date (2026-02-17) to legacy model table. Legacy model retirement dates added from official deprecation page.  
*Source: [Anthropic Opus 4.6 announcement](https://www.anthropic.com/news/claude-opus-4-6), [deprecation page](https://platform.claude.com/docs/en/about-claude/model-deprecations) — 2026-04-12*

---

## 2026-04-11

### 🔄 Pricing corrections: Meta Llama 4 provider rates

**Provider:** [Meta](models/meta.md)  
Corrected Llama 4 Scout and Maverick typical API prices based on current OpenRouter/DeepInfra rates (verified 2026-04-11):
- **Scout:** $0.11/$0.34 → **$0.08/$0.30** per 1M tokens
- **Maverick:** $0.27/$0.85 → **$0.15/$0.60** per 1M tokens  
These are third-party provider rates; Meta does not operate a first-party API.

---

### 🆕 Meta: Muse Spark released (2026-04-08)

**Provider:** [Meta](models/meta.md)  
**New model:** Muse Spark — first model from Meta Superintelligence Labs (MSL), led by Alexandr Wang. Proprietary (closed weights), rebuilt from scratch with new infrastructure. Now powers Meta AI app and meta.ai. Rolling out to WhatsApp, Instagram, Facebook, Messenger, and Ray-Ban AI glasses in coming weeks.  
- **Modalities:** Text, images, video, multimodal perception  
- **Special feature:** "Contemplating mode" for multi-agent orchestration  
- **Strengths:** Multimodal perception, reasoning, health, shopping recommendations  
- **Gap:** Coding and long-horizon agents (Meta acknowledged)  
- **API:** Private preview to select partners only. No public API date announced.  
- **Pricing:** Not yet disclosed (public API not yet available)  
- Next model codenamed "Watermelon" in development  
*Source: [Meta blog](https://about.fb.com/news/2026/04/introducing-muse-spark-meta-superintelligence-labs/), TechCrunch, NYT — 2026-04-08*

---

### 🆕 Google: Gemma 4 family released (2026-04-02)

**Provider:** [Google](models/google.md)  
**New models:** Gemma 4 E2B, E4B, 26B MoE (A4B), and 31B Dense — Google's most capable open-weight models to date. Released under **Apache 2.0** license (replacing the custom Gemma license used by previous generations).  
- 31B Dense: #3 on Arena AI open text leaderboard; 26B MoE: #6
- All variants: multimodal (text, image, video); E2B/E4B also audio
- Context: 128K (E2B/E4B) / 256K (26B, 31B); 140+ languages
- Available: HuggingFace, Kaggle, Ollama, AI Studio, AI Edge Gallery  
*Source: [Google Blog](https://blog.google/innovation-and-ai/technology/developers-tools/gemma-4/) — 2026-04-02*

---

### ⚠️ Google: Gemini API free tier restricted (2026-04-01)

**Provider:** [Google](models/google.md)  
Effective April 1, 2026, Google changed Gemini API free tier policies:
- **Pro models now paid-only** on the API free tier (previously accessible to free-tier users)
- Free tier now limited to **Flash and Flash-Lite models** only
- Mandatory spending caps enforced by tier (Tier 1: $250/month, Tier 2: $2,000/month)
- New accounts may require prepaid billing (buy credits upfront)  
*Source: FindSkill.ai, Google API docs — 2026-04-01*

---

### 🆕 Anthropic: Claude Mythos Preview announced (2026-04-07)

**Provider:** [Anthropic](models/anthropic.md)  
**New model (gated):** Claude Mythos Preview — Anthropic's most capable model to date, described as a "step change" above Claude Opus 4.6. Available **only** to ~50 partner organizations under **Project Glasswing** for cybersecurity use.  
- Internally codenamed "Capybara"  
- Autonomous zero-day vulnerability discovery across large codebases  
- Preview pricing: **~$25 / $125 per 1M input/output tokens** (gated, not public API)  
- No general availability date announced  
- Anthropic withheld broad release due to offensive cybersecurity risk  
*Source: TechCrunch, [Anthropic System Card](https://www.anthropic.com/claude-mythos-preview-system-card) — 2026-04-07*

---

### 🆕 OpenAI: ChatGPT $100/month Pro tier launched (2026-04-09)

**Provider:** [OpenAI](models/openai.md)  
OpenAI launched a new **$100/month ChatGPT Pro** subscription tier, positioned between the existing Plus ($20/month) and Pro ($200/month) plans. Designed to compete directly with Anthropic's Claude Max 5x ($100/month).  
- 5× more Codex usage than the Plus plan  
- "Best for longer, high-effort Codex sessions"  
- Total ChatGPT personal subscription tiers: Free, Go ($8), Plus ($20), Pro ($100), Pro ($200)  
*Source: TechCrunch, CNBC — 2026-04-09*

---

## 2026-04-10

### 🆕 Initial knowledge base creation

This is the first run of the Model Tracker agent. The following files were created from scratch based on data verified as of 2026-04-10:

- `models/openai.md` — GPT-5.4 family, GPT-4.1 family, o3/o4-mini reasoning models
- `models/anthropic.md` — Claude 4.6 generation (Opus, Sonnet, Haiku)
- `models/google.md` — Gemini 2.5 GA + Gemini 3.x preview models
- `models/mistral.md` — Mistral Small 4, Large 3, Medium 3, Devstral 2
- `models/xai.md` — Grok 4.20, Grok 4, Grok 4.1 Fast
- `models/deepseek.md` — DeepSeek V3.2 (chat + reasoner modes)
- `models/cohere.md` — Command A, Command R series
- `models/meta.md` — Llama 4 Scout/Maverick, Llama 3.3 70B
- `comparison.md` — side-by-side pricing and feature matrix
- `deprecated.md` — sunset dates and migration paths

---

## Changes Captured (Backdated to actual event dates)

### 2026-04-02 — Anthropic: Subscription policy change for agent tools

**Provider:** [Anthropic](models/anthropic.md)  
Claude Pro and Max subscriptions no longer cover third-party agent frameworks (e.g. OpenClaw) from 2026-04-04. Users must use a direct API key with pay-as-you-go token billing. Affected subscribers received a one-time credit equal to their plan cost.  
*Source: TechCrunch 2026-04-04*

---

### 2026-04-02 — Google: New Gemini inference pricing tiers

**Provider:** [Google](models/google.md)  
Google introduced Standard, Flex, Priority, Batch, and Caching inference tiers for the Gemini API. Batch processing offers 50% discount (matching OpenAI and Anthropic).  
*Source: Seeking Alpha 2026-04-02*

---

### 2026-04-02 — OpenAI: Codex flexible pricing for teams

**Provider:** [OpenAI](models/openai.md)  
OpenAI expanded Codex with pay-as-you-go pricing for ChatGPT Business teams. New **Codex seat** type introduced for Enterprise: token-based billing, no fixed per-seat cost. ChatGPT Business price reduced from **$25 → $20/seat/month**.  
*Source: OpenAI blog 2026-04-02*

---

### 2026-03-31 — xAI: Grok 4.20 released

**Provider:** [xAI](models/xai.md)  
**New model:** `grok-4.20` — xAI's flagship model with 2 M token context, agentic tool calling, 4-agent reasoning system (Grok + Harper + Benjamin + Lucas). Pricing: **$2.00 input / $6.00 output** per 1M tokens.  
*Source: OpenRouter listing 2026-03-31*

---

### 2026-03-26 — Mistral: Voxtral TTS released (open source)

**Provider:** [Mistral](models/mistral.md)  
**New model:** Voxtral TTS — open source text-to-speech model supporting 9 languages. Designed for enterprise voice agents (customer support, sales). Optimized for edge deployment (smartwatch/smartphone). Competes with ElevenLabs, Deepgram, OpenAI TTS.  
*Source: TechCrunch 2026-03-26*

---

### 2026-03-17 — OpenAI: GPT-5.4 Mini and Nano released

**Provider:** [OpenAI](models/openai.md)  
**New models:** `gpt-5.4-mini` ($0.75/$4.50) and `gpt-5.4-nano` ($0.20/$1.25) per 1M tokens. Both support 1 M token context. Mini scores 54.38% on SWE-bench Pro (vs 57.7% for Standard at 6× lower cost). Free-tier ChatGPT gets limited Mini access.  
*Source: OpenAI blog 2026-03-17*

---

### 2026-03-16 — Mistral: Mistral Small 4 released

**Provider:** [Mistral](models/mistral.md)  
**New model:** `mistral-small-2603` — 119B parameter model with 262K context, unifying Magistral (reasoning) + Pixtral (vision) + Devstral (coding) capabilities in a single model. Pricing: **$0.15 / $0.60** per 1M tokens. Open weights on HuggingFace.  
*Source: OpenRouter listing 2026-03-16*

---

### 2026-03-09 — Google: Gemini 3-pro-preview retired

**Provider:** [Google](models/google.md)  
`gemini-3-pro-preview` retired. Migrate to `gemini-3.1-pro-preview`.

---

### 2026-03-05 — OpenAI: GPT-5.4 released

**Provider:** [OpenAI](models/openai.md)  
**New model:** `gpt-5.4` — First general-purpose model with native computer-use. 1 M token context. Standard pricing: **$2.50 / $15.00** per 1M tokens (2× for tokens >272K). OSWorld-Verified: **75%** (surpasses human baseline of 72.4%). GPT-5.4 Pro also released at $30/$180. GPT-5.2 Thinking deprecated in ChatGPT; retires **2026-06-05**.  
*Source: OpenAI blog 2026-03-05*

---

### 2026-03-03 — Google: Gemini 3.1 Flash-Lite Preview released

**Provider:** [Google](models/google.md)  
**New model:** `gemini-3.1-flash-lite-preview` — High-speed, low-cost model. Pricing: $0.25/$1.50 per 1M tokens.

---

### 2026-02-26 — Google: Gemini 3.1 Flash Image Preview released

**Provider:** [Google](models/google.md)  
**New model:** `gemini-3.1-flash-image-preview` — Native image generation support.

---

### 2026-02-19 — Google: Gemini 3.1 Pro Preview released

**Provider:** [Google](models/google.md)  
**New model:** `gemini-3.1-pro-preview` — Most capable Gemini model. GPQA Diamond: 94.3%. Pricing: **$2.00 / $12.00** per 1M tokens (≤200K). Currently preview-only.

---

### 2026-02-04 — Anthropic: Claude Opus 4.6 released

**Provider:** [Anthropic](models/anthropic.md)  
**New model:** `claude-opus-4-6` — Full 1 M token context at standard pricing (no long-context premium). Pricing: **$5.00 / $25.00** per 1M tokens. GPQA Diamond: 91.3%. 67% cheaper than Opus 4.1 ($15/$75).

---

### 2025-12-01 — DeepSeek: V3.2 released

**Provider:** [DeepSeek](models/deepseek.md)  
**New model:** DeepSeek V3.2 — Unified model for chat and reasoning. Replaces both V3 and R1. Pricing: **$0.27/$1.10** (chat) and **$0.55/$2.19** (reasoner) per 1M tokens. 90% cache discount. Open weights.

---

### 2025-07-09 — xAI: Grok 4 released

**Provider:** [xAI](models/xai.md)  
**New model:** `grok-4` — Always-on reasoning model. 256 K context. Pricing: **$3.00 / $15.00** per 1M tokens. GPQA Diamond: 87.7%.

---

### 2025-04-16 — OpenAI: o3 and o4-mini released

**Provider:** [OpenAI](models/openai.md)  
**New models:** `o3` ($10/$40) and `o4-mini` ($1.10/$4.40) per 1M tokens. New standard for math, science, coding, and visual reasoning. Also launched Codex CLI.

---

### 2025-04-14 — OpenAI: GPT-4.1 family released

**Provider:** [OpenAI](models/openai.md)  
**New models:** `gpt-4.1` ($2/$8), `gpt-4.1-mini` ($0.40/$1.60), `gpt-4.1-nano` ($0.10/$0.40) — all with 1 M token context. `gpt-4.5-preview` deprecated.

---

*This changelog is maintained automatically by the Model Tracker agent. Entries are prepended on each run.*
