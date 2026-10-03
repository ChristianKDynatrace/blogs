# Blog #1 Outline — Agentic Analytics

*Drafted 2026-08-01. Restructures `PNB-Agentic-Analytics_Original.md` around the four durable pillars agreed in `tasks.md` §1 — evolves the existing draft's content, drops its release-note framing, replaces the dropped Christoph proof points, and adds the beyond-incidents section it was missing. Written against `writing-style.md`'s conventions (thesis-first open, third person, benefit-phrase H2s, bulleted parallel lists with bolded lead terms, quoted literal example prompts, "Get started" close).*

---

## Working title

**"Ask your environment anything: how Dynatrace reasons across everything you run"**

Keeps the "ask anything" hook from Christian's own web draft H1 (message-match between the landing page and the blog is a feature, not a coincidence), but frames it as a blog title rather than a CTA line, and the "everything you run" clause does the "beyond incidents" signaling right in the title instead of waiting for section 4 to make that case.

---

## Opening (no H2 — thesis + context, per the two-beat open pattern)

- **Thesis sentence** (declarative, no question hook): something like *"Dynatrace's agentic analytics lets you ask any question about your environment in natural language and get an answer grounded in real, live data — whether that question is about a root cause, a cost spike, a forecast, or a vulnerability."* Sets scope wide from sentence one, so the piece isn't read as an incident-only story that later "also" mentions other things.
- **Context paragraph**: the general problem this solves — practitioners currently stitch together dashboards, queries, and tribal knowledge to answer questions across different domains; most conversational AI tools in this space (per the competitive review) are built for one job (investigation) and bolt everything else on. Sets up why breadth-with-depth is the actual differentiator, without naming competitors.

---

## H2 1 — A reasoning engine built for real investigations *(pillar 1)*

- Reuse the existing draft's explanation almost as-is: multi-step reasoning, tool use across a long investigation, following a dependency graph upstream without losing context of where it started.
- **Add the competitive edge explicitly** (currently only implicit in the existing draft): name that Grail + Smartscape exist and are precomputed *before* the question is asked — contrast this plainly with "reasoning that assembles its own picture at query time," without naming Causely/Traversal directly (matches the existing draft's practice of not naming competitors).
- **Proof, using the pptx prompts descriptively** (not their stale screenshot numbers): quote 1-2 prompts verbatim as literal example strings, per the style guide's convention —
  > *"What is causing the issues in the EntityResourceImpl service."*
  > *"I want a deep failure investigation across the frontend and astroshop services... find multiservice traces involving more than 3 services and show me the entry endpoint and full chains."*
  These demonstrate reasoning depth without requiring a number to land.
- **Cross-link**: mention Medium post #1's causal alert-merge example as a "read the deep dive" pointer — *"Choose the latest problem where astroshop-payment is the root cause and summarize the major reasons why the single alert events were merged into the problem"* is a good second quoted example, already validated as safe (double-sourced, already public).

## H2 2 — A model fluent in your data, not just language *(pillar 2)*

- Reuse existing draft's explanation near-verbatim: purpose-built model trained on real DQL queries, understands data structure the way a fluent practitioner would.
- Evidence: the ~85% zero-context query validity / 2-3x speed stats — **pending the ownership/currency check flagged in `tasks.md`** before this ships; if not cleared in time, this section can run on the qualitative claim alone (data fluency) without the stat, since the existing draft's mechanism explanation is real substance on its own.
- Mention it runs identically through Assist, Notebooks, Dashboards, and the MCP server (existing draft's "ask a data question anywhere" point) — this is good breadth evidence at the *infrastructure* level, complementing pillar 4's job-level breadth.

## H2 3 — The investigation playbook, encoded *(pillar 3)*

- Reuse the existing draft's section close to verbatim — it's solid and untouched by either other source: curated skills (RCA, telemetry correlation, hyperscaler-specific expertise for AWS/Azure/Kubernetes), the "senior SRE playbook, not reasoning from scratch" framing.
- Keep the forward-looking line about teams contributing their own skills later — good, distinctive, no competitor claims an extensible customer-owned skill layer.

## H2 4 — One brain, every job — not just incidents *(pillar 4, the "beyond incident remediation" section, currently one throwaway sentence in the existing draft)*

- **Argument paragraph first**: explain *why* this generalizes — the reasoning engine, the data fluency, and the skills aren't incident-specific, so the same system answers a cost question, a forecast, a security question, or a report request the same way it answers a root-cause question. This is the section that actually earns the "more than incident remediation" claim instead of asserting it.
- **Bulleted list, 5 items, bolded lead term each** (per style convention), corrected group names, one line each, cross-linked to Blog #4:
  - **Investigate** — find root cause with evidence, traced across your stack.
  - **Optimize & Tune** — spot waste, tune performance and resource usage, not just cost.
  - **Risk & Impact** — simulate what might happen before it does, not just forecast a number.
  - **Security** — confirm what's actually exploitable, in business terms.
  - **Agentic Reporting** — compare status quo against the past to surface trends automatically.
- **One supporting stat**, in place of the dropped Christoph vignette: Medium #2's headline number — *"a real investigation can involve tens of thousands of raw log lines; Dynatrace's log-pattern tooling distills that down to roughly a thousand tokens of signal before it ever reaches the reasoning engine"* (paraphrased from the 49,538 → 3.3M → 22,473 → ~1,000 tokens figure) — already public, no verification risk, and reinforces "efficient, deterministic, not brute-force" rather than just breadth.
- Explicit cross-link line to Blog #4 for readers who want full worked examples per job (standard practice per style guide's "cross-link to related content" convention).

## Closing — "Get started" *(per style convention)*

- Short, punchy restatement of the value prop as a tagline line (style guide pattern).
- Concrete CTA: try it in the Dynatrace Playground / turn on agentic mode in Assist — reuse the existing draft's closing paragraph almost as-is, it already does this well ("Turn on agentic mode and put it to work on a real problem...").
- **Availability footnote, demoted from framing device to closing detail**: keep a line noting these capabilities are live today, but drop the specific "SaaS release 338 (May 2026)" anchor as the article's organizing device — that date is now three months stale relative to today. If a specific release reference is still wanted for credibility, it should be updated to whatever's current at publish time, not carried over from the old draft.
- Cross-link to Blog #2 (Agentic Operations) as the natural next read: *"Every job above can also run autonomously, without a person asking the question — that's Agentic Operations."*

---

## What's intentionally NOT in this draft

- No specific numeric proof from Christoph's `index-assist.html` (dropped, per `tasks.md`).
- No full worked examples per use-case job — those stay in Blog #4; this piece only teases with one line + one supporting stat per the capability/use-case split.
- No "AI Observability" content from the pptx — it doesn't fit any of the five jobs and isn't a capability-layer point either; leave it for whoever plans that gap (flagged in `tasks.md` §4).
