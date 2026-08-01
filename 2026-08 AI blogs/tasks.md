# Blog Production Plan — Task Breakdown (Aug 2026)

*Purpose: break the planned blog series into concrete sub-tasks/decisions before we move into per-blog planning. Draws on the memory docs in `memory/` (writing-style, product-ai-messaging, competition, positioning-evolution, medium-content-analysis) and the existing draft in `agentic analytics/`.*

Five planned pieces, in the order the user listed them:

1. Agentic Analytics / Agentic Investigations
2. Agentic Operations (± dedicated SRE Agent blog)
3. Five use-case groups, concrete examples (human-led + autonomous)
4. Governance & enterprise readiness
5. Medium blog summary/consolidation

---

## 0. Cross-cutting decisions needed before drafting (blockers, not busywork)

These recur across multiple blogs below, so resolving them once up front saves rework:

- **Naming: "Agentic Analytics" vs "Agentic Investigations."** Affects blog #1's title/framing and how it cross-links to blog #3. `positioning-evolution.md` §1/§3 uses "Conversational Agentic Analytics" as the umbrella term; Christoph's pages use "Investigation" as one product surface within it, not a synonym for the whole thing. Needs a decision, not more research.
- **SRE Agent: folded into "Agentic Operations" or its own blog?** `positioning-evolution.md` §2/§4 shows Christian already drafted these as separate page pairs (`overview-v1-*` vs `sre-agent-v1-*`), and Christoph split further into `index` / `index-assist` / `index-investigation`. Precedent leans toward **two pieces** (an Operations overview + a dedicated SRE Agent deep-dive), but this is the user's call.
- **New vocabulary vs. Problems-journey continuity.** Christian's copy coins "the operator" / "TRIAGE. ROUTE. REMEDIATE." as a standalone tagline; Christoph deliberately avoids new terms and anchors to the existing Problems-app spine (Triage → Investigate → Remediate). Flagged as unresolved in `positioning-evolution.md` §9 — whichever blog covers SRE Agent / Operations needs one consistent choice.
- **Outcome vs. Trust: two audiences or one blended narrative?** Same section shows these as full parallel page pairs today. For a blog (linear, one read-through) we likely want one blended narrative rather than two versions — but worth confirming before drafting blog #2, since it affects structure more than blog #1 or #3.
- **Overpromise risk on autonomous remediation.** Explicitly flagged in `positioning-evolution.md` §9 and `product-ai-messaging.md`: current SRE Agent triages/routes/recommends, but full autonomous execution needs a manual trigger today; true end-to-end autonomy depends on cloud SRE agent collaboration (future). Any Operations/SRE Agent copy needs to state capability honestly — this is a wording discipline item, not a research gap.

---

## 1. Agentic Analytics / Agentic Investigations blog

**Status:** furthest along — a full draft already exists: `agentic analytics/PNB-Agentic-Analytics_Original.md` + a language-reviewed pass `..._after_language_review.md`.

Sub-tasks:
- [ ] Resolve the naming/framing decision (§0) — retitle/reframe if needed.
- [ ] Reconcile the existing draft against the newer messaging captured in `positioning-evolution.md` — in particular, decide whether to pull in any of Christoph's `index-assist.html` material (the live-tenant proof numbers: 1,277 checkout events, 98.8% CPU host, ~85% valid-query rate — see §10.2) as harder, more concrete proof points than what's currently in the draft.
- [ ] Cross-check against `product-ai-messaging.md` for anything shipped/announced since the draft was written that should be added.
- [ ] Decide whether the "one question can cross your whole environment" cross-domain vignette style (Browser event → Trace ID → Service → Host → Kubernetes cluster) from `index-assist.html` is worth adopting as a structural device.
- [ ] Pass through `writing-style.md` voice check (this is Christian's own blog, so should match his established register, not the more first-person Medium voice).
- [ ] Final proofread/language review (a review pass already happened once — confirm whether another is needed after content changes).

---

## 2. Agentic Operations blog (and possibly a separate SRE Agent blog)

**Status:** no draft yet. Richest available source material of any planned piece.

Sub-tasks:
- [ ] Decide the one-blog-vs-two-blog question (§0).
- [ ] Decide the vocabulary question (§0) — this determines whether the blog leads with "Triage. Route. Remediate." as a branded tagline or with Problems-journey language ("the investigation is already there before you open the problem").
- [ ] If doing a dedicated SRE Agent blog, the 8-stage problem-journey diagram (`positioning-evolution.md` §8/§10.3) is close to a ready-made backbone — decide whether to adapt it as a visual for the blog itself.
- [ ] Pull in the three named scenario vignettes (Resolve/Prevent/Collaborate) — already reused verbatim across three separate drafts, so they're clearly considered strong, reusable material.
- [ ] Decide whether to name specific ecosystem partners (AWS DevOps Agent, Azure SRE Agent, ServiceNow Assist, Kiro, GitHub Copilot, Atlassian Rovo Ops — from `index-investigation.html`, §10.3) and confirm current partnership/launch status of each before naming them publicly — some of these ("Kiro," "Atlassian Rovo Ops") aren't yet cross-referenced elsewhere in our memory docs and should be confirmed before publishing.
- [ ] Explicitly apply the overpromise-risk wording discipline (§0) throughout — this is the section most likely to overstate current autonomy.
- [ ] Consider folding in Medium post #5 ("Agentic Workflows are Killing your Classic Weekly Observability Report") for the workflow-automation/governance angle (service-user actor, permission boundary) — see `medium-content-analysis.md` §"Reusable Concrete Assets — #5".
- [ ] Voice/style pass against `writing-style.md`.

---

## 3. Five use-case groups blog (human-led + autonomous examples)

**Status:** no draft yet, but `medium-content-analysis.md` already did most of the source-mapping work.

Sub-tasks:
- [ ] Build the (use case) × (human-led example, autonomous example) matrix. Current backbone mapping from `medium-content-analysis.md`:
  - **Incident Analysis** — human-led: Medium #1 (Problem Analysis Skill, `astroshop-payment` demo). Autonomous: SRE Agent "Resolve" vignette (§10.1/10.3).
  - **Optimize & Tune** — human-led: Medium #3 (Predictive Analytics Skill — disk capacity, cost/token forecasting). Autonomous: the "Prevent" vignette (forecast-triggered capacity fix) doubles as this group's autonomous side.
  - **Agentic Reporting** — human-led: Medium #4 (ad-hoc conversational adoption report) as the manual-trigger variant. Autonomous: Medium #5 (scheduled agentic workflow report) is the ready-made autonomous example.
  - **Risk & Impact** — Medium #4's SDK-version-bump impact question, reframed explicitly as "what if" rather than generic RUM (flagged in `medium-content-analysis.md` as needing this reframe).
  - **Security** — **confirmed gap, both human-led and autonomous.** No existing post/page substantially covers this group; only passing mentions (PCI-DSS masking in Medium #2, "malicious situations" in Medium #3, the "Secure" card and "Collaborate"/vulnerability-to-PR vignette in the positioning drafts). This group needs either new material sourced from elsewhere, or a genuinely new example written from scratch.
- [ ] Confirm the "Agentic Reporting" gap is fully closed by Medium #4/#5 for this blog even though it's absent from every positioning-draft's 4-card section (`positioning-evolution.md` §7/§9) — i.e., this blog may be the first place Agentic Reporting gets proper treatment.
- [ ] Decide the actual named taxonomy question flagged in `positioning-evolution.md` §9: does this blog make "the five use case groups" an explicit, named framework for readers, or keep the grouping as internal structure only?
- [ ] Voice/style pass; likely the most example-dense blog, so watch length/pacing.

---

## 4. Governance & enterprise readiness blog

**Status:** no draft yet. **Weakest source material of the five** — this is a real content gap, not just an ordering choice.

What we do have (all secondary/trust-module fragments, not a dedicated treatment):
- Trust-badge language from the positioning drafts: "Grounded / Approved / Audited / In your IAM," "Customer-isolated," "Not used for training — opt out anytime," "Governed by IAM," the DATA/ANALYTICS/UNDERSTAND/ACT/TRUST five-layer stack (`positioning-evolution.md` §6, §10.1–10.3).
- Medium #5's service-user/permission-boundary governance narrative (dedicated service user with reduced scope as agent actor) — the single most concrete, step-by-step governance example available (`medium-content-analysis.md` §"Reusable Concrete Assets — #5").
- Competitor governance framing for contrast, in `competition.md` (e.g., Datadog's audit trail / fair-use limits language, Rootly's BYOK/zero-training trust positioning).

Sub-tasks:
- [ ] **Source real governance/compliance detail** — SOC2/ISO status, data residency specifics, exact IAM/RBAC mechanics for agent actions, audit-trail retention/format, any AI-specific governance certifications. None of this is in the memory docs yet; needs either a docs pass (`docs.dynatrace.com`), an SME conversation, or pointers from the user.
- [ ] Decide whether this blog is customer-facing marketing (reuse the trust-badge language above) or more technical/compliance-oriented (would need the missing detail above) — the answer changes how much new research is required.
- [ ] Once sourced, map content against competitor trust claims in `competition.md` for differentiation (e.g., Causely's agent-agnostic middleware stance, Traversal's read-only "Agentless Data Capture" pitch).
- [ ] This is a good candidate to plan **last**, after the others surface any additional governance mentions worth folding in.

---

## 5. Medium blog summary/consolidation

**Status:** open decision — may not need to be its own blog.

The reuse plan in `medium-content-analysis.md` already assigns each of the 5 Medium posts a home:
- #1 → backbone for blog #2 (Incident Analysis / SRE Agent side)
- #2 (log-pattern/token-efficiency numbers) → cross-cutting proof point, usable in blog #1 and/or #3
- #3 → backbone for blog #3's Optimize & Tune example
- #4 → blog #3 (Risk & Impact, reframed) and secondarily blog #3's Agentic Reporting human-led example
- #5 → blog #2 (governance/workflow angle) and blog #3's Agentic Reporting autonomous example

Sub-tasks:
- [ ] **Decide if a standalone "summary of the Medium posts" blog is still needed** once #1–#4 above absorb most of the source material — if blogs #1–#4 use everything substantial, a 6th piece may be thin or redundant.
- [ ] If it does go ahead, the natural remaining scope is: (a) explicitly cross-linking the Medium posts as "deep technical dives" for readers of the dynatrace.com blogs, and (b) surfacing whatever content doesn't fit elsewhere (e.g., Medium #2's academic citations — Drain algorithm, "Lost in the Middle" — and its raw token-count numbers, which are good standalone credibility proof but don't have an obvious home in #1–#4 otherwise).
- [ ] If it doesn't go ahead as its own blog, fold the above residual content into blog #1 or #3 instead and retire this as a separate deliverable.

---

## Suggested sequencing (not a decision, just a recommendation)

1. **Blog #1 (Agentic Analytics/Investigations)** first — closest to done, mostly reconciliation work.
2. **Blog #3 (five use cases)** next — benefits from #1 and #2 existing, but its Security gap and taxonomy decision can be worked in parallel now.
3. **Blog #2 (Agentic Operations / SRE Agent)** — richest material but has the most unresolved framing decisions (§0); tackle once those are settled.
4. **Blog #4 (Governance)** last among the primary four — blocked on sourcing real content.
5. **Blog #5 (Medium summary)** — decide go/no-go only after #1–#4 are drafted and it's clear what's left over.
