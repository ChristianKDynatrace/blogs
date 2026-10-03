# Blog learnings: Cloud SRE Agents

## 1. Context

- Topic: Cloud SRE Agents (Dynatrace Hub app orchestrating AWS DevOps Agent, Azure SRE Agent, Google Gemini Cloud Assist).
- Post type: product launch hybrid (feature announcement + thought leadership + ecosystem integration).
- Audiences: (1) SREs and platform engineers on multi-cloud; (2) engineering managers / IT decision-makers.
- Date: 2026-10-03.

---

## 2. Workflow that worked

- **[general]** Build the author's personal style file **before** drafting if none exists. Fetched 5 of the author's past blog posts via WebFetch, derived patterns (opening rhythm, vocabulary, section structure, CTA habits), saved to `references/personal-styles/personal-style-<firstname>.md`. Because voice calibration downstream is faster when the signature is already codified.
- **[general]** Run an inline 6-question interview when no brief exists (topic, post type, persona, key message, CTA, author). Because this forces the author to make the hard calls up front rather than during section drafts.
- **[general]** Read every repo input (`help.md`, `blog_prompt.md`, `new-doc.txt`, prior Claude drafts) as source-of-truth before touching the draft. Mid-session input arrivals (user dropped `new-doc.txt` after Section 2) are normal; expect them and re-read.
- **[general]** Compare the new draft against any previous Claude draft explicitly, as a table (structure, style compliance, content gaps). Because the author remembers both and needs to see what changed and why.
- **[general]** Per-section approval gate: present each section, state what it does and tradeoffs, wait for explicit approval before moving on. Because batched approvals bury disagreements.
- **[general]** Final anti-AI sweep is a distinct pass after sections are approved, not during. Catches cross-section repetitions and symmetric structural tells only visible in context.
- **[type: product launch]** Produce a consolidated `update-prompt.md` at session end that captures the editorial decisions (not just the output), so revisions in a later session don't accidentally undo them.

---

## 3. Editorial principles

- **[type: product launch]** Lead paragraph opens with the platform/strategy positioning (Dynatrace Intelligence as the agentic operations system), **then** narrows to the specific announcement. Author pushed back on a product-first opener. Because a product launch inside a bigger strategy needs the strategy framed first for the decision-maker secondary audience.
- **[type: ecosystem integration]** Keep partner-agent capability parity. Do not call out that AWS/Azure support mitigation and GCP does not. Explicit author instruction: "Let's not differentiate that much between the three agents." Because the announcement is about one app orchestrating three equals, not a comparison matrix.
- **[general]** Reframe cost/budget content as **governance**, not cost savings, whenever the underlying signal is a proxy rather than billing-grade. For this app, agent working time is derived from event timestamps in Grail (not the cloud provider's clock), so framing it as cost accounting would be dishonest. Reframed as circuit breaker + directional signal, reconciled against cloud bills.
- **[general]** Reframe visibility/dashboard sections as **governance** when they serve both SRE audit and manager ROI purposes. Section 5 heading changed from "Full visibility into every investigation" to "Agent governance: full visibility into every investigation" because that single word earns the section its place for both personas at once.
- **[type: product launch]** Announcement vs. walkthrough is a real distinction. Author rejected an Interaction Profiles section that enumerated every filter type with technical attributes. Rewrote around *what judgment it lets you encode* with one concrete routing example, not every filter name. Walkthroughs belong in docs, not announcements.
- **[general]** Quote customers paraphrased, never verbatim (copyright). United Airlines story described rather than quoted.
- **[general]** CTA is a time-boxed numbered ladder, not a single sentence. "First 5 minutes: 1. Setup (3 min) / 2. Connect agent (1 min) / 3. Add profile (1 min) / 4. Validate (30 sec)." Because this reduces activation energy from "visit the Hub" to "I can try this before lunch."
- **[type: ecosystem integration]** Community-supported status gets exactly one sentence at the very end. Author's explicit brief constraint; mentioning it earlier would undercut the launch.

---

## 4. Walkthrough and UX honesty

- **[type: product launch]** Name UI tabs and controls in bold (**Setup**, **Overview**, **Trigger Investigation > Test (Dry Run)**) so readers can match on the actual button labels.
- **[type: product launch]** Mention `Test (Dry Run)` wherever a step touches production. Not as a feature callout, but as a safety-net framing: "the first live dispatch isn't also the first time you're learning what your rule actually matches."
- **[general]** When the product documentation acknowledges a proxy or approximation (working-time duration from event timestamps vs. cloud provider clock), surface that honesty in the post. Author did not want the post to overclaim cost accuracy.
- **[type: ecosystem integration]** Dropped the AWS "Workflow 3 — Event Handlers (AWS-only)" cloud-specific nuance from body text, kept the three workflows as parity. Technical accuracy preserved by saying "Event Handlers normalize the raw cloud-provider event stream" without flagging the AWS-only exception.
- **[type: product launch]** Do not include CLI/dtctl content from product docs in an announcement post. Belongs in companion operator posts or docs. Keeping it out preserves the launch focus.

---

## 5. Anti-AI-artefact findings

Fixes applied during the final sweep, ranked by frequency observed across this session plus the previous Claude draft:

1. **Em dashes in body text**: previous Claude draft had 4; final draft has 0. Replaced with commas, colons, parentheses. Only tolerated in the title by convention.
2. **"seamlessly"**: previous Claude draft used it twice ("integrating seamlessly", "flow directly into"). Removed in final; replaced with concrete descriptions.
3. **Symmetric parallel openers**: three sentences in Section 4 use case 1 followed "X belongs to Y" pattern. Varied verbs to "belongs to / calls for / lands with."
4. **Repeated phrase within same section**: "the moment the problem fires" appeared twice in Section 2 (prose + bullet). Dropped from the bullet because the prose already established it.
5. **"navigate" for UI motion**: style guide prefers "go to." Changed "double-click to navigate directly to the associated problem" → "double-click to go to."
6. **Missing trademark on first mention**: previous Claude draft omitted Smartscape®. Added in final (plus OneAgent®).
7. **Multi-paragraph lead**: previous Claude draft split the lead across three paragraphs. Style guide requires one paragraph. Compressed to a single ~175-word lead.
8. **Figure caption drift after rewrite**: Figure 2 caption still referenced features (per-agent filters, circuit-breaker budget) that were cut when Section 3 was reframed. Updated caption to match.

Exception: direct customer phrasing in paraphrased stories (United Airlines "single pane of glass") is kept even where it reads marketing-y, because the author's intent is reporting what the customer said.

---

## 6. Guideline checks (AEO, style guide, SEO)

**Applied:**
- Sentence-case H2/H3 headings. Because Dynatrace blog style requires it; was violated in the previous Claude draft (title-case in some headings).
- Trademark on first mention only, never in headings. Added Smartscape®, OneAgent®.
- Lead paragraph single-paragraph, 90-180 words. Hit 175.
- Primary keyword ("Cloud SRE Agents") in title, lead, one H2. Confirmed.
- Meta description 150-160 chars with primary keyword and action language. Hit 158.
- "In this blog post" numbered TOC after the lead. Christian's signature pattern; kept per personal style file.
- CTA is specific, action-led, time-boxed, with destination (not "learn more"). Four-step ladder with Hub install as the terminal action.
- Positive-spin rule: problem framed generically ("the question has shifted from X to Y"), not as a Dynatrace shortcoming.

**Deliberately NOT applied:**
- **Em dash in title retained** (`...resolution — introducing Cloud SRE Agents`). Style guide says no em dashes in blog posts, but the ban is enforced in body text where AI-detection pattern matching happens; the title is a short display element and the dash provides a clean subtitle separator. If a title-level audit is added later, revisit.
- **No tags/categories at draft time**. Those are a `pnb-compose` responsibility against `references/blog-tags.md`. Draft-time taxonomy guesses rot before publish.
- **No before/after ASCII timeline** from `new-doc.txt`, even though it was compelling. Does not fit Christian's published style; author's past posts never use ASCII art. If visualized, it belongs as a designed graphic at compose time.
- **No dtctl / CLI examples**. Appropriate for the product docs or an operator-focused follow-up, not an announcement.
- **No "What's next" / roadmap teaser**. Launch post should land the current app, not pre-announce. Reconsider on a Feature Deep Dive follow-up.
- **No release-radar framing**. `pnb-brief` and `pnb-draft` both refuse to auto-recommend Release Radar; this is a Product Launch hybrid.

**Not checked (gap, flag for next session):**
- No formal AEO (Answer Engine Optimization) scan beyond the generic "GEO" section in the style guide. If an AEO checklist exists in the skills, add it to the review pass.

---

## 7. Reusable structure

Generalized outline for a **product launch + ecosystem integration + thought leadership hybrid**:

1. **Lead** (one paragraph, 90-180 words): platform/strategy positioning first, then the specific announcement in the pivot sentence, then the "how to use it together" value.
2. **"In this blog post" TOC** (if author uses this signature pattern).
3. **Section 1: Why one orchestration layer** — recap the individual integrations with real customer stats, then name the multi-tool/multi-cloud problem that the new app solves.
4. **Section 2: How it works** — mechanics in prose plus a short bullet list of named sub-components (here, three workflows). End with the primary UI surface (here, Overview tab) as a figure anchor.
5. **Section 3: The intelligent decision layer** (the configuration object that makes the product more than a dispatcher). Announcement framing, not feature catalog. One concrete example beats five filter names.
6. **Section 4: Three operational patterns** (not three features). Each H3 starts with a concrete operational moment, then names the mechanism, then describes the outcome.
7. **Section 5: Governance / visibility** — frame as agent governance to earn both personas. Audit trail tab + metrics tab. Be honest about any proxy/directional signals.
8. **Section 6: The vendor difference** — the production-context argument, then customer proof points (quant stats → mid-size customer → named marquee customer with the paraphrased before/after).
9. **Section 7: Get started** — numbered time-boxed ladder (minutes per step), cross-links to prior posts, primary CTA, support status note at the very end.

---

## 8. Tooling notes

- **WebFetch for style derivation**: 4-5 past posts from the author is enough signal to populate a personal style file. More is diminishing returns.
- **Personal style file location**: `C:\Users\christian.kiesewette\.claude\skills\pnb-draft\references\personal-styles\personal-style-<firstname>.md`. One-time cost per author; reused forever.
- **Anti-AI checklist lives in**: `C:\Users\christian.kiesewette\.claude\skills\pnb-draft\references\anti-ai-checklist.md`. Single source of truth; don't inline-copy the rules into other skills.
- **Compose vs draft responsibility**: taxonomy (tags, categories) and image embedding happen in `/pnb-compose`, not `/pnb-draft`. Don't guess them in the draft.
- **Known limitation**: `WebFetch` on dynatrace.com returned a lightly summarized version of the shorter blog posts rather than full text. Enough for style derivation; not reliable for exact-quote extraction. [assumption] Haven't confirmed if a different fetch strategy returns raw HTML.
- **Known limitation**: when `pnb-draft` is run inside a session with no brief, the inline interview covers the critical fields but misses secondary brief metadata (keywords list, trend anchor, differentiation angle). Would be worth adding one follow-up question for SEO primary keyword if the author did not supply one.

---

## 9. Mistakes and surprises

- **Dropped the "use cases" section without approval**. I merged the three use cases into Section 3 to reduce length, then said so transparently. Author caught it: "Did you intentionally not add the use cases?" Reinstated as its own section. Learning: when consolidating sections from a prior structure, ask first, don't ship-then-explain.
- **Section 3 drafted as feature walkthrough**. Default pattern was to enumerate every filter type with technical attributes. Author rejected: "This is very feature focused and more a walkthrough rather than an announcement." Rewrote around what judgment the profile lets you encode, with one concrete example. Learning: an announcement post is not product documentation. Test every section against the question "would this read as a feature in the Changelog or as news on a blog?"
- **New source document arrived mid-session** (`new-doc.txt` after Section 2). Had to rewrite Section 2 and backport the richer three-workflow framing. Learning: ask up front "are there other docs I should read?" rather than assuming the first set is complete.
- **Naming inconsistency surfaced late**. "Google Cloud Assist" vs. "Google Gemini Cloud Assist" appeared in different source docs; the lead paragraph used the shorter form and Section 2 revealed the mismatch. Author chose the longer form; fixed everywhere. Learning: when multiple source docs disagree on a product name, confirm with the author before the first draft paragraph.
- **Nearly missed**: the Dry Run tip from `new-doc.txt` that it also surfaces available field names. Easy to lose when summarizing a long docs page. Caught on re-read.

---

## 10. Pre-publish checklist

- [ ] Lead paragraph is one paragraph, 90-180 words, with pivot sentence naming the capability.
- [ ] Lead opens with platform/strategy framing (not product-first) if post is a hybrid launch.
- [ ] "In this blog post" numbered TOC after the lead (if author's signature).
- [ ] Primary keyword in title, lead, and at least one H2.
- [ ] Title length 50-65 characters. Meta description 150-160 characters with action-close.
- [ ] All H2/H3 headings sentence case, no gerunds, no closing punctuation.
- [ ] Trademarks (Smartscape®, OneAgent®, Grail®, Dynatrace®) on first body mention only, never in headings.
- [ ] No em dashes in body text. Title em dash tolerated.
- [ ] Anti-AI banned word sweep clean (seamless, robust, streamline, leverage-as-verb, navigate-metaphorical, landscape, delve, harness, comprehensive, powerful, empower, etc.).
- [ ] No symmetric openers across 3+ consecutive sentences or bullets.
- [ ] No same-length paragraphs in a 3+ run.
- [ ] Every section advances toward the primary CTA.
- [ ] At least 2 micro-CTAs or inline doc links in body sections.
- [ ] One primary CTA, specific and time-estimated.
- [ ] Customer quotes paraphrased, not verbatim.
- [ ] Partner-agent parity preserved (no accidental capability-comparison language).
- [ ] Any proxy/directional metrics (cost estimates, duration, satisfaction) honestly framed, not sold as billing-grade.
- [ ] Figure captions match the content of the section after any rewrites.
- [ ] Community-supported / preview status mentioned once, at the very end, if applicable.
- [ ] No draft-time tags or categories (defer to compose).

---

## Open questions

- Should the title's em dash be retained after the next anti-AI pass tightens? Current call is "keep for display aesthetics," but no explicit decision from author.
- Primary SEO keyword was never explicitly chosen. Current implicit keyword is "Cloud SRE Agents" (brand term). Should there be a secondary descriptive keyword like "autonomous incident resolution" or "multi-cloud AI agents" validated for search volume?
- The before/after ASCII timeline in `new-doc.txt` is powerful but was dropped. If visualized as a designed graphic at compose time, which section should host it? Section 6 (Dynatrace difference) was my working assumption but not confirmed.
- Who sources the four screenshots before `/pnb-compose`? Author did not say. [assumption] Author will source them from a staging tenant.
