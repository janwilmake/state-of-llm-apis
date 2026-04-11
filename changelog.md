# LLM API Changelog

Changes tracked by the Model Tracker agent. Most recent entries first.

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
