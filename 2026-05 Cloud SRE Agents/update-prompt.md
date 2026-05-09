# Cloud SRE Agents — consolidated blog prompt

**Purpose of this file:** self-contained brief so a new Claude session has full context to draft, revise, or extend the Cloud SRE Agents announcement post without having to re-derive decisions made in earlier sessions. Combines the original brief, the product documentation, the structural decisions we landed on, the style profile, and pointers to all reference material.

---

## 1. Task

Write a Dynatrace Product News Blog (PNB) post announcing the general availability of **Cloud SRE Agents** — a Dynatrace Hub app that orchestrates cloud-native AI agents (AWS DevOps Agent, Azure SRE Agent, Google Gemini Cloud Assist) for autonomous incident investigation and remediation. Position Cloud SRE Agents as the orchestration layer that sits on top of Dynatrace Intelligence, the agentic operations system that grounds the agents in deterministic root cause analysis and live topology.

**Title (final):** *Orchestrate cloud-native AI agents for autonomous incident resolution — introducing Cloud SRE Agents*
**Slug:** `cloud-sre-agents`
**Length:** ~1,300–1,400 words (~7 min read)
**Status:** draft, ready for `/pnb-compose`

---

## 2. Author and audience

- **Author:** Christian Kiesewetter (use standard Dynatrace author bio).
- **Personal style file:** `references/personal-styles/personal-style-christian.md` in the `pnb-draft` skill (`C:\Users\christian.kiesewette\.claude\skills\pnb-draft\references\personal-styles\personal-style-christian.md`). Always check that file before writing.
- **Primary audience:** SREs and platform engineers running production on multi-cloud environments.
- **Secondary audience:** engineering managers, IT leaders, decision-makers evaluating agentic AI strategy.
- **Voice:** Analyst + Product Strategist hybrid (per Christian's profile). Industry-anchored, evidence-led, outcome-focused, written for a practitioner with strategic framing that resonates one level up.

---

## 3. Key messages

1. Dynatrace Intelligence is the agentic operations system orchestrating both Dynatrace's own AI-driven agents and external ecosystem agents.
2. Cloud SRE Agents is the orchestration layer for hyperscaler SRE agents — a configurable, intelligent decision layer, not a relay.
3. Interaction Profiles give precise, code-free control over which problems go to which agents.
4. The Activity and Statistics views (framed as **agent governance**) provide auditability and measurable ROI on agentic workflows.
5. Dynatrace's deterministic, causation-based AI is what makes external agent investigations trustworthy at scale.

---

## 4. Final agreed structure (7 sections)

| # | Section | Purpose |
|---|---|---|
| Lead | Single paragraph (~175 words) | Position Dynatrace Intelligence + frame the multi-cloud agent question + announce Cloud SRE Agents |
| TOC | "In this blog post" numbered list | Christian's signature pattern |
| 1 | From point integrations to intelligent orchestration | Recap the three individual integrations; name the multi-cloud problem |
| 2 | How Cloud SRE Agents works | Mechanics: detect → call in cloud-native specialists → three workflows orchestrate dispatch and write-back. Dropped per-cloud capability differentiation per author preference |
| 3 | Intelligent routing with Interaction Profiles | Reframed as announcement, not feature walkthrough. Conditions described by breadth, not by enumerated filter list. One concrete routing scenario as illustration |
| 4 | Three ways teams put it to work | Three operational use cases: route-to-right-cloud, budget governance, tier-by-severity |
| 5 | Agent governance: full visibility into every investigation | Activity tab as audit trail, Statistics tab as directional ROI/cost lens. Honest on working time being a proxy, not billing-grade |
| 6 | The Dynatrace difference | Production context as multiplier. Customer proof points: AWS stats (75/80/94%), 70% joint MTTR, WGU, United Airlines |
| 7 | Get started | "First 5 minutes" 4-step ladder (Setup → Connect agent → Add profile → Validate with Dry Run). Cross-links + community-supported note |

---

## 5. Editorial decisions made (preserve these in revisions)

These shaped the current draft and are easy to lose in a rewrite:

- **Lead opens with Dynatrace Intelligence positioning**, not the multi-cloud problem. Author specifically asked for this framing up front.
- **Cloud-agent capability parity** — do not call out AWS/Azure mitigation vs. Gemini investigation-only. Reference all three uniformly.
- **Naming standardized** to *Google Gemini Cloud Assist* on first mention, *Gemini Cloud Assist* afterward (matches new-doc.txt and the Google product page).
- **Section 3 is announcement, not walkthrough.** Avoid feature inventories, exhaustive filter lists, and configuration object explanations. Keep one concrete routing example only.
- **Budget framing is governance, not cost savings.** The duration figure is a *proxy from event timestamps*, useful as a circuit breaker and directional signal — not a substitute for cloud-provider billing reports. Always frame this honestly.
- **Section 5 reframed as agent governance**, not just visibility. Both personas care about it: SREs want to see what the agent did; decision-makers want evidence of value.
- **No before/after ASCII timeline** in the body text (from new-doc.txt). It's powerful but doesn't fit Christian's published style. If visualized, it should be a designed graphic at compose time.
- **CTA is a four-step time-boxed ladder**, not "go to the Hub." Built from the new-doc "First 5 minutes" path.
- **Community-supported note** is a single sentence at the end. Brief explicitly says "mention only briefly at the very end."

---

## 6. Style requirements (anti-AI checklist already applied)

- No em dashes (—) anywhere in the body. Replace with comma, colon, semicolon, or parenthetical. Em dashes in the title are tolerated by convention.
- No banned intensifiers: seamless, robust, streamline, comprehensive, powerful, game-changer, revolutionary, cutting-edge, unprecedented, pivotal.
- No banned AI words: delve, harness, leverage (as verb), navigate (metaphorical), landscape, realm, tapestry, myriad, plethora, empower (vague).
- No banned phrases: "It's important to note", "In today's X", "Not only/but also", "Let's dive in", "First and foremost", "When it comes to X" as opener, "In order to", "A holistic approach".
- No banned transitions: Furthermore, Moreover, Additionally, In conclusion, To summarize.
- Sentence-case headings; no closing punctuation; no gerund verb forms.
- Trademarks on **first mention only**: Smartscape®, OneAgent®, Dynatrace® where relevant. Never in headings.
- Mixed paragraph rhythm; vary sentence-opening patterns; no three-paragraph stretches of identical length.
- Use contractions naturally (it's, you'll, don't, can't).

Authoritative references in the `pnb-draft` skill:
- `references/style-guide.md`
- `references/anti-ai-checklist.md`
- `references/positive-spin.md`
- `references/intro-style.md`
- `references/voice-profiles.md`
- `references/cta-patterns.md`
- `references/differentiators.md`
- `references/personal-styles/personal-style-christian.md`

---

## 7. Customer proof points and stats (used in section 6)

| Proof point | Numbers | Source |
|---|---|---|
| Joint AWS DevOps Agent + Dynatrace customers | Up to **70%** MTTR reduction | Dynatrace AWS DevOps Agent blog |
| AWS DevOps Agent (preview results) | Up to **75%** lower MTTR, **80%** faster investigations, **94%** root cause accuracy | AWS GA announcement |
| **United Airlines** | 500K+ daily passengers; 38K Dynatrace OneAgent deployments; 500+ AWS accounts; 20K Lambda functions; before/after framed as "multi-tool gaps and black boxes" → "single pane of glass, no 3 a.m. tool-switching" | AWS DevOps Agent product page (paraphrase only — do not reproduce verbatim) |
| **Western Governors University** | 200,000 students on a fully online learning environment; AWS DevOps Agent + Dynatrace automates cross-system correlation that previously required manual effort across multiple tools | AWS DevOps Agent product page |

---

## 8. Reference URLs

### Dynatrace blogs (linked in post)

- AWS DevOps Agent integration: https://www.dynatrace.com/news/blog/integration-with-aws-devops-agent-autonomous-investigations-powered-by-production-context/
- Azure SRE Agent integration: https://www.dynatrace.com/news/blog/boost-cloud-reliability-dynatrace-and-azure-sre-agent-unite-for-autonomous-operations/
- Dynatrace Intelligence positioning (CTO blog): https://www.dynatrace.com/news/blog/dynatrace-intelligence-at-the-core-of-autonomous-operations/
- Dynatrace agentic AI foundation (CPO blog, Perform 2026): https://www.dynatrace.com/news/blog/dynatrace-introduces-a-new-foundation-for-agentic-ai-at-perform-2026/
- Dynatrace Intelligence platform page: https://www.dynatrace.com/platform/artificial-intelligence/
- Atlassian Rovo Ops + Dynatrace: https://www.dynatrace.com/news/blog/dynatrace-and-atlassian-delivering-agentic-ai-that-transforms-your-end-to-end-incident-management/
- Dynatrace MCP Server: https://www.dynatrace.com/news/blog/dynatrace-mcp-server-allow-ai-interact-dynatrace-access-production-insights/
- Bedrock + Dynatrace MCP: https://www.dynatrace.com/news/blog/fuel-bedrock-agents-with-observability-data-via-the-dynatrace-mcp-server/
- Preventive operations / Davis AI: https://www.dynatrace.com/news/blog/advancing-aiops-preventive-operations-powered-by-davis-ai/

### Hyperscaler references

- AWS DevOps Agent product page (WGU + United Airlines stories): https://aws.amazon.com/devops-agent/
- AWS DevOps Agent GA announcement: https://aws.amazon.com/blogs/mt/announcing-general-availability-of-aws-devops-agent/
- AWS DevOps Agent + Dynatrace walkthrough: https://aws.amazon.com/blogs/mt/resolve-application-issues-autonomously-with-aws-devops-agent-and-dynatrace/
- Azure SRE Agent welcome: https://sre.azure.com/welcome
- Azure SRE Agent docs: https://learn.microsoft.com/en-us/azure/sre-agent/
- Dynatrace MCP in Azure SRE Agent (Microsoft blog): https://techcommunity.microsoft.com/blog/appsonazureblog/get-started-with-dynatrace-mcp-server-in-azure-sre-agent/4492363
- Gemini Cloud Assist product page: https://cloud.google.com/products/gemini/cloud-assist
- Gemini Cloud Assist investigations docs: https://docs.cloud.google.com/cloud-assist/investigations

### Author background (style derivation source)

- Christian Kiesewetter author page: https://www.dynatrace.com/news/blog/author/christian-kiesewetter/

### Background reading (do not necessarily link)

- LinkedIn from AWS DevOps Agent product manager on GA: https://www.linkedin.com/pulse/from-preview-ga-aws-devops-agent-gets-multi-cloud-skills-simon-moore-mfiqc/
- Dynatrace + Google Cloud partnership PR: https://ir.dynatrace.com/news-events/press-releases/detail/375/dynatrace-announces-early-access-for-joint-google-cloud-customers-to-capabilities-enabling-real-time-actionable-intelligence-from-data

---

## 9. Source files in this repo

| File | Purpose |
|---|---|
| `blog_prompt.md` | Original brief: structure proposal (8 sections), proof points, references, do-not-include list |
| `help.md` | Initial in-app documentation: app architecture, agents, profiles, filters, tabs, cost model |
| `new-doc.txt` | Updated documentation (richer): three-workflow architecture, agent specifics, "First 5 minutes" path, honest cost-model framing, dtctl CLI usage, validate-configurations function |
| `CLAUDE-cloud_sre_agents_blog.md` | Earlier Claude draft used as comparison baseline |
| `draft/cloud-sre-agents.md` | **Final draft** produced via the `/pnb-draft` skill, consolidating all of the above |
| `update-prompt.md` | This file — consolidated brief for new sessions |

---

## 10. Do-not-include constraints

- Do **not** reproduce the United Airlines testimonial verbatim. Paraphrase only (copyright).
- Do **not** include deep technical setup instructions in the body. Reference docs instead.
- Do **not** link to investor relations URLs (`ir.dynatrace.com`).
- Do **not** link to the Google Cloud Marketplace listing (requires login).
- Do **not** publish the draft as Release Radar even if the brief tags overlap.
- Do **not** call out per-cloud capability differences (mitigation vs. investigation-only). Author wants parity framing.
- Do **not** describe Cloud SRE Agents as "community-supported" up front. The note belongs in a single sentence at the very end.

---

## 11. Figures planned (for compose step)

| # | Source tab | Caption |
|---|---|---|
| 1 | Overview | Interactive network graph showing a live problem connected to dispatched agents and their activity statuses |
| 2 | Configuration | Interaction Profile showing routing conditions, agent assignments, and the Test (Dry Run) validation panel |
| 3 | Statistics | Per-agent working time, MTTR improvement, and satisfaction scores across a selected time range |
| 4 | Activity | Expanded investigation card with agent findings and Good/OK/Bad rating controls |

All four screenshots still need to be sourced from the app before `/pnb-compose`.

---

## 12. Tags (proposed; finalize at compose)

Agentic ecosystem, AI, AWS, Azure, Google Cloud, Cloud SRE Agents, Dynatrace Intelligence, Incident management, MCP, Observability, SRE, autonomous operations.

(Per `pnb-compose` rules, taxonomy is decided against `references/blog-tags.md` at compose time, not draft time.)

---

## 13. How a new session should resume

1. Read `update-prompt.md` (this file).
2. Read `draft/cloud-sre-agents.md` (the current state of the post).
3. Read `references/personal-styles/personal-style-christian.md` in the `pnb-draft` skill for voice calibration.
4. Skim `help.md` and `new-doc.txt` for product accuracy if revisions are technical.
5. If the user wants to revise: ask which section, then apply the editorial decisions in §5 + style rules in §6 before suggesting changes.
6. If the user wants to compose: run `/pnb-compose` once the four figures from §11 are sourced.
