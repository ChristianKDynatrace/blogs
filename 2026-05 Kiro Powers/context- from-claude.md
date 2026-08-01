# Context file — Dynatrace Kiro Power blog

This file captures the approach, decisions, and reference material from the editorial session on the "Dynatrace observability, one click away in Kiro" blog post. It is intended as a starting point for future related work.

## Overall approach to the blog

### Audience

Two audiences, in order of priority:

1. **Existing Dynatrace customers** who are using or considering Kiro. The goal is to make them aware that connecting Dynatrace to Kiro is now a one-click action rather than a manual MCP setup.
2. **Developers using Kiro** who are not yet Dynatrace customers. The goal is to surface what Dynatrace can do for them in the context of their Kiro workflow.

### Tone and framing principles

- **Lead with the news, not the timing.** Avoid "Today, we're excited to announce..." openings — the power has been available for some time, so the story is the introduction itself, not the launch moment.
- **Acknowledge the friction the power removes, but don't dwell on pain.** A single sentence ("No JSON editing, no manual MCP setup") carries more weight than a full paragraph of pain framing. Powers exists to make things easier — that's the right register.
- **Address both audiences explicitly in the intro.** A two-sentence pivot ("For Dynatrace customers... For developers new to Dynatrace...") signals to each reader that this post is for them.
- **Differentiate Dynatrace, but don't overdo it.** The blog is primarily about the power existing, not a Dynatrace Intelligence deep-dive. One paragraph on the grounding/causal AI angle is enough; more would derail the post.
- **Pitch language at developers, not ops teams.** The audience is debugging code and shipping features. Avoid MTTR-flavored, ops-marketing phrasing. Prefer "tighter loop between writing code and understanding how it behaves in production."
- **Concrete capabilities over abstract bullets.** "Smart suggestions for monitoring configuration" is meaningless. "Investigate live incidents and get root cause analysis directly in the Kiro chat" is something a developer can picture.

### Structural decisions made in this session

- **Title:** "Dynatrace observability, one click away in Kiro" — leads with the news, names both products, scans cleanly.
- **Intro structure:** What is Kiro → what are powers → what does the Dynatrace power do → both audiences → walkthrough signpost. The walkthrough signpost was retained from the original draft because it sets reader expectations well.
- **Merged sections:** The original draft's separate "Challenge" and "Dynatrace AI-Driven Development Life Cycle" sections were collapsed into one tighter "Why this matters for developers" block. The abstract "How the Integration Works" bullets were cut entirely — the diagram now carries that concept.
- **Quote placement:** The Mike Kobush customer quote (NAIC) was moved from the end of the post to right after the capabilities bullets, where it validates the claims just made. Stronger than closing the post with it.
- **Conclusion:** Does not restate the intro. Points forward to what the developer's new reality looks like, then a clean CTA to install.
- **Diagram (Figure 1):** Two-panel schematic showing (left) how Kiro analyzes a task and activates the Dynatrace power, and (right) what the power unlocks (Investigate problems, Get production insights, Access observability data, Provide root cause/remediation, Execute and verify fix). Placed in the "Why this matters" section because the right panel reinforces the capability bullets and the left panel illustrates dynamic activation.
- **Video (Figure 2):** Three-part demo — activating the power, verifying the connection, querying top 10 vulnerabilities. Placed at the end of the install section, before the conclusion. The "list top 10 vulnerabilities" example aligns with the natural-language examples in the "Start asking questions" prose, so the prose and video reinforce each other.

### Specific install-step details to preserve

- The user clicks Install and **gets an error message** that the MCP server can't be reached, because the configuration ships with placeholder values. This is expected UX, not a bug. The user clicks **Open Settings** to replace the placeholders.
- Placeholder convention used in this blog: `YOUR_DT_URL` and `YOUR_BEARER_TOKEN`. (The Dynatrace announcement blog uses `$TENANT_ID` / `$DT_PLATFORM_TOKEN` — the two conventions co-exist; preserve whichever the actual UI ships with.)
- MCP gateway URL pattern: `https://TENANT_ID.apps.dynatrace.com/platform-reserved/mcp-gateway/v0.1/servers/dynatrace-mcp/mcp`
- Token format example: `dt0s16.XXXXX`

### Phrasing decisions worth carrying forward

- **"Curated, partner-validated bundles"** — borrowed from the AWS Observability press release as a credibility framing for what powers are. Stronger than "one-click bundles" alone.
- **"Ground Kiro's reasoning in real facts from your environment, not guesses"** — the core differentiation phrase. Plants the Dynatrace Intelligence angle without name-dropping Grail/Smartscape in the intro.
- **"Less waiting on someone else for diagnostic data. Less guesswork from an AI assistant operating without context."** — the conclusion's forward-looking framing. Concrete, developer-flavored.

### What was actively avoided

- Generic AI marketing language like "AI agent-assisted workflows."
- Listing internal Dynatrace components (Grail, Smartscape, Davis CoPilot) by name in the main argument. Useful for depth, but bloats the intro and "why" sections. The Dynatrace Intelligence link carries readers to the depth if they want it.
- MTTR/ops framing — wrong audience.
- Mirroring the original article's structure when paraphrasing content from sources. Always rewrite into our own voice.

## Relevant context: Dynatrace Intelligence

### What it is, in one sentence

Dynatrace Intelligence is the agentic operations system at the core of the Dynatrace platform. It fuses deterministic, causal AI with agentic AI to ground answers in real production facts rather than probabilistic LLM guesses.

### Why it matters for AI-assisted development

The core argument relevant to Kiro/agent integrations: LLM-based agents can hallucinate or guess plausibly when they lack production context. Dynatrace Intelligence provides the grounding layer — real-time telemetry, deterministic root cause, dependency awareness — that turns agent answers from "sounds confident" into "actually right." This is the differentiator versus other observability tools when the integration target is an AI agent.

### Components worth knowing (for depth, not for the intro)

- **Grail** — the Dynatrace data lakehouse. Schema-on-read, unifies observability, security, and business data at exabyte scale. Enables any-question, any-time analytics.
- **Smartscape** — real-time dependency graph across services, infrastructure, business processes, ownership. Continuously refined.
- **Deterministic agents** — Root Cause Agent (causal AI), Analytics Agent (distills Grail data), Forecasting Agent, Operator Agent (orchestration).
- **Domain-specific agents** — built on the deterministic foundation, serving Dev, SRE, and Security.
- **Davis CoPilot** — the natural-language assistant for the Dynatrace platform.
- **Bi-directional ecosystem integration** — Dynatrace Intelligence coordinates with external agents (Kiro, GitHub Copilot, ServiceNow, Azure SRE agent, Atlassian Rovo, etc.). Submits tickets, invokes coding agents, assesses deployment risk, etc.

### Maturity model framing (Dynatrace's autonomous operations vision)

Three stages: **Automated** → **Supervised Autonomous** → **Fully Autonomous**. Most organizations today are in or moving toward Automated. The vision is human-supervised autonomy where AI executes with reliability, transparency, and feedback loops.

### URLs

- **Platform page:** https://www.dynatrace.com/platform/artificial-intelligence/
- **CTO announcement (Bernd Greifeneder, Jan 2026):** https://www.dynatrace.com/news/blog/dynatrace-intelligence-at-the-core-of-autonomous-operations/
- **Original Dynatrace + Kiro announcement blog (Nov 2025):** https://www.dynatrace.com/news/blog/real-time-insights-leverage-dynatrace-observability-capabilities-within-amazon-kiro/
- **Dynatrace MCP server hub listing:** https://www.dynatrace.com/hub/detail/dynatrace-mcp-server/
- **MCP server documentation (shortlink):** https://docs.dynatrace.com/docs/shortlink/dynatrace-mcp-server
- **Platform token creation docs:** https://docs.dynatrace.com/docs/manage/identity-access-management/access-tokens-and-oauth-clients/platform-tokens
- **Free trial signup:** https://www.dynatrace.com/signup/

## Relevant context: Kiro powers

### What Kiro is

Kiro is an AI-powered IDE built around spec-driven development and an agentic assistant. It reached general availability in 2025. It has a built-in MCP client for connecting to external tools and data sources.

### What Kiro powers is

Powers is the Kiro mechanism for packaging specialized expertise into one-click installable bundles. Each power contains:

1. **POWER.md** — the entry-point steering file. Tells the agent what MCP tools are available, when to use them, and what workflows it supports. Frontmatter contains keywords that trigger activation.
2. **MCP server configuration** — the connection details for the relevant MCP server(s).
3. **Steering files and hooks** — additional context loaded on-demand for specific workflows, plus any agent hooks the power wants to install.

### What makes powers different from raw MCP

- **Dynamic loading.** Traditional MCP clients load every tool from every server upfront, eating into context windows (5 servers can consume 50,000+ tokens / ~40% of context before the first prompt — "context rot"). Powers activate only when relevant. Mention "database" → Supabase power activates. Switch to deployment → Netlify activates and Supabase deactivates.
- **Unified packaging.** MCP servers, steering, hooks, and rules historically required separate configuration in separate files. Powers bundle them.
- **Curated and partner-validated.** Powers in the official directory are vetted by Kiro partners, providing a quality signal that bare MCP server configs don't.
- **One-click install.** No JSON editing required. If a power needs API keys, it prompts on first use.

### Launch partners (Dec 2025)

Datadog, **Dynatrace**, Figma, Neon, Netlify, Postman, Supabase, Stripe, Strands Agent. Plus community-built powers (SaaS builder, AWS CDK, Aurora DSQL).

### Other observability vendors with powers

- **Datadog** — launch partner.
- **AWS Observability** — announced Feb 24, 2026. Bundles four MCP servers (CloudWatch, Application Signals, CloudTrail, AWS Documentation) plus eight steering guides. Pitched at MTTR reduction and gap analysis. Different positioning angle from Dynatrace (breadth of AWS services vs. unified causal AI platform).

### Cross-compatibility roadmap

Kiro is building toward powers working across other AI development tools (Cursor, Claude Code, Cline, Kiro CLI). Not available today — powers currently work only in Kiro IDE. Worth noting for forward-looking content.

### Phrasing reference points

- **Kiro's own framing:** "Dynamic loading of context and MCP servers."
- **AWS framing (worth borrowing for credibility):** "curated and pre-packaged MCP servers, steering files, and hooks validated by Kiro partners."
- **Competitor one-liner that informed our positioning:** "Specialize your Kiro agents for observability use cases by one-click download of MCP server and steering files for use in Kiro to enable debugging of production issues and develop better code."
- **Our adapted version:** "...the Dynatrace power gives Kiro's agent the tools and context to investigate production behavior and turn that insight into better code."

### URLs

- **Kiro homepage:** https://kiro.dev/
- **Kiro powers landing page:** https://kiro.dev/powers/
- **Kiro powers announcement blog (Dec 3, 2025):** https://kiro.dev/blog/introducing-powers/
- **Kiro general availability blog:** https://kiro.dev/blog/general-availability/
- **Kiro spec-driven development docs:** https://kiro.dev/docs/specs/
- **Kiro MCP docs:** https://kiro.dev/docs/mcp/
- **One-click MCP install changelog:** https://kiro.dev/changelog/remote-mcp-and-global-steering/#one-click-mcp-installation
- **Dynatrace power install link:** https://kiro.dev/launch/powers/dynatrace
- **AWS Observability power press release (for competitive context):** https://aws.amazon.com/about-aws/whats-new/2026/02/aws-observability-kiro-power/

## Reusable structure for similar future blogs

If writing another partner-integration / power-announcement blog, this structure held up well:

1. **Title** — lead with the news, name both products, no "we're excited to announce."
2. **Intro** — What is the host product (Kiro) → what is the integration mechanism (powers) → what does our specific integration do → both audiences → walkthrough signpost.
3. **Why this matters** — Brief problem framing (one paragraph, not three) → our differentiator in one paragraph → diagram → concrete capability bullets → customer quote.
4. **Walkthrough** — Prerequisites → prep work → install steps (with realistic UX, including expected error states) → configuration → first-use prompt examples → demo video.
5. **Conclusion** — Restate the news in fresh language, paint the new developer reality, CTA.
