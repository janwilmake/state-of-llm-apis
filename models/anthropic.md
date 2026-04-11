# Anthropic Model Catalog

> **Source:** [Anthropic API Pricing](https://platform.claude.com/docs/en/about-claude/pricing) · [Models Overview](https://platform.claude.com/docs/en/about-claude/models/overview) · **Verified:** 2026-04-11

---

## Current Recommended Models (Claude 4.x generation)

### Claude Opus 4.6 (Released 2026-02-04)

Anthropic's most capable model. 1 M token context at standard pricing — no long-context premium.

| Metric | Value |
|---|---|
| API name | `claude-opus-4-6` |
| Context window | 1,000,000 tokens |
| Max output | — |
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

Anthropic's Claude 5 generation is underway. **Sonnet 5 "Fennec"** was released February 2026. Claude 5 Opus is anticipated **Q2–Q3 2026** (April–August), following the typical 2–4 month lag after Sonnet releases.

---

## Legacy Models

| Model | Status | Notes |
|---|---|---|
| Claude Opus 4.1 | Active (legacy) | $15 input / $75 output — 67% more expensive than Opus 4.6 |
| Claude 3.5 Sonnet | Active (legacy) | Older generation; lower benchmarks |
| Claude 3 Haiku | Active (legacy) | Superseded by Haiku 4.5 |

*See [deprecated.md](../deprecated.md) for sunset dates.*

---

*See also: [comparison.md](../comparison.md) · [changelog.md](../changelog.md) · [deprecated.md](../deprecated.md)*
