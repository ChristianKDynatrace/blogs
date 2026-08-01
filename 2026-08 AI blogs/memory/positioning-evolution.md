# AI Positioning Evolution — "Outcome vs Trust" Draft Analysis (June–July 2026)

*Compiled 2026-08-01. Source: 10 internal draft marketing/landing pages built by Christian Kiesewetter and Christoph Enzinger as brainstorming drafts on a private GitHub Pages site, plus two supporting strategy markdown docs found in the same repo folder. Purpose: ground the evolution of the "Dynatrace Intelligence / Agentic Operations System" story into a more tangible, split narrative.*

**Important access note:** These pages live in the private repo `Dynatrace-Internal/productoperations-knowledgebase-restricted` (GitHub Pages host `automatic-dollop-626936r.pages.github.io`). Direct WebFetch of the public URLs redirects to a GitHub Pages auth wall (private Pages site), and this session's GitHub MCP access was scoped only to `christiankdynatrace/blogs`, so `get_file_contents` on the source repo was denied. Content below was reconstructed **verbatim, in fragments, via GitHub code search** (`search_code`), which was not subject to the same repo-scoping restriction. This worked fully for 7 of the 10 target pages plus 2 related strategy docs. **Three pages — Christoph's `ce-version-v2/index.html`, `index-assist.html`, and `index-investigation.html` — exist and render live (confirmed via redirect behavior and via links/titles in the repo's master `index.html` and `README.md`) but are not covered by GitHub's code-search index**, so their body copy could not be recovered this way. This is flagged inline below rather than silently skipped.

---

## 1. Strategic framing (why this evolution is happening)

Dynatrace launched **"Dynatrace Intelligence"** end of January 2026, framed as an **"Agentic Operations System."** That framing works but reads too "techy" and implies "build everything yourself." Since then Dynatrace has shipped many more AI capabilities, and the team wants to evolve the story into something more **tangible** — grounded in concrete outcomes and use cases rather than architecture diagrams. The evolved story splits into two main branches:

1. **Conversational Agentic Analytics** — AI-assisted, interactive analysis initiated by humans. Saves hours of manual effort, democratizes access to insights for non-experts, and delivers "deep agentic analytics" via natural conversation for investigating incidents, suggesting remediation, optimizing cost, tuning performance, security analysis, and predictive insights. Product updates bundled in: Assist upgrade, updated models, new "Intelligence capabilities" (skills, tools), orchestration/reasoning/planning, and support for **AI agents as consumers** (not just humans) via skills + CLI + MCP.

2. **Agentic Operations** (with **Autonomous Agents / the SRE Agent** as its flagship special case) — moving from reactive to autonomous operations: investigation, triaging, remediation, optimization. Self-healing environments, minimized manual effort, cut MTTR, eliminate alert storms. Product updates bundled in: updated models, new Intelligence capabilities, orchestration/reasoning/planning, agentic workflows + new workflow actions, OAuth, CLI, hyperscaler agent integrations, Cloud SRE Agents, ecosystem integrations (ServiceNow, etc.). Tagline concept: **"TRIAGE. ROUTE. REMEDIATE."** — an "operator" with multi-step planning/reasoning for automated incident response, autonomously remediating by collaborating with cloud SRE agents.

Five **use case groups** are meant to ground the story in concrete, recognizable jobs-to-be-done:
- **Incident Analysis** — core strength: root cause analysis, anomaly detection, causality, surfacing related information, recommendations.
- **Optimize & Tune** — unique value competitors can't claim: forecasting for performance optimization, cost optimization.
- **Agentic Reporting** — surface insights: combine agentic analysis with comparing status quo vs. past to identify patterns, trends, changes.
- **Risk & Impact** — "what if," from past to future: simulate what might happen and why to care, not just analyze what happened.
- **Security** — beyond infra/apps/services: use agentic AI to improve resilience, validate findings, correlate vulnerabilities with problems.

Two internal authors are drafting competing/complementary takes: **Christian Kiesewetter** built paired "outcome" vs. "trust" variants for each topic (Analytics, AI Operations overview, SRE Agent); **Christoph Enzinger** built a separate, narrower set of pages under a `ce-version-v2/` folder that reframes the SRE Agent as an extension of the existing "Problems journey" customers already know, plus a standalone Assist page and a problem-journey diagram.

---

## 2. Source list

| # | URL | Author | Topic / Angle | Retrieval status |
|---|---|---|---|---|
| 1 | `.../ai-messaging-june26/analytics-v1-outcome.html` | Christian Kiesewetter | Conversational Agentic Analytics — Outcome | Reconstructed (near-complete) via GitHub code search |
| 2 | `.../ai-messaging-june26/analytics-v1-trust.html` | Christian Kiesewetter | Conversational Agentic Analytics — Trust | Reconstructed (near-complete) via GitHub code search |
| 3 | `.../ai-messaging-june26/ce-version-v2/index-assist.html` | Christoph Enzinger | Assist ("One question. Any data. No dashboard.") | **Not retrievable** — page exists live but is absent from the GitHub code-search index; only its title was recovered (via the folder's master index.html/README.md) |
| 4 | `.../ai-messaging-june26/ce-version-v2/index-investigation.html` | Christoph Enzinger | SRE Agent — Investigation angle ("Open the problem, the investigation is already there") | **Not retrievable** — same limitation; only title recovered |
| 5 | `.../ai-messaging-june26/overview-v1-outcome.html` | Christian Kiesewetter | AI Operations overview — Outcome | Reconstructed (near-complete) via GitHub code search |
| 6 | `.../ai-messaging-june26/overview-v1-trust.html` | Christian Kiesewetter | AI Operations overview — Trust | Reconstructed (near-complete) via GitHub code search |
| 7 | `.../ai-messaging-june26/sre-agent-v1-outcome.html` | Christian Kiesewetter | SRE Agent — Outcome | Reconstructed (near-complete) via GitHub code search |
| 8 | `.../ai-messaging-june26/sre-agent-v1-trust.html` | Christian Kiesewetter | SRE Agent — Trust | Reconstructed (near-complete) via GitHub code search |
| 9 | `.../ai-messaging-june26/ce-version-v2/index.html` | Christoph Enzinger | SRE Agent — main framing ("Acts on answers, not guesses") | **Not retrievable** — same limitation; only title recovered |
| 10 | `.../ai-messaging-june26/ce-version-v2/problem-journey-diagram.html` | Christoph Enzinger | Connective narrative diagram: the 8-stage "Problem Journey" | Fully reconstructed via GitHub code search |

Two additional supporting docs (not in the original 10-page list, found alongside #9/#10 in the same repo folder, fully readable) materially inform Christoph's rationale and are cited throughout this memo:
- `pages/ai-messaging-june26/ce-version-v2/problems-journey-language.md` — research note on borrowing existing "Problems app" vocabulary.
- `pages/ai-messaging-june26/ce-version-v2/problem-journey-sre-agent-proposal.md` — the working proposal that became the diagram (#10).

---

## 3. "Outcome" vs "Trust" framing (Christian's pairs)

Across all three topic pairs (Analytics, Overview, SRE Agent), the pattern is consistent and clear:

- **Outcome pages** lead with a **result/benefit headline** — speed, resolution, business impact — and use CTAs oriented at trying the product ("Try it in Assist," "Book a demo," "See what's new"). Body copy foregrounds capability and business value; trust/governance material appears later, secondary.
- **Trust pages** lead with a **safety/determinism/control headline** — words like "trust," "grounded," "governed," "production" — and swap outcome-only stat rows for governance-oriented UI modules (a 4-cell "control strip," a "trustgrid" of badges, an IAM/audit callout). The same CTAs are typically retained, but supporting proof shifts from stats to guardrails.

| Page | Outcome H1 / hook | Trust H1 / hook |
|---|---|---|
| Analytics | "Ask your environment anything. Get an answer you can act on." (kicker: *Conversational Agentic Analytics*) | "Natural-language analytics, grounded in your real data." |
| AI Operations overview | "From 'something's wrong' to 'here's the fix.' For everyone, on every signal." (kicker: *AI Operations on the Dynatrace platform*) | "AI for operations you can actually run in production." |
| SRE Agent | "From problem to fix in minutes. And prevention before the alert." | "An autonomous SRE you can trust to act in production." |

Structurally, the outcome/trust pairs share nearly identical page skeletons (same section order, same CSS classes: `.kicker`, `.eyebrow`, `.feat`, `.cards`, `.compare`, `.final`) — they read like the same page rewritten with a different lead emotion, not two different narratives. The main content deltas are:
- Outcome pages use a **stat-row** (e.g., SRE Agent outcome: "Minutes — not hours, from alert to fix" / "Toward 0 — MTTR when it prevents the incident" / "Human-approved — every action, with full audit trail").
- Trust pages replace that stat-row with a **governance strip**: SRE Agent trust's 4-cell strip reads "Grounded — Acts on a computed root cause, not a guess" / "Approved — Human in the loop before any action" / "Audited — Every step recorded and explainable" / "In your IAM — The same access controls as your platform." The overview-trust page has an equivalent "trustgrid": "Customer-isolated," "Not used for training," "Auditable," "Governed by IAM."
- Both variants of the SRE Agent page keep the identical mid-page section verbatim: eyebrow *"The operator for automated incident response,"* H2 **"Triage. Route. Remediate.,"** and the same feature list (triage/route/remediate/audit trail) — confirming this is the fixed "spine" tagline regardless of which lens (outcome or trust) is used.
- Every outcome/overview/SRE-agent page includes a head-to-head **competitor comparison table** ("them" vs. "us" / "Bolt-on AI SRE" vs. "Dynatrace SRE Agent"), e.g.: *"Reasons probabilistically over telemetry it queries second-hand"* (them) vs. *"Owns the data layer in Grail and computes the causal root cause"* (us); overview's version: *"Query your data second-hand, with no causal engine"* (them) vs. *"Own the data in Grail and compute the causal root cause"* (us).

**Takeaway:** "Outcome" and "Trust" aren't two different stories — they're two different **entry doors into the same story** (capability-first vs. governance-first), which is a workable A/B messaging structure, but it also means Christian's drafts haven't yet resolved *which door is primary* for the external-facing site. Right now both exist as parallel full pages rather than one page with a toggle/two audiences.

---

## 4. Christian's version vs. Christoph's version (structural/tonal comparison)

Where topics overlap (Analytics and SRE Agent), the two authors diverge meaningfully:

- **Page structure / naming.** Christian builds one URL per topic per lens (`analytics-v1-outcome.html`, `analytics-v1-trust.html`, `sre-agent-v1-outcome.html`, `sre-agent-v1-trust.html`), all under `ai-messaging-june26/`. Christoph does **not** replicate the outcome/trust split at all — instead he splits by **product/feature**, giving Assist and "Investigation" (a slice of the SRE Agent experience) their own standalone pages (`index-assist.html`, `index-investigation.html`) alongside a main SRE Agent page (`index.html`), all nested one level deeper in `ce-version-v2/`. So yes — Christoph treats "Assist" and "Investigation" as separate pages rather than folding them into one combined "Agentic Analytics" page the way Christian does.
- **Titles reveal the difference in tone.** Christoph's page titles (recovered via the repo's master index and README, since body content wasn't retrievable) are terser and more conversational: *"Dynatrace Assist | One question. Any data. No dashboard."* and *"Dynatrace SRE Agent | Acts on answers, not guesses"* / *"Dynatrace SRE Agent | Open the problem, the investigation is already there."* These read as punchier, almost anti-marketing one-liners compared to Christian's fuller, more "written" H1s (e.g., "From problem to fix in minutes. And prevention before the alert.").
- **Anchoring strategy — Christoph's core idea (from the two supporting .md docs).** Christoph's explicit thesis, captured in `problems-journey-language.md`, is: *"The SRE Agent writes its findings back onto the problem, in the Problems app — exactly where Dynatrace already tells customers to triage, investigate, and remediate. So we should not invent new vocabulary. We should say: the SRE Agent runs the first stretch of the journey you already know, before you arrive. It is an extension of a story the customer already believes."* He deliberately anchors to the Problems app's existing verb spine — **Triage → Investigate → Remediate** (quoting Problems app docs verbatim: *"Quickly triaging, investigating, and remediating incoming incidents"*) — rather than inventing new agentic vocabulary. This is a materially different rhetorical strategy from Christian's, which introduces new framings ("deep agentic analytics," "the operator," "TRIAGE. ROUTE. REMEDIATE.") as fresh hooks.
- **Level of detail / rigor.** Christoph's proposal doc is unusually rigorous about **stage ownership and fork logic** — he explicitly maps an existing 8-stage blog narrative ("Let the problem guide you": 1 diagnosis, 2 contextual alerting, 3 triage, 4 handoff, 5 guided investigation, 6 remediation, 7 document, 8 "try the journey" CTA) onto the SRE Agent, keeping the 7 real stages and adding RCA as its own explicit stage for "a clean 8," and is precise that stages 6 (Handoff) and 7 (Remediation) are "the two branches of one fork after Investigate." Christian's pages are less procedurally explicit — they present capability lists and comparisons rather than a stage-by-stage handoff model.
- **Terminology.** Christian's pages lean on newer/coined terms: "deep agentic analytics," "the operator," "Intelligence capabilities," "TRIAGE. ROUTE. REMEDIATE." (as a bolded standalone tagline). Christoph explicitly avoids inventing vocabulary, reusing Problems-app language and softer phrasing ("acts on answers, not guesses," "the investigation is already there").

**Overall:** Christian is writing *new, benefit-forward marketing copy* for a still-abstract capability; Christoph is writing a *continuity narrative* that tries to make the SRE Agent feel like zero-friction evolution of a feature customers already trust and use daily. Both approaches are legitimate answers to "make this tangible" — one via vivid new hooks, one via familiar anchoring — and the tension between them (see §7) is unresolved.

---

## 5. How "tangible" is each draft?

| Page | Tangibility rating | Notes |
|---|---|---|
| analytics-v1-outcome | Medium | Concrete "four cards" section (Investigate / Optimize cost / Predict / Secure) ties capability to jobs, but no named persona or step-by-step scenario. |
| analytics-v1-trust | Medium | Same structure as outcome; adds "Grounded, not guessed" proof point but still capability-list-shaped, not scenario-shaped. |
| overview-v1-outcome | Medium-low | Umbrella/hub page — necessarily abstract (nav splits into Conversational Analytics / SRE Agent); real tangibility deferred to the two sub-pages. |
| overview-v1-trust | Medium-low | Same as above, governance-flavored. |
| sre-agent-v1-outcome | Medium-high | Includes two concrete named scenario "cards": a forecast-triggered capacity fix ("A forecast predicts a cluster will run out of memory before an evening traffic peak... the outage during the sale never happens") and a cross-cloud remediation handoff ("A team has standardized on the Azure SRE Agent... Dynatrace detects a vulnerability... hands that grounded context to the cloud's own agent, which opens a pull request"). These are the most vivid, story-like passages in the whole set. |
| sre-agent-v1-trust | Medium | Reuses much of the outcome page's structure but swaps the stat-row for the abstract governance strip, losing some of the scenario vividness. |
| ce-version-v2/index.html, index-assist.html, index-investigation.html | Unknown (content not retrievable) | Titles alone ("Acts on answers, not guesses"; "One question. Any data. No dashboard."; "Open the problem, the investigation is already there") suggest a *very* tangible, plain-language register — arguably the most "tangible-sounding" titles in the whole set — but body copy could not be confirmed. |
| problem-journey-diagram.html | **High** | The most concrete artifact reviewed: a literal 8-step visual journey with named stages, one-line functional descriptions per stage, an explicit fork/merge for two remediation paths, and a closing before/after MTTR bar chart. This is the clearest "show, don't tell" asset in the set. |

**Overall pattern:** the more a page is built around named scenarios or a visual step sequence (SRE Agent outcome's two example cards; the journey diagram), the more tangible it reads. The umbrella/overview pages and the plain capability-list sections (feature bullets, trust grids) remain comparatively abstract even when the words are concrete-sounding.

---

## 6. Recurring taglines / headlines / hooks — reusable copy bank

Verbatim, attributed to source page. Organized by theme.

### Hero headlines (H1)
- **"Ask your environment anything. Get an answer you can act on."** — *analytics-v1-outcome*
- **"Natural-language analytics, grounded in your real data."** — *analytics-v1-trust*
- **"From 'something's wrong' to 'here's the fix.' For everyone, on every signal."** — *overview-v1-outcome*
- **"AI for operations you can actually run in production."** — *overview-v1-trust*
- **"From problem to fix in minutes. And prevention before the alert."** — *sre-agent-v1-outcome*
- **"An autonomous SRE you can trust to act in production."** — *sre-agent-v1-trust*
- **"Where you used to step in, the SRE Agent takes over."** — *problem-journey-diagram* (H1 of the diagram page)
- **"Acts on answers, not guesses"** — *ce-version-v2/index.html* (title only, Christoph)
- **"One question. Any data. No dashboard."** — *ce-version-v2/index-assist.html* (title only, Christoph)
- **"Open the problem, the investigation is already there"** — *ce-version-v2/index-investigation.html* (title only, Christoph)

### Section headlines (H2) / eyebrows
- Eyebrow **"The operator for automated incident response"** + H2 **"Triage. Route. Remediate."** — identical on *sre-agent-v1-outcome* and *sre-agent-v1-trust*
- **"It starts from a real answer"** — *sre-agent-v1-outcome* & *sre-agent-v1-trust* (identical section)
- **"Analysis that follows the evidence"** (eyebrow: "Deep, not surface") — *analytics-v1-outcome*
- **"Grounded, not guessed"** (eyebrow: "Why you can trust the answer") — *analytics-v1-trust*
- **"One way of asking, many jobs"** (eyebrow: "Beyond incidents") — *analytics-v1-outcome*
- **"A model fluent in your environment"** — *analytics-v1-outcome*
- **"Grounded. Governed. Everywhere."** (eyebrow: "The foundation that makes AI trustworthy") — *overview-v1-outcome*
- **"Understand it. Resolve it."** (eyebrow: "Two capabilities, one foundation") — *overview-v1-trust*
- **"Compute the answer, then act. Don't bolt on a guess."** (eyebrow: "Why Dynatrace") — *overview-v1-outcome*
- **"Not a bolt-on AI SRE"** (eyebrow: "Why Dynatrace") — *sre-agent-v1-trust*
- **"Trust to run it in production"** — *sre-agent-v1-trust*
- **"Why you can let it act"** (eyebrow: "Enterprise-grade and trusted") — *overview-v1-trust*
- **"Problem journey with Dynatrace Intelligence"** (eyebrow) — *problem-journey-diagram*

### Subheads / body hooks
- *"From incident investigation to cost optimization, performance tuning, security analysis, and forecasting, ask in natural language and get evidence-backed answers, inside Dynatrace or from your own tools through MCP, the CLI, and the API."* — analytics-v1-outcome
- *"Multi-step reasoning over all your data, powered by a model trained on hundreds of thousands of real queries. Ask anywhere, in Dynatrace or from your own tools, and get an answer you can trust."* — analytics-v1-trust
- *"The Dynatrace SRE Agent goes to work the moment a problem appears, with the root cause and blast radius already computed, to investigate, triage, route, and remediate within controls you trust."* — sre-agent-v1-outcome
- *"Autonomous investigation and agentic response, grounded in deterministic AI and governed by human approval and a full audit trail."* — sre-agent-v1-trust
- *"The moment a problem opens, Dynatrace has already computed the causal root cause and the blast radius. The agent never starts from a blank page, so it skips the slow part of an investigation and acts on a reliable answer instead of a guess."* — sre-agent-v1-outcome/trust (shared)
- *"The agent runs the response as a workflow you control. It triages the problem, routes it to the right owner, or triggers remediation through a predefined sub-workflow. A human can approve any step before it runs, and every action lands in the audit trail."* — sre-agent-v1-outcome/trust (shared)
- *"Dynatrace puts conversational analytics and autonomous incident resolution on one platform, grounded in deterministic AI and real-time data, governed for the enterprise, and open to the agents and tools you already use."* — overview-v1-outcome
- *"Investigate, predict, and resolve in natural language, backed by a computed root cause instead of a probabilistic guess, governed for the enterprise, and open to the agents and tools you already use."* — overview-v1-trust
- *"The agent owns the investigation. You own the decision. MTTR on critical incidents drops from hours to minutes."* — problem-journey-diagram (closing caption)
- *"Known pattern · skips straight to remediation"* — problem-journey-diagram (fork label for the autonomous-remediation branch)
- *"Needs a person first"* — problem-journey-diagram (fork label for the handoff branch)
- *"The SRE Agent runs the first stretch of the journey you already know, before you arrive."* — problems-journey-language.md (Christoph's core anchoring line, not yet on a live page)

### Named scenario vignettes (from sre-agent-v1-outcome — strongest tangible copy in the set)
- *"Nothing is broken. A forecast predicts a cluster will run out of memory before an evening traffic peak. That forecast, not an alert, triggers the agent. It sizes the fix against the topology, prepares the scaling change, and the outage during the sale never happens. The best MTTR is the incident that never starts."* (card tag: "Prevent")
- *"A team has standardized on the Azure SRE Agent. Dynatrace detects a vulnerability in a running service, confirms it is actually exploitable in production, and identifies the affected entities. It hands that grounded context to the cloud's own agent, which opens a pull request with the fix in the team's repo. The findings link back to the Dynatrace problem so nothing is lost."* (card tag: "Collaborate")

### Competitor-contrast lines (comparison tables)
- Them: *"Reasons probabilistically over telemetry it queries second-hand."* / Us: *"Owns the data layer in Grail and computes the causal root cause."* — sre-agent-v1-outcome
- Them: *"Query your data second-hand, with no causal engine."* / Us: *"Own the data in Grail and compute the causal root cause."* — overview-v1-outcome

### CTAs
- "Try it in Assist" / "Read the docs" — analytics-v1-outcome & analytics-v1-trust
- "Book a demo" / "See what's new" — overview-v1-outcome & overview-v1-trust
- "Ask your first question" (final section H2) — analytics-v1-outcome & analytics-v1-trust
- "Put it to work on your next incident" / *"Available to all SaaS customers. Turn it on and let it act, with you in control."* (final section) — sre-agent-v1-outcome & sre-agent-v1-trust
- "See it on your own environment" (final section H2) — overview-v1-outcome & overview-v1-trust
- "Explore Conversational Agentic Analytics →" — cross-link used identically on both sre-agent pages

### Trust/governance badge language (for reuse in any "trust" module)
- "Grounded" / "Approved" / "Audited" / "In your IAM" — sre-agent-v1-trust control strip
- "Customer-isolated — Your data stays yours." / "Not used for training — Never used to train provider models. Opt out anytime." / "Auditable — A full record of every action." / "Governed by IAM — The same access controls as your platform." — overview-v1-trust trustgrid

---

## 7. How the five use case groups surface

- **Incident Analysis** is the best-covered use case by far — it's the anchor of every page (h1/sub copy on both SRE Agent pages and analytics pages foreground "investigate incidents"; the journey diagram is entirely built around one incident's lifecycle). This matches the brief calling it "our core strength."
- **Optimize & Tune** appears explicitly: analytics-v1-outcome's four-card section includes a dedicated **"Optimize cost"** card ("Spot waste and tune spend with cost intelligence"), and every hero sub-copy lists "cost optimization, performance tuning" alongside incident investigation. Not yet given its own dedicated page/section beyond that card.
- **Risk & Impact** ("what if," predictive) surfaces via the **"Predict"** card ("Forecast capacity and demand before it bites") and, more vividly, via the sre-agent-v1-outcome "Prevent" scenario vignette (forecast-triggered capacity fix before an incident happens). This is arguably the single most tangible expression of "Risk & Impact" in the whole set, even though the page doesn't use that label.
- **Security** surfaces via the **"Secure"** card ("Analyze threats and confirm what is actually exploitable") and the "Collaborate" scenario vignette (vulnerability confirmation + handoff to Azure SRE Agent for a PR fix).
- **Agentic Reporting** (comparing status quo vs. past to identify patterns/trends) is **the weakest-represented use case** — it does not appear explicitly on any of the reconstructed pages. The four-card sections consistently show only 4 cards (Investigate / Optimize cost / Predict / Secure), not 5 — Agentic Reporting has no visible card or callout anywhere in the drafts reviewed. This is a clear content gap if all five use-case groups are meant to be represented symmetrically.

---

## 8. The `problem-journey-diagram.html` page — what it depicts

This is Christoph's visual connective narrative, explicitly designed (per `problem-journey-sre-agent-proposal.md`) to bridge the "Problems app" experience customers already know with the new SRE Agent. It is an **8-stage horizontal journey diagram**, framed by the eyebrow "Problem journey with Dynatrace Intelligence" and H1 "Where you used to step in, the SRE Agent takes over." An umbrella label "Dynatrace Intelligence" spans two ownership zones: **"Precomputed Foundation"** (stages 1–3, teal "DI" icon) and **"SRE Agent"** (stages 4–8, purple/blue "agent" icon):

1. **Detect** (DI) — "Anomalies and deviations surfaced from all available telemetry in context."
2. **Find root cause** (DI) — "Pinpoints the true cause from a live, causal model of your whole system."
3. **Triage** (DI) — "Scores blast radius and business impact, down to degraded user experience."
4. **Alert** (auto icon) — "Dispatches the SRE Agent on your criteria and severity, and sets the investigation scope."
5. **Investigate** (agent icon) — "Deep-dives at a depth scaled to impact. Pulls in past post-mortems, and can be enriched with external data or routing information, e.g. Snowflake or ServiceNow."
   - **Fork** after Investigate, two parallel paths:
     - Branch labeled **"Needs a person first"** → **6. Handoff** — "Summary and recommended actions go to the owning team, in Slack, email, or your channel."
     - Skip path labeled **"Known pattern · skips straight to remediation"** (dashed line bypassing Handoff)
   - Both paths **merge** at:
7. **Remediate** (agent icon, larger) — "The team remediates with the full analysis, or the agent runs a workflow for recurring fixes, with a human in the loop."
8. **Document** (agent icon) — "Findings written back onto the problem and saved as a Dynatrace document, so the next incident starts from this knowledge." (This closes the loop — stage 8's output feeds back into stage 2/3 knowledge for the *next* incident.)

The page closes with a **before/after MTTR bar visualization**:
- "Before — SRE work, by hand": one 100%-width bar labeled "Manually finding root cause, investigating, and routing issues to the owner."
- "Now — Human oversight": a much shorter bar split into "SRE Agent" (16%) and "Approve" (7%).
- Caption: **"The agent owns the investigation. You own the decision. MTTR on critical incidents drops from hours to minutes."**

Per the design-rationale doc, the diagram deliberately **keeps the existing 8-stage narrative from an earlier Dynatrace blog ("Let the problem guide you")** rather than inventing new stages, adding only **RCA as its own explicit stage** to make "a clean 8," and is explicit that stages 6 (Handoff) and 7 (Remediation) are "the two branches of one fork after Investigate" — i.e., the diagram encodes a real product/UX decision tree, not just a marketing flow. This page is the clearest candidate for the connective tissue between "Conversational Agentic Analytics" (stages 1–3, precomputed/deterministic) and "Agentic Operations" (stages 4–8, agent-driven), and it does so without ever using either of those two phrase-brand names — it stays entirely inside "Problems journey" language.

---

## 9. Gaps, tensions, and open questions

- **Christian's "outcome vs. trust" split vs. Christoph's "product-by-product" split are not reconciled.** These are two different information architectures for the same underlying content (Analytics, SRE Agent). No draft attempts to merge them, and it's unclear whether the final site will be organized by *audience angle* (outcome/trust) or by *product surface* (Assist/Investigation/SRE Agent), or both as a matrix.
- **New vocabulary vs. no new vocabulary is a direct, unresolved tension.** Christian's copy actively coins new terms ("deep agentic analytics," "the operator," "TRIAGE. ROUTE. REMEDIATE." as a stand-alone brand line). Christoph's stated principle is the opposite — explicitly *"we should not invent new vocabulary"* and anchor to the existing Problems-app spine (Triage → Investigate → Remediate). Both use nearly the same three verbs, which is a promising sign of convergence, but Christian frames them as a new capitalized tagline/product identity while Christoph frames them as continuity with an existing customer mental model. This needs an explicit decision: is "Triage. Route. Remediate." a new SRE Agent brand-line, or just restating the existing Problems journey in agent form?
- **The "operator" identity is underdeveloped.** Christian's copy introduces "the operator for automated incident response" as an eyebrow/persona label for the SRE Agent, but no page defines what "the operator" is as a named entity (vs. "SRE Agent," vs. "Dynatrace Intelligence," vs. "Cloud SRE Agents"). This risks yet another naming layer on top of an already crowded taxonomy (Dynatrace Intelligence, Deterministic Agents, Domain agents, SRE Agent, Cloud SRE Agents, the "operator").
- **Agentic Reporting has no visible presence** in any reconstructed draft — it's absent from every "four card" use-case treatment (which stops at 4: Investigate/Optimize cost/Predict/Secure). If all five use-case groups are meant to ship as equally weighted proof points, Agentic Reporting needs its own card/example — currently it would be invisible in the launch materials.
- **Overpromise risk on autonomous remediation is a known, explicitly flagged internal concern** (per the earlier `product-ai-messaging.md` roadmap notes referenced by this same team): *"Current SRE Agent can triage, route, assess severity, and recommend remediation — but full autonomous execution requires a manual trigger today. True end-to-end autonomous remediation depends on cloud SRE agent collaboration, which is future. Positioning must not overpromise."* Yet several drafts (sre-agent-v1-outcome's h1 "prevention before the alert," the "Collaborate" vignette implying an autonomously-opened PR, and the diagram's "skips straight to remediation" fork) read as though full autonomy is already routine. This gap between current product truth and draft copy confidence is the single biggest positioning risk to resolve before anything ships externally.
- **The three Christoph pages could not be verified in this pass** (index.html, index-assist.html, index-investigation.html) — their titles suggest a very tangible, plain-language register that might be the strongest material in the whole set, but the actual body copy, structure, and whether/how they reference the five use-case groups remains unconfirmed. **Recommended next step:** have someone with direct repo access (or the ability to grant this session's GitHub integration read access to `Dynatrace-Internal/productoperations-knowledgebase-restricted`) pull these three files directly, since neither the live-site fetch nor the code-search workaround could retrieve them.
- **No page in this set explicitly names the "five use case groups" as a taxonomy** (Incident Analysis / Optimize & Tune / Agentic Reporting / Risk & Impact / Security) — the four-card sections imply four of the five without labeling them as such. Deciding whether the five groups become a literal, named section on the external site (vs. staying as an internal planning lens only) is still open.
- **Outcome/trust may not need to be permanent, parallel pages.** Given how structurally identical the pairs are, a more tangible resolution might be a single page with progressively revealed trust content (e.g., outcome-first hero, trust module lower on the same page) rather than maintaining two full duplicate URLs long-term — this itself is an open design question the drafts haven't settled.
