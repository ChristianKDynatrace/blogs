---
title: "Orchestrate cloud-native AI agents for autonomous incident resolution — introducing Cloud SRE Agents"
slug: cloud-sre-agents
authors: Christian Kiesewetter
status: draft
meta_description: "Cloud SRE Agents orchestrates AWS DevOps Agent, Azure SRE Agent, and Google Gemini Cloud Assist for multi-cloud incident resolution. Available now in the Hub."
tags: Agentic ecosystem, AI, AWS, Azure, Google Cloud, Incident management, SRE, Observability
---

# Orchestrate cloud-native AI agents for autonomous incident resolution — introducing Cloud SRE Agents

Autonomous operations aren't a future state. They're happening now. At Dynatrace, [Dynatrace Intelligence](https://www.dynatrace.com/platform/artificial-intelligence/) is our agentic operations system: orchestrating Dynatrace's own AI-driven agents (including new investigation agents we'll introduce shortly) while also connecting with external ecosystem agents to drive precise, trustworthy actions across complex environments. The goal is to move organizations from human-driven operations to supervised autonomous operations, where AI investigates, recommends, and remediates, and humans stay in control of what matters most.

A big part of delivering on that vision is working with the agents customers already run in their cloud environments. All three hyperscaler SRE agents have now reached general availability: [AWS DevOps Agent](https://aws.amazon.com/devops-agent/) for investigation and remediation in AWS, [Azure SRE Agent](https://sre.azure.com/welcome) for the same in Azure, and [Google Gemini Cloud Assist](https://cloud.google.com/products/gemini/cloud-assist) for incident analysis across GCP. For multi-cloud teams, the question isn't whether to use these agents; it's how to run all three with consistent intent, predictable cost, and a single audit trail. **Cloud SRE Agents**, now available in the Dynatrace Hub, answers that with one orchestration layer that routes problems based on configurable profiles, writes findings back into Dynatrace, and gives your team measurable visibility into every autonomous action.

### In this blog post

1. From point integrations to intelligent orchestration
2. How Cloud SRE Agents works
3. Intelligent routing with Interaction Profiles
4. Three ways teams put it to work
5. Governance that makes autonomous work measurable
6. Why production context multiplies the value
7. Get started

---

## From point integrations to intelligent orchestration

Over the past year, we've published how Dynatrace supercharges each of these cloud agents individually. When [Dynatrace integrates with AWS DevOps Agent](https://www.dynatrace.com/news/blog/integration-with-aws-devops-agent-autonomous-investigations-powered-by-production-context/), topology-aware root cause analysis combines with AWS's frontier agent capabilities, and joint customers report up to 70% reductions in mean time to resolution. When [Azure SRE Agent connects with Dynatrace](https://www.dynatrace.com/news/blog/boost-cloud-reliability-dynatrace-and-azure-sre-agent-unite-for-autonomous-operations/), deterministic, causation-based AI flows directly into Azure-native remediation workflows, cutting the back-and-forth between teams. And with Google Gemini Cloud Assist, Dynatrace delivers the same production context layer to GCP-hosted incidents: precise root cause, full topology, real business impact.

But most enterprises don't live in a single cloud. They run workloads across AWS, Azure, and Google Cloud simultaneously, and managing three separate integrations with separate routing logic and separate cost controls is its own operational tax. Cloud SRE Agents solves exactly this: one app, one configuration model, and one place to see everything happening across all three cloud agents.

---

## How Cloud SRE Agents works

When Dynatrace Intelligence detects a problem and names the root cause, Cloud SRE Agents calls in the cloud-native specialists from AWS, Azure, and Google Cloud to pull the deeper evidence only they can reach: CloudTrail history, Azure subscription policy, GCP project IAM, recent deployments, native runbooks. The agents run in parallel the moment the problem fires. Their findings, and where applicable a recommended remediation path, land back on the same Dynatrace problem screen the on-call SRE is already reading.

One screen. No tab-switching. The work starts without you.

Three workflows do the orchestration in the background:

- **Investigate** evaluates your Interaction Profiles and dispatches matching problems to the right agents in parallel.
- **Periodic Tasks** polls each cloud provider for completion, detects stalled or timed-out investigations, and writes findings back as problem annotations.
- **Event Handlers** normalize the cloud-provider event stream so every action correlates back to its originating problem, end to end.

The agents don't talk to each other; each runs independently in its own cloud. Cloud SRE Agents decides which agent gets which problem, tracks each run to completion, and brings the answers back together on a single screen. The **Overview** tab visualizes the whole picture in real time as an interactive network graph of problems, agents, and activities. Select any node to highlight its relationships; double-click to navigate to the associated problem or agent.

*Figure 1: The Overview tab's interactive network graph, showing a live problem connected to dispatched agents and their activity statuses.*

---

## Intelligent routing with Interaction Profiles

Routing rules sound like plumbing. In agentic operations, they're the difference between turning autonomous systems loose on every alert and pointing them precisely where they earn their keep. **Interaction Profiles** are how you express that judgment in Cloud SRE Agents. Each profile pairs a set of conditions with the agent or agents that should handle problems matching them, evaluated whenever Dynatrace Intelligence fires a problem.

The conditions you can write are deliberately broad. You can route by the cloud account, subscription, or project an incident touches; by problem category (availability, error, slowdown, resource contention); by affected entity type (a Kubernetes cluster, a database, a Lambda function); by tag, label, or any custom attribute carried in the problem record. Conditions combine with AND/OR logic and nest as deeply as you need, which keeps real production routing policy inside the app instead of spilling into custom workflows or scripts.

**Trigger Investigation > Test (Dry Run)** validates the rule against recent problems before any agent is invoked. The first live dispatch isn't also the first time you're learning what your rule actually matches.

*Figure 2: Interaction Profile configuration showing routing conditions, agent assignments, and the Test (Dry Run) validation panel.*

---

## Three ways teams put it to work

### Route problems to the right cloud, automatically

A spike in Lambda error rates belongs to AWS DevOps Agent. An Azure App Service degradation calls for Azure SRE Agent. A Pub/Sub latency issue lands with Gemini Cloud Assist. In a multi-cloud estate, none of those decisions should fall to a human at 2 a.m. A profile filtered by AWS Account ID, Azure Subscription ID, or GCP Project ID, then narrowed by resource type or tag, settles the routing question once. Every matching problem reaches the right specialist with the right cloud-native context, automatically.

### Optimize spend with budget-aware routing

Cloud AI agents do work, and that work has a cost. Cloud SRE Agents lets you set a **Monthly Duration Budget** per agent and gate dispatch on it via a **Has Available Budget** filter: once the budget is exhausted, new investigations either stop (in strict enforcement mode) or proceed with a logged warning. The duration figure itself is a proxy, derived from event timestamps in Dynatrace rather than the cloud provider's clock, which makes it useful as a circuit breaker and a directional signal, not a substitute for AWS, Azure, or GCP usage reports. The governance value is what matters: you decide how much autonomous investigation you're willing to underwrite each month, and the system holds the line.

### Tier autonomous investigation by problem type and entity

Not every Dynatrace problem warrants an autonomous investigation. **Problem Category** filters let you dispatch agents only for the categories that justify it: availability or error problems that need immediate action, separate from slowdowns or custom alerts where human triage may still be the right call. Layer on **Entity Type** filters and you can narrow further to specific infrastructure tiers (hosts, services, process groups, Kubernetes clusters). The result is a tiered model: high-severity issues get autonomous investigation immediately, lower-severity signals queue for human review, and your team controls the threshold.

---

## Governance that makes autonomous work measurable

Agentic operations earn trust when teams can see what the agents did, why, and whether it worked. Cloud SRE Agents treats that as a first-class concern, with two views built for the two audiences who care about it.

The **Activity** tab is the audit trail. Every investigation and mitigation appears as a card on a unified timeline; expand any card to see the agent's full findings, the evidence it pulled, and the action it took or recommended. Each response can be rated Good, OK, or Bad, building a quality signal grounded in what your team actually saw, not what the system predicted. When a single problem has triggered work across multiple agents, those activities roll up to one status (in progress, done, or stalled) so you always know where things stand without reconstructing the run from individual records.

The **Statistics** tab is where autonomous operations becomes a number you can show to a leadership team: problems handled, mitigations executed, average investigation time, MTTR and MTTI trends, success rates, and satisfaction scores broken down by agent. The same view doubles as a directional cost lens, since agent working time is the dominant driver on the cloud side of the bill. Treat the number as a trend signal and a circuit-breaker input, not a billing record (reconcile against AWS, Azure, and GCP usage reports for exact spend), and it makes the case for expanding agentic coverage with evidence rather than anecdote.

*Figure 3: The Statistics tab showing per-agent working time, MTTR improvement, and satisfaction scores across a selected time range.*

---

## Why production context multiplies the value

What turns Cloud SRE Agents from a smart dispatcher into something more is what Dynatrace Intelligence contributes before an agent ever begins its analysis. Dynatrace delivers deterministic, causation-based root cause analysis grounded in Smartscape®, the real-time topology mapping that continuously maps dependencies across your full stack, alongside business impact assessment and correlated telemetry. That context shapes the entire direction of the investigation. A cloud agent arriving with that foundation starts from "this specific service on this specific host is the root cause, and here's the customer impact" rather than "something is wrong somewhere in this account."

The numbers reflect it. According to AWS, organizations using AWS DevOps Agent with Dynatrace see up to 75% lower mean time to resolution.

Western Governors University, which runs a fully online learning environment for 200,000 students, uses AWS DevOps Agent with Dynatrace to automate cross-system correlation that previously required manual effort across multiple tools. At larger scale, United Airlines transports more than 500,000 passengers daily across a hybrid environment that includes more than 500 AWS accounts, 20,000 Lambda functions, and 38,000 OneAgent® deployments. The team's description of the before and after is direct: previously, multiple tools with overlapping functions created gaps and black boxes during troubleshooting. With AWS DevOps Agent and Dynatrace, Dynatrace identifies the responsible layer, the agent investigates and provides resolution steps, and everything surfaces in a single Dynatrace screen. No 3 a.m. tool-switching required.

*Figure 4: The Activity tab showing an expanded investigation card with agent findings and Good/OK/Bad rating controls.*

---

## Get started

Cloud SRE Agents is available now in the [Dynatrace Hub](https://www.dynatrace.com/hub/). The shortest path from install to first investigation is roughly five minutes:

1. **Set up** (3 minutes). Open the Setup tab and follow the guided flow to install the IAM policy, service user, and the three orchestration workflows. Live status badges show what's configured and what's still missing.
2. **Connect one agent** (1 minute). In Configuration, add an agent of any cloud type, paste the endpoint URL and credential from your cloud provider's console, and save.
3. **Add one profile** (1 minute). Create an Interaction Profile with one global filter (something simple, like *Has AWS Resources*), assign the agent, and enable the profile.
4. **Validate** (30 seconds). Open Trigger Investigation, pick a recent problem, and run **Test (Dry Run)**. If the profile matches as expected, uncheck Dry Run and dispatch live.

The next matching problem dispatches automatically, and findings start appearing on the Dynatrace problem screen as each agent completes its work. For a closer look at the individual integrations, read the posts on [AWS DevOps Agent and Dynatrace](https://www.dynatrace.com/news/blog/integration-with-aws-devops-agent-autonomous-investigations-powered-by-production-context/) and [Azure SRE Agent and Dynatrace](https://www.dynatrace.com/news/blog/boost-cloud-reliability-dynatrace-and-azure-sre-agent-unite-for-autonomous-operations/), or see how [Dynatrace Intelligence powers autonomous operations](https://www.dynatrace.com/news/blog/dynatrace-intelligence-at-the-core-of-autonomous-operations/). To put your cloud agents to work today, install Cloud SRE Agents from the Dynatrace Hub. (Cloud SRE Agents is currently available as a community-supported app.)

---

*[Standard author bio]*
