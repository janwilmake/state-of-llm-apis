# LLM API Changelog

Changes tracked by the Model Tracker agent. Most recent entries first.

---

## 2026-06-15

### ✅ Anthropic: June 15 retirements COMPLETED — `claude-sonnet-4-20250514` and `claude-opus-4-20250514` shut down

**Provider:** [Anthropic](models/anthropic.md)  
As of today (**June 15, 2026**), the following models are shut down and return API errors:

| Model | API name | Replacement |
|---|---|---|
| Claude Sonnet 4 | `claude-sonnet-4-20250514` ❌ | `claude-sonnet-4-6` ($3/$15 per 1M) |
| Claude Opus 4 | `claude-opus-4-20250514` ❌ | `claude-opus-4-7` ($5/$25 per 1M) |

If you still have calls targeting either dated model ID, they will fail immediately. Migrate to `claude-sonnet-4-6` or `claude-opus-4-7` (or newer — Opus 4.8 at the same $5/$25 pricing is also recommended).

Updated: `deprecated.md`  
*Source: [Anthropic model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations) — confirmed 2026-06-15*

---

### ✅ Anthropic: Agent SDK billing split NOW LIVE (2026-06-15)

**Provider:** [Anthropic](models/anthropic.md)  
The Anthropic **Agent SDK billing split** went into effect today. Programmatic/autonomous Claude Code usage — via the Agent SDK, `claude -p` CLI flag, GitHub Actions, and third-party integrations (OpenClaw, Zed, Cursor, etc.) — now draws from a **dedicated monthly credit pool**, separate from interactive chat usage in the claude.ai interface.

| Subscription plan | Autonomous agent credits/month |
|---|---|
| Pro ($20/month) | $20 in API-rate credits |
| Max 5x ($100/month) | $100 in API-rate credits |
| Max 20x ($200/month) | $200 in API-rate credits |

Overflow beyond the monthly credit pool is charged at standard API rates per token. Teams with heavy automated Claude Code workloads (CI pipelines, agent loops, GitHub Actions) should monitor credit consumption immediately to avoid unexpected overage charges.

*Source: [Anthropic billing announcement](https://www.anthropic.com/news/agent-sdk-billing) — announced 2026-05-14 · effective 2026-06-15*

---

### ⚠️ Google: Gemini CLI / Gemini Code Assist consumer shutdown — **June 18, 2026 (3 DAYS)**

**Provider:** [Google](models/google.md)  
Google's **Gemini CLI** and **Gemini Code Assist IDE extensions** stop serving all Google AI Pro, Ultra, and free Gemini Code Assist for individuals users on **June 18, 2026**. The successor is the **Antigravity CLI** (`agy` binary).

> ⚠️ **Enterprise exception:** Organizations on Gemini Code Assist Standard/Enterprise licenses or paid API keys are **not** affected — this is a consumer-tier shutdown only.

**What breaks on June 18 for consumer users:**
- `gemini` CLI binary stops serving
- Gemini Code Assist IDE extensions (VS Code, JetBrains, etc.) stop serving
- Gemini Code Assist for GitHub: no new org installations; existing requests stop serving in the following weeks

**Migration:** Install the Antigravity CLI (`agy`). Note: the migration script does not update CI/CD pipelines or automation. One known silent failure: a specific MCP `serverUrl` config field fails without an error. Test carefully before cutover.

Updated: `deprecated.md`  
*Source: [Google I/O 2026 announcement — May 19, 2026](https://cloud.google.com/blog/products/ai-machine-learning/innovations-from-google-io-26-on-google-cloud) · [Antigravity migration guide](https://www.digitalapplied.com/blog/gemini-cli-to-antigravity-cli-migration-june-18-2026-guide) — verified 2026-06-15*

---

### 🆕 Google: Veo 3.0 / Veo 2.0 retiring June 30, 2026 — **15 DAYS**

**Provider:** [Google](models/google.md)  
Three Veo video generation models are scheduled for retirement on **June 30, 2026**, per the official Google Cloud model lifecycle page. Replacement is Veo 3.1 (released November 2025, no announced shutdown date).

| Model | API name | Retirement | Replacement |
|---|---|---|---|
| Veo 3.0 | `veo-3.0-generate-001` | **2026-06-30** | `veo-3.1-generate-001` |
| Veo 3.0 Fast | `veo-3.0-fast-generate-001` | **2026-06-30** | `veo-3.1-fast-generate-001` |
| Veo 2.0 | `veo-2.0-generate-001` | **2026-06-30** | `veo-3.1-generate-001` |

Updated: `deprecated.md`  
*Source: [Google Cloud — Model versions and lifecycle](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/model-versions) — verified 2026-06-15*

---

### ⏱️ Deadlines: Key upcoming cutoffs

| Deadline | Days | Action |
|---|---|---|
| **2026-06-18** | **3 days** 🚨 | Gemini CLI + Code Assist consumer users: migrate to Antigravity CLI (`agy`) |
| **2026-06-24** | 9 days ⚠️ | Imagen 4.0 models retire on Gemini Dev API → `gemini-3-pro-image` |
| **2026-06-25** | 10 days ⚠️ | `gemini-3.1-flash-image-preview` and `gemini-3-pro-image-preview` → GA versions |
| **2026-06-27** | 12 days | GPT-4.5 retired from **ChatGPT** (no API change) |
| **2026-06-30** | 15 days ⚠️ | Mistral `labs-leanstral-2603` hard shutdown |
| **2026-06-30** | 15 days ⚠️ | Google Veo 3.0 / Veo 2.0 retire → `veo-3.1-generate-001` |
| **2026-07-24** | 39 days | DeepSeek `deepseek-chat` / `deepseek-reasoner` hard cutoff → `deepseek-v4-flash` (returns errors, no redirect) |
| **2026-07-31** | 46 days | Mistral `mistral-small-2506`, `magistral-small-2509` → `mistral-small-2603` |
| **2026-10-16** | ~123 days | `gemini-2.5-pro`, `gemini-2.5-flash`, `gemini-2.5-flash-lite` retire |
| **2026-11-30** | ~168 days | OpenAI Agent Builder shut down |
| **2026-12-01** | ~169 days | `gpt-image-1-mini`, `gpt-image-1.5`, `chatgpt-image-latest` shut down → `gpt-image-2` |

*Verified 2026-06-15*

---

## 2026-06-14

### 🔴 OpenAI: GPT-5.2 family retired from ChatGPT (2026-06-12) — API unaffected

**Provider:** [OpenAI](models/openai.md)  
As of **June 12, 2026**, GPT-5.2 Instant, GPT-5.2 Thinking, and GPT-5.2 Pro are no longer available in ChatGPT. Existing conversations migrate automatically to corresponding GPT-5.5 models. This retirement was previously announced with the GPT-5.3 Instant release (models typically remain in ChatGPT for 90 days after a successor ships). **There are no API changes** — GPT-5.2 model IDs, if still available on the API, continue to work.

*Source: [ChatGPT Release Notes — June 12, 2026](https://help.openai.com/en/articles/6825453-chatgpt-release-notes) — verified 2026-06-14*

---

### 🆕 OpenAI: GPT Image 1 family deprecated — retire Dec 1, 2026

**Provider:** [OpenAI](models/openai.md)  
On **June 2, 2026**, OpenAI notified developers of deprecation for three older image models. These remain accessible until December 1, 2026.

| Model | API name | Shutdown date | Replacement |
|---|---|---|---|
| GPT Image 1 Mini | `gpt-image-1-mini` | **2026-12-01** | `gpt-image-2` |
| GPT Image 1.5 | `gpt-image-1.5` | **2026-12-01** | `gpt-image-2` |
| ChatGPT Image Latest | `chatgpt-image-latest` | **2026-12-01** | `gpt-image-2` |

GPT Image 2 (`gpt-image-2`) was released April 21, 2026 and is the current recommended model. Supports Batch API (50% discount), token-based billing, and flexible image sizes.

Updated: `deprecated.md`  
*Source: [OpenAI Deprecations](https://developers.openai.com/api/docs/deprecations) — verified 2026-06-14*

---

### 🆕 OpenAI: Agent Builder deprecated — shut down Nov 30, 2026

**Provider:** [OpenAI](models/openai.md)  
On **June 3, 2026**, OpenAI announced deprecation of the **Agent Builder** product. ChatKit remains available. Migration path: move to the Agents SDK or ChatGPT Workspace Agents.

| Milestone | Date |
|---|---|
| Deprecation announced | June 3, 2026 |
| Shut down | **November 30, 2026** |

This affects developers who built on Agent Builder's no-code/low-code interface — not the Agents SDK or Responses API, which remain active.

Updated: `deprecated.md`  
*Source: [OpenAI Deprecations](https://developers.openai.com/api/docs/deprecations) — verified 2026-06-14*

---

### ⏱️ Deadlines: ~~TOMORROW~~ — Anthropic June 15 retirements ✅ COMPLETED TODAY; Gemini image previews in 10 days

| Deadline | Action |
|---|---|
| **2026-06-15** | ✅ **TODAY COMPLETED** — `claude-sonnet-4-20250514` and `claude-opus-4-20250514` shut down — migrate to `claude-sonnet-4-6` / `claude-opus-4-7` |
| **2026-06-15** | ✅ **TODAY LIVE** — Anthropic Agent SDK billing split in effect; SDK/`claude -p`/GitHub Actions usage now draws from dedicated credit pool (Pro=$20, Max 5x=$100, Max 20x=$200) |
| **2026-06-25** | ⚠️ 11 days — Gemini image preview models retire: `gemini-3.1-flash-image-preview` → `gemini-3.1-flash-image`; `gemini-3-pro-image-preview` → `gemini-3-pro-image` |
| **2026-06-27** | ⚠️ 13 days — GPT-4.5 retired from **ChatGPT** (no API change) |
| **2026-06-24** | ⚠️ 10 days — Imagen 4.0 models retire on Gemini Developer API (`imagen-4.0-*`) → `gemini-3-pro-image` |
| **2026-06-30** | 16 days — Mistral `labs-leanstral-2603` (Leanstral) hard shutdown |
| **2026-07-24** | 40 days — DeepSeek `deepseek-chat` / `deepseek-reasoner` hard cutoff → use `deepseek-v4-flash` (returns errors, no redirect) |
| **2026-07-31** | 47 days — Mistral `mistral-small-2506`, `magistral-small-2509`, `devstral-2512` → `mistral-small-2603`/`mistral-medium-3-5` |
| **2026-08-26** | ~73 days — OpenAI o3 retired from **ChatGPT** (no API change) |
| **2026-10-16** | ~124 days — `gemini-2.5-pro`, `gemini-2.5-flash`, `gemini-2.5-flash-lite` retire |
| **2026-11-30** | ~169 days — OpenAI Agent Builder shut down |
| **2026-12-01** | ~170 days — `gpt-image-1-mini`, `gpt-image-1.5`, `chatgpt-image-latest` shut down → `gpt-image-2` |

*Verified 2026-06-14*

---

## 2026-06-13

### 🚨 Anthropic: Claude Fable 5 and Mythos 5 SUSPENDED — US export control directive (2026-06-12)

**Provider:** [Anthropic](models/anthropic.md)  
The most consequential AI regulatory event of 2026 so far. On **June 12, 2026 at 5:21 PM ET**, the U.S. Commerce Department (Secretary Howard Lutnick) issued an export control directive ordering Anthropic to suspend all access to Claude Fable 5 and Claude Mythos 5 by any foreign national, whether inside or outside the United States — including Anthropic's own foreign national employees. Because ordinary service made targeted compliance impossible, Anthropic disabled both models **for all customers globally**.

**Timeline:**
- **June 9, 2026:** Claude Fable 5 (public) and Claude Mythos 5 (Glasswing partners) launched. Best-in-class coding/reasoning model; SWE-bench Pro 80.3%.
- **June 12, 2026 at 5:21 PM ET:** U.S. government directive received. Both models taken offline for all users, no warning window.
- **June 13, 2026:** Anthropic published [full statement](https://www.anthropic.com/news/fable-mythos-access) disputing the directive's basis.

**Why:** The government's stated reason was a claimed jailbreak of Fable/Mythos that could enable cybersecurity harm. Anthropic's review found the technique demonstrated "a small number of previously known, minor vulnerabilities" and that "other publicly-available models (including OpenAI's GPT-5.5) are able to discover them as well."

**Current status (2026-06-13):** Both models remain offline. Anthropic says it is "working to restore access as soon as possible." No timeline given.

**Impact on developers:**
- `claude-fable-5` and `claude-mythos-5` API calls return errors
- All other Claude models (Opus 4.8, Sonnet 4.6, Haiku 4.5, etc.) are **unaffected**
- Migrate to `claude-opus-4-8` ($5/$25 per 1M) for best available Anthropic performance
- The June 22 free-subscription-access deadline is now moot until access is restored

Updated: `models/anthropic.md`, `comparison.md`  
*Source: [Anthropic statement](https://www.anthropic.com/news/fable-mythos-access) · [Anthropic @AnthropicAI on X](https://x.com/AnthropicAI/status/2065597531644743999) · [AP](https://www.santacruzsentinel.com/2026/06/12/anthropic-trump/) · [CNBC](https://www.cnbc.com/2026/06/12/anthropic-disables-access-to-fable-5-and-mythos-5-to-comply-with-government-directive.html) · [Wired](https://www.wired.com/story/anthropic-says-us-government-ordered-it-to-shut-down-mythos-models/) — verified 2026-06-13*

---

### 🆕 xAI: Grok Build Plugin Marketplace launched (2026-06-11)

**Provider:** [xAI](models/xai.md)  
xAI launched the **Grok Build Plugin Marketplace** on June 11, 2026 — a built-in plugin catalog for the Grok Build CLI. A plugin bundles skills, slash commands, agents, hooks, MCP servers, and LSPs into a single installable package. Users browse, install, and update plugins without leaving the terminal.

**Launch partners (6 plugins):** MongoDB, Vercel, Sentry, Chrome DevTools, Cloudflare, Superpowers.  
**Security:** Every remote plugin is pinned to a commit SHA verified at install time.  
**Open catalog:** Submit plugins via PR to [xai-org/plugin-marketplace](https://github.com/xai-org/plugin-marketplace).  
**Access:** `/marketplace` inside Grok Build; `grok plugin install <name> --trust` via CLI.

Updated: `models/xai.md`  
*Source: [xAI — Grok Build Plugin Marketplace](https://x.ai/news/grok-plugin-marketplace) — 2026-06-11 · verified 2026-06-13*

---

### 🆕 xAI: Composer 2.5 added to Grok Build (2026-06-01)

**Provider:** [xAI](models/xai.md)  
xAI added **Composer 2.5** as a second model inside the Grok Build CLI on June 1, 2026. Based on an open-source checkpoint of Moonshot's Kimi K2.5, trained with 25× more synthetic tasks than Composer 2. Optimized for long-running tasks and complex instruction-following.

| Pricing | Rate |
|---|---|
| Input (standard) | $0.50 / 1M tokens |
| Output (standard) | $2.50 / 1M tokens |
| Input (fast variant) | $3.00 / 1M tokens |
| Output (fast variant) | $15.00 / 1M tokens |

**Note:** This is a third-party model (Kimi K2.5 base) integrated into Grok Build — not an xAI-trained model. Not available on the standard xAI API (`docs.x.ai/developers/models`).  
**Access:** SuperGrok and X Premium+ subscribers via `/model` menu in Grok Build.

Updated: `models/xai.md`  
*Source: [xAI — Composer 2.5](https://x.ai/news/composer-2-5) — 2026-06-01 · verified 2026-06-13*

---

### ⏱️ Deadlines: **2 DAYS** to Anthropic retirements + Agent SDK billing change

| Deadline | Days | Action |
|---|---|---|
| **2026-06-15** | **2 days** 🚨 | Migrate `claude-sonnet-4-20250514` → `claude-sonnet-4-6` and `claude-opus-4-20250514` → `claude-opus-4-7` (hard shutdown) |
| **2026-06-15** | **2 days** 🚨 | **Anthropic Agent SDK billing split takes effect** — autonomous `claude -p`/SDK/GitHub Actions usage moves to metered API-rate credit pool |
| **2026-06-24** | 11 days ⚠️ | Imagen 4.0 models retire on Gemini Dev API → `gemini-3-pro-image` |
| **2026-06-25** | 12 days ⚠️ | Gemini image preview models `gemini-3.1-flash-image-preview` and `gemini-3-pro-image-preview` retire → GA versions |
| **2026-06-30** | 17 days | Mistral `mistral-moderation-2411` → `mistral-moderation-2` |
| **2026-07-24** | 41 days | DeepSeek `deepseek-chat` / `deepseek-reasoner` hard cutoff → `deepseek-v4-flash` (returns errors, no redirect) |
| **2026-07-31** | 48 days | Mistral `mistral-small-2506`, `magistral-small-2509` → `mistral-small-2603` |
| **2026-10-16** | 125 days | `gemini-2.5-pro`, `gemini-2.5-flash`, `gemini-2.5-flash-lite` retire |

*Verified 2026-06-13*

---

## 2026-06-11

### ✅ Mistral: May 31 retirements COMPLETED — 5 models confirmed retired

**Provider:** [Mistral](models/mistral.md)
The following Mistral models reached their retirement date of **2026-05-31** and are now shut down:

| Model | API name | Replacement |
|---|---|---|
| Mistral Large 2.1 | `mistral-large-2411` | `mistral-large-latest` (Mistral Large 3) |
| Pixtral Large | `pixtral-large-2411` | `mistral-large-latest` (Mistral Large 3) |
| Devstral Medium 1.0 | `devstral-medium-2507` | `mistral-medium-3-5` |
| Voxtral Mini | `voxtral-mini-2507` | `voxtral-mini-transcribe-2` |
| Mistral OCR 2 | `mistral-ocr-2505` | `mistral-ocr-3` |

Updated: `deprecated.md`  
*Source: [Mistral Models Overview](https://docs.mistral.ai/models/overview) — verified 2026-06-11*

---

### 🆕 xAI: `grok-imagine-video-1.5-preview` pricing confirmed — $0.08/sec output

**Provider:** [xAI](models/xai.md)  
The official xAI model docs page for `grok-imagine-video-1.5-preview` now lists confirmed pricing:

| Item | Price |
|---|---|
| Output video | **$0.08 / second** |
| Image input | $0.01 / image |
| Video input (480p) | $0.08 / second |
| Video input (720p) | $0.14 / second |
| Rate limit | 60 requests per minute |

**Key caveat:** The preview model currently **does not support text-to-video**. It animates still images into video using natural-language motion prompts. Text-to-video support may be added in a future update.

The `grok-imagine-video-1.5-preview` model is also available via alias `grok-imagine-video-1.5-2026-05-30`.

Updated: `models/xai.md`  
*Source: [xAI model docs — grok-imagine-video-1.5-preview](https://docs.x.ai/developers/models/grok-imagine-video-1.5-preview) — verified 2026-06-11*

---

### 🆕 xAI: `grok-imagine-1.5` image generation model launched (2026-06-03)

**Provider:** [xAI](models/xai.md)  
xAI launched `grok-imagine-1.5` (also aliased `grok-imagine-quality` — replaces `grok-imagine-image-quality`) on **June 3, 2026**. A higher-quality image generation model replacing the previous Grok Imagine Quality model.

**Key improvements:** Higher realism, stronger text rendering in generated images, better creative control.  
**API name:** `grok-imagine-1.5` (or `grok-imagine-quality`)  
**Pricing:** Not yet published separately — check [xAI Pricing docs](https://docs.x.ai/developers/pricing) for current rates.

*Source: [xAI News — Grok Imagine 1.5 Preview](https://x.ai/news) — 2026-06-03 · verified 2026-06-11*

---

### 🆕 OpenAI: Container billing changed to per-minute (2026-06-02)

**Provider:** [OpenAI](models/openai.md)  
Starting **June 2, 2026**, eligible container sessions are billed per minute with a **5-minute minimum**, instead of being billed at the full 20-minute session rate. The underlying per-minute rate is unchanged.

**Impact:** Shorter sessions now cost less. Previously a 6-minute session was billed as a full 20 minutes; now it's billed as 6 minutes.

*Source: [OpenAI API Changelog — June 2026](https://developers.openai.com/api/docs/changelog) — verified 2026-06-11*

---

### 🆕 OpenAI: GPT-5.4 and GPT-5.5 now available in Amazon Bedrock (2026-06-01)

**Provider:** [OpenAI](models/openai.md)  
OpenAI models `gpt-5.4` and `gpt-5.5` are now available in **Amazon Bedrock** through an OpenAI-compatible Responses API endpoint. Supported models and features vary by AWS region. This is in addition to existing availability on OpenAI's own API.

*Source: [OpenAI API Changelog — June 1, 2026](https://developers.openai.com/api/docs/changelog) — verified 2026-06-11*

---

### ⏱️ Countdown: **4 days** to Anthropic model retirements; **6 days** to Gemini 2.5 retirements

| Deadline | Days | Action |
|---|---|---|
| **2026-06-15** | **4 days** 🚨 | Migrate `claude-sonnet-4-20250514` → `claude-sonnet-4-6` and `claude-opus-4-20250514` → `claude-opus-4-7` (hard shutdown) |
| **2026-06-15** | **4 days** 🚨 | Anthropic Agent SDK billing split takes effect — autonomous `claude -p`/SDK usage moves to per-API-rate credit pool |
| **2026-06-17** | **6 days** ⚠️ | `gemini-2.5-pro` retires → `gemini-3.1-pro-preview` or `gemini-3.5-flash` |
| **2026-06-17** | **6 days** ⚠️ | `gemini-2.5-flash` retires → `gemini-3-flash-preview` or `gemini-3.5-flash` |
| **2026-06-22** | 11 days | Claude Fable 5 free subscription access ends — usage credits required |
| **2026-06-30** | 19 days | Mistral `mistral-moderation-2411` retires → `mistral-moderation-2` |
| **2026-07-22** | 41 days | `gemini-2.5-flash-lite` retires → `gemini-3.1-flash-lite` (GA) |
| **2026-07-24** | 43 days | DeepSeek `deepseek-chat` / `deepseek-reasoner` hard cutoff → `deepseek-v4-flash` (returns errors, no redirect) |
| **2026-07-31** | 50 days | Mistral `mistral-small-2506`, `magistral-small-2509` → `mistral-small-2603` (Mistral Small 4) |

*Verified 2026-06-11*

---

## 2026-05-21

### 🆕 Google: Managed Agents API launched — `antigravity-preview-05-2026` now in public preview

**Provider:** [Google](models/google.md)  
At Google I/O 2026 (May 19), Google launched the **Managed Agents API** in public preview. Developers can now spin up stateful, autonomous agents inside secure Google-hosted Linux sandboxes with a single API call — no infrastructure setup required.

**Key facts:**
- Model/agent ID: `antigravity-preview-05-2026`
- Inherits Agent Platform enterprise data privacy and governance
- Antigravity SDK also released for self-hosted deployments with full harness customization
- Pricing: not yet published (preview); check [Agent Platform docs](https://docs.cloud.google.com/gemini-enterprise-agent-platform/build/managed-agents)
- Builds on Gemini 3.5 Flash for the underlying model backend

Updated: `models/google.md`  
*Source: [Google Gemini API changelog — May 19, 2026](https://ai.google.dev/gemini-api/docs/changelog) · [Google Cloud Blog](https://cloud.google.com/blog/products/ai-machine-learning/innovations-from-google-io-26-on-google-cloud) — verified 2026-05-21*

---

### 🆕 Mistral: `mistral-ocr-2505` (OCR 2) retiring May 31, 2026 — migrate to `mistral-ocr-3`

**Provider:** [Mistral](models/mistral.md)  
Confirmed from the [official Mistral Models Overview deprecation table](https://docs.mistral.ai/models/overview): `mistral-ocr-2505` (Mistral OCR 2, released May 2025) was deprecated 2026-02-27 and **retires May 31, 2026**. Replacement is **`mistral-ocr-3`** (OCR 3).

This retirement was not previously tracked in this knowledge base.

| Model | API name | Retirement | Replace with |
|---|---|---|---|
| Mistral OCR 2 | `mistral-ocr-2505` | **2026-05-31** | `mistral-ocr-3` |

Updated: `deprecated.md`, `comparison.md`  
*Source: [Mistral Models Overview](https://docs.mistral.ai/models/overview) — verified 2026-05-21*

---

### ⚠️ Mistral: PyPI supply chain attack — `mistralai==2.4.6` was malicious (2026-05-11)

**Provider:** [Mistral](models/mistral.md)  
Security alert (not a model/API change). On May 11, 2026, attackers published `mistralai==2.4.6` to PyPI — a version Mistral AI never released. The package contained a backdoor that fires at import time on Linux, steals credentials (API keys, cloud tokens, CI/CD tokens, GitHub tokens), and in some cases triggers destructive commands.

**Who is affected:** Developers who installed `mistralai` via pip between ~May 10–12, 2026 on Linux systems.

**Immediate actions:**
1. `pip uninstall mistralai && pip install mistralai==2.4.5` (or latest legitimate version)
2. Rotate all secrets on the affected host
3. Check for `/tmp/transformers.pyz` and outbound connections to `83.142.209.194`

**Not affected:** Raw HTTP users; LiteLLM users (no `mistralai` SDK import).

Added security advisory section to `models/mistral.md`.  
*Source: [LiteLLM security advisory](https://docs.litellm.ai/blog/mistral-supply-chain-attack-may-2026) · [Aikido Security](https://www.aikido.dev/blog/mini-shai-hulud-is-back-tanstack-compromised) — 2026-05-12 · verified 2026-05-21*

---

### ⏱️ Reminders: **4 days** to gemini-3.1-flash-lite-preview shutdown; **10 days** to DeepSeek promo end & Mistral retirements

| Deadline | Days | Action |
|---|---|---|
| **2026-05-25** | 4 days | Migrate `gemini-3.1-flash-lite-preview` → `gemini-3.1-flash-lite` (GA, same pricing $0.25/$1.50) |
| **2026-05-26** | 5 days | Opt-in to new Gemini Interactions API schema — add `Api-Revision: 2026-05-26` header (raw HTTP) or upgrade Python/JS SDK ≥2.0.0. Legacy schema disabled June 8. |
| **2026-05-31** | 10 days | DeepSeek V4 Pro 75% promo ends → price reverts from $0.435 → **$1.74 per 1M input**, $0.87 → **$3.48 per 1M output** |
| **2026-05-31** | 10 days | Mistral retirements: `mistral-large-2411`, `pixtral-large-2411` → `mistral-large-latest`; `devstral-medium-2507` → `mistral-medium-3-5`; `voxtral-mini-2507` → `voxtral-mini-transcribe-2`; `mistral-ocr-2505` → `mistral-ocr-3` |
| **2026-06-01** | 11 days | Google: `gemini-2.0-flash`, `gemini-2.0-flash-lite` shut down |
| **2026-06-08** | 18 days | Gemini Interactions API legacy schema removed entirely |
| **2026-06-15** | 25 days | Anthropic: `claude-sonnet-4-20250514`, `claude-opus-4-20250514` retire; Agent SDK billing split takes effect |

*Verified 2026-05-21*

---

## 2026-05-20

### ⚠️ Gemini 3.5 Flash pricing CORRECTION — $2.70/$16.20 (not $1.50/$9.00)

**Provider:** [Google](models/google.md)  
The Gemini 3.5 Flash pricing recorded on 2026-05-19 was based on pre-launch estimates and was **incorrect**. The official Google AI Developer API pricing page (last updated **2026-05-19 UTC**) shows:

| Metric | Correct value | Previously recorded |
|---|---|---|
| Input (per 1M tokens) | **$2.70** | ~~$1.50~~ |
| Output (per 1M tokens, incl. thinking) | **$16.20** | ~~$9.00~~ |
| Context caching | **$0.27 / 1M** | ~~$0.15~~ |

All pricing ratios are consistent: output is 6× input; caching is 10% of input. This pricing positions Gemini 3.5 Flash above Gemini 3.1 Pro Preview ($2.00/$12.00) rather than below it — which aligns with Google's positioning of 3.5 Flash as their strongest model yet.

**Grounding:** 5,000 prompts/month free (shared across Gemini 3 family), then **$14 / 1,000 search queries**.

Updated: `models/google.md`, `comparison.md`  
*Source: [Google AI Developer API pricing page](https://ai.google.dev/gemini-api/docs/pricing) — last updated 2026-05-19 UTC · correction verified 2026-05-20*

---

### 🆕 Google: Gemini Omni Flash announced at I/O 2026 — consumer rollout only (API not yet available)

**Provider:** [Google](models/google.md)  
Google announced **Gemini Omni Flash** at Google I/O 2026 on May 19. It is an "any-to-any" model designed for video creation and editing from mixed inputs (text, audio, image, video).

**Status as of 2026-05-20:**
- ✅ Available in Gemini app, Google Flow, YouTube Shorts/Create for AI Plus/Pro/Ultra subscribers
- ❌ **No developer API yet** — Vertex AI / Gemini API access expected "in the coming weeks"
- No model ID, no token pricing, no quotas announced for API

**Do not plan production integrations yet.** Monitor for API launch announcement.

Updated: `models/google.md`  
*Source: [VentureBeat](https://venturebeat.com/ai/google-unveils-gemini-omni-any-to-any-ai-model-what-enterprises-should-know) · [Google Cloud Blog](https://cloud.google.com/blog/products/ai-machine-learning/innovations-from-google-io-26-on-google-cloud) — verified 2026-05-20*

---

### 🔄 Google: AI subscription tiers confirmed (exact pricing from Mashable/Google I/O)

**Provider:** [Google](models/google.md)  
Exact pricing confirmed for revised 3-tier structure announced at Google I/O 2026:

| Plan | Price | Key features |
|---|---|---|
| AI Plus | **$7.99/month** | Gemini 2.5 Flash + limited access |
| AI Pro | **$19.99/month** | Gemini 3 Flash, Deep Research, Veo 3.1, Jules coding agent |
| AI Ultra (new entry) | **$99.99/month** | 5× Pro limits, Gemini 3.5 Flash, priority Antigravity, 20 TB storage, YouTube Premium, Gemini Spark beta |
| AI Ultra (premium) | **$199.99/month** ↓ (was $250) | All Ultra features + highest limits |

Previous entry had AI Ultra at "$100/month" — corrected to $99.99/month. The premium tier drop from $250 → $200 was previously recorded; the exact new price is $199.99/month.

Updated: `models/google.md`  
*Source: [Mashable — Google I/O 2026 subscription tiers](https://mashable.com/article/google-io-2026-gemini-ultra-ai-subscription-tiers) — verified 2026-05-20*

---

### ⏱️ Reminders: **5 days** to gemini-3.1-flash-lite-preview shutdown; **11 days** to DeepSeek promo end & Mistral retirements

| Deadline | Days | Action |
|---|---|---|
| **2026-05-25** | 5 days | Migrate `gemini-3.1-flash-lite-preview` → `gemini-3.1-flash-lite` (GA, same pricing $0.25/$1.50) |
| **2026-05-26** | 6 days | Opt-in to new Gemini Interactions API schema (upgrade Python/JS SDK ≥2.0.0 or add `Api-Revision: 2026-05-26` header) — old schema disabled June 8 |
| **2026-05-31** | 11 days | DeepSeek V4 Pro 75% promo ends → price reverts from $0.435 → **$1.74 per 1M input**, $0.87 → **$3.48 per 1M output** |
| **2026-05-31** | 11 days | Mistral: `mistral-large-2411`, `pixtral-large-2411` retire → `mistral-large-latest`; `devstral-medium-2507` → `mistral-medium-3-5`; `voxtral-mini-2507` → `voxtral-mini-transcribe-2` |
| **2026-06-01** | 12 days | Google: `gemini-2.0-flash`, `gemini-2.0-flash-lite` shut down |
| **2026-06-15** | 26 days | Anthropic: `claude-sonnet-4-20250514`, `claude-opus-4-20250514` retire; Agent SDK billing split takes effect |

*Verified 2026-05-20*

---

## 2026-05-19

### 🆕 Google: Gemini 3.5 Flash launched at Google I/O 2026

**Provider:** [Google](models/google.md)  
Google announced **Gemini 3.5 Flash** at the Google I/O 2026 keynote (10am PT, May 19, 2026). CEO Sundar Pichai described it as faster than the previous Gemini 3.1 model and built for complex agentic tasks, longer workflows, and real-world developer use.

**Key specs:**

| Metric | Value |
|---|---|
| API name | `gemini-3.5-flash` |
| Context window | 1,000,000 tokens |
| Max output | 64,000 tokens |
| Input (standard) | **$1.50 / 1M** tokens |
| Output (standard) | **$9.00 / 1M** tokens |
| Context caching | $0.15 / 1M |
| Batch input | $0.75 / 1M |
| Batch output | $4.50 / 1M |
| Free tier | ✅ (rate-limited) |

**Key highlights:**
- ~4× faster output token generation than other frontier models (per Google benchmarking)
- Built for agentic multi-step tasks and long-horizon developer workflows
- Pricing sits between Gemini 3 Flash Preview ($0.50/$3.00) and Gemini 3.1 Pro Preview ($2.00/$12.00) — a strong mid-range speed-focused option
- Knowledge cutoff: January 2025
- Available as of keynote announcement (pricing confirmed on official Gemini API pricing page, last updated 2026-05-19)

Updated: `models/google.md`, `comparison.md`  
*Source: [Google I/O 2026 keynote](https://io.google/2026/) · [CNET I/O live blog](https://www.cnet.com/news-live/google-io-2026-live-news-updates/) · [Gemini API pricing](https://ai.google.dev/gemini-api/docs/pricing) — verified 2026-05-19*

---

### 🔄 Google: AI Ultra plan repriced — $250 → $200/month; new $100/month Ultra tier added

**Provider:** [Google](models/google.md)  
Announced at Google I/O 2026:
- **Google AI Ultra** (premium) price reduced from **$250/month → $200/month**
- New **Google AI Ultra** tier at **$100/month** added — provides access to Gemini 3.5 Flash and Gemini 3.1 Pro
- Competes directly with Anthropic Max 5x ($100/month) and OpenAI Pro ($100/month)

Updated: `models/google.md`  
*Source: [CNET I/O live blog](https://www.cnet.com/news-live/google-io-2026-live-news-updates/) · [Google One](https://one.google.com/intl/en/about/google-ai-plans/) — 2026-05-19*

---

## 2026-05-18

### 🔭 Google I/O 2026 TOMORROW (May 19, 10am PT) — Gemini model announcement confirmed

**Provider:** [Google](models/google.md)  
Google I/O 2026 main keynote is **tomorrow, May 19, 2026 at 10am PT** (1pm ET). Developer keynote follows at 1:30pm PT. A new major Gemini model is confirmed as the centerpiece announcement. Reports describe it as "roughly in the class of OpenAI's recent GPT-5.5" (Sources.news/Alex Heath), or a "Gemini 4.0" (Android Authority), or "Gemini 3.5" per some outlets — the exact version numbering is unconfirmed.

**Expected API changes (unconfirmed until keynote):**
- New Gemini model IDs (likely `gemini-4.0-*` or `gemini-3.5-*` family)
- Possible pricing changes from current `gemini-3.1-pro-preview` ($2.00/$12.00 per 1M)
- Gemini Omni: unified text/image/video model surfaced in UI strings
- Deep Think reasoning mode for broader access (beyond Ultra subscribers)
- "Gemini Intelligence": new agentic AI push for Android

**No API changes recorded today.** This knowledge base will update immediately after confirmed pricing and API details are published post-keynote.

*Source: Android Authority (2026-05-12), Yahoo Tech (2026-05-14), AIxploria (2026-05-17), AndroidCentral live blog (2026-05-18)*

---

### 🆕 OpenAI: `gpt-realtime-1.5` and `gpt-realtime-mini` added to catalog

**Provider:** [OpenAI](models/openai.md)  
Two previously un-catalogued realtime voice models confirmed on the official OpenAI pricing page. Added to `models/openai.md`.

| Model | Audio in | Cached audio in | Audio out | Text in | Text out | Notes |
|---|---|---|---|---|---|---|
| `gpt-realtime-1.5` | $32.00/1M | $0.40/1M | $64.00/1M | $4.00/1M | **$16.00/1M** | Legacy; lower text-out rate than gpt-realtime-2 ($24.00) |
| `gpt-realtime-mini` | $10.00/1M | $0.30/1M | $20.00/1M | $0.60/1M | $2.40/1M | Budget realtime voice; ~3× cheaper than gpt-realtime-2 |

`gpt-realtime-1.5` is the predecessor to `gpt-realtime-2` (launched 2026-05-07). `gpt-realtime-mini` is a budget variant for cost-sensitive voice deployments. Both remain available alongside `gpt-realtime-2`.

Updated: `models/openai.md`  
*Source: [OpenAI API pricing](https://developers.openai.com/api/docs/pricing) — verified 2026-05-18*

---

### ⏱️ Reminders: 7 days to gemini-3.1-flash-lite-preview shutdown; 8 days to Gemini Interactions API schema change; 13 days to DeepSeek promo end & Mistral retirements

| Deadline | Days | Action |
|---|---|---|
| **2026-05-25** | 7 days | Migrate `gemini-3.1-flash-lite-preview` → `gemini-3.1-flash-lite` (GA, same pricing $0.25/$1.50) |
| **2026-05-26** | 8 days | Opt-in to new Gemini Interactions API schema (Python SDK ≥2.0.0 / JS SDK ≥2.0.0 automatic; raw HTTP add `Api-Revision: 2026-05-26` header). Legacy schema disabled **June 8** |
| **2026-05-31** | 13 days | DeepSeek V4 Pro 75% promo ends → price reverts to **$1.74/$3.48 per 1M** (from $0.435/$0.87) |
| **2026-05-31** | 13 days | Mistral: `mistral-large-2411`, `pixtral-large-2411` → `mistral-large-latest`; `devstral-medium-2507` → `mistral-medium-3-5`; `voxtral-mini-2507` → `voxtral-mini-transcribe-2` |
| **2026-06-15** | 28 days | Anthropic Agent SDK billing split takes effect; `claude-sonnet-4-20250514` / `claude-opus-4-20250514` retire |

*Verified 2026-05-18*

---

### 📊 OpenAI: ChatGPT personal finance feature launched (Pro US only, May 15)

**Provider:** [OpenAI](models/openai.md)  
On May 15, 2026, OpenAI launched a **personal finance experience** in ChatGPT for Pro subscribers in the U.S. Users can connect bank accounts (via Plaid, Intuit coming soon) and get financial dashboards and AI-powered advice. This is a **ChatGPT product feature, not an API change** — no new model IDs or pricing. Built on the GPT-5.5 stack; will expand to Plus users after the Pro preview period.

**Developer note:** No API changes. Financial data is user-owned, can be disconnected anytime, not used in ChatGPT Memory by default.

*Source: [OpenAI — A new personal finance experience in ChatGPT](https://openai.com/index/personal-finance-chatgpt/) — 2026-05-15*

---

## 2026-05-17

### ⚠️ Anthropic: Claude Agent SDK usage split into dedicated credit pool — effective June 15, 2026

**Provider:** [Anthropic](models/anthropic.md)  
Anthropic [announced](https://x.com/ClaudeDevs/status/2054610152817619388) a major billing change for Claude Code subscriptions, effective **June 15, 2026**: programmatic/autonomous Claude usage is being separated from interactive usage into its own credit pool, billed at standard API rates.

**What's changing:**
- **Human-in-the-loop usage** (Claude Code terminal, web chat, desktop app, Cowork): continues drawing from existing subscription limits as before.
- **Autonomous / programmatic usage** (Agent SDK, `claude -p`, GitHub Actions, third-party tools like OpenClaw/Zed/Cursor): **moves to a new monthly Agent SDK credit**, billed at standard API token rates.

**Agent SDK credits by plan:**

| Plan | Monthly Agent SDK credit | Overage |
|---|---|---|
| Pro ($20/mo) | $20 in API credits | Billed at standard API rates if extra usage enabled; stops if not |
| Max 5x ($100/mo) | $100 in API credits | Billed at standard API rates if extra usage enabled |
| Max 20x ($200/mo) | $200 in API credits | Billed at standard API rates if extra usage enabled |

**Developer impact:** Subscriptions previously subsidized autonomous agent workloads at roughly 15–30× cheaper than API rates. With the credit pool billed at API rates ($5/$25 per 1M on Opus 4.7; $3/$15 on Sonnet 4.6), heavy autonomous workflows will cost significantly more starting June 15. Users who relied on OpenClaw, Zed (via ACP), or `claude -p` pipelines for long-running agent tasks are most affected.

**Context:** Anthropic's April 4 change (banning third-party agent tools from subscriptions entirely) was partly reversed — tools like OpenClaw are now re-allowed, but placed on the metered credit pool rather than the main subscription. This is a structured middle path. Note that the Zed editor, which uses ACP (Agent Client Protocol), is now in the same bucket as third-party agent frameworks for billing purposes.

Updated: `models/anthropic.md`  
*Source: [Anthropic — Use the Claude Agent SDK with your Claude plan](https://support.claude.com/en/articles/15036540-use-the-claude-agent-sdk-with-your-claude-plan) · [InfoWorld](https://www.infoworld.com/article/4171274/anthropic-puts-claude-agents-on-a-meter-across-its-subscriptions.html) · [Zed Blog](https://zed.dev/blog/anthropic-subscription-changes) — 2026-05-14 · verified 2026-05-17*

---

### ⏱️ Reminders: 8 days to gemini-3.1-flash-lite-preview shutdown; 14 days to DeepSeek promo end

| Deadline | Action |
|---|---|
| **2026-05-25** (8 days) | Migrate `gemini-3.1-flash-lite-preview` → `gemini-3.1-flash-lite` (GA, same $0.25/$1.50 pricing) |
| **2026-05-31** (14 days) | DeepSeek V4 Pro promo ends → price reverts to **$1.74/$3.48 per 1M tokens** (from $0.435/$0.87) |
| **2026-05-31** (14 days) | Mistral retirements: `mistral-large-2411`, `pixtral-large-2411` → `mistral-large-latest`; `devstral-medium-2507` → `mistral-medium-3-5`; `voxtral-mini-2507` → `voxtral-mini-transcribe-2` |

*Verified 2026-05-17*

---

## 2026-05-16

### 🆕 xAI: Grok Build coding agent launched (early beta, SuperGrok Heavy only)

**Provider:** [xAI](models/xai.md)  
xAI launched **Grok Build** on May 14, 2026 — an early beta coding agent and CLI targeting professional software engineering. Available now for **SuperGrok Heavy** subscribers ($300/month); broader availability not yet announced.

**Key capabilities:**
- Interactive TUI with plan mode (review/approve before execution)
- Parallel subagents for complex multi-step tasks
- Headless mode (`-p`) for scripts and CI automations
- Agent Client Protocol (ACP) for building orchestration apps
- Compatible with AGENTS.md, existing plugins, hooks, skills, MCP servers
- Underlying model: `grok-4.3` (standard API pricing applies when using API key)

**Developer context:** Enters a crowded market vs. Anthropic's Claude Code and OpenAI's Codex CLI, both of which have significant head starts in IDE integrations and production deployments. xAI CEO Elon Musk acknowledged in March 2026 that xAI has lagged behind competitors in coding.

Updated: `models/xai.md`  
*Source: [xAI — Introducing Grok Build Early Beta](https://x.ai/news/grok-build-cli) — 2026-05-14 · Engadget, PCMag, CIO Dive — 2026-05-15 — verified 2026-05-16*

---

### 🆕 OpenAI: GPT-5.3-Codex documented in catalog (released 2026-02-24)

**Provider:** [OpenAI](models/openai.md)  
Added a dedicated entry for `gpt-5.3-codex` to the OpenAI model catalog. This model was released February 24, 2026 and is the backbone of OpenAI's Codex product (cloud tasks, code reviews). Previously mentioned only as a pricing line item; now fully documented.

| Field | Value |
|---|---|
| API name | `gpt-5.3-codex` |
| Context window | 400,000 tokens |
| Input | $1.75 / 1M |
| Output | $14.00 / 1M |
| Cached input | $0.175 / 1M |
| Priority tier | $3.50 / $28.00 per 1M |
| GPQA Diamond | 91.5% |
| Knowledge cutoff | 2025-08-31 |

**Note:** `GPT-5.3-Codex-Spark` (research preview, Pro only) is a faster day-to-day variant; pricing TBD.

Updated: `models/openai.md`, `comparison.md`  
*Source: [OpenRouter gpt-5.3-codex](https://openrouter.ai/openai/gpt-5.3-codex) · [PricePerToken](https://pricepertoken.com/pricing-page/model/openai-gpt-5.3-codex) · [OpenAI API pricing](https://developers.openai.com/api/docs/pricing) — verified 2026-05-16*

---

### ⚠️ Mistral: 4 additional models retiring May 31 & July 31, 2026

**Provider:** [Mistral](models/mistral.md)  
Added four previously-untracked Mistral deprecations to `deprecated.md` (source: [Mistral Models Overview](https://docs.mistral.ai/models/overview)):

**Retiring May 31, 2026:**
- `mistral-large-2411` → `mistral-large-latest` *(was previously tracked)*
- `pixtral-large-2411` → `mistral-large-latest` *(new)*
- `devstral-medium-2507` → `mistral-medium-3-5` *(new)*
- `voxtral-mini-2507` → `voxtral-mini-transcribe-2` *(new)*

**Retiring July 31, 2026:**
- `mistral-small-2506` → `mistral-small-2603` (Mistral Small 4) *(new)*
- `magistral-small-2509` → `mistral-small-2603` (Mistral Small 4) *(new)*

Updated: `deprecated.md`, `comparison.md`  
*Source: [Mistral Models Overview](https://docs.mistral.ai/models/overview) — verified 2026-05-16*

---

### 🔭 Google I/O 2026 (May 19): New Gemini model confirmed, "GPT-5.5 class" per leaks

**Provider:** [Google](models/google.md)  
Google I/O 2026 is **3 days away** (May 19, 2026). Sources close to Google (The Verge/Sources.news reporter Alex Heath, May 14) confirm a new Gemini model will be announced — described as "roughly in the class of OpenAI's recent GPT-5.5." Google is under particular internal pressure to improve coding capabilities.

**Additional leaks (May 12–14):**
- Forbes: 7 hidden Gemini Live voice models in internal testing (variants with codenames "Capybara" and "Nitrogen"); one identified itself as "Gemini 3.1 Pro" when queried
- Chrome Unboxed / 9to5Google: **Gemini Omni** — a new video generation/editing model surfacing for select users, capable of video remixing, in-chat editing, template creation

**What to do:** No API changes yet. Watch for announcements May 19. This knowledge base will update immediately after confirmed pricing/specs.

*Source: [Sources.news — Alex Heath, 2026-05-14](https://sources.news/p/google-about-to-release-new-gemini) · Mashable (2026-05-14) · Forbes (2026-05-12)*

---

### ⏱️ Reminder: DeepSeek V4 Pro promo ends May 31 (15 days)

**Provider:** [DeepSeek](models/deepseek.md)  
The 75% promotional discount on DeepSeek V4 Pro expires **May 31, 2026 at 15:59 UTC** — 15 days from today. Post-promo prices revert to **$1.74 input / $3.48 output** per 1M tokens (from current $0.435/$0.87).

If you are evaluating V4 Pro for budget planning, use the post-promo list price in your projections. The promotional window ends in 15 days.

*Source: [DeepSeek API pricing](https://api-docs.deepseek.com/quick_start/pricing) — verified 2026-05-16*

---

## 2026-05-15

### ✅ xAI: May 15 retirements COMPLETED — slugs redirect (not error); silent 6× cost risk

**Provider:** [xAI](models/xai.md)  
The 8 model retirements announced for today (2026-05-15 at 12pm PT) are now effective. **Critical correction from prior entries:** The retired model slugs **do not return errors** — they **automatically redirect to `grok-4.3`** per the [official xAI migration guide](https://docs.x.ai/developers/migration/may-15-retirement). Previous changelog entries (2026-05-13 and 2026-05-14) incorrectly stated that "requests will no longer work" and "return errors."

**What this means for developers:**
- Code that still uses `grok-4-fast-reasoning`, `grok-4-1-fast-non-reasoning`, `grok-4-0709`, `grok-code-fast-1`, `grok-3`, etc. will **not break immediately**
- However, those requests are now **silently billed at `grok-4.3` pricing** ($1.25 input / $2.50 output per 1M tokens)
- If you relied on the Fast model pricing ($0.20 input / $0.50 output), you are now paying **~6× more per request** without any API error to alert you
- `grok-imagine-image-pro` redirects to `grok-imagine-image-quality`

**Action required:** Update your `model` field explicitly. Even if your code doesn't break, staying on old slugs means you lose the ability to control `reasoning_effort` and you will be over-paying.

Updated: `models/xai.md`, `comparison.md`, `deprecated.md`  
*Source: [xAI Migration Guide — May 15 Retirement](https://docs.x.ai/developers/migration/may-15-retirement) — verified 2026-05-15*

---

### 🔧 xAI: Voice API TTS pricing corrected — $4.20/1M chars (launch) → $15.00/1M chars (current official)

**Provider:** [xAI](models/xai.md)  
The xAI Voice API launched on **2026-04-17** with TTS priced at **$4.20 / 1M characters**. The official xAI pricing page (last updated 2026-05-09) now shows **$15.00 / 1M characters** for TTS. This is a 3.6× increase from the launch price. STT pricing is unchanged.

| Mode | Launch price (2026-04-17) | Current price (2026-05-09) |
|---|---|---|
| TTS (Text-to-Speech) | $4.20 / 1M characters | **$15.00 / 1M characters** |
| STT REST (batch) | $0.10 / hour | $0.10 / hour (unchanged) |
| STT WebSocket (streaming) | $0.20 / hour | $0.20 / hour (unchanged) |
| Voice Agent (realtime) | $0.05 / min ($3.00/hr) | $0.05 / min ($3.00/hr) (unchanged) |

Even at $15.00/1M, Grok TTS is still significantly cheaper than OpenAI TTS ($30.00/1M characters via Realtime API context), Google WaveNet ($16.00/1M), Azure TTS ($16.00/1M), and ElevenLabs (~$50.00/1M). STT ($0.10/hr batch) remains the market's lowest.

Updated: `models/xai.md`  
*Source: [xAI Pricing docs](https://docs.x.ai/developers/pricing) — verified 2026-05-15*

---

### 🆕 xAI: `grok-4.20-multi-agent-0309` added to official pricing page

**Provider:** [xAI](models/xai.md)  
The official xAI pricing page now lists `grok-4.20-multi-agent-0309` as a distinct model ID alongside `grok-4.20-0309-reasoning` and `grok-4.20-0309-non-reasoning`. Pricing is identical: **$1.25 / 1M input · $2.50 / 1M output · $0.20 / 1M cached input**. 2M context window. This model ID explicitly exposes the multi-agent (4-agent parallel reasoning) capability that was previously available only via the standard `grok-4.20` alias.

Updated: `models/xai.md`  
*Source: [xAI Pricing docs](https://docs.x.ai/developers/pricing) — verified 2026-05-15*

---

## 2026-05-14

### 🔧 Anthropic: Claude Sonnet 4 / Opus 4 retirement date CORRECTED — June 15, 2026 (not May 14)

**Provider:** [Anthropic](models/anthropic.md)  
The previous changelog entry (2026-05-13) stated that `claude-sonnet-4-*` and `claude-opus-4-*` were shutting down "TOMORROW (May 14, 2026)". This was **incorrect**. The [official Anthropic model deprecations page](https://platform.claude.com/docs/en/about-claude/model-deprecations) clearly shows:

- `claude-sonnet-4-20250514` — deprecated 2026-04-14 — **retirement: June 15, 2026**
- `claude-opus-4-20250514` — deprecated 2026-04-14 — **retirement: June 15, 2026**

The error arose from misreading the "Not before 2026-05-14" language in our legacy model table, which was a minimum retention guarantee, not the actual retirement date. Corrected in `deprecated.md`, `models/anthropic.md`, and `comparison.md`.

| Field | Previous (incorrect) | Corrected |
|---|---|---|
| Sonnet 4 retirement | 2026-05-14 | **2026-06-15** |
| Opus 4 retirement | 2026-05-14 | **2026-06-15** |

*Source: [Anthropic model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations) — verified 2026-05-14*

---

### ⚠️ Anthropic: Claude Opus 4.7 — new tokenizer uses up to 35% more tokens than Opus 4.6

**Provider:** [Anthropic](models/anthropic.md)  
Per-token pricing for Opus 4.7 is **unchanged** from Opus 4.6 at $5.00/$25.00 per 1M tokens. However, Opus 4.7 ships with a new tokenizer that may use **up to 35% more tokens** for identical input text. The effective per-request cost can therefore be up to 1.35× higher than Opus 4.6 for the same content — even though the rate card looks identical.

Highest impact cases:
- **Code** — token count can be significantly higher
- **Structured data** (JSON, XML) — longer token representations
- **Non-English text** — tokenizer changes disproportionately affect non-Latin scripts

Recommended action: after migrating to `claude-opus-4-7`, monitor actual token counts in API responses and re-benchmark costs before finalizing production budgets.

Added note to `models/anthropic.md`.  
*Source: [CloudZero — Opus 4.7 tokenizer analysis](https://www.cloudzero.com/blog/claude-opus-4-7-pricing/) — verified 2026-05-14*

---

### 🚨 xAI: 8 models retire TODAY (May 15, 2026 at 12pm PT)

**Provider:** [xAI](models/xai.md)  
Today is the deadline. **Effective 2026-05-15 at 12:00pm PT**, the following xAI models will return errors on all API requests:

| Retiring model | Replacement |
|---|---|
| `grok-4-1-fast-reasoning` | `grok-4.3` |
| `grok-4-1-fast-non-reasoning` | `grok-4.3` (reasoning_effort: none) |
| `grok-4-fast-reasoning` | `grok-4.3` |
| `grok-4-fast-non-reasoning` | `grok-4.3` (reasoning_effort: none) |
| `grok-4-0709` | `grok-4.3` |
| `grok-code-fast-1` | `grok-4.3` |
| `grok-3` | `grok-4.3` |
| `grok-imagine-image-pro` | `grok-imagine-image-quality` |

**Cost impact reminder:** `grok-4.3` ($1.25/$2.50 per 1M) is ~6× more expensive than the retired Fast models ($0.20/$0.50). Evaluate whether you need `grok-4.3` or if a cheaper alternative (e.g. Mistral Small 4 at $0.15/$0.60) fits your use case.

Updated `deprecated.md`, `models/xai.md`, and `comparison.md`.  
*Source: [xAI Migration Guide — May 15 Retirement](https://docs.x.ai/developers/migration/may-15-retirement) — verified 2026-05-14*

---

### 🔭 Google I/O 2026 (May 19): Gemini 4.0 expected in 4 days

**Provider:** [Google](models/google.md)  
Google I/O 2026 is **4 days away** (May 19, 2026, 10am PT). All major tech outlets (CNET, Android Authority, Mashable, PCMag) confirm a major Gemini model update — "Gemini 4.0" or similar — is the centerpiece announcement. Additional expected announcements:
- **Gemini 4.0 API:** New API model IDs, context window expansion, unified native multimodal (images/text/audio/video/code in one model)
- **"Remy" agent:** Proactive agentic capability for Gemini (emails, calendar, tasks)
- **Veo / Lyria updates**: Next-gen video and music generation
- **Android XR smart glasses** (first consumer devices)
- **Aluminum OS / Googlebook**: Android-based desktop OS + premium laptop category

No confirmed API names, pricing, or benchmarks yet. This knowledge base will be updated immediately after official announcements on May 19.

*Source: CNET (2026-05-13), Mashable (2026-05-14), Android Authority (2026-05-12), PCMag (2026-05-13)*

---

## 2026-05-13

### 🔄 xAI: Grok 4.20 pricing corrected — $2.00/$6.00 → $1.25/$2.50 per 1M tokens

**Provider:** [xAI](models/xai.md)  
The official xAI API pricing page (`docs.x.ai/developers/pricing`, last updated May 9, 2026) now shows `grok-4.20-0309-reasoning` and `grok-4.20-0309-non-reasoning` priced at **$1.25 input / $2.50 output** per 1M tokens — the same as Grok 4.3. The previous entry in `models/xai.md` still showed the old $2.00/$6.00 rates from before the Grok 4.3 launch. Corrected now.

| Field | Old value | Corrected value |
|---|---|---|
| Grok 4.20 input | $2.00 / 1M | **$1.25 / 1M** |
| Grok 4.20 output | $6.00 / 1M | **$2.50 / 1M** |

Updated: `models/xai.md`  
*Source: [xAI Pricing](https://docs.x.ai/developers/pricing) — verified 2026-05-13*

---

### ⚠️ Anthropic: Claude Sonnet 4 + Opus 4 shut down TOMORROW (2026-05-14)

**Provider:** [Anthropic](models/anthropic.md)  
Both `claude-sonnet-4-*` and `claude-opus-4-*` retire **tomorrow, May 14, 2026**. If you are still using either model in production, you must migrate today.  
- `claude-sonnet-4-*` → `claude-sonnet-4-6` (same price: $3.00/$15.00 per 1M)  
- `claude-opus-4-*` → `claude-opus-4-7` (same price: $5.00/$25.00 per 1M)

Updated urgency counters in `deprecated.md` and `comparison.md`.  
*Source: [Anthropic model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations) — verified 2026-05-13*

---

### ⚠️ xAI: 8 models retire in 2 days (2026-05-15 at 12pm PT)

**Provider:** [xAI](models/xai.md)  
Countdown update: `grok-4-fast-reasoning`, `grok-4-fast-non-reasoning`, `grok-4-1-fast-reasoning`, `grok-4-1-fast-non-reasoning`, `grok-4-0709`, `grok-code-fast-1`, `grok-3`, and `grok-imagine-image-pro` all retire **May 15 at 12:00pm PT — in 2 days**.  
- Recommended replacement for all: `grok-4.3` (see [migration guide](https://docs.x.ai/developers/migration/may-15-retirement))  
- **Cost impact warning:** `grok-4.3` ($1.25/$2.50) is ~6× more expensive than `grok-4.1-fast` ($0.20/$0.50). If cost is the primary concern, consider `grok-4.20-non-reasoning` ($1.25/$2.50) or evaluate whether the Grok Fast models can be replaced with a cheaper alternative (e.g. Mistral Small 4 at $0.15/$0.60).

Updated urgency counters in `deprecated.md` and `comparison.md`.  
*Source: [xAI Migration Guide — May 15 Retirement](https://docs.x.ai/developers/migration/may-15-retirement) — verified 2026-05-13*

---

### 🔭 Google I/O 2026 (May 19): Gemini 4.0 / Gemini Omni expected

**Provider:** [Google](models/google.md)  
Google I/O 2026 is scheduled for **May 19–20, 2026**. Multiple leaks and media reports indicate Google is expected to announce a next-generation Gemini model (variously called "Gemini 4.0" or "Gemini Omni") with significantly upgraded multimodal (video, audio, text, image) capabilities. Separately, **Gemini Omni** has leaked as a new video-generation model. No confirmed API names, pricing, or benchmarks as of today.

**Action required:** None yet — no API changes. Watch for announcements on May 19. This note will be updated as soon as official model specs and pricing are published.  
*Source: CNET (2026-05-09), Android Authority (2026-05-12), Gadgets360 (2026-05-12), FelloAI (2026-05-12)*

---

## 2026-04-18

### 🔄 DeepSeek: API pricing corrected back to V3.2 — $0.28/$0.42 per 1M tokens (reverts 2026-04-14 entry)

**Provider:** [DeepSeek](models/deepseek.md)  
The official DeepSeek API docs (re-verified 2026-04-18) now clearly state that both `deepseek-chat` and `deepseek-reasoner` correspond to **DeepSeek-V3.2**, priced at **$0.28 input / $0.42 output** per 1M tokens (cache miss), with cache-hit input at **$0.028/1M** (90% discount). This corrects the 2026-04-14 entry which logged V3.1-Terminus at $0.56/$1.68 — that appears to have been a transient documentation change that has since been reverted, or a data error. Current official pricing is back to the V3.2 standard rates.

| Field | 2026-04-14 (incorrect) | 2026-04-18 (corrected) |
|---|---|---|
| Model behind endpoints | DeepSeek-V3.1-Terminus | **DeepSeek-V3.2** |
| Input (cache miss) | $0.56 / 1M | **$0.28 / 1M** |
| Input (cache hit) | $0.07 / 1M | **$0.028 / 1M** |
| Output | $1.68 / 1M | **$0.42 / 1M** |

Updated: `models/deepseek.md`, `comparison.md`  
*Source: [DeepSeek API Docs — Models & Pricing](https://api-docs.deepseek.com/quick_start/pricing) — verified 2026-04-18*

---

### 🆕 xAI: Grok 4.3 Beta spotted in early access on Grok.com (no API/pricing yet)

**Provider:** [xAI](models/xai.md)  
On April 17, 2026, multiple users discovered **"Grok 4.3 (beta)"** listed as an "Early Access" option in Grok.com's model selector. No official xAI announcement or API pricing has been published. Reported improvements include enhanced ultra-long context handling and native multimodal video understanding. Available to SuperGrok Heavy subscribers ($300/month). No action required for API developers — no model ID or pricing to act on yet.

*Source: KuCoin Flash (2026-04-17), BlockBeats — verified 2026-04-18*

---

### ⚠️ Anthropic Claude 3 Haiku retires in 2 days (2026-04-20)

**Provider:** [Anthropic](models/anthropic.md)  
Countdown update: Claude 3 Haiku (`claude-3-haiku-20240307`) retires **April 20, 2026** — **2 days from today**. Updated urgency counters in `deprecated.md`, `models/anthropic.md`.  
*Migrate to `claude-haiku-4-5-20251001` immediately. Price change on migration: $0.25/$1.25 → $1.00/$5.00 per 1M tokens (+4×).*

---

### ⚠️ xAI: Files and Collections storage billing starts in 2 days (2026-04-20)

**Provider:** [xAI](models/xai.md)  
Reminder: xAI Files and Collections storage billing begins **April 20, 2026** — 2 days from today. Developers using the Files or Collections APIs for persistent storage (RAG, document retrieval) should review usage at `console.x.ai/team/default/files` before this date.  
*Source: [xAI Models & Pricing docs](https://docs.x.ai/developers/models) — previously tracked 2026-04-17*

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
