# Blog Writing Prompt: Cloud SRE Agents

## Task
Write a blog post for publication on the Dynatrace website (dynatrace.com/news/blog) announcing the availability of the **Cloud SRE Agents** app — a new Dynatrace Hub app that orchestrates AI-driven investigation and remediation across hyperscaler SRE agents from AWS, Azure, and Google Cloud.

---

## Author
**Christian Kiesewetter** (use standard Dynatrace author bio)

---

## Target audience
Both technical practitioners (SREs, platform engineers) and decision-makers (engineering managers, IT leaders).

---

## Length & tone
- ~800–1,200 words
- Tone: confident, practitioner-friendly, minimal marketing fluff. Reference existing Dynatrace blogs for style and tonality: https://www.dynatrace.com/news/category/artificial-intelligence/

---

## Availability
The app is available now. It is community-supported — mention this only briefly at the very end.

---

## Recommended blog structure

1. **Intro** — Start with Dynatrace's position in agentic/autonomous operations (Dynatrace Intelligence as the agentic operations system). Transition to the hyperscaler agent collaborations as an expression of that vision. Note that all three agents are now generally available. Introduce Cloud SRE Agents as the orchestration layer that ties it all together.

2. **From point integrations to intelligent orchestration** — Briefly recap the individual integrations (AWS, Azure, GCP) and explain why a single orchestration layer is needed for multi-cloud environments.

3. **What Cloud SRE Agents does** — Explain the core mechanics: Dynatrace detects a problem → Interaction Profiles are evaluated → matched agents dispatched in parallel → findings written back to Dynatrace as problem annotations → optional mitigation (AWS and Azure). Mention the Overview tab network graph.

4. **Intelligent routing with Interaction Profiles** — Explain Interaction Profiles as configurable routing rules. Cover filter types (cloud-specific attributes, resource types, tags, problem category, entity type, custom fields), AND/OR logic, per-agent assignments. Position this as an intelligent decision layer, not a simple dispatcher.

5. **Full visibility into every investigation** — Cover the Activity timeline (per-investigation log, expandable findings, Good/OK/Bad rating) and the Statistics dashboard (problems handled, mitigations executed, average investigation time, MTTR, MTTI, success rates, per-agent breakdowns, graph view). Close with the "prove it's working" framing relevant to both practitioners and managers.

6. **Three use cases:**
   - Route problems to the right cloud automatically (cloud-specific filters)
   - Optimize spend with budget-aware routing (Monthly Duration Budget, Has Available Budget filter, strict enforcement toggle, Statistics tab as cost lens)
   - Tier investigations by problem type and entity (Problem Category + Entity Type filters for a tiered model)

7. **The Dynatrace difference** — Position Dynatrace Intelligence as the production context layer that makes agent investigations more accurate. Explain that deterministic AI (not probabilistic guessing) is what separates fast from trustworthy agentic operations. Include the United Airlines customer quote (paraphrased — do not reproduce verbatim): United Airlines operates 500K+ daily passengers, 38K Dynatrace OneAgents, 500+ AWS accounts, 20K Lambda functions. Before: multiple tools, gaps, black boxes during troubleshooting. After: Dynatrace detects and identifies the responsible layer, the agent investigates and provides resolution steps, all in a single pane of glass — no 3 a.m. incident calls with tool-switching.

8. **Get started** — Point to the Dynatrace Hub, mention the Setup tab with guided IAM/workflow setup and live status badges, suggest using Trigger Investigation → Test (Dry Run) to validate filters. Link to individual integration blogs. Close with community-supported note.

---

## Screenshot suggestions (to be sourced from the app)
- Overview tab: interactive network graph showing a live problem connected to agents and activity statuses
- Configuration tab: Interaction Profile with cloud-specific filters and two per-agent assignments
- Statistics tab: per-agent breakdown showing MTTR, investigation time, and success rates
- Activity tab: expanded investigation card with agent findings and Good/OK/Bad rating control

---

## Key messages
- Dynatrace Intelligence is the agentic operations system orchestrating both Dynatrace's own agents and external ecosystem agents
- Cloud SRE Agents is the orchestration layer for hyperscaler SRE agents — not a simple relay, but a configurable, intelligent decision layer
- Interaction Profiles give precise, code-free control over which problems go to which agents
- The Activity and Statistics views provide full auditability and measurable ROI on agentic workflows
- Dynatrace's deterministic, causation-based AI is what makes external agent investigations trustworthy at scale

---

## External sources & references

### Dynatrace blogs (link in post)
- AWS DevOps Agent integration: https://www.dynatrace.com/news/blog/integration-with-aws-devops-agent-autonomous-investigations-powered-by-production-context/
- Azure SRE Agent integration: https://www.dynatrace.com/news/blog/boost-cloud-reliability-dynatrace-and-azure-sre-agent-unite-for-autonomous-operations/
- Dynatrace Intelligence positioning (CTO blog): https://www.dynatrace.com/news/blog/dynatrace-intelligence-at-the-core-of-autonomous-operations/
- Dynatrace agentic AI foundation (CPO blog): https://www.dynatrace.com/news/blog/dynatrace-introduces-a-new-foundation-for-agentic-ai-at-perform-2026/
- Dynatrace Intelligence platform page: https://www.dynatrace.com/platform/artificial-intelligence/

### Hyperscaler references (link where relevant)
- AWS DevOps Agent GA announcement: https://aws.amazon.com/blogs/mt/announcing-general-availability-of-aws-devops-agent/
- AWS DevOps Agent product page (includes WGU and United Airlines customer stories): https://aws.amazon.com/devops-agent/
- AWS DevOps Agent + Dynatrace walkthrough: https://aws.amazon.com/blogs/mt/resolve-application-issues-autonomously-with-aws-devops-agent-and-dynatrace/
- Azure SRE Agent: https://sre.azure.com/welcome
- Azure SRE Agent docs: https://learn.microsoft.com/en-us/azure/sre-agent/
- Dynatrace MCP in Azure SRE Agent (Microsoft blog): https://techcommunity.microsoft.com/blog/appsonazureblog/get-started-with-dynatrace-mcp-server-in-azure-sre-agent/4492363
- Gemini Cloud Assist product page: https://cloud.google.com/products/gemini/cloud-assist

### Background reading (do not necessarily link in post)
- LinkedIn post on AWS DevOps Agent GA by AWS DevOps Agent manager: https://www.linkedin.com/pulse/from-preview-ga-aws-devops-agent-gets-multi-cloud-skills-simon-moore-mfiqc/
- Dynatrace + Google Cloud partnership PR: https://ir.dynatrace.com/news-events/press-releases/detail/375/dynatrace-announces-early-access-for-joint-google-cloud-customers-to-capabilities-enabling-real-time-actionable-intelligence-from-data

---

## Stats & proof points to include
- Up to 70% MTTR reduction reported by joint AWS DevOps Agent + Dynatrace customers (source: Dynatrace AWS blog)
- AWS DevOps Agent preview results: up to 75% lower MTTR, 80% faster investigations, 94% root cause accuracy (source: AWS GA announcement)
- United Airlines: 500K+ daily passengers, 38K Dynatrace OneAgents, 500+ AWS accounts, 20K Lambda functions — moved from multi-tool troubleshooting to single-pane-of-glass resolution with AWS DevOps Agent + Dynatrace (source: AWS DevOps Agent product page)
- Western Governors University: 200K students relying on 24/7 online learning; AWS DevOps Agent + Dynatrace enables automatic cross-system correlation that previously required manual effort across multiple tools (source: AWS DevOps Agent product page)

---

## Do not include
- United Airlines quote verbatim (paraphrase only — copyright)
- Deep technical setup instructions (point to docs instead)
- Investor relations links (ir.dynatrace.com)
- Google Cloud Marketplace listing (requires login)
- Excessive use of bold, bullet lists, or headers — follow Dynatrace blog prose style
