# Blog learnings: Agentic Analytics (planning phase)

## 1. Context

- Topic: Agentic Analytics (human-led, conversational) blog for dynatrace.com, first of a planned 6-post series.
- Post type: capability/positioning post evolved from a release-announcement draft (thought leadership with product proof).
- Audiences in priority order: practitioners (SREs, platform engineers), then decision makers; competitors read it too, so claims must hold up next to Datadog, Rootly, Resolve.ai, Causely, Traversal.
- Dates: 2026-08-01 to 2026-08-02 (written 2026-10-03).
- Scope of this session: research, positioning decisions and an outline. No full prose was written, so there was no revision or final-version diff. Sections 5 and parts of 6 are therefore thin on purpose.

## 2. Workflow that worked

- **[general]** Build durable memory docs first (writing style, product messaging, competition, source drafts) in `memory/`, because a later session or machine has none of the chat context.
- **[general]** Cross-reference our drafts against competitor claims before outlining, because it exposed that "deterministic/causal" is no longer unique (Causely and Traversal claim it too).
- **[general]** Resolve cross-cutting decisions before any single blog outline (naming, one blog vs two, vocabulary, category term), because they change structure and are costly to fix after drafting.
- **[general]** Keep a `tasks.md` with decisions marked `[x]`, open items `[ ]`, and a dated handoff note naming the immediate next step, because the work moved from a cloud session to a local machine.
- **[general]** Persist every ephemeral upload (HTML saves, pptx) into a memory doc the same session, because uploaded files do not survive the session.
- **[general]** Ask for decisions in plain text when structured multi-question prompts fail; one batch of three questions went unanswered, while conversational questions got fast, clear answers.
- **[type: positioning/capability post]** Compare three source artifacts (web landing drafts, the existing blog draft, a colleague's page) per dimension (breadth, depth, proof tier, voice) and take each one's strength, because none was best across the board.
- **[general]** Commit, push and merge in small PRs after each decision batch, because the user switched environments mid-project and `main` had to be complete.

## 3. Editorial principles

- **[type: positioning/capability post]** Separate durable capability content from use-case content that evolves on a different cadence. Capability posts carry a one-line-per-job teaser and link to a dedicated use-case post, because bundling forces rewrites on every release and duplicates examples across posts.
- **[general]** "Capability-focused" and "release-note voice" are different axes. Keep the scope, drop the "this release brings" throughline, and demote the release number to a closing footnote, because the release date ages while the pillars do not.
- **[type: positioning/capability post]** Organize around 3 to 4 durable pillars with current evidence attached as support, because a stat change then costs one sentence, not a restructure.
- **[type: positioning/capability post]** Pick the umbrella name that does not concede the category. "Agentic Analytics" over "Agentic Investigations", because all five competitors are investigation products.
- **[general]** Avoid adopting a competitor-defined category term ("AI SRE"), because it means competing on their terms.
- **[general]** Never let "deterministic" or "causal" stand alone. Tie it to the mechanism (Grail and Smartscape precomputed before the question), because competitors now claim the adjective.
- **[general]** State the shipped autonomy stage honestly and do not let vivid scenarios imply more, because competitors' headlines outrun their own docs and honesty is a differentiator.
- **[general]** Keep competitor comparisons anonymous ("them vs us"); if one is ever named, check the claim against `competition.md` first, because several competitors do market human approval gates.
- **[general]** Use only already-published or verifiable proof. Internal, unverifiable figures were dropped entirely, because a demo-tenant snapshot is stale even if it was real once.
- **[type: positioning/capability post]** Use the headline stat of a published deep-dive in the overview post and reserve the methodology for the deep-dive, because it plants the teaser without spending the deeper piece.
- **[general]** Reuse the author's own landing-page hook as the blog title idea (message match), reframed as a descriptive title.
- **[general]** Quote example prompts as literal strings and describe results qualitatively, because prompts stay valid while screenshot numbers go stale.
- **[type: positioning/capability post]** Use the five use-case group names exactly as defined ("Optimize & Tune", not "Optimize cost"; "Risk & Impact" as "what if" simulation, not forecasting), because narrower card labels from drafts had drifted from the definitions.

## 4. Walkthrough and UX honesty

Nothing notable. No step-by-step content was written. One related rule: example prompts must be runnable on the demo environment; the source pptx was flagged as outdated, so re-run before citing outputs.

## 5. Anti-AI-artefact findings

Nothing notable. No prose was drafted or revised, so no artefact pass occurred. Style constraints captured for later passes (from `writing-style.md`, not from a pass): third person with "you", thesis-first opening, no rhetorical questions, benefit-phrase H2s, bolded lead terms in bullets, "Get started" close.

## 6. Guideline checks (AEO, style guide, SEO)

- Applied: author style checklist in `memory/writing-style.md` for the outline's structure (thesis-first open, 5 to 6 H2s, bulleted parallel list with bold leads, quoted prompts, CTA close, cross-links).
- Not applied yet: SEO and AEO guidelines. No keyword, meta or answer-engine pass was requested or run. **[assumption]** these will be applied at the prose stage.
- Deliberately not applied: the landing-page register (short card copy, CTAs like "Try it") to the blog, because it does not port to blog prose; only hooks were reused.
- Deliberately not applied: the "outcome vs trust" two-page split to this blog, because it is a linear read; it was kept as two angles within one piece for the Operations and SRE Agent posts only.
- Deliberately not applied: Christoph's tenant-sourced numbers (1,277 checkouts, 98.8% CPU host), because the source cannot be verified and the figures are stale by publish time.

## 7. Reusable structure

Capability post outline that came out of this session:

1. Working title with a breadth signal in it.
2. Opening without H2: one declarative thesis sentence scoped wide, then one problem-context paragraph.
3. Pillar 1 H2: reasoning/mechanism, with the differentiator named explicitly and 1 to 2 quoted example prompts.
4. Pillar 2 H2: model/data fluency, with the one verified stat (or qualitative claim if not cleared).
5. Pillar 3 H2: encoded expertise, plus the forward-looking extensibility line.
6. Pillar 4 H2: breadth argument first, then a bulleted teaser of the use-case jobs, one line each, linking to the use-case post; one supporting stat.
7. Get started: CTA, tagline restatement, availability footnote (not the framing device), link to the next post in the series.

## 8. Tooling notes

- Browser "view-source" HTML saves wrap each source line in table cells with escaped markup. Reconstruct by joining the `line-content` cells with BeautifulSoup and html.parser, then parse the result as normal HTML. `lxml` was not installed.
- `markitdown` was not installed; `pip install "markitdown[pptx]"` worked. It extracts slide text and prompts but not screenshot content, so outputs in images were not reviewed.
- GitHub code search could surface page fragments from a private repo that direct fetch and file reads could not; results were partial and had to be marked as reconstructed.
- GitHub MCP tools disconnected and reconnected mid-session; reload them via ToolSearch before each PR step.
- Files only on a working branch are invisible when browsing `main`; `SendUserFile` delivered the outline directly when the user could not see it.
- A case-only folder rename ("AI Blogs" vs "AI blogs") created a duplicate top-level folder in git; check casing on any web-UI move.

## 9. Mistakes and surprises

- Conflated "capabilities focus" with "release-note voice"; the user caught it, and the pillar reframe resolved it.
- A batch of structured questions went unanswered and plan mode exited; plain-text discussion worked better for this user.
- First competitive pass underrated the Governance blog as thin; real shipped mechanics (OAuth 2.1, allow-listing, audit trail, budget caps with circuit breaker) already existed in the messaging memo and had not been routed into the plan.
- The three key colleague pages were initially unrecoverable; the user supplied saved HTML. Full text showed far more verbatim reuse of the author's own copy than the fragments suggested, which reversed an earlier "independent voices" conclusion.
- The pptx contained a category (AI Observability) that fits none of the five use-case groups, and its forecast slides were point forecasts, so the "what if" gap stayed open.
- A PR description mentioned a file as new that an earlier PR had already merged; harmless, but check the diff before writing PR text.
- The cloud session itself became a friction point (file visibility, merge-to-view); the user moved to local.

## 10. Pre-publish checklist

- [ ] Every number is from a published source or freshly re-run, with owner confirmed.
- [ ] No internal-only figures, tenant names or "representative" testimonials presented as real.
- [ ] Differentiator is tied to a named mechanism, not an adjective ("deterministic", "causal").
- [ ] Autonomy claims match the shipped maturity stage; roadmap items are labeled as such.
- [ ] Any named competitor claim checked against `competition.md`.
- [ ] Release or date references are current at publish time, not carried from the old draft.
- [ ] Use-case group names match the agreed definitions; teaser links point to live posts.
- [ ] Example prompts are copy-pasteable and were run on the demo environment recently.
- [ ] Voice pass against the style checklist, then a language review after restructuring.
- [ ] SEO and AEO pass done (not yet done for this post).
- [ ] Cross-links to the next post in the series work.

## Open questions

- ~85% valid-query and 2 to 3x speed stats: stated as fact in the existing draft, hedged as "pending validation" on the colleague's page. Ownership not yet confirmed. Used in the outline conditionally.
- Is the Medium summary post still needed, or does it fold into other posts? Decision deferred until the other five are drafted.
- Should "AI Observability" become a sixth use-case group, a Security sub-case, or stay out of scope?
- Whether the five use-case groups become a named, visible framework for readers or stay internal.
- Final blog title and exact wording of the opening thesis: only a working proposal exists, and the outline has not yet been reviewed by the user.
- Outcome and trust: one earlier assumption (blend into one narrative) was reversed by the user (two angles in one piece); the Operations and SRE Agent posts need to reflect the reversal.
- "The operator" is still undefined as a named entity, despite the decision to lead with that branding.
