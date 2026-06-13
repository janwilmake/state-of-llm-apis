# Deprecated & Sunset Models

> Track sunset dates and migration paths. **Last updated:** 2026-06-13.
>
> ⚠️ = Deprecated, still accessible. ❌ = Shut down, no longer accessible.

---

## Upcoming Shutdowns (Action Required)

### Anthropic — June 15, 2026 🚨 **2 DAYS**

| Model | API name | Deprecated | Shutdown date | Replacement |
|---|---|---|---|---|
| Claude Sonnet 4 | `claude-sonnet-4-20250514` | 2026-04-14 | **2026-06-15** | `claude-sonnet-4-6` |
| Claude Opus 4 | `claude-opus-4-20250514` | 2026-04-14 | **2026-06-15** | `claude-opus-4-7` |

⚠️ **Correction (2026-05-14):** The actual retirement date is **June 15, 2026** — not May 14. Previous changelog entries incorrectly stated May 14 as the shutdown date. The "Not before 2026-05-14" language in the legacy model table was a minimum retention guarantee, not the retirement date. Verified against the [official Anthropic model deprecations page](https://platform.claude.com/docs/en/about-claude/model-deprecations).

Migrate before June 15. Same pricing tier ($3/$15 for Sonnet 4.6; $5/$25 for Opus 4.7).  
*Source: [Anthropic model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations) — verified 2026-05-14*

> ⚠️ **Also on June 15:** Anthropic's **Agent SDK billing split** takes effect. Autonomous/programmatic Claude Code usage (Agent SDK, `claude -p`, GitHub Actions, third-party tools like OpenClaw/Zed/Cursor) moves from the shared subscription pool to a dedicated monthly credit billed at API rates. Credits: Pro = $20, Max 5x = $100, Max 20x = $200. See [anthropic.md](models/anthropic.md) for details. Announced 2026-05-14.

---

### xAI — May 15, 2026 Retirements ✅ COMPLETED (2026-05-15)

**Effective 2026-05-15 at 12:00 pm PT**, the following models were retired from the xAI API. Requests to these IDs now **automatically redirect to `grok-4.3`** (not return errors as previously noted — see correction below).

| Model retired | Auto-redirect | Explicit replacement |
|---|---|---|
| `grok-4-1-fast-reasoning` | `grok-4.3` (low reasoning) | `grok-4.3` |
| `grok-4-1-fast-non-reasoning` | `grok-4.3` (no reasoning) | `grok-4.3` |
| `grok-4-fast-reasoning` | `grok-4.3` (low reasoning) | `grok-4.3` |
| `grok-4-fast-non-reasoning` | `grok-4.3` (no reasoning) | `grok-4.3` |
| `grok-4-0709` | `grok-4.3` (low reasoning) | `grok-4.3` |
| `grok-code-fast-1` | `grok-4.3` (low reasoning) | `grok-4.3` |
| `grok-3` | `grok-4.3` (no reasoning) | `grok-4.3` |
| `grok-imagine-image-pro` | `grok-imagine-image-quality` | `grok-imagine-image-quality` |

> ⚠️ **Correction (2026-05-15):** Previous changelog entries stated retired slugs "will return errors." The actual behavior per the [official xAI migration guide](https://docs.x.ai/developers/migration/may-15-retirement) is that **slugs redirect to `grok-4.3`**. However, if you haven't explicitly updated your `model` field, you are now being **silently billed at `grok-4.3` rates** ($1.25/$2.50 per 1M) instead of Fast model rates ($0.20/$0.50) — a ~6× cost increase. Update your `model` field immediately.

*Source: [xAI Migration Guide — May 15 Retirement](https://docs.x.ai/developers/migration/may-15-retirement) — verified 2026-05-15*

---

### Google Gemini — May 25, 2026

| Model | Shutdown date | Migrate to |
|---|---|---|
| `gemini-3.1-flash-lite-preview` | **2026-05-25** | `gemini-3.1-flash-lite` (GA, identical pricing) |

> Deprecated 2026-05-11. The stable GA model `gemini-3.1-flash-lite` was released 2026-05-07. Same pricing ($0.25/$1.50 per 1M tokens), same model. Just update the model ID.  
*Source: [Google Gemini API changelog](https://ai.google.dev/gemini-api/docs/changelog) — verified 2026-05-12*

---

### ⚠️ Gemini Interactions API — Breaking Schema Change (May 26 / June 8, 2026)

This is a **code change**, not a model retirement, but it will break integrations that use the Interactions API (v1beta).

| Deadline | Event |
|---|---|
| **2026-05-26** | New schema becomes default; old schema still works with explicit `Api-Revision` header |
| **2026-06-08** | Legacy schema removed entirely — integrations without SDK update will break |

**What's changing:** `outputs` array → `steps` schema; `response_format` field restructured.  
**Fix:** Upgrade Python SDK to ≥2.0.0 or JavaScript SDK to ≥2.0.0. Or add `Api-Revision: 2026-05-26` header to raw HTTP requests.  
*Source: [Google — Interactions API: Breaking changes migration guide (May 2026)](https://ai.google.dev/gemini-api/docs/interactions-breaking-changes-may-2026) — 2026-05-06 · verified 2026-05-12*

---

### Google Gemini — June 2026 deadlines

**2026-06-01** ❌ COMPLETED: `gemini-2.0-flash` and `gemini-2.0-flash-lite` shut down. See "Already Shut Down" section.

**2026-06-25** — ⚠️ **13 DAYS** — Google Gemini image preview models retiring:

| Model | Shutdown date | Migrate to |
|---|---|---|
| `gemini-3.1-flash-image-preview` | **2026-06-25** ⚠️ | `gemini-3.1-flash-image` (GA as of 2026-05-28) |
| `gemini-3-pro-image-preview` | **2026-06-25** ⚠️ | `gemini-3-pro-image` (GA as of 2026-05-28) |

*Source: [Google Gemini API changelog — May 28, 2026](https://ai.google.dev/gemini-api/docs/changelog) — verified 2026-06-12*

---

**2026-06-24** — ⚠️ **12 DAYS** — Imagen 4.0 models retiring on the Gemini Developer API:

| Model | Shutdown date | Migrate to |
|---|---|---|
| `imagen-4.0-generate-001` | **2026-06-24** ⚠️ | `gemini-3-pro-image-preview` or `gemini-2.5-flash-image` |
| `imagen-4.0-ultra-generate-001` | **2026-06-24** ⚠️ | `gemini-3-pro-image-preview` or `gemini-2.5-flash-image` |
| `imagen-4.0-fast-generate-001` | **2026-06-24** ⚠️ | `gemini-3-pro-image-preview` or `gemini-2.5-flash-image` |

*Source: [Google Gemini Deprecations](https://ai.google.dev/gemini-api/docs/deprecations) — verified 2026-06-12*

---

**2026-10-16** — `gemini-2.5-pro`, `gemini-2.5-flash`, `gemini-2.5-flash-lite` retiring:

> ⚠️ **Dates corrected (2026-06-12):** The official [Google Gemini deprecations page](https://ai.google.dev/gemini-api/docs/deprecations) (last updated 2026-06-01) shows **October 16, 2026** as the shutdown date for all three models — NOT June 17 / July 22 as previously tracked. The June 17 date appeared in an earlier version of the page as "earliest possible" but has since been updated. Take no migration action before October 16.

| Model | Shutdown date | Migrate to |
|---|---|---|
| `gemini-2.5-pro` | **2026-10-16** | `gemini-3.1-pro-preview` or `gemini-3.5-flash` |
| `gemini-2.5-flash` | **2026-10-16** | `gemini-3.5-flash` |
| `gemini-2.5-flash-lite` | **2026-10-16** | `gemini-3.1-flash-lite` (GA) |

**Migration price notes:**
- `gemini-2.5-pro` ($1.25/$10.00) → `gemini-3.1-pro-preview` ($2.00/$12.00): ~1.6× price increase; or → `gemini-3.5-flash` ($1.50/$9.00) for faster agentic workloads at similar cost
- `gemini-2.5-flash` ($0.30/$2.50) → `gemini-3.5-flash` ($1.50/$9.00): 5× output price increase but dramatically better benchmarks

*(Previous June 1 entries moved to "Already Shut Down" section below.)*

> ⚠️ **Note (Vertex AI):** As of 2026-03-06, `gemini-2.0-flash-001` and `gemini-2.0-flash-lite-001` are unavailable to **new** Vertex AI projects. Existing customers retain access until June 1, 2026.

---

### Mistral — May 31, 2026 ✅ COMPLETED

> ❌ **Retired 2026-05-31.** These models are no longer accessible. See "Already Shut Down" section.

| Model | API name | Retired | Replacement |
|---|---|---|---|
| Mistral Large 2.1 | `mistral-large-2411` | **2026-05-31** | `mistral-large-latest` (Mistral Large 3) |
| Pixtral Large | `pixtral-large-2411` | **2026-05-31** | `mistral-large-latest` (Mistral Large 3) |
| Devstral Medium 1.0 | `devstral-medium-2507` | **2026-05-31** | `mistral-medium-3-5` |
| Voxtral Mini | `voxtral-mini-2507` | **2026-05-31** | `voxtral-mini-transcribe-2` |
| Mistral OCR 2 | `mistral-ocr-2505` | **2026-05-31** | `mistral-ocr-3` (OCR 3) |

*Source: [Mistral Models Overview](https://docs.mistral.ai/models/overview) — verified 2026-06-11*

---

### Mistral — June 30, 2026

| Model | API name | Deprecated | Retirement date | Replacement |
|---|---|---|---|---|
| Mistral Moderation v2 | `mistral-moderation-2411` | 2026-03-31 | **2026-06-30** | `mistral-moderation-2` |

*Source: [Mistral Models Overview](https://docs.mistral.ai/models/overview) — verified 2026-06-10*

---

### Mistral — July 31, 2026

| Model | API name | Deprecated | Retirement date | Replacement |
|---|---|---|---|---|
| Mistral Small 3.2 | `mistral-small-2506` | 2026-04-30 | **2026-07-31** | `mistral-small-2603` (Mistral Small 4) |
| Magistral Small 1.2 | `magistral-small-2509` | 2026-04-30 | **2026-07-31** | `mistral-small-2603` (Mistral Small 4) |

*Source: [Mistral Models Overview](https://docs.mistral.ai/models/overview) — verified 2026-05-16*

---

### DeepSeek — July 24, 2026 ⚠️

| Alias | Currently points to | Retirement date | Replacement |
|---|---|---|---|
| `deepseek-chat` | `deepseek-v4-flash` (non-thinking mode) | **2026-07-24 15:59 UTC** | `deepseek-v4-flash` |
| `deepseek-reasoner` | `deepseek-v4-flash` (thinking mode) | **2026-07-24 15:59 UTC** | `deepseek-v4-flash` or `deepseek-v4-pro` |

> ⚠️ **No silent redirect after July 24.** Unlike xAI's May 15 retirement, DeepSeek has stated that calls to `deepseek-chat` and `deepseek-reasoner` will **return errors** (not redirect) after the deadline. This is a hard cutoff.

*Source: [DeepSeek API Docs — Models & Pricing](https://api-docs.deepseek.com/quick_start/pricing) — verified 2026-06-10*

---

### OpenAI DALL-E 2 and DALL-E 3 image models ❌ RETIRED 2026-05-12

| Model | Retirement date | Replacement |
|---|---|---|
| `dall-e-2` | **2026-05-12** ❌ RETIRED | `gpt-image-2` |
| `dall-e-3` | **2026-05-12** ❌ RETIRED | `gpt-image-2` |

*Source: [OpenAI API Pricing](https://developers.openai.com/api/docs/pricing) — verified 2026-05-12*

---

### OpenAI GPT-5.2 Thinking

| Model | Retirement date | Migration |
|---|---|---|
| GPT-5.2 Thinking (ChatGPT) | **2026-06-05** | GPT-5.4 Thinking (already deployed) |

GPT-5.4 replaced GPT-5.2 Thinking in ChatGPT as of 2026-03-05. GPT-5.2 Thinking remains in the Legacy Models section of the model picker for paid users until June 5, 2026. Enterprise/Edu users: enable via admin settings.

---

## Recently Deprecated (Still Accessible)

### Anthropic

| Model | API name | Deprecated | Retirement date | Replacement |
|---|---|---|---|---|
| Claude Sonnet 4 | `claude-sonnet-4-20250514` | 2026-04-14 | **2026-06-15** | `claude-sonnet-4-6` |
| Claude Opus 4 | `claude-opus-4-20250514` | 2026-04-14 | **2026-06-15** | `claude-opus-4-7` |

> ⚠️ Both Claude Sonnet 4 and Claude Opus 4 retire **June 15, 2026**. See Upcoming Shutdowns above.  
*Source: [Anthropic model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations) — verified 2026-05-14*

### OpenAI

| Model | Deprecated | Notes |
|---|---|---|
| `gpt-4.5-preview` | 2025-04-14 | Announced deprecated at GPT-4.1 launch. Check [OpenAI changelog](https://developers.openai.com/api/docs/changelog) for sunset date. |

### Google (Preview models — upcoming retirement)

| Model | Shutdown date | Replacement |
|---|---|---|
| `gemini-robotics-er-1.5-preview` | **2026-04-30** | `gemini-robotics-er-1.6-preview` |

*Source: [Google AI for Developers — Gemini API changelog](https://ai.google.dev/gemini-api/docs/changelog) — 2026-04-14*

### Google (Preview models — retired)

| Model | Retired | Replacement |
|---|---|---|
| `gemini-3-pro-preview` | **2026-03-09** | `gemini-3.1-pro-preview` |
| `gemini-2.5-flash-lite-preview-09-2025` | **2026-03-31** | `gemini-3.1-flash-lite-preview` |
| `gemini-2.0-flash-lite-preview` | 2025-12-09 | `gemini-2.5-flash-lite` |
| `gemini-2.0-flash-live-001` | 2025-12-09 | `gemini-3.1-flash-live-preview` |
| `gemini-2.0-flash-preview-image-generation` | 2025-11-14 | `gemini-2.5-flash-image` |
| `imagen-4.0-generate-preview-06-06` | 2026-02-17 | `imagen-4.0-generate-001` |

---

## Already Shut Down

### Mistral (2026-05-31)

| Model | API name | Retired | Replacement |
|---|---|---|---|
| Mistral Large 2.1 | `mistral-large-2411` | **2026-05-31** | `mistral-large-latest` |
| Pixtral Large | `pixtral-large-2411` | **2026-05-31** | `mistral-large-latest` |
| Devstral Medium 1.0 | `devstral-medium-2507` | **2026-05-31** | `mistral-medium-3-5` |
| Voxtral Mini | `voxtral-mini-2507` | **2026-05-31** | `voxtral-mini-transcribe-2` |
| Mistral OCR 2 | `mistral-ocr-2505` | **2026-05-31** | `mistral-ocr-3` |

*Source: [Mistral Models Overview](https://docs.mistral.ai/models/overview) — verified 2026-06-11*

---

### OpenAI (2026-05-12)

| Model | Retired | Replacement |
|---|---|---|
| `dall-e-2` | **2026-05-12** | `gpt-image-2` |
| `dall-e-3` | **2026-05-12** | `gpt-image-2` |

---

### Cohere (2026-04-04)

Effective April 4, 2026, Cohere retired the following models. API requests to these IDs now fail.

| Model | Retired | Replacement |
|---|---|---|
| `embed-english-v2.0` | **2026-04-04** | `embed-english-v3.0` or `embed-v4.0` |
| `embed-english-light-v2.0` | **2026-04-04** | `embed-english-v3.0` |
| `embed-multilingual-v2.0` | **2026-04-04** | `embed-multilingual-v3.0` or `embed-v4.0` |
| `c4ai-aya-expanse-8b` | **2026-04-04** | `command-r7b-12-2024` or `command-a-03-2025` |
| `c4ai-aya-vision-8b` | **2026-04-04** | `command-a-03-2025` |

*Source: [Cohere deprecations page](https://docs.cohere.com/docs/deprecations) — verified 2026-04-13*

---

### Anthropic

| Model | API name | Retired | Was replaced by |
|---|---|---|---|
| Claude 3 Haiku | `claude-3-haiku-20240307` | **2026-04-20** | `claude-haiku-4-5-20251001` |
| Claude 3.5 Haiku | `claude-3-5-haiku-20241022` | **2026-02-19** | `claude-haiku-4-5-20251001` |
| Claude Sonnet 3.7 | `claude-3-7-sonnet-20250219` | **2026-02-19** | `claude-sonnet-4-5-20250929` |
| Claude 3 Opus | `claude-3-opus-20240229` | 2026-01-05 | `claude-opus-4-6` (preserved via special request) |
| Claude 3.5 Sonnet | `claude-3-5-sonnet-*` | 2025-10-28 | `claude-opus-4-6` |

> **Note:** Claude Opus 3 is retired but still accessible to paid claude.ai subscribers and on the API [by request](https://www.anthropic.com/research/deprecation-updates-opus-3) — special exception under Anthropic's model preservation commitments.

### Google

| Model | Shut down | Was replaced by |
|---|---|---|
| `gemini-2.0-flash` | **2026-06-01** | `gemini-2.5-flash` or `gemini-3-flash-preview` |
| `gemini-2.0-flash-001` | **2026-06-01** | `gemini-2.5-flash` |
| `gemini-2.0-flash-lite` | **2026-06-01** | `gemini-2.5-flash-lite` |
| `gemini-2.0-flash-lite-001` | **2026-06-01** | `gemini-2.5-flash-lite` |
| `gemini-1.5-pro-001` | 2025-05-24 | `gemini-2.0-flash` |
| `gemini-1.5-pro-002` | 2025-09-24 | `gemini-2.0-flash` |
| `gemini-1.5-flash-001` | 2025-05-24 | `gemini-2.0-flash-lite` |
| `gemini-1.5-flash-002` | 2025-09-24 | `gemini-2.0-flash-lite` |
| `gemini-1.0-pro-001` | 2025-04-21 | `gemini-2.0-flash` |
| `gemini-1.0-pro-vision-001` | 2025-04-21 | `gemini-2.0-flash` |
| `text-embedding-004` | 2026-01-14 | `gemini-embedding-001` |
| `gemini-2.5-flash-preview-05-20` | 2025-11-18 | `gemini-3-flash-preview` |

---

## Migration Notes

### Switching from `gemini-2.0-flash` to `gemini-2.5-flash`

**Price change:** $0.10/$0.40 → $0.30/$2.50 per 1M tokens (3× input, 6.25× output increase)  
**Capability improvement:** Significantly better reasoning and multimodal understanding  
**Action:** Update model identifier. Test system prompt behavior — 2.5 is more capable but may behave differently on edge cases.

### Switching from `gemini-2.0-flash-lite` to `gemini-2.5-flash-lite`

**Price change:** $0.075/$0.30 → $0.10/$0.40 per 1M tokens (~1.3× increase)  
**Action:** Update model identifier. Run regression tests.

### Switching from `gemini-2.5-pro` to `gemini-3.1-pro-preview`

**Price change:** $1.25/$10.00 → $2.00/$12.00 per 1M tokens (~1.6× increase)  
**Capability improvement:** Better GPQA (94.3% vs ~90%), stronger coding  
**Action:** Preview model — evaluate stability before committing to production. Use `gemini-2.5-pro` as fallback until GA.

### 🚨 Switching from `claude-3-haiku-20240307` to `claude-haiku-4-5-20251001` (Deadline: 2026-04-20 — **3 days**)

**Price change:** $0.25/$1.25 → $1.00/$5.00 per 1M tokens (4× more expensive)  
**Capability improvement:** Extended thinking support, 64K max output (vs 4K), significantly higher quality  
**Action required:** Update model identifier **immediately** — shutdown in 3 days. Run regression tests — Haiku 4.5 may respond differently on edge cases.  
**Tip:** Haiku 3.5 (`claude-3-5-haiku-20241022`) is already retired (2026-02-19) — do not use.

### Switching from `gpt-4.5-preview` to `gpt-5.4` or `gpt-4.1`

`gpt-4.1` provides 1 M context at lower cost. `gpt-5.4` is the current flagship.

### Anthropic Claude subscription → API for agents

From 2026-04-04, Claude Pro/Max subscriptions do **not** power third-party agent tools (OpenClaw, etc.). Switch to API key + pay-as-you-go. See [Anthropic models](models/anthropic.md).

---

*See also: [changelog.md](changelog.md)*
