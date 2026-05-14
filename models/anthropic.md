# Anthropic Model Catalog

> **Source:** [Anthropic API Pricing](https://platform.claude.com/docs/en/about-claude/pricing) · [Models Overview](https://platform.claude.com/docs/en/about-claude/models/overview) · **Verified:** 2026-05-14

---

## Current Recommended Models (Claude 4.x generation)

### Claude Opus 4.7 (Released 2026-04-16) 🆕 NEW

Anthropic's most capable publicly available model. Notable improvements over Opus 4.6 in software engineering (70% on CursorBench vs 58%), vision (higher resolution image understanding), and long-horizon agentic tasks. First Claude model released with Project Glasswing cyber safeguards (detects and blocks high-risk cybersecurity use attempts). Available across Anthropic API, Amazon Bedrock, Google Cloud Vertex AI, and Microsoft Foundry.

| Metric | Value |
|---|---|
| API name | `claude-opus-4-7` |
| Context window | 1,000,000 tokens |
| Max output | 128,000 tokens |
| Input (≤200K) | **$5.00 / 1M** |
| Output (≤200K) | **$25.00 / 1M** |
| Input (>200K) | $10.00 / 1M |
| Output (>200K) | $37.50 / 1M |
| Cache write | $6.25 / 1M |
| Cache read | $0.50 / 1M |

**Best for:** Complex software engineering, full-codebase analysis, autonomous agents, vision tasks, scientific research.  
**CursorBench:** 70% (vs 58% for Opus 4.6) | **Rakuten-SWE-Bench:** 3× more production tasks resolved vs Opus 4.6  
**Cyber safeguards:** Built-in detection for prohibited cybersecurity uses; security professionals can apply to [Cyber Verification Program](https://claude.com/form/cyber-use-case)

> ⚠️ **Tokenizer change:** Opus 4.7 uses a new tokenizer that may use **up to 35% more tokens** for the same input text versus Opus 4.6. The per-token price is unchanged ($5/$25), but identical prompts may cost up to 1.35× more. Impact is worst on code, structured data (JSON/XML), and non-English text. Verify your actual token usage after migration.

*Source: [Anthropic announcement](https://www.anthropic.com/news/claude-opus-4-7) — 2026-04-16 · [CloudZero tokenizer analysis](https://www.cloudzero.com/blog/claude-opus-4-7-pricing/) — verified 2026-05-14*

---

### Claude Opus 4.6 (Released 2026-02-04)

Previous flagship; still active legacy. 1 M token context at standard pricing — no long-context premium.

| Metric | Value |
|---|---|
| API name | `claude-opus-4-6` |
| Context window | 1,000,000 tokens |
| Max output | 128,000 tokens |
| Input (≤200K) | **$5.00 / 1M** |
| Output (≤200K) | **$25.00 / 1M** |
| Input (>200K) | $10.00 / 1M |
| Output (>200K) | $37.50 / 1M |
| Cache write | $6.25 / 1M |
| Cache read | $0.50 / 1M |

**Best for:** Complex reasoning, full-codebase analysis, autonomous agents, scientific research.  
**GPQA Diamond:** 91.3%

---

### Claude Sonnet 4.6

Balanced performance and cost. Same price as Sonnet 4.5.

| Metric | Value |
|---|---|
| API name | `claude-sonnet-4-6` |
| Context window | 1,000,000 tokens |
| Input (≤200K) | **$3.00 / 1M** |
| Output (≤200K) | **$15.00 / 1M** |
| Input (>200K) | $6.00 / 1M |
| Output (>200K) | $22.50 / 1M |
| Cache write | $3.75 / 1M |
| Cache read | $0.30 / 1M |

**Best for:** Production chatbots, coding assistants, balanced cost/quality workloads.

---

### Claude Sonnet 4.5

Previous Sonnet; identical pricing to 4.6. Still supported and available.

| Input | Output | Cache write | Cache read |
|---|---|---|---|
| $3.00 / 1M | $15.00 / 1M | $3.75 / 1M | $0.30 / 1M |

---

### Claude Haiku 4.5

Fastest and cheapest in the current lineup.

| Metric | Value |
|---|---|
| API name | `claude-haiku-4-5` |
| Context window | 200,000 tokens |
| Input (≤200K) | **$1.00 / 1M** |
| Output (≤200K) | **$5.00 / 1M** |
| Input (>200K) | $2.00 / 1M |
| Output (>200K) | $7.50 / 1M |
| Cache write | $1.25 / 1M |
| Cache read | $0.10 / 1M |

**Best for:** High-volume classification, summarization, simple Q&A, latency-sensitive tasks.

---

## Batch API

**50% discount** on all models. Asynchronous processing via the Message Batches API. No SLA on turnaround, typically a few minutes to several hours.

## Prompt Caching

- **Cache write:** 25% premium over standard input rate (charged once to store)
- **Cache read:** ~10% of standard input rate (very cheap on re-use)
- Useful for multi-turn conversations, repeated system prompts, large document contexts

## Extended Thinking

Claude models support `extended_thinking` mode, which enables multi-step chain-of-thought reasoning. Thinking tokens are billed at standard output rates. Useful for complex math, coding, and analytical tasks.

---

## Subscription Tiers (claude.ai)

| Plan | Price | Key features |
|---|---|---|
| Free | $0 | Limited access to Claude Sonnet |
| Pro | $20/month | Higher limits, Claude Code access, priority |
| Max 5x | $100/month | 5× more usage than Pro, priority access |
| Max 20x | $200/month | 20× more usage than Pro, priority access |
| Team Standard | $25/user/month (annual) | SSO, admin controls, Slack/M365 integration |
| Team Premium | $150/user/month | All Standard + Claude Code access |
| Enterprise | Custom | SCIM, audit logs, compliance API, custom data retention |

---

## Enterprise Analytics API (Released 2026-05-07)

Anthropic launched the **Enterprise Analytics API** — gives Enterprise plan Primary Owners programmatic access to per-user cost and adoption data across Claude, Claude Code, Cowork, and Office agents.

**Nine endpoints in two categories:**
1. **Engagement & Adoption (5 endpoints):** Per-user activity (conversations, commits, PRs, lines of code, Cowork sessions), organization-wide DAU/WAU/MAU, seat utilization
2. **Usage & Cost (4 endpoints, beta):** Per-user token consumption and USD spend, broken down by model, context window, inference region, or speed; cost over time; token usage over time

**Key facts:**
- Available on **Enterprise plans only**
- Data starts January 1, 2026; 90-day history for engagement, 365 days for cost
- 3-day engagement data delay; 4–24 hour cost data refresh; revisions possible up to 30 days
- Rate limit: 60 req/min (customizable)
- Does **not** include Bedrock-routed Claude Code data

*Source: [Anthropic Enterprise Analytics API docs](https://support.claude.com/en/articles/13694757-get-started-with-the-claude-enterprise-analytics-api) — 2026-05-07*

---

## API Rate Limit Increase (May 2026)

Effective **2026-05-06**, Anthropic raised API rate limits for Claude Opus models — enabled by new compute capacity (SpaceX Colossus 1 deal: 300MW+ / 220K+ NVIDIA GPUs). Three changes effective immediately:
1. **Claude Code 5-hour rate limits doubled** for Pro, Max, Team, and seat-based Enterprise plans
2. **Peak hours limit reduction removed** for Claude Code on Pro and Max accounts
3. **API rate limits raised considerably** for Claude Opus models (see [official rate limits page](https://platform.claude.com/docs/en/api/rate-limits))

*Source: [Anthropic — Higher limits and SpaceX compute deal](https://www.anthropic.com/news/higher-limits-spacex) — 2026-05-06*

## API Policy Change (April 2026)

Effective **2026-04-04**, Claude Pro and Max subscriptions can **no longer be used to power third-party agent frameworks** (e.g. OpenClaw). Users must connect via direct API key with pay-as-you-go token billing. Affected subscribers received a one-time credit equal to their monthly plan cost. *Source: TechCrunch, 2026-04-04*

---

## Claude Mythos Preview (2026-04-07) — Gated / Not Publicly Available

> ⚠️ **Not available via public API.** Access is restricted to ~50 partner organizations under **Project Glasswing** for cybersecurity use only.

Anthropic's most capable model to date, described as a "step change" above Claude Opus 4.6. Excels at reasoning, coding, and — most notably — autonomous vulnerability discovery in software systems. Named internally "Capybara".

| Metric | Value |
|---|---|
| API name | `claude-mythos-preview` (gated) |
| Public API | ❌ No general availability |
| Preview pricing | **~$25.00 / 1M input** · **~$125.00 / 1M output** |
| General release date | Not announced |

**Why gated:** Anthropic identified Mythos as a cybersecurity risk if broadly released. Under Project Glasswing, ~50 infrastructure partners use it solely for defensive security scanning. In internal testing, it identified thousands of zero-day vulnerabilities, many decades old.

**What developers should know:** Mythos is the precursor to the next Claude generation. Its benchmark scores substantially exceed Opus 4.6 on software engineering and reasoning. No timeline for general availability has been announced. *Source: TechCrunch, Anthropic System Card — 2026-04-07*

---

## Claude 5 Roadmap

Anthropic's Claude 5 generation is underway. **Sonnet 5 "Fennec"** was released February 2026. With Opus 4.7 launching today (2026-04-16), Claude 5 Opus is now anticipated **Q3 2026** (July–September), as Anthropic appears to be iterating further on the 4.x generation before the 5.x flagship jump.

---

## Legacy Models

| Model | Status | Retirement | Notes |
|---|---|---|---|
| Claude Opus 4.6 | Active (legacy) | Not before 2026-11-24 | $5/$25 input/output — same price as Opus 4.7 but one generation older |
| Claude Opus 4.5 | Active (legacy) | Not before 2026-11-24 | $5/$25 input/output — same price as Opus 4.7 but older |
| Claude Opus 4.1 | Active (legacy) | Not before 2026-08-05 | $15/$75 — 3× more expensive than Opus 4.7 |
| Claude Sonnet 4.5 | Active (legacy) | Not before 2026-09-29 | $3/$15 — same price as Sonnet 4.6 but older |
| Claude Sonnet 4 | ⚠️ Deprecated | **2026-06-15** | $3/$15 — deprecated 2026-04-14; API name `claude-sonnet-4-20250514` |
| Claude Opus 4 | ⚠️ Deprecated | **2026-06-15** | $15/$75 — deprecated 2026-04-14; API name `claude-opus-4-20250514` |
| Claude 3 Haiku | ❌ **RETIRED 2026-04-20** | **2026-04-20** | Migrate to `claude-haiku-4-5-20251001` |
| Claude 3.5 Haiku | Retired 2026-02-19 | — | Use Haiku 4.5 |
| Claude Sonnet 3.7 | Retired 2026-02-19 | — | Use Sonnet 4.6 |
| Claude 3 Opus | Retired 2026-01-05 | — | Available to paid claude.ai subscribers by special request |

*See [deprecated.md](../deprecated.md) for sunset dates.*

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md) · [deprecated.md](../deprecated.md)*
