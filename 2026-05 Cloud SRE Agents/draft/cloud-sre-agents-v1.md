# Orchestrate cloud-native AI agents for autonomous incident resolution — introducing Cloud SRE Agents

**By Christian Kiesewetter**
**Tags:** Agentic ecosystem, AI, AWS, Azure, Google Cloud, Incident management, SRE, Observability

---

Autonomous operations aren't a future state — they're happening now. At Dynatrace, [Dynatrace Intelligence](https://www.dynatrace.com/platform/artificial-intelligence/) is our agentic operations system: orchestrating Dynatrace's own AI-driven agents while also integrating seamlessly with external ecosystem agents to drive precise, trustworthy actions across complex environments. The goal is to move organizations from human-driven operations to supervised autonomous operations — where AI investigates, recommends, and remediates, and humans stay in control of what matters most.

A big part of delivering on that vision is working with the agents customers already run in their cloud environments. Over the past year, we've built deep integrations with the hyperscaler SRE agents from AWS, Azure, and Google Cloud — collaborations that combine Dynatrace's deterministic, causation-based AI with the native capabilities of each cloud platform. And now all three of those agents have crossed into general availability: AWS DevOps Agent went GA in March 2026, Azure SRE Agent is live in the Azure portal, and Google Cloud Assist is actively investigating production incidents today.

With the hyperscaler agents production-ready, the next natural question is: how do you run all of them together, consistently, across a multi-cloud environment? Today, we have the answer. **Cloud SRE Agents** is now available in the Dynatrace Hub: a single orchestration layer that connects Dynatrace Intelligence with AWS DevOps Agent, Azure SRE Agent, and Google Cloud Assist — routing the right problems to the right agents, automatically.

---

## From point integrations to intelligent orchestration

Over the past months, we've published how Dynatrace supercharges each of these agents individually. When [Dynatrace integrates with AWS DevOps Agent](https://www.dynatrace.com/news/blog/integration-with-aws-devops-agent-autonomous-investigations-powered-by-production-context/), topology-aware root cause analysis combines with AWS's frontier agent capabilities — and joint customers report up to 70% reductions in mean time to resolution. When [Azure SRE Agent connects with Dynatrace](https://www.dynatrace.com/news/blog/boost-cloud-reliability-dynatrace-and-azure-sre-agent-unite-for-autonomous-operations/), deterministic AI-based root cause analysis flows directly into Azure-native remediation workflows, eliminating the back-and-forth between teams. And across both, Dynatrace acts as the production context layer: the causal, precise, topology-aware understanding of your live environment that makes agent investigations dramatically more effective.

But most enterprises don't live in a single cloud. They run workloads across AWS, Azure, and Google Cloud simultaneously — and managing separate integrations, separate routing logic, and separate cost controls for each agent is its own operational burden.

Cloud SRE Agents solves exactly this.

---

## What Cloud SRE Agents does

When Dynatrace detects a problem, Cloud SRE Agents evaluates it against your configured **Interaction Profiles** — routing rules that determine which cloud agent should handle it, and under what conditions. Matched agents are dispatched in parallel, investigate using their platform's native tooling, and write findings back directly into the Dynatrace problem as annotations. Everything happens without leaving Dynatrace.

For AWS and Azure, successful investigations can be followed by automated **mitigation steps**. For Google Cloud Assist, investigation findings are returned and surfaced in full context. All activities — whether ongoing, completed, timed out, or awaiting human input — roll up into a unified view inside the app.

> **📸 Suggested screenshot:** The Overview tab's interactive network graph, showing a live problem connected to dispatched agents and their activity statuses.

---

## Three use cases that matter

### 1. Route problems to the right cloud, automatically

Not every problem belongs to every agent. A spike in Lambda error rates should go to AWS DevOps Agent. An Azure App Service degradation belongs to Azure SRE Agent. A GCP Pub/Sub latency issue is [Google Cloud Assist](https://cloud.google.com/products/gemini/cloud-assist) territory.

Interaction Profiles let you express this precisely. Filter by cloud-specific attributes — AWS Account ID, Azure Subscription ID, GCP Project ID — and by resource type, tags, or labels. Combine filters with AND/OR logic to match even complex multi-attribute conditions. Only problems that match get dispatched to a given agent, so each investigation starts from a relevant, cloud-native context rather than a generic alert.

> **📸 Suggested screenshot:** The Configuration tab showing an Interaction Profile with cloud-specific filters configured for two agents side by side.

### 2. Optimize spend with budget-aware routing

Cloud AI agents are powerful — and like all cloud services, they have a cost. Cloud SRE Agents includes a **Monthly Duration Budget** per agent, with a **Has Available Budget** filter that can gate dispatch when a budget ceiling is reached. In strict enforcement mode, dispatch is blocked once the budget is exhausted. With strict enforcement off, a warning is logged and investigations continue — giving you the flexibility to choose between hard guardrails and visibility-first cost management.

The Statistics tab gives you the full picture: agent working time, success rates, satisfaction scores (rate each investigation as Good / OK / Bad), and per-agent breakdowns. Since agent working time directly drives cloud costs, this is your primary lens for understanding and optimizing spend.

> **📸 Suggested screenshot:** The Statistics tab showing per-agent working time and satisfaction scores across a time range.

### 3. Tier your investigations by problem type and entity

Not all incidents warrant the same response. Cloud SRE Agents lets you use **Problem Category** filters — AVAILABILITY, ERROR, SLOWDOWN, RESOURCE_CONTENTION, and more — to selectively dispatch agents only for problem types that justify autonomous investigation. Layer on **Entity Type** filters to further narrow dispatch to specific infrastructure tiers: hosts, services, process groups, Kubernetes clusters.

The result is a tiered model where high-severity availability issues trigger immediate agentic investigation, while low-priority custom alerts are handled differently — or not routed to agents at all. You stay in control of what gets escalated and what doesn't.

> **📸 Suggested screenshot:** Filter configuration showing Problem Category and Entity Type filters combined with AND logic within an Interaction Profile.

---

## The Dynatrace difference

What makes Cloud SRE Agents more than a dispatcher is the production context Dynatrace contributes to every investigation. Before an agent ever begins its analysis, it receives Dynatrace's deterministic root cause analysis, full service topology, business impact assessment, and correlated telemetry. Real-world results speak for themselves: organizations using AWS DevOps Agent with Dynatrace report up to 75% lower MTTR, 80% faster investigations, and 94% root cause accuracy.

This is the role Dynatrace plays across all three cloud agent integrations — not just triggering investigations, but making each one more accurate, more targeted, and more likely to reach resolution without human intervention.

The impact is tangible at scale. United Airlines transports more than 500,000 passengers daily across a hybrid cloud environment spanning more than 500 AWS accounts, 20,000 Lambda functions, and 38,000 Dynatrace OneAgents. Their team described the before and after plainly: previously, multiple tools performing overlapping functions created gaps and black boxes during troubleshooting. With AWS DevOps Agent and Dynatrace, Dynatrace detects and identifies the responsible layer, the agent investigates further and provides precise resolution steps — all surfaced inside Dynatrace. As they put it: instead of initiating an incident call at 3 a.m. and switching between tools, the answers are ready in a single pane of glass.

---

## Get started

Cloud SRE Agents is available now in the Dynatrace Hub. The Setup tab within the app walks you through IAM policy configuration, service user setup, and workflow installation, with live status badges showing exactly what's configured and what's still missing. Use **Trigger Investigation → Test (Dry Run)** to validate your Interaction Profile filters before going live.

For a deeper look at each individual integration, explore our blogs on [AWS DevOps Agent](https://www.dynatrace.com/news/blog/integration-with-aws-devops-agent-autonomous-investigations-powered-by-production-context/) and [Azure SRE Agent](https://www.dynatrace.com/news/blog/boost-cloud-reliability-dynatrace-and-azure-sre-agent-unite-for-autonomous-operations/), or learn more about [Gemini Cloud Assist](https://cloud.google.com/products/gemini/cloud-assist) and the broader Dynatrace and Google Cloud partnership. To get started, head to the [Dynatrace Hub](https://www.dynatrace.com/hub/) to install the app. Cloud SRE Agents is currently available as a community-supported app.

---

*[Standard author bio]*
