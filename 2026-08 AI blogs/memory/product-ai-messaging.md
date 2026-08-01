# Dynatrace AI/Agentic Messaging Briefing (Memory Doc)

*Compiled: 2026-08-01. Source: 16 Dynatrace pages (7 Christian Kiesewetter blogs, 6 colleague blogs, 3 evergreen platform pages). Purpose: reusable background reference for writing new Dynatrace AI/agentic content.*

---

## 1. Product / Feature Timeline

Roughly chronological by publish date, showing how the story built up over ~8 months (Nov 2025 → Jun 2026):

| Date | Article | What was announced |
|---|---|---|
| Nov 19, 2025 | *Boost Cloud Reliability: Dynatrace and Azure SRE Agent Unite* | Dynatrace ↔ **Azure SRE Agent** integration via MCP. Dynatrace supplies topology/business-context/deterministic root cause; Azure SRE Agent runs continuous monitoring and remediation, integrates with ServiceNow, GitHub Copilot, Azure DevOps. |
| Nov 24, 2025 | *Real-Time Insights: Dynatrace in Amazon Kiro* | First **Kiro** (AWS's agentic/spec-driven IDE) integration — manual MCP config (local or remote server) so developers query production data, root cause, remediation from inside Kiro. |
| Jan 28, 2026 | *Dynatrace MCP Server: Empower Your AI Assistants* | **Dynatrace MCP Server** goes **generally available**. Central plumbing exposing Grail data, Smartscape topology, and causal root-cause analysis to any MCP client (GitHub Copilot, Microsoft Copilot, Slack, Azure SRE Agent, AWS DevOps Agent, Atlassian Rovo Ops, ServiceNow Assist, n8n). |
| Jan 28, 2026 | *Fuel Bedrock Agents with Observability Data via Dynatrace MCP Server* | Dynatrace becomes **first AWS Partner to integrate as an MCP target for Amazon Bedrock AgentCore Gateway** — Bedrock agents can query Dynatrace metrics, problems, traces, topology, logs via natural language. |
| Jan 28, 2026 | *Dynatrace Intelligence at the Core of Autonomous Operations* | Launch/positioning of **Dynatrace Intelligence** as "the industry's first agentic operations system" — architecture of Deterministic Agents (Root Cause, Analytics, Forecasting, Operator) + Domain-specific ready-made agents (Dev/SRE/Security) + Assist Agents + Agentic Workflows. Introduces the 3-stage maturity model: Automated → Supervised Autonomous → Fully Autonomous. |
| Mar 30, 2026 | *Bring Real-Time Production Insights into Claude Code with the Dynatrace MCP Server* | **Claude Code** connector for Dynatrace MCP Server (install via Claude "Connectors" search); also mentions **dtctl**, the open-source CLI for the Dynatrace platform, for terminal-based DQL/workflow/dashboard management. |
| Apr 3, 2026 | *Dynatrace AI Agents Begin Working for You on Day One* | Framing of **ready-made agents** (e.g., Kubernetes Troubleshooting Agent) as production-ready (not preview), triggered via **Dynatrace Workflows** or the **MCP Server**, and testable via **Dynatrace Assist**. Mentions agent access from Claude Code and Cowork, Microsoft Copilot, Slack, n8n, Azure SRE, AWS DevOps, GitHub Copilot, Atlassian Rovo Ops, Amazon Q. |
| Apr 23, 2026 | *Dynatrace for AI: Teach Your AI Coding Agent How to Use Dynatrace* | **Dynatrace for AI** — open "agent skills" package (SKILL.md format, compatible with Claude Code, GitHub Copilot, Cursor, Cline) providing DQL fundamentals, observability domain knowledge, prompt templates. A *knowledge/workflow layer*, explicitly not a live-action layer (pairs with MCP server/dtctl for execution). Installed via `npx skills add` or Claude Code plugin marketplace. |
| May 27, 2026 | *Dynatrace MCP Server for Atlassian Rovo* | Dynatrace MCP Server becomes a **pre-approved external MCP integration for Atlassian Rovo** (Jira, JSM, Confluence), included free with Dynatrace SaaS. Per-user OAuth 2.1 enforcement, per-tool admin allowlisting, unified audit trail, usage-based (not per-seat) pricing. |
| May 28, 2026 | *AI Agents Are Redefining Software Development but They're Flying Blind Without Observability* | Bernd Greifeneder's thought-leadership piece framing the "bimodal world" (human-led vs agent-led teams) and observability as the bridge. Cites 12× higher SRE success rate and Grail as agent "long-term memory engine." |
| Jun 5, 2026 | *Port and Dynatrace: One-Prompt Incident Triage* | Dynatrace MCP Server available in **Port** (internal developer portal) via Port MCP Connectors — combines Dynatrace's observability signals with Port's ownership/on-call/deployment data for single-prompt triage. |
| Jun 12, 2026 | *Dynatrace Observability Is Now a Kiro Power* | Evolution of the Kiro integration into a **"Kiro Power"** — a one-click, partner-validated bundle (MCP server + steering files + best practices), replacing manual JSON/MCP setup. Includes NAIC customer testimonial. |
| Jun 15, 2026 | *Orchestrate Multicloud AI Agents for Autonomous Incident Resolution* | Launch of **Cloud SRE Agents** app — an orchestration layer on top of AWS DevOps Agent, Azure SRE Agent, and Google Gemini Cloud Assist. Adds **Interaction Profiles** (rule-based routing), budget-aware dispatch, governance/audit views (Activity tab, Statistics tab), and workflows (Investigate, Periodic Tasks, Event Handlers). |

### How the pieces fit together (architecture view)
- **Grail** (unified data lakehouse) + **Smartscape** (real-time dependency/topology graph) = the deterministic data foundation.
- **Dynatrace Intelligence** = the "agentic operations system" sitting on top of Grail/Smartscape, combining deterministic AI (causal, precise) with agentic AI (reasoning/action). Houses the Deterministic Agents (Root Cause, Analytics, Forecasting, Operator) and Domain agents (Developer, SRE, Security).
- **Dynatrace MCP Server** = the distribution/access layer — exposes Dynatrace Intelligence's data and agents to *any* external MCP-compatible AI client/agent (Bedrock, Claude Code, Copilot, Rovo, Port, n8n, ServiceNow, Kiro, Amazon Q, Slack).
- **Dynatrace for AI (agent skills)** = a *knowledge* layer (prompt templates + domain expertise) that pairs with the MCP Server/dtctl for execution — explicitly separate from data/action.
- **AutomationEngine** = the execution/automation substrate — turns "answers" (from causal AI/Grail/Smartscape) into no-code/low-code, event- or schedule-triggered actions (remediation, progressive delivery, security routing, provisioning).
- **Cloud SRE Agents** = the newest layer — a meta-orchestrator that routes problems identified by Dynatrace Intelligence *out* to third-party hyperscaler agents (AWS DevOps Agent, Azure SRE Agent, Gemini Cloud Assist), then brings their findings back into a unified Dynatrace view with governance.
- Individual point integrations (Kiro, Bedrock AgentCore, Azure SRE Agent, Atlassian Rovo, Claude Code, Port) are all instances of "Dynatrace as the observability/data layer feeding someone else's agent via MCP," while ready-made agents / Dynatrace Intelligence / Cloud SRE Agents represent "Dynatrace building/orchestrating its own agents."

---

## 2. Core AI Messaging Themes & Terminology

Recurring vocabulary and framings across nearly all pieces:

- **"Agentic AI" / "agentic operations system"** — Dynatrace Intelligence is repeatedly called "the industry's first agentic operations system."
- **"Autonomous operations"** as the end-state goal, reached via a **three-stage maturity journey**:
  1. **Automated** — pre-defined workflows execute automatically.
  2. **Supervised autonomous** — AI proposes execution-ready action plans; human approves ("humans stay in control of what matters most").
  3. **Fully autonomous** — Dynatrace Intelligence acts independently, humans only set goals/review outcomes.
- **Observability as the "eyes" for AI agents** — framed via the "flying blind" metaphor: "AI agents cannot perceive production behavior without assistance"; "AI agents are only as effective as the data that powers them."
- **"Grounded" / "deterministic" data foundation** — near-universal phrase: answers/root causes are "grounded in deterministic, causal AI and real-time production data, not probabilistic guesses." Explicit contrast between deterministic AI (Dynatrace) and probabilistic/generative AI (LLMs).
- **"Precision, not prompts"** — analyst quote (Rob Strechay) capturing the differentiation angle.
- **MTTR / MTTI reduction as the proof metric** — recurring stats: "up to 70%"/"up to 75% reduction in mean time to resolution" (AWS DevOps Agent + Dynatrace); "12× higher success rate in SRE use cases."
- **Human-in-the-loop / trust & governance framing** — "guardrails," "audit trail," per-user OAuth 2.1, per-tool admin allow-listing, Activity/Statistics tabs for review, "Good/OK/Bad" rating of agent responses, budget caps on agent spend. Consistent message: autonomy expands only as trust is earned/measured.
- **"World model" / topology framing via Smartscape** — Smartscape described as providing "an always-accurate understanding of your entire IT landscape," "zero overhead," "foundation for Dynatrace Intelligence," giving agents "facts, not guesses" about blast radius, ownership, and dependency.
- **Grail as "long-term memory engine"** — from Greifeneder's piece: Grail serves as the agent's memory/context substrate, not just a data store.
- **"Bimodal world"** — human-led teams (augmented SDLC) vs. agent-led teams (full agent swarms, spec-only humans) as two coexisting operating models Dynatrace serves simultaneously.
- **Ready-made vs. custom agents** — Dynatrace agents are marketed as "not concepts or previews" but immediately usable, while also being extensible via Agentic Workflows for custom builds.
- **MCP as the universal connective tissue** — Model Context Protocol is repeatedly called "the standard for connecting AI assistants to live tools and data," used identically across every partner integration.
- **Minimal-friction install narrative** — "no server to install, host, or maintain," "connect... in minutes," "setup is a configuration task, not a project," "one-click install," "no extra cost" (Rovo/SaaS bundling).

---

## 3. Positioning & Differentiation Claims

What Dynatrace claims sets it apart from generic AI/LLM-based approaches:

- **Causal AI vs. statistical/probabilistic correlation** — deterministic, causation-based root cause analysis vs. "probabilistic guesses" typical of LLM-only agents. Explicit claim: "Dynatrace takes the guesswork out of AI" by balancing deterministic AI, contextual analytics, and stochastic (generative) AI.
- **Unified data lakehouse (Grail) at exabyte scale** with schema-on-read for "zero-latency analytics" — positioned as solving the LLM context-window/hallucination problem by distilling vast telemetry into compact high-quality context before it ever reaches a prompt.
- **Real-time, zero-maintenance topology (Smartscape)** — "always-accurate," "no manual tagging," positioned as a deterministic ground-truth graph that other AI/agents can trust, contrasted implicitly with agents that reason without a live dependency model.
- **Precision/determinism as the ROI story** — analyst quote: "The real ROI in Dynatrace Intelligent Agents comes from precision, not prompts... reduces costs, increases trust, and enables supervised autonomy that enterprises can actually scale."
- **Permission/governance controls baked into the architecture** — OAuth 2.1 per-user enforcement, per-tool admin selection, unified audit logs spanning both Dynatrace and the partner tool, cost attribution by data owner, and (in Cloud SRE Agents) explicit per-agent monthly budget caps with a "circuit breaker" mode. This is positioned as necessary infrastructure for enterprises to trust autonomy at scale, not just a feature checkbox.
- **Platform-neutral / hyperscaler-agnostic stance** — Dynatrace explicitly serves as the common context layer across AWS, Azure, and GCP simultaneously (Cloud SRE Agents), avoiding lock-in to any one cloud's native agent.
- **"Observes other AI"** — Dynatrace Intelligence conclusion line frames Dynatrace as meta-observability for AI itself: it "observes other AI and helps organizations build more resilient applications."

---

## 4. Ecosystem / Partnership Narrative

Dynatrace consistently positions itself as **the observability/data layer that feeds other companies' agent ecosystems via MCP**, while *also* building and orchestrating its own ready-made agents — a dual-track strategy:

**Track A — "Fuel other agents" (data/context provider via MCP):**
- AWS: Bedrock AgentCore Gateway (first AWS Partner as an MCP target), AWS DevOps Agent, Amazon Kiro / Kiro Powers, Amazon Q.
- Microsoft: Azure SRE Agent, Microsoft Copilot, GitHub Copilot.
- Atlassian: Rovo / Rovo Ops (Jira, JSM, Confluence) — pre-approved external MCP integration.
- Anthropic: Claude Code connector (native "Connectors" install).
- Port: developer-portal MCP connector combining ownership/on-call data with Dynatrace telemetry.
- Also mentioned as MCP-connected: ServiceNow Assist, Slack, n8n.

**Track B — "Build our own agents/orchestration":**
- Dynatrace Intelligence's own Deterministic Agents (Root Cause, Analytics, Forecasting, Operator) and Domain agents (Developer, SRE, Security), plus Assist Agents and Agentic Workflows.
- Dynatrace for AI — its own "agent skills" content layer for third-party coding agents (rather than an agent itself).
- Cloud SRE Agents — Dynatrace's own orchestration app that sits *above* AWS/Azure/GCP native agents, routing problems to them and pulling results back — i.e., Dynatrace positions itself as the **meta-orchestrator/control plane** across hyperscaler agent ecosystems, not merely a data source for any single one.

**Narrative synthesis:** every partner integration follows the same shape — "[Partner]'s agent gets deterministic, causal, real-time context from Dynatrace via MCP, and Dynatrace gets a new surface for its intelligence." Over the timeline this evolves from simple one-directional data-feed integrations (Kiro, Bedrock, Azure SRE Agent — late 2025/early 2026) toward two-way, governed, and orchestrated relationships (Rovo, Port — mid 2026) and finally to Dynatrace explicitly orchestrating *across* multiple hyperscaler agents at once (Cloud SRE Agents, June 2026) — a clear ambition arc from "plumbing" to "control plane."

---

## 5. Notable Verbatim Quotes (with attribution)

- "Organizations are evolving from human-driven operations to supervised autonomous operations, where AI investigates, recommends, and remediates, and humans stay in control of what matters most." — *Orchestrate Multicloud AI Agents...*, Christian Kiesewetter, Jun 15, 2026
- "Kiro's answers are grounded in deterministic, causal AI and real-time production data, not probabilistic guesses." — *Dynatrace Observability Is Now a Kiro Power*, Christian Kiesewetter & Shashiraj Jeripotula, Jun 12, 2026
- "Using Kiro powers for Dynatrace has been a total game-changer in the observability space. Deep-dive root cause analysis of complex system issues that once required lengthy manual intervention now happens in seconds, giving us unprecedented speed and confidence." — Mike Kobush, Sr. Software Performance Engineer, NAIC (in same Kiro Power blog)
- "AI agents are only as effective as the data that powers them." — *Dynatrace MCP Server: Empower Your AI Assistants*, Christian Kiesewetter & Christoph Enzinger, Jan 28, 2026
- "Connect Dynatrace to any MCP client" within minutes without deploying additional infrastructure. — same article
- According to AWS, "organizations using the AWS DevOps Agent with Dynatrace see up to a 75% reduction in mean time to resolution." — *Orchestrate Multicloud AI Agents...*, Jun 15, 2026
- "77% of IT teams still lack full visibility across hybrid environments." — *AI Agents Are Redefining Software Development but They're Flying Blind Without Observability*, Bernd Greifeneder, May 28, 2026
- "12× higher success rate in SRE use cases." — same article (Greifeneder), describing Dynatrace Intelligence benchmarks for human-led teams
- "Speed is now the primary driver of innovation, forcing organizations to rethink processes, compliance, and roles." — Fortune 500 CTO quoted in Greifeneder's piece
- "Hallucinations aren't minor errors – they can trigger wrong actions leading to outages, security risks, and financial exposure." — *Dynatrace Intelligence at the Core of Autonomous Operations*, Bernd Greifeneder, Jan 28, 2026
- "Models have finite context windows and can underweight important details in very long prompts." — same article
- "[Dynatrace Intelligence] observes other AI and helps organizations to build more resilient applications and better customer experiences." — same article, closing line
- "As our digital environment grows more complex, we're looking to move beyond reactive operations and manual intervention... It's observability that doesn't just detect problems—it understands them and acts on them reliably." — Alexander Bicalho, Sr. Director of Engineering, Autodesk (Dynatrace Intelligence platform page, dynatrace.com/platform/artificial-intelligence)
- "The real ROI in Dynatrace Intelligent Agents comes from precision, not prompts. Deterministic AI, unlike LLMs, reduces costs, increases trust, and enables supervised autonomy that enterprises can actually scale." — Rob Strechay, Principal Analyst, TheCUBE Research & Sumget Consulting (same platform page)
- "The Smartscape technology is really impressive because it shows us a visual diagram of everything it's monitoring, and that allows us to see how systems are interacting in real-time." — Adrian Jacobs, Sr. Director of Business Engagement & Systems, IP Australia (Smartscape platform page)
- "The new AutomationEngine applies Dynatrace AIOps to our data, and its no-code and low-code toolset and predefined actions make it easy to automate tasks that once required engineering input." — Alex Hibbitt, Engineering Director, Customer Platform, Photobox (AutomationEngine platform page)
- "Drive intelligent cloud ecosystem automation with precise answers and secure integrations that leverage causal AI and all your data." — AutomationEngine platform page, main value proposition
- "Ask Port AI what's wrong; you'll get details about the failing service, the error signature, the file and function, and the suspect commit." — *Port and Dynatrace: One-Prompt Incident Triage*, Rob Jahn & Christoph Enzinger, Jun 5, 2026
- "Every call runs with the permissions of the requesting user, every action is logged, and data access and cost remain under central control." — *Dynatrace MCP Server for Atlassian Rovo*, Christoph Enzinger & Davor Stosic, May 27, 2026
- "Ready-made agents... are not concepts or previews; they're available now, integrated into existing Dynatrace workflows, and designed to solve real operational problems." — *Dynatrace AI Agents Begin Working for You on Day One*, Milan Steskal & Rosa Van Dam, Apr 3, 2026
- Skills/prompts constitute "a knowledge and workflow layer" that doesn't directly connect to Dynatrace environments or define agent actions. — *Dynatrace for AI*, Christian Kiesewetter & Milan Steskal, Apr 23, 2026
- "dtctl" described as "the open source CLI for the Dynatrace platform." — *Bring Real-Time Production Insights into Claude Code...*, Milan Steskal & Christoph Enzinger, Mar 30, 2026

---

## 6. Source List (for citation)

1. Orchestrate Multicloud AI Agents for Autonomous Incident Resolution — C. Kiesewetter, Jun 15, 2026
2. Dynatrace Observability Is Now a Kiro Power — C. Kiesewetter & S. Jeripotula, Jun 12, 2026 (updated Jun 22, 2026)
3. Dynatrace for AI: Teach Your AI Coding Agent How to Use Dynatrace — C. Kiesewetter & M. Steskal, Apr 23, 2026
4. Fuel Bedrock Agents with Observability Data via the Dynatrace MCP Server — L. Berda & C. Kiesewetter, Jan 28, 2026 (updated Feb 26, 2026)
5. Dynatrace MCP Server: Allow AI to Interact with Dynatrace and Access Production Insights — C. Kiesewetter & C. Enzinger, Jan 28, 2026 (updated Feb 27, 2026)
6. Real-Time Insights: Leverage Dynatrace Observability Capabilities within Amazon Kiro — C. Kiesewetter & S. Jeripotula, Nov 24, 2025 (updated Jan 19, 2026)
7. Boost Cloud Reliability: Dynatrace and Azure SRE Agent Unite for Autonomous Operations — C. Kiesewetter & C. Enzinger, Nov 19, 2025 (updated Feb 9, 2026)
8. AI Agents Are Redefining Software Development but They're Flying Blind Without Observability — B. Greifeneder, May 28, 2026
9. Dynatrace Intelligence at the Core of Autonomous Operations — B. Greifeneder, Jan 28, 2026
10. Port and Dynatrace: One-Prompt Incident Triage — R. Jahn & C. Enzinger, Jun 5, 2026
11. Dynatrace MCP Server for Atlassian Rovo: Investigate Production Problems Without Leaving Jira or JSM — C. Enzinger & D. Stosic, May 27, 2026
12. Dynatrace AI Agents Begin Working for You on Day One and Are Built to Grow with You — M. Steskal & R. Van Dam, Apr 3, 2026
13. Bring Real-Time Production Insights into Claude Code with the Dynatrace MCP Server — M. Steskal & C. Enzinger, Mar 30, 2026
14. Dynatrace Platform: Artificial Intelligence (Dynatrace Intelligence) — evergreen platform page
15. Dynatrace Platform: Application Topology Discovery — Smartscape — evergreen platform page
16. Dynatrace Platform: AutomationEngine — evergreen platform page
