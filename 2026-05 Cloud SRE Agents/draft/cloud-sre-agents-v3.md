---
title: "Orchestrate cloud-native AI agents for autonomous incident resolution"
slug: cloud-sre-agents
authors: Christian Kiesewetter
status: draft
meta_description: "Cloud SRE Agents orchestrates AWS DevOps Agent, Azure SRE Agent, and Google Gemini Cloud Assist for multi-cloud incident resolution. Available now in the Hub."
---

# Orchestrate cloud-native AI agents for autonomous incident resolution — introducing Cloud SRE Agents

Autonomous operations are happening in production today. [Dynatrace Intelligence](https://www.dynatrace.com/platform/artificial-intelligence/) is the agentic operations system orchestrating them, directing Dynatrace's own AI-driven agents while connecting with the ecosystem agents your cloud providers already run. **Cloud SRE Agents**, now generally available in the Dynatrace Hub, extends that orchestration to the three cloud-native AI agents that have all reached general availability this year: [AWS DevOps Agent](https://aws.amazon.com/devops-agent/) for investigation and remediation in AWS, [Azure SRE Agent](https://sre.azure.com/welcome) for the same in Azure, and [Google Gemini Cloud Assist](https://cloud.google.com/products/gemini/cloud-assist) for incident analysis across GCP. For multi-cloud teams, the question isn't whether to use these agents; it's how to run all three with consistent intent, predictable cost, and a single audit trail. Cloud SRE Agents answers that with one orchestration layer that routes problems to the right agent based on configurable profiles, writes every finding back to the Dynatrace problem screen, and gives your team measurable visibility into every autonomous action.

### In this blog post

1. Three cloud agents, one production reality
2. The orchestration layer in action
3. Routing rules that encode operational intent
4. Governance that makes autonomous work measurable
5. Why production context multiplies the value
6. Get started

---

## Three cloud agents, one production reality

Over the past year, we've published the integration story for each of these agents individually. The [AWS DevOps Agent integration with Dynatrace](https://www.dynatrace.com/news/blog/integration-with-aws-devops-agent-autonomous-investigations-powered-by-production-context/) feeds topology-aware root cause into AWS's frontier agent capabilities. [Azure SRE Agent connects with Dynatrace](https://www.dynatrace.com/news/blog/boost-cloud-reliability-dynatrace-and-azure-sre-agent-unite-for-autonomous-operations/) to flow deterministic, causation-based AI into Azure-native remediation workflows. Google Gemini Cloud Assist taps the same Dynatrace production context for GCP-hosted incidents, naming the responsible service before any investigation begins.

Most enterprises don't live in a single cloud. They run workloads across AWS, Azure, and Google Cloud at the same time, and managing three separate integrations with three sets of routing decisions and three cost models is its own operational tax. The question isn't whether each agent is useful. It's how to run them as a coordinated team. Cloud SRE Agents is what coordinates them: one app, one configuration model, and one place to see what's happening across all three.

---

## The orchestration layer in action

When Dynatrace Intelligence detects a problem and names the root cause, Cloud SRE Agents calls in the cloud-native specialists from AWS, Azure, and Google Cloud to pull the deeper evidence only they can reach: CloudTrail history, Azure subscription policy, GCP project IAM, recent deployments, native runbooks. The agents run in parallel the moment the problem fires. Their findings, and where applicable a recommended remediation path, land back on the same Dynatrace problem screen the on-call SRE is already reading.

One screen. No tab-switching. The work starts without you.

Three workflows do the orchestration in the background:

- **Investigate** evaluates your Interaction Profiles and dispatches matching problems to the right agents in parallel.
- **Periodic Tasks** polls each cloud provider for completion, detects stalled or timed-out investigations, and writes findings back as problem annotations.
- **Event Handlers** normalize the cloud-provider event stream so every action correlates back to its originating problem, end to end.

The agents don't talk to each other; each runs independently in its own cloud. Cloud SRE Agents decides which agent gets which problem, tracks each run to completion, and brings the answers back together on a single screen. The Overview tab visualizes the whole picture in real time as an interactive network graph of problems, agents, and activities.

*Figure 1: The Overview tab's interactive network graph, showing a live problem connected to dispatched agents and their activity statuses.*

---

## Routing rules that encode operational intent

Routing rules sound like plumbing. In agentic operations, they're the difference between turning autonomous systems loose on every alert and pointing them precisely where they earn their keep. **Interaction Profiles** are how you express that judgment in Cloud SRE Agents. Each profile pairs a set of conditions with the agent or agents that should handle problems matching them, evaluated whenever Dynatrace Intelligence fires a problem.

The conditions you can write are deliberately broad. You can route by the cloud account, subscription, or project an incident touches; by problem category (availability, error, slowdown, resource contention); by affected entity type (a Kubernetes cluster, a database, a Lambda function); by tag, label, or any custom attribute carried in the problem record. Conditions combine with AND/OR logic and nest as deeply as you need, which keeps real production routing policy inside the app instead of spilling into custom workflows or scripts.

A representative example: a payments platform team writes one profile that dispatches AWS DevOps Agent for availability or error problems on a specific production AWS account, capped by a monthly duration budget so dispatch stops automatically when the cap is reached. A second profile narrows by Problem Category = AVAILABILITY only, raising the bar for the highest-impact investigations. A third covers slowdowns under a tighter resource scope. One tiered, budget-aware policy, expressed in one place and changed in one place when reality shifts.

**Trigger Investigation > Test (Dry Run)** validates the rule against recent problems before any agent is invoked. The first live dispatch isn't also the first time you're learning what your rule actually matches.

*Figure 2: Interaction Profile configuration showing routing conditions, agent assignments, and the Test (Dry Run) validation panel.*

---

## Governance that makes autonomous work measurable

Agentic operations earn trust when teams can see what the agents did, why, and whether it worked. Cloud SRE Agents treats that as a first-class concern, with two views built for the two audiences who care about it.

The **Activity** tab is the audit trail. Every investigation and mitigation appears as a card on a unified timeline; expand any card to see the agent's full findings, the evidence it pulled, and the action it took or recommended. Each response can be rated Good, OK, or Bad, building a quality signal grounded in what your team actually saw, not what the system predicted. When a single problem has triggered work across multiple agents, those activities roll up to one status (in progress, done, or stalled) so you always know where things stand without reconstructing the run from individual records.

The **Statistics** tab is where autonomous operations becomes a number you can show to a leadership team: problems handled, mitigations executed, average investigation time, MTTR and MTTI trends, success rates, and satisfaction scores broken down by agent. The same view doubles as a directional cost lens, since agent working time is the dominant driver on the cloud side of the bill. Treat the number as a trend signal and a circuit-breaker input, not a billing record (reconcile against AWS, Azure, and GCP usage reports for exact spend), and it makes the case for expanding agentic coverage with evidence rather than anecdote.

*Figure 3: The Statistics tab showing per-agent working time, MTTR improvement, and satisfaction scores across a selected time range.*

---

## Why production context multiplies the value

What turns Cloud SRE Agents from a smart dispatcher into something more is what Dynatrace Intelligence contributes before an agent ever begins its analysis. Dynatrace delivers deterministic, causation-based root cause analysis grounded in Smartscape®, the real-time topology mapping that continuously maps dependencies across your full stack, alongside business impact assessment and correlated telemetry. That context shapes the entire direction of the investigation. A cloud agent arriving with that foundation starts from "this specific service on this specific host is the root cause, and here's the customer impact" rather than "something is wrong somewhere in this account."

The numbers reflect it. Organizations using AWS DevOps Agent with Dynatrace report up to 75% lower MTTR, 80% faster investigations, and 94% root cause accuracy, according to AWS. Joint customers across the partnership report up to 70% MTTR reductions overall.

Western Governors University, which runs a fully online learning environment for 200,000 students, uses AWS DevOps Agent with Dynatrace to automate cross-system correlation that previously required manual effort across multiple tools. At larger scale, United Airlines transports more than 500,000 passengers daily across a hybrid environment that includes more than 500 AWS accounts, 20,000 Lambda functions, and 38,000 OneAgent® deployments. The team's description of the before and after is direct: previously, multiple tools with overlapping functions created gaps and black boxes during troubleshooting. With AWS DevOps Agent and Dynatrace, Dynatrace identifies the responsible layer, the agent investigates and provides resolution steps, and everything surfaces in a single Dynatrace screen. No 3 a.m. tool-switching required.

*Figure 4: The Activity tab showing an expanded investigation card with agent findings and Good/OK/Bad rating controls.*

---

## Get started

Cloud SRE Agents is available now in the [Dynatrace Hub](https://www.dynatrace.com/hub/). The shortest path from install to first investigation is roughly five minutes:

1. **Set up** (3 minutes). Open the Setup tab and follow the guided flow to install the IAM policy, service user, and the three orchestration workflows. Live status badges show what's configured and what's still missing.
2. **Connect one agent** (1 minute). In Configuration, add an agent of any cloud type, paste the endpoint URL and credential from your cloud provider's console, and save.
3. **Add one profile** (1 minute). Create an Interaction Profile with one global filter (something simple, like *Has AWS Resources*), assign the agent, and enable the profile.
4. **Validate** (30 seconds). Open Trigger Investigation, pick a recent problem, and run **Test (Dry Run)**. If the profile matches as expected, uncheck Dry Run and dispatch live.

The next matching problem dispatches automatically, and findings start appearing on the Dynatrace problem screen as each agent completes its work. For a closer look at the individual integrations, read the posts on [AWS DevOps Agent and Dynatrace](https://www.dynatrace.com/news/blog/integration-with-aws-devops-agent-autonomous-investigations-powered-by-production-context/) and [Azure SRE Agent and Dynatrace](https://www.dynatrace.com/news/blog/boost-cloud-reliability-dynatrace-and-azure-sre-agent-unite-for-autonomous-operations/), or see how [Dynatrace Intelligence powers autonomous operations](https://www.dynatrace.com/news/blog/dynatrace-intelligence-at-the-core-of-autonomous-operations/). To put your cloud agents to work today, install Cloud SRE Agents from the Dynatrace Hub.

Cloud SRE Agents is currently available as a community-supported app.

<!-- v2 draft. primary style: christian. drafted with --express flag from update-prompt.md + new-doc.txt; existing v1 at draft/cloud-sre-agents.md preserved. -->
