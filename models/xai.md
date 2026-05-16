# xAI Grok Model Catalog

> **Source:** [xAI Models & Pricing](https://docs.x.ai/developers/models) · [xAI Pricing](https://docs.x.ai/developers/pricing) · [xAI API](https://x.ai/api) · [OpenRouter](https://openrouter.ai/x-ai/grok-4.3) · **Verified:** 2026-05-16

---

## Current Models

### Grok 4.3 (Released 2026-04-30) — Current Flagship 🆕 NEW

xAI's newest and recommended flagship. ~40% price cut vs. Grok 4.20; expanded to 1M context window; native video input support; Voice API launched same day.

> xAI explicitly states: *"We strongly recommend all API callers use grok-4.3. It is the most intelligent and fastest model we've built."*

| Metric | Value |
|---|---|
| API names | `grok-4.3` · `grok-4.3-latest` · `grok-latest` |
| Context window | 1,000,000 tokens |
| Input | **$1.25 / 1M** |
| Cached input | **$0.20 / 1M** |
| Output | **$2.50 / 1M** |
| Web search | $5.00 / 1K calls |
| Code execution | $5.00 / 1K calls |
| File attachments | $10.00 / 1K calls |
| Safety filter violation fee | $0.05 / blocked request |

**Higher context pricing** applies to requests exceeding 200K total tokens (rate TBD per region; see [xAI docs](https://docs.x.ai/developers/models/grok-4.3)).

**Reasoning effort:** Configurable — `none`, `low`, `medium` (default), `high`. Reasoning tokens billed at standard completion token rate.

**Key capabilities:** Vision input, tool calling/function calling, structured outputs, prompt caching, batch API, provisioned throughput.

**Voice API (launched 2026-04-17; pricing updated 2026-05-09):**
- Voice Agent (Realtime): **$3.00 / hour** ($0.05 / minute), WebSocket-based; up to 30 min sessions
- TTS: **$15.00 / 1M characters** (REST + WebSocket streaming; 5 voices, 20+ languages)
- STT: **$0.10 / hour** (REST batch) · **$0.20 / hour** (WebSocket streaming); 25+ languages, speaker diarization

> ⚠️ **Pricing correction (2026-05-15):** At launch (2026-04-17), xAI TTS was priced at $4.20/1M characters. The official pricing page (last updated 2026-05-09) now shows **$15.00 / 1M characters**. STT pricing is unchanged ($0.10/hr batch, $0.20/hr streaming). Grok Voice Agent (realtime) remains $3.00/hr.

*Source: [xAI Pricing docs](https://docs.x.ai/developers/pricing) — verified 2026-05-15*

*Source: [xAI Docs — grok-4.3](https://docs.x.ai/developers/models/grok-4.3) · [OpenRouter](https://openrouter.ai/x-ai/grok-4.3) · VentureBeat (2026-05-01) — verified 2026-05-10*

> ✅ **Retirement completed (2026-05-15 at 12pm PT):** Old model slugs now redirect to `grok-4.3`. See retirement section below — requests will NOT error, but will be silently billed at `grok-4.3` pricing. Update your `model` field explicitly.

---

### Grok 4.20 (Released 2026-03-31)

Previous flagship. 2M token context, agentic tool calling. Still available; pricing matches Grok 4.3 on the official xAI API page ($1.25/$2.50 input/output).

> **Note (2026-04-17):** The canonical dated model IDs are `grok-4.20-0309-reasoning` and `grok-4.20-0309-non-reasoning`. The alias `grok-4.20` remains valid. The `-0309` suffix pins to the March 9 training checkpoint.

| Metric | Value |
|---|---|
| API names | `grok-4.20-0309-reasoning` · `grok-4.20-0309-non-reasoning` · `grok-4.20-multi-agent-0309` · `grok-4.20` (alias) |
| Context window | 2,000,000 tokens |
| Input | **$1.25 / 1M** |
| Cached input | **$0.20 / 1M** |
| Output | **$2.50 / 1M** |
| Web search | $5.00 / 1K calls |
| Knowledge cutoff | November 2024 |

**Architecture:** 4-agent system (Grok + Harper + Benjamin + Lucas) for parallel reasoning and cross-verification. "Heavy" variant uses 16 agents for deeper analysis.

**Key capabilities:** Reasoning (can be toggled on/off), vision, X (Twitter) real-time data access, image generation.

**GPQA Diamond:** ~88%

---

### Grok 4 (Released 2025-07-09)

| Metric | Value |
|---|---|
| API name | `grok-4` |
| Context window | 256,000 tokens |
| Input | **$3.00 / 1M** |
| Cached input | $0.75 / 1M |
| Output | **$15.00 / 1M** |

Always-on reasoning model. No `reasoning_effort` parameter — reasoning cannot be disabled.  
`presencePenalty`, `frequencyPenalty`, and `stop` are not supported.

**GPQA Diamond:** 87.7% | **MMLU:** 86.6% | **LiveCodeBench:** 81.9%

---

### Grok 4 Fast / Grok 4.1 Fast (Recommended for most developers)

Near-frontier capability at a fraction of the flagship price. 2 M token context.

> **API name update (2026-04-15):** xAI's official API now surfaces these as `grok-4-fast-reasoning` and `grok-4-fast-non-reasoning`. `grok-4.1-fast` remains a valid alias. Both sets of names return identical pricing.

| Metric | Value |
|---|---|
| API names | `grok-4-fast-reasoning` · `grok-4-fast-non-reasoning` · `grok-4.1-fast` |
| Context window | 2,000,000 tokens |
| Input | **$0.20 / 1M** |
| Cached input | $0.05 / 1M |
| Output | **$0.50 / 1M** |
| Live search | $25.00 / 1K sources |

Available in reasoning and non-reasoning variants. 40% fewer thinking tokens than Grok 4 on average.

**Best for:** Long documents, large codebases, extended agent workflows, high-volume tasks.

---

### Grok 4.20 — Pricing via xAI Characters API

xAI also offers a **characters-based pricing** option at **$4.20 / 1M characters** with 10 rps for Grok 4.20.

---

### Grok Code Fast (Coding-Specialist)

Coding-focused model derived from the Grok 4.1 Fast architecture, optimized for programming tasks.

| Metric | Value |
|---|---|
| API name | `grok-code-fast-1` |
| Context window | 256,000 tokens |
| Input | **$0.20 / 1M** |
| Output | **$1.50 / 1M** |

**Best for:** Code generation, debugging, refactoring. Higher output price than Grok 4.1 Fast reflects longer code outputs. Vision not included.

---

### Grok 3 Beta (Legacy)

| Context | Input | Output |
|---|---|---|
| 131,072 tokens | $3.00 / 1M | $15.00 / 1M |

---

### Grok 3 Mini Beta

| Context | Input | Output |
|---|---|---|
| 131,072 tokens | $0.30 / 1M | $0.50 / 1M |

---

## Tools Pricing

| Tool | Price |
|---|---|
| Web search | $2.50–$5.00 / 1K calls (varies by model) |
| X (Twitter) search | Included with API access |
| Code execution | Per token |
| Collections search (RAG) | Per token |

---

## Subscription Plans (consumer)

| Plan | Price | Notes |
|---|---|---|
| Free | $0 | Grok 4.1 Fast, limited daily messages |
| SuperGrok | **$30/month** | Grok 4 + 2 M context, full usage |
| Grok Business | **$30/seat/month** | Team plan |
| X Premium+ | $16/month | Grok access through X platform |

---

## ✅ Model Retirements — May 15, 2026 (COMPLETED TODAY)

**Effective 2026-05-15 at 12:00pm PT**, the following models were retired from the xAI API:

| Model retired | Auto-redirect target | Recommended explicit action |
|---|---|---|
| `grok-4-1-fast-reasoning` | `grok-4.3` with `low` reasoning effort | Update to `grok-4.3` |
| `grok-4-1-fast-non-reasoning` | `grok-4.3` with `none` reasoning effort | Update to `grok-4.3` |
| `grok-4-fast-reasoning` | `grok-4.3` with `low` reasoning effort | Update to `grok-4.3` |
| `grok-4-fast-non-reasoning` | `grok-4.3` with `none` reasoning effort | Update to `grok-4.3` |
| `grok-4-0709` | `grok-4.3` with `low` reasoning effort | Update to `grok-4.3` |
| `grok-code-fast-1` | `grok-4.3` with `low` reasoning effort | Update to `grok-4.3` |
| `grok-3` | `grok-4.3` with `none` reasoning effort | Update to `grok-4.3` |
| `grok-imagine-image-pro` | `grok-imagine-image-quality` | Update to `grok-imagine-image-quality` |

> ✅ **Important correction (2026-05-15):** Per the official xAI migration guide, requests to retired model slugs **automatically redirect** to `grok-4.3` (previous entries said "return errors" — this was wrong). Your code will not break, but will be **silently charged at `grok-4.3` pricing** ($1.25/$2.50 per 1M) even if you were using the cheap Fast models ($0.20/$0.50). Update your `model` field explicitly to avoid unexpected cost increases.

**Pricing impact:** ~6× cost increase for teams using `grok-4-fast-*` ($0.20/$0.50) who have not yet migrated to `grok-4.3` ($1.25/$2.50).

*Source: [xAI Migration Guide — May 15 Retirement](https://docs.x.ai/developers/migration/may-15-retirement) — verified 2026-05-15*

---

## Grok Build (Coding Agent — Launched 2026-05-14)

xAI's coding agent CLI, launched May 14, 2026 as an early beta. Competes with Anthropic's Claude Code and OpenAI's Codex CLI.

**Access:** Early beta for **SuperGrok Heavy** subscribers only ($300/month). Broader availability not yet announced.

**Install:**
```bash
curl -fsSL https://x.ai/cli/install.sh | bash
```

**Key features:**
- Full-screen interactive TUI (terminal UI) with plan mode — review/approve plans before execution
- Subagents that work in parallel for complex tasks
- Headless mode (`-p` flag) for scripts and automations
- Agent Client Protocol (ACP) support for building bots and orchestration apps
- Works with existing AGENTS.md, plugins, hooks, skills, and MCP servers
- Underlying model: `grok-4.3` (standard API pricing applies for API-key usage)

> ⚠️ **Limitation:** Grok 4.3's 1M context is competitive, but xAI has acknowledged it has lagged behind in coding. Grok Build is early stage — Claude Code and OpenAI Codex CLI have significant head starts in IDE integrations and third-party extensions. More than 50 researchers/engineers left SpaceX AI since the Feb 2026 merger with SpaceX, including coding specialists.

*Source: [xAI — Introducing Grok Build Early Beta](https://x.ai/news/grok-build-cli) · Engadget (2026-05-15) · PCMag (2026-05-14) · DevOps.com (2026-05-15)*

---

## Grok 5 (Expected Q2 2026)

Grok 5 has been delayed past the original Q1 2026 target. xAI now points to **Q2 2026** as the likely window. Training on the 1 GW Colossus 2 supercluster in Memphis. Reported 6 trillion parameters with MoE architecture.

---

## Storage Billing (Effective 2026-04-20)

xAI Files and Collections (used for RAG/context storage) will begin incurring storage charges starting **April 20, 2026**. Developers using the Files or Collections APIs to persist data should review storage usage before this date. Visit the [xAI Console](https://console.x.ai/team/default/files) to view and manage stored files and collections.

## New Features (2026)

- **Batch API** (new) — async processing at reduced cost
- **Prompt Caching** (new) — automatic caching for repeated context
- **Provisioned Throughput** (new) — dedicated compute for enterprise
- **mTLS Authentication** (new) — enhanced security for API connections
- **Video input/output** (new capability)
- **Audio input/output** (new capability)

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md)*
