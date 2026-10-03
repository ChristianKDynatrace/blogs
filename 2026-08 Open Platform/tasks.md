# Open Platform blog — task tracker

Purpose: handoff note for resuming this blog after a break. Draws on
`context/blog-context.md`, `context/blog-structure.md`,
`Open-Platform_Outline.md`, and `draft/open-platform-v1.md`.

**Status as of 2026-08-24:** draft v1 exists. Sections 1-4 have been through a
full revision pass with the user. Sections 5-8 are still the original text from
the outline and haven't been touched yet.

---

## Key decisions locked in

- **Voice:** Steve Tack (business/strategy) — declarative, low-metaphor, stats
  unadorned.
- **Framing:** blend of Spin A (safe "three deals, one thread" structure/close)
  and Spin B (openness framed partly as adoption/distribution logic, not
  altruism).
- **Phoenix's Elastic License 2.0 status:** omit entirely. Describe Arize/Phoenix
  the way Dynatrace's own materials already do (OSS-native), don't drill into
  license specifics.
- **No competitors named anywhere** — not Datadog, not Cisco/Galileo.
- **Platform statement must not lead with the acquisitions.** Lead with the
  commitment itself, use history as the "built for what's next" proof, defer all
  acquisition specifics to section 3.
- **Keptn** is used as a historical proof point in section 2, but with **no
  hyperlink** — it was moved to Archived status by the CNCF in Sept 2025, so
  linking to its project page would undercut the point it's meant to prove.
- **Headline requirement:** "open platform" and "AI" / "AI lakehouse" must each
  land in at least one subheadline — tracked in the outline's style guardrails.
- **"Autonomous enterprise"** must be named explicitly in the payoff (section 7),
  not just "agentic analytics" — this is what ties the piece back to Bernd's
  product-vision posts instead of reading as a standalone acquisitions recap.
- **Byline is still a placeholder** (`[author TBD — drafted in Steve Tack's
  voice]`) — needs an actual decision before this goes further.
- **Intro stat** is sourced/linked to the real report, [The Pulse of Agentic AI
  2026](https://www.dynatrace.com/info/reports/the-pulse-of-agentic-ai-in-2026/),
  not just to Steve's Arize post (which only re-cites it).

## Where the draft stands (`draft/open-platform-v1.md`)

- **Intro:** stat linked to the primary report. Note: the report's actual #1
  barrier is security/compliance at 52%, not the 51% technical-challenges stat
  currently used alone — flagged to the user, not yet acted on.
- **Section 2** ("The Dynatrace commitment..."): rewritten. Commitment stated
  first, three historical proof points (Keptn, OpenTelemetry, OpenFeature) each
  as their own paragraph, no acquisitions named, closes with a "why" (shared
  ground truth vs. a private version of it) and a bridge line, not a bare "same
  instinct" transition.
- **Section 3** ("One open platform, three signal types"): rewritten with a
  date-led, plain-language treatment per acquisition (DevCycle Jan 2026,
  Bindplane April 2026, Arize announced Aug 2026). Has **5 headline variations
  listed inline, unresolved** — user was leaning toward "Same open platform,
  adding three new signal types" but hadn't confirmed.
- **Section 4** ("Why an open platform matters"): has **4 intro variations
  listed inline, unresolved**. Bullets + Grafana stat unchanged. New closing
  line added: "one platform doing what would otherwise take three."
- **Sections 5-8** (AI lakehouse, developer/SRE split, autonomous-enterprise
  payoff, closing): **not yet reviewed/revised** — same close-reading pass that
  2-4 got still needs to happen here.

## Immediate next steps

1. Resolve the two inline variation choices sitting in sections 3 and 4
   (headline + intro) — pick one, delete the rest.
2. Decide the byline.
3. Do the same close-reading/rewrite pass on sections 5-8 that sections 2-4
   already got.
4. Full read-through against the style guardrails listed at the bottom of
   `Open-Platform_Outline.md` once every section has been revised.

## Files

- `context/blog-context.md`, `context/blog-structure.md` — original
  research/structure from the Claude Cowork session that produced the source
  deck (`Dynatrace Open Platform.pptx`).
- `Open-Platform_Outline.md` — the working outline, kept in sync with the draft
  as it evolves.
- `draft/open-platform-v1.md` — the actual draft.

---

**To resume:** open a session in this repo and say something like "continue the
Open Platform blog, check `tasks.md` for where we left off."
