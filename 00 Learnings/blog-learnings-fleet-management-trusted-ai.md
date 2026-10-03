# Blog learnings: Fleet Management launch blog and Trusted AI trust center copy

## 1. Context
- Topic: Fleet Management feature launch blog (draft v1 only), then line-by-line rework of the Trusted AI trust center table (Deterministic AI, Agentic and Generative AI, AI Observability rows).
- Post type: feature launch blog; trust center web copy (table rows with "What it does" and "Trust highlights").
- Audiences in priority order: admins running OneAgent and ActiveGate at scale (blog); security, compliance and AI governance reviewers (trust center) [assumption, not stated by the user].
- Date: 2026-10-03. Status: blog draft not yet reviewed section by section; trust table not finalized.
- Only `draft-v1.md` and `handover.md` were saved as files. The trust table work exists only in chat, so there is no final version to diff.

## 2. Workflow that worked
- [general] Read the docx skill, then converted the three uploads with pandoc to markdown, because the skill covers environment quirks and pandoc keeps text readable.
- [general] Fetched the live docs page and treated it as the most reliable source, because it was far more detailed than the PM bullets and the Hub tile.
- [type: feature launch with competitor context] Fetched the competitor product page and two competitor blogs for positioning and tone only, because no feature comparison was requested.
- [type: feature launch with competitor context] Presented candidate differentiators split into "claimable" and "do not claim" before drafting, because the user wanted to choose the angle first. This worked better than drafting first.
- [general] Used the tappable question tool for three framing choices. One answer came back as prose ("show me the differentiators first"), because the competitor question depended on a decision not yet made. Ask for dependent decisions in sequence.
- [general] Drafted in markdown, rendered it with `present_files`, then produced a handover file with sources, decisions, open items and the full draft, because the user routinely moves work between sessions.
- [type: trust center copy] For each table row, fetched every linked docs page and compared it with the existing copy. This found two real accuracy problems (see section 9), which a pure wording pass would have missed.
- [type: trust center copy] Worked one row at a time, offering 2 to 5 wording variants per line, then assembled the row after each decision, because the user edits by reacting to concrete options.
- [type: trust center copy] When the user named an additional source (evals blog, solutions page, governance blog), fetched it and mapped what was new against the existing bullets before proposing changes.
- [general] Asked one targeted question when a factual gap blocked wording (for example whether workflows orchestrate agents or are agents), instead of guessing.

## 3. Editorial principles
- [general] Describe capability categories, not feature names, for fast-moving areas, because the agentic roster changes every 2 to 3 weeks. Exception: keep real product terms such as Dynatrace MCP, because the user confirmed it is a product name.
- [general] Never state a capability the product does not have today. Example: chat cannot start an action (workflows do), and workflows cannot yet call reasoning-based agents. "Calls tools for you" and "autonomous agents" were both pulled back, because trust copy gets checked.
- [general] Roadmap items go in a "what's next" section, never in the shipped-capability list, because the Fleet Management scope today is OneAgent and ActiveGate only.
- [type: feature launch] Lead with the vision hook but keep it to two short paragraphs, and cut unverifiable PM language such as "3rd Gen UX", because readers cannot check it.
- [type: feature launch with competitor context] Differentiate implicitly, without naming the competitor, on at most two points. Chosen: Grail and DQL unification, and the health-state model with prioritized recommendations, because both are architectural, not price-based.
- [type: feature launch with competitor context] Do not use "free to query" as a differentiator. The user judged "unified" to be the real argument and pricing a footnote.
- [type: feature launch with competitor context] Do not claim parity or leadership where the competitor is ahead (OTel collector management, breadth). Say it is roadmap.
- [type: trust center copy] State the exact mechanism when two behaviors differ. Example: standard mode masks personal information, agentic mode blocks the request. One merged "masked or blocked" bullet hid a stricter control.
- [type: trust center copy] Prefer a concrete figure or control over an adjective, for example "up to 10 years" over "supports compliance".
- [type: trust center copy] Keep each row's scope exact: AI Observability covers the customer's own AI workloads, not Dynatrace's internal AI. The user corrected a line that blurred this.
- [type: trust center copy] Reuse the site's own verbs (monitor, optimize, secure) so the table matches the solutions page.
- [type: trust center copy] A row-level connective thread (establish, act, watch) was liked for rows 1 and 2. Drop transition sentences that blur "our AI" versus "your AI".
- [general] Do not repeat a word within one passage (the double "reliable" in the Dynatrace Intelligence intro), and cut closing clauses that say nothing specific ("tackle complexity ... with reliable automation").
- [general] Keep the user's existing live copy unless they say to cut it. Two original trust bullets were dropped silently and had to be restored.
- [general] Describe workflows as something you build or configure in the app, not something you "use via" the app, because the user rejected the location-note phrasing.

## 4. Walkthrough and UX honesty
Nothing notable. No step-by-step content was written. The guided install flow is mentioned in one bullet only.

## 5. Anti-AI-artefact findings
No dedicated anti-AI pass was run in this session. The findings below come from rereading draft v1 afterwards, so they are **[assumption]** where the user did not confirm them.
1. Em dashes: 5 in the draft body (for example `telemetry — starting with`, and a dash pair around the four health states), plus heavy use in chat replies. The user preference bans them. Fix: use a comma, colon or full stop.
2. "Not X, but Y" contrast lines: for example `one query, not two tools and a spreadsheet`, `prioritized by impact, not alphabetically`. Fix: state the positive claim only.
3. Punchy stand-alone closers: `Fleet Management exists to close that gap.`, `Fleet Management is the first step on that road.`, `Health issues hide until they don't.` Fix: merge into the preceding sentence or cut.
4. Tricolon lists that pad (three problems, three roadmap groups). Keep only where the source has three real items.
5. Invented pain points ("checking three tools") not backed by any source. Fix: use only pains stated in the PM input or docs.
- User-flagged phrasing issues in the trust copy: duplicated adjective, generic value-statement tail, "LLM-based chat" described as boring, "using the Workflows app" as a location note.
- Exceptions: no customer quotes were used in this session.

## 6. Guideline checks (AEO, style guide, SEO)
No AEO, SEO or formal style guide was supplied or applied. Nothing else to report for those.
Guidelines that were applied:
- User preferences (no em dashes, plain English, banned buzzword list, SharePoint-only rule for the M365 connector). Applied to wording. Not applied consistently to em dashes, see section 9. The M365 connector was not used.
- Competitor content rules. Applied: paraphrase only, no quotes, no competitor names in the draft.
- Accuracy over completeness, from the user's standing principle. Applied: unconfirmed features stayed out of the shipped list.
Deliberately NOT applied, and why:
- Naming the competitor: user wants implicit differentiation unless they approve.
- Feature-by-feature comparison: the user assumed Dynatrace is behind and did not ask for it. Differentiation claims are therefore worded carefully, not as proven gaps.
- "Free to query" claim: it is a pricing point and weaker than "unified".
- EU AI Act, NIST and ISO alignment bullets: the user ruled them out because the source text was not specific to AI Observability.
- Dynatrace's own AI observability dashboard example from the docs: true, but tangential to a customer-facing row.
- Retention of "prompts" stretched to "prompts and responses": see section 9.

## 7. Reusable structure
Feature launch blog (worked as a first draft, about 750 words):
1. Title tied to the vision, then two short paragraphs on the problem and the destination, one bold line naming the product as the first step.
2. The problem practitioners already know (3 bullets, sourced).
3. What you get today (one line per capability, shipped only).
4. Why this is more than an inventory screen (1 or 2 implicit differentiators).
5. What's next (roadmap, clearly labeled).
6. Try it and docs link.

Trust center table row:
- Heading plus a category subheading (not a product list).
- "What it does": one sentence stating the row's role, then 3 capability bullets in category language.
- "Trust highlights": 3 to 6 bullets, each a specific control, number or mechanism, each traceable to a docs page.

## 8. Tooling notes
- pandoc converts docx to markdown cleanly. Docx skill must be read first.
- `web_fetch` returns full pages with navigation noise. Docs pages were the most useful, blog pages contained the quotable specifics.
- `present_files` is required for the user to see a markdown file in the app. `view` alone shows nothing to the user.
- The visualizer `read_me` call returned a 400 error once, so the table was delivered as inline markdown.
- The tappable question tool suits independent preference questions, not chained ones.
- Network access in bash was disabled, so no downloads there.

## 9. Mistakes and surprises
- The first draft was shown with `view` only, so the user saw nothing. Fixed by pasting inline, then calling `present_files`.
- The handover file carries the wrong date ("July 21, 2026"). The session date was 2026-10-03. Not yet corrected.
- Em dashes appeared in the draft and in most chat replies despite the preference.
- Two original trust bullets were removed without saying so, and "ignore the first one" was misread as covering existing copy. Rule: removals of live copy must be stated explicitly.
- Overclaims corrected by the user: chat "calls tools for you", workflows as "autonomous agents".
- The PII bullet merged two behaviors (mask versus block). Found only by reading the data privacy docs page.
- Root cause analysis and causal correlation were described as one thing. The docs show they are separate mechanisms.
- The evals blog describes the evaluation capability as a Preview. The proposed AI Observability bullet does not say so.
- "Up to 10 years" was stated for "prompts and responses", but the solutions page says prompts, and the governance blog says AI events.
- One provided Datadog blog (the fourth link) was not read, because the pattern seemed repeated. **[assumption]** that it added nothing.
- The Hub link in the draft CTA was constructed, not taken from a source. **[assumption]** that it is correct.
- Verified from sources: feature set in the draft, 10-year retention (solutions page and governance blog), PII behavior (docs). Supplied by the user and not source-checked: the Settings toggles and the semantic index exclusion.

## 10. Pre-publish checklist
- [ ] Every shipped claim traced to a docs page or release note; roadmap items labeled.
- [ ] Preview or beta status stated wherever the source says so.
- [ ] Numbers and scopes match the source wording (prompts versus events, standard versus agentic mode).
- [ ] No competitor named unless approved.
- [ ] No em dashes, no banned buzzwords, no "not X, but Y" or stand-alone closer lines.
- [ ] No duplicated adjectives within a paragraph.
- [ ] Links verified, not constructed.
- [ ] Dates in handover files match the session date.
- [ ] Existing live copy retained unless the user approved each removal.
- [ ] Every provided source URL read, or the gap noted.

## Open questions
- Should the AI Observability row keep the establish, act, watch thread? It was replaced by "Monitors, optimizes, and secures" without a decision.
- Row 2 subheading "AI-driven investigation and action" sits above a chat bullet that cannot act. Is the row-level "agents that can act on your behalf" line still wanted?
- Workflows bullet: three wordings were offered (autonomous operations, reliably, generative plus agentic tasks). None chosen, and "reliably" is undecided.
- Is "skills" understandable to a trust center audience? Is "guidance" or "context" the better retrieval word?
- Row 2 now has six trust bullets and row 3 has five sub-bullets. Trimming was offered, not decided.
- The "flagged by your model providers" bullet may conflict with the LLM-as-judge evaluation bullet. Which detection source should the row state?
- AI Observability trust bullets: two retention bullets overlap. Merge, or keep the prompt retention and event routing separately?
- Settings toggle names and semantic index exclusion need a docs source before publishing.
- Memory notes the Fleet Management blog as already drafted and locked. How does this session's v1 relate to that earlier draft?
