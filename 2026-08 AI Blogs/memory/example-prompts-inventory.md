# Example Prompts Inventory — "Conversational Agentic Analytics" Demo Deck

*Source: `Agentic_Analytics__Example_Prompts.pptx`, internal deck maintained by the productoperations team, last updated 2026-07-02 ("Initial version" per its own changelog slide). Uploaded by the user 2026-08-01; the original file is a session-ephemeral upload and will not persist, so this doc is the durable record of its content. Purpose per the deck's own TL;DR: sample prompts to demonstrate "Conversational Agentic Analytics" capabilities, meant to be run live in the Dynatrace Playground — not a static reference (the deck explicitly asks readers to use the live link, not a downloaded copy, "to always have the last version," and to direct questions to `#help-productoperations`).*

**Important caveat, carried over from the user's own description:** this deck is "a bit outdated." Each slide pairs a prompt (durable, safe to reuse) with a screenshot of Assist's actual output (dated, likely stale numbers). **Treat the prompt text as reusable; treat every number/finding visible in a screenshot as needing a fresh re-run before any external use** — the same caution that applied to Christoph Enzinger's `index-assist.html` tenant numbers (see `positioning-evolution.md` §10.2, dropped entirely from Blog #1 for this reason). This deck's prompts were not viewed in screenshot detail in this pass — only the slide text (titles + prompts) was extracted; screenshots would need a separate look if a specific example's current output is needed.

**Independent confirmation of the "Agentic Analytics" naming decision:** the deck's own subtitle (slide 1) is literally "Conversational Agentic Analytics" — this matches the taxonomy decision made for Blog #1 in `tasks.md` before this deck was even reviewed.

---

## Structure

49 slides, organized into 8 named categories (deck's own grouping, slide 2's TL;DR):

1. Investigate incidents
2. Forecast & Predictions
3. Infrastructure
4. AI Observability
5. Security
6. APM
7. DEM
8. Cost Intelligence / Optimize Cost

**Mapping to the five use-case groups** (Incident Analysis / Optimize & Tune / Agentic Reporting / Risk & Impact / Security):
- Investigate incidents, Infrastructure, APM, DEM → **Incident Analysis** (the bulk of the deck)
- Cost Intelligence / Optimize Cost → **Optimize & Tune**
- Security → **Security**
- Forecast & Predictions → partially **Risk & Impact**, but see the gap noted below
- **Agentic Reporting has no dedicated category in this deck at all** — consistent with every other source reviewed so far (`positioning-evolution.md` §7/§9), reinforcing that this remains the weakest-represented group across the entire corpus, not just the positioning drafts.
- **AI Observability does not map to any of the five groups.** This is a genuine new category (Dynatrace observing other AI systems: LLM calls, token cost, agent evaluations, agent health) — a direct, concrete instantiation of the "observes other AI" line in `product-ai-messaging.md` §3. Flagged in `tasks.md` (§4) as needing a decision: 6th group, Security sub-case, or out of scope.
- **Forecast & Predictions is point-forecasting, not "what if" simulation** — "will this cluster's CPU stay healthy," "predict response time for the next 24 hours" are projections of a metric forward, not scenario simulation of a hypothetical decision. This does **not** close the Risk & Impact gap flagged repeatedly elsewhere (`positioning-evolution.md`, `medium-content-analysis.md`); Medium #4's SDK-version-bump "what if I raise minSdk to 26" example remains the closest genuine "what if" narrative found anywhere in this project's source material.

---

## Full prompt inventory (verbatim, by category)

### Investigate incidents

| Slide | Title | Prompt |
|---|---|---|
| 5 | Root cause analysis | "Determine the root cause of P-2605201741, why it happened, and actionable steps to remediate it." |
| 6 | Analyze failed service | "What is causing the issues in the EntityResourceImpl service." |
| 7–8 | Deep investigation | "I want a deep failure investigation across the frontend and astroshop services. For each service, show me the failure rate over the last 2 hours broken down by endpoint, then drill into the failure reasons (HTTP codes, exceptions, gRPC status). For any exceptions found, show me the top exception types with exemplar trace IDs so I can drill in. Also show me the downstream database calls from product-catalog (PostgreSQL) and cart (Redis), using proper extrapolation for aggregated spans – and flag any that look unusually slow at p99. Finally, find multiservice traces involving more than 3 services and show me the entry endpoint and full chains." |
| 9 | Root-cause and user impact | "Choose the latest problem where astroshop-payment is the root-cause and do a deep root-cause and impact analysis on that problem and summarize the major findings on cause and real user impact in a short summary." |
| 10 | Agentic AI Real User Impact Assessment | "Choose the latest problem where astroshop-payment is the root-cause and do a deep real user impact analysis on that problem and summarize the major findings on real user impact in a short, executive summary." |
| 11 | Explain Causal Alert Reduction | "Choose the latest problem where astroshop-payment is the root-cause and do a deep analysis on that problem and summarize the major reasons why the single alert events were merged into the problem." |
| 12 | Expose and Repair Systemic Failures | "Check all the detected problems of the last 7 days and find systemic, recurring issues. Cluster those and give suggestions on how to avoid the continuous detection of those issue clusters." |
| 13 | Log pattern analysis 1 | "Check all the log patterns shown on the Kubernetes workload name 'payment'. Start with a summary table of the top 10 patterns, list the number of matches as well as the severity. Share details about the top 3 patterns and recommended follow-up actions." |
| 14 | Log pattern analysis 2 | "Compare yesterday's log patterns on Kubernetes workload named 'payment' with today's log patterns and identify newly discovered ones" |
| 15 | Log pattern analysis 3 | "Discover abnormal log patterns in context of the latest problem where the root cause was identified as astroshop-payment" |

Note: the `astroshop-payment` / `astroshop` / `frontend` demo entities recur throughout, consistent with the same demo-world already flagged in `medium-content-analysis.md` as worth standardizing on across content (Medium posts #1 and #5 use the same Astroshop demo app).

### Forecast & Prediction

| Slide | Title | Prompt |
|---|---|---|
| 17 | Forecast cluster health | "Will this cluster's CPU stay healthy" |
| 18 | Cloud fleet trending | "Is any cloud's fleet trending toward a CPU ceiling?" |
| 19 | Predict Service Load | "Identify the top 3 services in terms of load and give me a prediction for their response time in the next 24 hours. Summarize the prediction in a compact table showing the key findings." |
| 20 | Predicting Event Occurrences | "Count the number of occurrences of the error log 'Interface GigabitEthernet1/0/33, changed state to up' over the last 24 hours and give me a prediction of the next 2 hours." |

(Slide 20's prompt is identical to the example already recorded from Medium post #3 in `medium-content-analysis.md` — further cross-confirmation these are the same underlying demo material referenced across multiple sources.)

### Infrastructure

| Slide | Title | Prompt |
|---|---|---|
| 22 | Cost waste report | "Build a consolidated cost waste report. Find: (1) unattached EBS volumes with their sizes grouped by type; (2) stopped EC2 instances that still have volumes attached; (3) RDS cluster snapshots of type 'manual' that exist in the account." |
| 23 | Service Relationship | "Analyze service to service relationships for the astroshop-checkout service." |
| 24 | Log analysis | "Search logs for checkout, break the volume down by Kubernetes cluster" (follow-up: "Search logs for requestId and extract the request ID value from the raw message.") |
| 25 | Infra – everyday prompts | (screenshot only, no prompt text extracted) |
| 26 | Kubernetes everyday prompts | (screenshot only, no prompt text extracted) |

### AI Observability

*(Does not map to any of the five use-case groups — see note above.)*

| Slide | Title | Prompt |
|---|---|---|
| 28 | Failed evaluations | "Show me all failed evaluations for my app, including the evaluation name, score, and the question and answer that failed." |
| 29 | Token usage | "Which prompts and model versions are driving the most token usage and cost? Break it down by model and provider." |
| 30 | Failed LLM calls | "Which of my agents and LLM calls are failing most often, and why? Break the errors down by agent and exception type to separate real faults from normal control-flow, and show me how to drill into a specific failed run." |
| 31 | Health overview | "Give me a health overview of my AI application over the last 24 hours — request traffic and error rate, p95 latency by model, total token usage and the top cost drivers by model and provider, any failing or looping agents, blocked or truncated responses, and any failed quality evaluations. Flag anything anomalous and tell me what to investigate next." |
| 32 | Improve agent | "How to improve my AI agent based on the relevance evaluation results?" |

### Security

| Slide | Title | Prompt |
|---|---|---|
| 34 | Vulnerabilities | "How many vulnerabilities do I have" (follow-up: "What are the most vulnerable libraries") |
| 35 | Vulnerabilities | "Am I vulnerable to CVE-2025-55182?" (follow-up: "What are the related entities of this vulnerability") |
| 36 | Vulnerability summary | "Provide a detailed overview of the active security vulnerabilities and recommendations for remediation." |
| 37 | Security detections | "What security detections do I have?" |
| 38 | Compliance | "What are the top 5 compliance issues of dt-cloudbleed-kspm-lima?" |

### APM

| Slide | Title | Prompt |
|---|---|---|
| 40 | Process failure pattern | "I want to identify processes experiencing a cascading failure pattern — where both exception count AND timeout count are simultaneously elevated. For each process group, calculate what fraction of ERROR logs are 'exception' and what fraction are 'timeout'. List only the services where both fractions exceed 20% of their error logs, and rank them by combined anomaly score." |

### DEM (Digital Experience Monitoring)

| Slide | Title | Prompt |
|---|---|---|
| 42 | DEM | "Show me the slowest frontend requests and which backend service and host handled them" |

### Cost Intelligence / Optimize Cost

| Slide | Title | Prompt |
|---|---|---|
| 44 | Understand a cost spike | "I received a cost alert that my full-stack costs have increased. Can you check if you find anything notable?" (follow-ups: "Break that down by host group." / "Compare this week's full-stack usage with last week's") |
| 45–46 | Predict upcoming costs | "Based on my log ingest usage over the last 90 days, can you predict my next 30 days?" (follow-up: "Now show me the same forecast for the next 60 and 90 days.") |
| 47–48 | Optimize usage | "Looking at optimizing my log query usage — are there any queries duplicated by multiple users?" (follow-up: "Give me a short summary I can share with the team.") |

---

## Candidates already earmarked for Blog #1 (Agentic Analytics)

Per the decision recorded in `tasks.md` §1 (replacing the dropped Christoph proof points), these are the strongest pillar-1 (investigation depth) candidates — chosen because they demonstrate reasoning quality/breadth without requiring a specific number to land:

- **Slide 11 ("Explain Causal Alert Reduction")** — double-sourced: identical prompt pattern already published in Medium post #1. Safe, no verification risk, and a distinctive transparency angle few competitors market.
- **Slide 6 ("Analyze failed service")** and **slides 7–8 (deep multi-part investigation prompt)** — good for showing multi-step reasoning across services and downstream dependencies.
- **Slide 12 ("Expose and Repair Systemic Failures")** — matches Medium #1's "systemic, recurring issues" pattern; good breadth-of-reasoning proof.

---

## Open items

- The deck's screenshots were not reviewed in detail in this pass — only slide titles and prompt text were extracted. If a specific example needs its actual output/finding described (not just the prompt), the screenshots should be viewed directly, with the same "re-verify before use" caveat as any other numbers in this deck.
- Slides 25–26 ("Infra – everyday prompts," "Kubernetes everyday prompts") and slide 49 ("Template") had no prompt text extracted via text export — screenshot-only or placeholder content, would need direct visual review if needed.
- The deck is explicitly a **living document** ("we will regularly update this presentation with new prompts") — worth checking for a newer version before final publication of any blog that leans on it, since this copy is already flagged by the user as outdated.
