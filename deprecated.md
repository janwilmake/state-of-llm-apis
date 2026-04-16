# Deprecated & Sunset Models

> Track sunset dates and migration paths. **Last updated:** 2026-04-16.
>
> ⚠️ = Deprecated, still accessible. ❌ = Shut down, no longer accessible.

---

## Upcoming Shutdowns (Action Required)

### Google Gemini — June 2026 deadline

| Model | Shutdown date | Migrate to |
|---|---|---|
| `gemini-2.0-flash` | **2026-06-01** | `gemini-2.5-flash` (or `gemini-3-flash-preview`) |
| `gemini-2.0-flash-001` | **2026-06-01** | `gemini-2.5-flash` |
| `gemini-2.0-flash-lite` | **2026-06-01** | `gemini-2.5-flash-lite` |
| `gemini-2.0-flash-lite-001` | **2026-06-01** | `gemini-2.5-flash-lite` |
| `gemini-2.5-pro` | **2026-06-17** | `gemini-3.1-pro-preview` |
| `gemini-2.5-flash` | **2026-06-17** | `gemini-3-flash-preview` |
| `gemini-2.5-flash-lite` | **2026-07-22** | `gemini-3.1-flash-lite-preview` |

> ⚠️ **Note:** Gemini 3.x replacements are currently in preview stage (no GA stability guarantee). Stable GA versions expected before shutdown dates. Source: [Google Gemini Deprecations](https://ai.google.dev/gemini-api/docs/deprecations) — verified 2026-04-10.

> ⚠️ **Note (Vertex AI):** As of 2026-03-06, `gemini-2.0-flash-001` and `gemini-2.0-flash-lite-001` are unavailable to **new** Vertex AI projects. Existing customers retain access until June 1, 2026.

---

### OpenAI GPT-5.2 Thinking

| Model | Retirement date | Migration |
|---|---|---|
| GPT-5.2 Thinking (ChatGPT) | **2026-06-05** | GPT-5.4 Thinking (already deployed) |

GPT-5.4 replaced GPT-5.2 Thinking in ChatGPT as of 2026-03-05. GPT-5.2 Thinking remains in the Legacy Models section of the model picker for paid users until June 5, 2026. Enterprise/Edu users: enable via admin settings.

---

## Recently Deprecated (Still Accessible)

### Anthropic

> 🚨 **URGENT: Claude 3 Haiku retires April 20, 2026 — 4 days away!** Migrate now.

| Model | API name | Deprecated | Retirement date | Replacement |
|---|---|---|---|---|
| Claude 3 Haiku | `claude-3-haiku-20240307` | 2026-02-19 | **2026-04-20** | `claude-haiku-4-5-20251001` |

*Source: [Anthropic model deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations) — verified 2026-04-12*

### OpenAI

| Model | Deprecated | Notes |
|---|---|---|
| `gpt-4.5-preview` | 2025-04-14 | Announced deprecated at GPT-4.1 launch. Check [OpenAI changelog](https://developers.openai.com/api/docs/changelog) for sunset date. |

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
| Claude 3.5 Haiku | `claude-3-5-haiku-20241022` | **2026-02-19** | `claude-haiku-4-5-20251001` |
| Claude Sonnet 3.7 | `claude-3-7-sonnet-20250219` | **2026-02-19** | `claude-sonnet-4-5-20250929` |
| Claude 3 Opus | `claude-3-opus-20240229` | 2026-01-05 | `claude-opus-4-6` (preserved via special request) |
| Claude 3.5 Sonnet | `claude-3-5-sonnet-*` | 2025-10-28 | `claude-opus-4-6` |

> **Note:** Claude Opus 3 is retired but still accessible to paid claude.ai subscribers and on the API [by request](https://www.anthropic.com/research/deprecation-updates-opus-3) — special exception under Anthropic's model preservation commitments.

### Google

| Model | Shut down | Was replaced by |
|---|---|---|
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

### 🚨 Switching from `claude-3-haiku-20240307` to `claude-haiku-4-5-20251001` (Deadline: 2026-04-20 — **4 days**)

**Price change:** $0.25/$1.25 → $1.00/$5.00 per 1M tokens (4× more expensive)  
**Capability improvement:** Extended thinking support, 64K max output (vs 4K), significantly higher quality  
**Action required:** Update model identifier **immediately** — shutdown in 4 days. Run regression tests — Haiku 4.5 may respond differently on edge cases.  
**Tip:** Haiku 3.5 (`claude-3-5-haiku-20241022`) is already retired (2026-02-19) — do not use.

### Switching from `gpt-4.5-preview` to `gpt-5.4` or `gpt-4.1`

`gpt-4.1` provides 1 M context at lower cost. `gpt-5.4` is the current flagship.

### Anthropic Claude subscription → API for agents

From 2026-04-04, Claude Pro/Max subscriptions do **not** power third-party agent tools (OpenClaw, etc.). Switch to API key + pay-as-you-go. See [Anthropic models](models/anthropic.md).

---

*See also: [changelog.md](changelog.md)*
