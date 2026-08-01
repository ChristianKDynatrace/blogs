# Blog Production Plan — Task Breakdown (Aug 2026)

*Purpose: break the planned blog series into concrete sub-tasks/decisions before we move into per-blog planning. Draws on the memory docs in `memory/` (writing-style, product-ai-messaging, competition, positioning-evolution, medium-content-analysis, competitive-differentiation-review) and the existing draft in `agentic analytics/`.*

**Update (2026-08-01, planning session):** the cross-cutting decisions in §0 have been resolved through planning discussion, and the series is now **6 pieces**, not 5 (SRE Agent confirmed as its own blog). A structural principle also emerged that reshapes several of these: **separate durable capability content from evolving use-case content** — see the note at the top of §1.

1. Agentic Analytics (capability-focused, human-led)
2. Agentic Operations overview (capability-focused, autonomous — mirrors #1's structure)
3. SRE Agent (dedicated deep-dive)
4. Five use-case groups, concrete examples (human-led + autonomous) — **now the sole owner of full worked examples**, referenced by #1 and #2 rather than duplicated in them
5. Governance & enterprise readiness
6. Medium blog summary/consolidation (still open go/no-go)

---

## 0. Cross-cutting decisions — RESOLVED (2026-08-01)

- **Naming: "Agentic Analytics."** Decided over "Agentic Investigations." All five reviewed competitors (`competition.md`) are fundamentally investigation products — naming the human-led blog "Investigations" would read as entering their game on their terms. "Agentic Analytics" is wide enough to include investigation as the lead job while making room for cost/tuning, forecasting/risk, security, and reporting as jobs none of the five competitors claim conversationally. Investigation stays the opening chapter (competitive parity, most relatable hook) but isn't the umbrella name.
- **SRE Agent: its own blog**, separate from a broader Agentic Operations overview. Matches how both Christian (`overview-v1-*` vs `sre-agent-v1-*`) and Christoph (`index` vs `index-investigation`) already split their drafts independently — a strong signal this is the natural seam.
- **Vocabulary: new branded vocabulary**, not Problems-journey-only continuity. Operations/SRE Agent content leads with "the operator" / "Triage. Route. Remediate." as a distinct SRE Agent brand line. Note: "the operator" is still an undefined entity per `positioning-evolution.md` §9 — the SRE Agent blog needs to do that definitional work, not just reuse the label.
- **Outcome vs. Trust: kept as two angles within one piece**, not blended into a single narrative. Whichever blog covers Operations/SRE Agent should read as one outcome-led piece with a distinct, identifiable trust/governance section or callout — not two separate articles, but not fully dissolved into one voice either.
- **Category naming: avoid "AI SRE."** Don't fight on a category term Rootly and Traversal have already invested in defining. Keep using Dynatrace's own names (Dynatrace Intelligence, SRE Agent, the five use-case groups).
- **Overpromise risk on autonomous remediation** (wording discipline, not a decision to make): current SRE Agent triages/routes/recommends, but full autonomous execution needs a manual trigger today; true end-to-end autonomy depends on cloud SRE agent collaboration (future). State the current maturity stage honestly in any Operations/SRE Agent copy — per `competitive-differentiation-review.md` §3, this is a chance to look *more* disciplined than Datadog/Traversal (whose headlines outrun their own docs), not just a risk to manage defensively.

---

## 1. Agentic Analytics blog

**Status:** furthest along — a full draft already exists: `agentic analytics/PNB-Agentic-Analytics_Original.md` + a language-reviewed pass `..._after_language_review.md`. **Decision (2026-08-01): evolve this draft**, don't start fresh — its actual content (reasoning engine, model fluency, investigation skills) is already capability-shaped, which is exactly the right scope per the principle below.

**Core structural principle, decided 2026-08-01:** separate *capabilities* (how it works — durable, but the specific evidence behind it evolves every release) from *use cases* (what job gets done — evolves on a much slower cadence, roughly 6-9 months). This blog and the Agentic Operations overview (§2) own capabilities; the five-use-case blog (§4) owns full worked examples for both. This keeps capability updates from forcing rewrites of use-case narrative that didn't change, and keeps examples from being duplicated/drifting across three blogs.

This does **not** mean the release-note framing of the existing draft should be kept — "capability-focused" and "release-note voice" are different axes. The existing draft's throughline ("this release brings...") should be replaced with a value narrative organized around durable pillars, with current evidence attached as support rather than as the structure itself. Proposed pillars:

1. **A reasoning engine that doesn't lose the thread across a real investigation** — multi-step reasoning, tool use, follows Smartscape topology as far as the evidence leads. Competitive edge to make explicit here (from `competitive-differentiation-review.md` §1): Grail + Smartscape are precomputed *before* the question is asked, unlike Causely/Traversal, which build their causal graph at investigation time. This is the sharpest, least-contested differentiator available — name it, don't imply it.
2. **A model fluent in your data, not just language** — trained on real DQL queries. Evidence: ~85% valid-query rate in zero-context cases / 2-3x faster than previous implementations. These appear stated as fact (unhedged) in the existing draft, unlike the more cautious "pending external validation" caption on Christoph's `index-assist.html` — treat them as real evidence, but do a quick ownership check before publishing.
3. **Investigation expertise that's encoded, not reasoned from scratch** — the curated skills (RCA, telemetry correlation, hyperscaler-specific knowledge), plus the forward-looking detail that teams will contribute their own skills later. Frame as "versioned, inspectable, eventually yours to extend" — a specific angle Rootly/Causely don't claim.
4. **One brain, every job — not just incidents.** This is where "beyond incident remediation" gets a real section instead of the current draft's one throwaway line. Argue *why* it generalizes (the engine/fluency/skills aren't incident-specific), then a short, named 5-job teaser — **Investigate / Optimize & Tune / Risk & Impact / Security / Agentic Reporting** (corrected group names — "Optimize & Tune" not "Optimize cost," "Risk & Impact" framed as forward-looking "what if" simulation, not just forecasting; also now 5 jobs, closing the Agentic Reporting gap flagged everywhere else) — each one line, cross-linked to the use-case blog (§4) for depth. Prove the breadth claim with a real example rather than just an assertion — see the replacement proof-point decision below (Christoph's vignette is no longer available for this).

**Decision (2026-08-01): drop Christoph's `index-assist.html` proof points entirely** — not just pending verification, but decided against. We have no way to independently confirm the tenant-sourced numbers (1,277 checkout events, 98.8% CPU host, 477 sessions/hr), and even if genuine when captured, they're a point-in-time demo-tenant snapshot that would need a fresh run regardless. Not worth the risk for a public blog. The structural device (a cross-domain vignette proving breadth) is still worth keeping — it's just re-sourced, per below.

**Replacement proof-point sources found (2026-08-01):**
- **A new internal source: `Agentic_Analytics__Example_Prompts.pptx`** (uploaded by the user, dated 7/2/2026, "a bit outdated") — 49 slides of real prompts run against the demo environment, organized by category (Investigate incidents, Forecast & Prediction, Infrastructure, AI Observability, Security, APM, DEM, Cost Intelligence). Its own subtitle is literally "Conversational Agentic Analytics," independently confirming the naming decision. **The prompt text is durable and safe to reuse; the screenshot numbers are stale/outdated like Christoph's were** — use prompts descriptively, don't cite specific figures from the screenshots without a fresh re-run. **Action: persist this deck's content into a memory doc — the uploaded file itself is session-ephemeral and will not survive after this session.** Strongest pillar-1 candidates identified so far (investigation depth, no number required to land): "explain why the single alert events were merged into the problem" (matches Medium #1), "what is causing the issues in the EntityResourceImpl service," the multi-part deep cross-service failure investigation prompt, "find systemic, recurring issues" over 7 days.
- **Medium #1's causal alert-merge explanation** — same prompt pattern as the pptx slide above, so it's double-sourced (internal deck + already-published post). Safe to use since it's already public; no new reveal, no verification risk.
- **Medium #2's log-pattern token-compression stat** (49,538 raw log records → 3.3M tokens unfiltered → 22,473 tokens filtered → ~1,000 tokens after pattern extraction) — decided (2026-08-01) to use the **headline stat only**, as a single supporting sentence for pillars 1/2 ("efficient, deterministic reasoning, not brute-force"), not the full methodology (Drain algorithm/"Lost in the Middle" citations) — that deeper technical grounding stays reserved for blog §6 if it goes ahead, so citing the headline number here doesn't cannibalize that piece's distinct value. Already public, so no verification risk.
- **Also noted:** the pptx's "AI Observability" category (LLM/agent failures, token cost, agent health) doesn't map to any of the five use-case groups — worth a mention in this blog or flagging for §4/§5 as a possible 6th category or Security sub-case, not force-fit into the existing five.

Sub-tasks:
- [x] Naming/framing decision — resolved, "Agentic Analytics" (§0).
- [x] Capability-vs-use-case scope decision — resolved, this blog owns capabilities only, light 5-job teaser + cross-link, full examples deferred to §4.
- [x] Christoph's `index-assist.html` numbers — resolved, dropped entirely (see decision above), replaced with the pptx + Medium #1/#2 sources.
- [ ] Rewrite the existing draft's throughline away from "this release brings..." into the four pillars above; demote the SaaS-release-338 tie-in to a closing footnote (the existing draft already does this in its last paragraph — keep that, drop the framing role it currently also plays earlier in the piece).
- [x] Persist the `Agentic_Analytics__Example_Prompts.pptx` content into a memory doc before it's lost (session-ephemeral upload) — done, see `memory/example-prompts-inventory.md`.
- [ ] Use the pptx's causal-alert-merge / EntityResourceImpl / systemic-recurring-issues prompts as pillar 1 demonstration material (descriptively, not numerically).
- [ ] Use Medium #1's causal alert-merge example and Medium #2's headline token-compression stat as pillar 1/2/4 evidence, per the decision above.
- [ ] Verify ownership/current validity of the ~85% / 2-3x stats before publishing (pillar 2) — this one is still pending, not dropped; it comes from the existing draft (a real, reviewed release blog), not from Christoph's page, so it's a different evidentiary tier.
- [ ] Cross-check against `product-ai-messaging.md` for anything shipped/announced since the draft was written that should be folded into the pillars.
- [ ] When §4 (five use-case blog) exists, add the actual cross-links from the pillar-4 teaser row.
- [ ] Pass through `writing-style.md` voice check (Christian's own blog register, not the first-person Medium voice).
- [ ] Final proofread/language review after the restructuring (a review pass already happened once on the old structure — will need another after these changes).

---

## 2. Agentic Operations overview blog

**Status:** no draft yet. Confirmed as its own blog, separate from the dedicated SRE Agent piece (§0/§3).

Should mirror Blog #1's shape: capability-focused, not a use-case tour. Same principle applies — the "Prevent/Resolve/Collaborate" autonomous jobs are the operations-side counterpart to Blog #1's 5-job teaser, so this blog gets its own short teaser row + cross-link to §4 rather than developed examples, and leans on its own durable pillars (autonomous triage/routing/remediation mechanics, governance-by-design, cross-hyperscaler orchestration) rather than a specific release.

Sub-tasks:
- [x] One-blog-vs-two-blog and vocabulary questions — resolved (§0): separate SRE Agent blog, branded vocabulary ("the operator," "Triage. Route. Remediate.").
- [ ] Foreground the cross-hyperscaler orchestration story (Cloud SRE Agents routing across AWS DevOps Agent, Azure SRE Agent, *and* Gemini Cloud Assist simultaneously) more explicitly — per `competitive-differentiation-review.md` §4, this is the single most defensible, uncontested differentiator found in the whole review and is currently under-leaned-on in the draft copy.
- [ ] Apply the outcome/trust-as-two-angles structure (§0) — one outcome-led narrative with a distinct, identifiable trust/governance section.
- [ ] Explicitly apply the overpromise-risk wording discipline (§0) — state the current maturity stage (Automated → Supervised Autonomous → Fully Autonomous, `product-ai-messaging.md` §2) honestly rather than letting vivid copy imply more autonomy than exists.
- [ ] Consider folding in Medium post #5 ("Agentic Workflows are Killing your Classic Weekly Observability Report") for the workflow-automation/governance angle (service-user actor, permission boundary) — see `medium-content-analysis.md` §"Reusable Concrete Assets — #5".
- [ ] Voice/style pass against `writing-style.md`.

---

## 3. SRE Agent blog (dedicated deep-dive)

**Status:** no draft yet. Richest available source material of any planned piece.

Sub-tasks:
- [ ] Define "the operator" as a named entity (§0 flags this as currently undefined anywhere) — needed since the branded-vocabulary decision leans on it.
- [ ] The 8-stage problem-journey diagram (`positioning-evolution.md` §8/§10.3) is close to a ready-made backbone — adapt it as a visual for this blog.
- [ ] Pull in the three named scenario vignettes (Resolve/Prevent/Collaborate) — already reused verbatim across three separate drafts, so they're clearly considered strong, reusable material.
- [ ] Decide whether to name specific ecosystem partners (AWS DevOps Agent, Azure SRE Agent, ServiceNow Assist, Kiro, GitHub Copilot, Atlassian Rovo Ops — from `index-investigation.html`, §10.3) and confirm current partnership/launch status of each before naming them publicly — some of these ("Kiro," "Atlassian Rovo Ops") aren't yet cross-referenced elsewhere in our memory docs and should be confirmed before publishing.
- [ ] Explicitly apply the overpromise-risk wording discipline (§0) throughout — this is the section most likely to overstate current autonomy.
- [ ] Apply the outcome/trust-as-two-angles structure (§0), same as §2.
- [ ] Voice/style pass against `writing-style.md`.

---

## 4. Five use-case groups blog (human-led + autonomous examples)

**Status:** no draft yet, but `medium-content-analysis.md` already did most of the source-mapping work. **Role clarified (2026-08-01):** this blog is now the sole owner of full worked examples for all five groups — Blogs #1 and #2 only carry a one-line-per-job teaser and cross-link here rather than developing their own examples. Worth sketching this blog's outline in parallel with #1, since #1's teaser links depend on this blog existing.

Sub-tasks:
- [ ] Build the (use case) × (human-led example, autonomous example) matrix. Current backbone mapping from `medium-content-analysis.md`:
  - **Incident Analysis** — human-led: Medium #1 (Problem Analysis Skill, `astroshop-payment` demo). Autonomous: SRE Agent "Resolve" vignette (§10.1/10.3).
  - **Optimize & Tune** — human-led: Medium #3 (Predictive Analytics Skill — disk capacity, cost/token forecasting). Autonomous: the "Prevent" vignette (forecast-triggered capacity fix) doubles as this group's autonomous side.
  - **Agentic Reporting** — human-led: Medium #4 (ad-hoc conversational adoption report) as the manual-trigger variant. Autonomous: Medium #5 (scheduled agentic workflow report) is the ready-made autonomous example.
  - **Risk & Impact** — Medium #4's SDK-version-bump impact question, reframed explicitly as "what if" rather than generic RUM (flagged in `medium-content-analysis.md` as needing this reframe).
  - **Security** — **confirmed gap, both human-led and autonomous.** No existing post/page substantially covers this group; only passing mentions (PCI-DSS masking in Medium #2, "malicious situations" in Medium #3, the "Secure" card and "Collaborate"/vulnerability-to-PR vignette in the positioning drafts). This group needs either new material sourced from elsewhere, or a genuinely new example written from scratch.
- [ ] Confirm the "Agentic Reporting" gap is fully closed by Medium #4/#5 for this blog even though it's absent from every positioning-draft's 4-card section (`positioning-evolution.md` §7/§9) — i.e., this blog may be the first place Agentic Reporting gets proper treatment.
- [ ] Decide the actual named taxonomy question flagged in `positioning-evolution.md` §9: does this blog make "the five use case groups" an explicit, named framework for readers, or keep the grouping as internal structure only?
- [ ] **New source (2026-08-01):** `Agentic_Analytics__Example_Prompts.pptx` (see §1) has real prompt examples across all five groups plus infra/APM/DEM — its Cost Intelligence slides map directly to Optimize & Tune and its Security slides to Security, both with concrete, ready-to-adapt prompts (vulnerability lookups, CVE-specific queries, cost-spike investigation, cost forecasting). Its screenshot numbers are outdated and would need a fresh run before use as worked examples here.
- [ ] **New gap confirmed (2026-08-01):** the pptx's Forecast & Prediction slides are point-forecasts ("will this cluster's CPU stay healthy"), not "what if" scenario simulation — this does *not* close the Risk & Impact gap; Medium #4's SDK-bump example is still the closest available "what if" narrative and remains the best backbone for this group.
- [ ] **New category discovered (2026-08-01):** the pptx's "AI Observability" slides (failed evaluations, token usage/cost by model, failed LLM calls, agent health) don't map to any of the five groups — decide whether this becomes a 6th group, a Security sub-case, or stays out of scope for this blog.
- [ ] Voice/style pass; likely the most example-dense blog, so watch length/pacing.

---

## 5. Governance & enterprise readiness blog

**Status:** no draft yet. **Revised (2026-08-01, see `competitive-differentiation-review.md` §4):** this blog is better-sourced than first assessed — real *shipped* governance mechanics already exist in `product-ai-messaging.md` §3 and just hadn't been routed into this plan yet.

What we do have:
- **Shipped, concrete mechanics** (`product-ai-messaging.md` §3): per-user OAuth 2.1 enforcement, per-tool admin allow-listing, a unified audit trail spanning both Dynatrace and the partner tool, cost attribution by data owner, and — the most distinctive item — **per-agent monthly budget caps with a "circuit breaker" mode** in Cloud SRE Agents. None of the five competitors reviewed in `competition.md` mention budget-capped agent spend; this is a genuine differentiator worth leading with rather than burying.
- Trust-badge language from the positioning drafts: "Grounded / Approved / Audited / In your IAM," "Customer-isolated," "Not used for training — opt out anytime," "Governed by IAM," the DATA/ANALYTICS/UNDERSTAND/ACT/TRUST five-layer stack (`positioning-evolution.md` §6, §10.1–10.3).
- Medium #5's service-user/permission-boundary governance narrative (dedicated service user with reduced scope as agent actor) — the single most concrete, step-by-step governance example available (`medium-content-analysis.md` §"Reusable Concrete Assets — #5").
- Competitor governance framing for contrast, in `competition.md` (e.g., Datadog's audit trail / fair-use limits language, Rootly's BYOK/zero-training trust positioning) — Dynatrace's OAuth 2.1 + budget caps are more specific than any of these.

Sub-tasks:
- [ ] Still worth **sourcing formal compliance detail** — SOC2/ISO status, data residency specifics, any AI-specific certifications — for a fully enterprise-readiness-grade treatment, but this is now a nice-to-have deepening rather than a blocking gap; the product-mechanics material above is enough to draft a solid first version.
- [ ] Decide whether this blog is customer-facing marketing (reuse the trust-badge language above) or more technical/compliance-oriented (would need the missing detail above) — the answer changes how much new research is required.
- [ ] Once sourced, map content against competitor trust claims in `competition.md` for differentiation (e.g., Causely's agent-agnostic middleware stance, Traversal's read-only "Agentless Data Capture" pitch).
- [ ] This is a good candidate to plan **last**, after the others surface any additional governance mentions worth folding in.

---

## 6. Medium blog summary/consolidation

**Status:** open decision — may not need to be its own blog.

The reuse plan in `medium-content-analysis.md` already assigns each of the 5 Medium posts a home (updated to the current 6-blog numbering):
- #1 → backbone for blog #3 (SRE Agent, Incident Analysis side)
- #2 (log-pattern/token-efficiency numbers) → cross-cutting proof point, usable in blog #1 and/or #4
- #3 → backbone for blog #4's Optimize & Tune example
- #4 → blog #4 (Risk & Impact, reframed) and secondarily blog #4's Agentic Reporting human-led example
- #5 → blog #2/#3 (governance/workflow angle) and blog #4's Agentic Reporting autonomous example

Sub-tasks:
- [ ] **Decide if a standalone "summary of the Medium posts" blog is still needed** once #1–#5 above absorb most of the source material — if the other five blogs use everything substantial, a 6th piece may be thin or redundant.
- [ ] If it does go ahead, the natural remaining scope is: (a) explicitly cross-linking the Medium posts as "deep technical dives" for readers of the dynatrace.com blogs, and (b) surfacing whatever content doesn't fit elsewhere.
- [x] **Decided (2026-08-01): Medium #2's headline token-compression stat is used lightly in Blog #1 now**, not reserved for this blog — Blog #6's existence is uncertain (lowest priority, last in sequence) while Blog #1 has an acute, current need for a safe proof point now that Christoph's numbers are dropped. This doesn't cost Blog #6 anything: the deeper technical grounding behind that stat (Drain algorithm citation, "Lost in the Middle" citation, the full DQL/DPL methodology walkthrough) stays untouched and becomes *this* blog's actual point of differentiation if it goes ahead — "here's the deeper story behind that number we mentioned" is a better sequence than repeating the same depth twice.
- [ ] If it doesn't go ahead as its own blog, fold the above residual content into blog #1 or #4 instead and retire this as a separate deliverable.

---

## Suggested sequencing (not a decision, just a recommendation)

1. **Blog #1 (Agentic Analytics)** first — furthest along, being actively planned now (2026-08-01).
2. **Blog #4 (five use cases)** sketched in parallel with #1, since #1's job-teaser row needs to cross-link somewhere — doesn't need to be fully drafted yet, but its outline should exist before #1 is finalized.
3. **Blog #2 (Agentic Operations overview)** next — now unblocked since §0's framing decisions are resolved; mirrors #1's capability-first structure.
4. **Blog #3 (SRE Agent)** — richest raw material, but needs "the operator" definitional work done first; natural follow-on to #2.
5. **Blog #5 (Governance)** — blocked on deciding marketing-vs-compliance depth, otherwise has enough material for a first draft.
6. **Blog #6 (Medium summary)** — decide go/no-go only after #1–#5 are drafted and it's clear what's left over.
