# Deprecated & Sunset Models

> Track sunset dates and migration paths. **Last updated:** 2026-04-10.
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

### Switching from `gpt-4.5-preview` to `gpt-5.4` or `gpt-4.1`

`gpt-4.1` provides 1 M context at lower cost. `gpt-5.4` is the current flagship.

### Anthropic Claude subscription → API for agents

From 2026-04-04, Claude Pro/Max subscriptions do **not** power third-party agent tools (OpenClaw, etc.). Switch to API key + pay-as-you-go. See [Anthropic models](models/anthropic.md).

---

*See also: [changelog.md](changelog.md)*
