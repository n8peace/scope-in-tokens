---
name: scope
description: Scope any piece of work in tokens needed, not hours, and pick the cheapest model that does each part well. Use for "scope this", "how big is this", "estimate", "how long will it take", "plan the build", a release plan, a roadmap item that needs a size, or any timeline.
---

# Scope in tokens

Agents run in parallel, so hours don't decide speed. Tokens do, and they also decide cost. Every scope answers three questions: how many tokens, on which model, and what the real critical path is.

## Steps

1. **Split the work into lanes** that can run at the same time. Each lane has its own check (a test, a build, a screenshot, a listen) and touches files no other lane touches. Lanes that share files run one after another.
2. **Pick the worker for each lane:** the cheapest one that does it well.
   - A script (no model) for checks, counts, fetches and "did it go live".
   - A small model (for example Haiku) for finding files, reading logs and bulk extraction.
   - A coding agent (for example Codex, with a stronger model for hard lanes) for code whose check is mechanical.
   - A mid model (for example Sonnet) for scoped drafts, critics and release steps.
   - A top model (for example Opus) for judgment: the lead, design, payments, security and public words.
3. **Estimate tokens per lane, re-reads included.** Split the coding agent from the chat model, and the chat model by tier.
4. **Name the critical path.** It's usually not tokens. It's people (keys, picks, approvals), outside reviews (an app store) and shared hardware (one simulator). Say which extra lanes would help and which wouldn't.
5. **Use dates only where someone outside sets them** (a store review, a launch day, a price deadline).
6. **Log actual tokens beside the estimate** when the work ships, so the next scope gets better.

## Output shape

| Lane | Coding agent | Chat model |
|---|---|---|
| (a) App player | 6M | Top 0.8M lead; Mid 0.5M check |
| (b) Daily render | 3M | Top 0.3M |
| **Total** | **N M** | **N M (Top, Mid, Small)** |

Then give the share of your weekly usage limit it takes, the critical path in 3 to 5 bullets, and the outside dates.

## Never

- Hours or days as the size.
- One model for everything because it's the default.
- A swarm where lanes edit the same files.
