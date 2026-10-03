# Dynatrace: An open platform

### Why we keep betting on open standards, and what it means for AI

**By:** [author TBD — drafted in Steve Tack's voice per outline decision]
**Tags:** Open source, AI, Agentic AI, Observability, Platform strategy

---

Most agentic and AI observability tools lock customers into vendor-specific formats. That's a bet enterprises are increasingly unwilling to make. In [The Pulse of Agentic AI 2026](https://www.dynatrace.com/info/reports/the-pulse-of-agentic-ai-in-2026/), Dynatrace's global survey of 919 senior leaders responsible for agentic AI development and deployment, 51% cited the technical challenge of managing and monitoring agents at scale as a top barrier to production. 45% said they lack clear rules for when agents can act autonomously and when a human has to step in. 42% have limited real-time visibility to trace or troubleshoot what an agent actually did.

Enterprises are moving into agentic AI faster than their data architecture can support it. The instrumentation layer chosen now, before most of this is even running in production, is the layer they'll be stuck with. Get it wrong, and every agent, every integration, and every future acquisition inherits the lock-in.

---

## The Dynatrace commitment: openness is how we scale our platform

Openness is how we scale our platform. Not a checkbox, not a defensive move against critics: a leadership position we've held for years.

Already a while back, we started backing the standards that would matter, before it was obvious they would.

In 2019, we built Keptn internally and donated it to the CNCF: event-driven orchestration for cloud-native delivery and operations, years before "agentic" was a word anyone used in this context.

We've held a governance seat on OpenTelemetry since before its tracing and metrics working groups even merged into the project.

And in 2022, we co-founded OpenFeature alongside LaunchDarkly, GitLab, Split, Flagsmith, and CloudBees, long before feature flagging had anything to do with AI agents deciding what to ship.

None of that was about claiming credit for being first. It was about building on ground truth our customers already trust, not a private version of it we alone control. That's why decisions made in 2019 and 2022 still hold up today. It's the same thinking behind what came next.

## One open platform, three signal types

*Headline variations, pick one:*
- One open platform, three signal types
- Three moves, one open platform
- Same platform, three new signal types
- 2026 so far: three moves, one open platform
- Same open platform, adding three new signal types

Earlier this year, in January 2026, we closed the acquisition of DevCycle, a feature management platform built natively on OpenFeature. Because it's OpenFeature-native, customers can run DevCycle or swap in any other OpenFeature-compliant system without re-instrumenting anything.

Later, in April, we closed the acquisition of Bindplane, a telemetry pipeline that acts as a control plane for data moving from the edge through to analytics. Bindplane built BDOT, the Bindplane Distribution of OpenTelemetry: an open-source collector, and the first distribution to implement OpAMP, the open protocol for managing collector fleets remotely at scale.

The collector stays backend-agnostic after the acquisition, routing telemetry to whichever vendors a customer already uses, not just Dynatrace.

In August, we announced our intent to acquire Arize, an AI-native evaluation and observability company behind Phoenix, an open-source platform for tracing model calls, tool use, and agent decisions during development. Arize created and maintains OpenInference, the open specification for AI and agent tracing built on top of OpenTelemetry, and that's the standard this acquisition extends.

Three different signal types, and one open platform underneath all of them. Each one plugs into the same underlying architecture and the same open standard we already helped build or now help steward, rather than running as a separate product beside the platform. That's the actual difference between an open platform and a stitched-together suite: the seams don't show up in the data model. They only show up in a press release.

That openness isn't charity. It's how a platform earns adoption in tools it doesn't own, and how a "one platform" claim becomes something customers can check for themselves instead of something they're asked to take on faith.

## Why an open platform matters

*Alternative intros, pick one:*
- Dynatrace customers benefit from an open platform in ways that show up long before anyone's talking about AI.
- The benefits of an open platform show up well before AI enters the conversation.
- None of this requires AI to pay off. Dynatrace customers get these benefits from an open platform today, whether or not an agent is involved.
- An open platform pays for itself long before agentic AI is even part of the conversation.

Dynatrace customers benefit from an open platform in ways that show up long before anyone's talking about AI.

- No re-instrumentation cost when you add or switch tools.
- No vendor lock-in. Instrumentation done once holds up regardless of which compliant tool sits behind it.
- Less agent and collector sprawl. BDOT alone can replace a fleet of vendor-specific collectors running in parallel.
- Future-proofing. These standards keep evolving, and we have a seat at the table shaping them, so customers aren't exposed when they do.

The market is already pricing this risk in. Grafana Labs' 2026 Observability Survey found that 37% of practitioners cite "freedom to switch vendors" as their top reason for adopting OpenTelemetry in the first place.

Add it up and it's one platform doing what would otherwise take three: fewer integrations to maintain, fewer teams to keep in sync, and none of it resets at the next tool boundary.

## The AI lakehouse: where open data becomes trusted context

Here's a link worth drawing out loud: agents can't infer missing context the way a person reading a dashboard can. The data reaching an agent has to already be connected, meaningful, and real-time, because there's no human in the loop to fill the gaps. And that data has to come from somewhere. Standardized, open instrumentation is the only way to get it in at the scale and speed agentic systems require. Proprietary formats create exactly the gaps agents can't fill in on their own.

Grail, our AI lakehouse, is the context engine this requires, and it's the same platform described above, not an adjacent product bundled alongside it. The open instrumentation layer and the AI lakehouse are one continuous architecture.

Five capabilities define it: data unity across all data types through real-time pipelines and more than 1,000 integrations; a semantic store that maps topology, dependencies, causality, and ownership; a context engine that keeps that map hydrated and queryable; trusted action through access control, lineage, and auditability; and AI economics, meaning less retrieval, fewer oversized prompts, and fewer wasted tool calls.

Open instrumentation is what actually gets exabyte-scale, standards-based data into that lakehouse in the first place. Without it, "1,000+ integrations" and real-time context don't happen. They're just numbers on a slide.

## One platform, two views: what it enables for developers and SREs

For developers, three kinds of agents map to the three standards described above, all running on the same platform rather than three separate tools. Coding agents work in OpenInference. Observability agents work in OpenTelemetry and BDOT. Deployment agents work in OpenFeature and DevCycle. One pass through the loop looks like this: a coding agent ships a fix, an observability agent triggers monitoring on it, a deployment agent rolls it out behind a flag.

For SREs, it's the same loop, the same platform, a different vantage point. The SRE sets the flag-flip risk policy up front. They get paged from the same telemetry the agents already triaged, not a separate, disconnected feed. And they review the agent's evaluation traces before trusting a change in production. Agents act. The SRE decides how much rope they get.

## The payoff: an open platform ready for the autonomous enterprise

Bring the three threads together and you get feature rollout state, infrastructure telemetry, and AI and agent behavior, all reasoned over in one context layer instead of three disconnected tools and three disconnected teams.

Because it's one open platform and not a stitched-together suite, the loop can actually close. Agents can act, not just report, and that's what an autonomous enterprise requires. A collection of point tools can surface insight. Only one connected platform can safely act on it.

Trust in that action comes from data lineage carried through from open instrumentation, not from taking an agent's word for it. This is what makes the autonomous enterprise trustworthy, not just powerful.

## Closing

None of this works without the communities that built the standards underneath it. OpenFeature, OpenTelemetry and the BDOT collector, and OpenInference weren't ours to begin with, and openness only means something if we keep contributing to them rather than just benefiting from them. The commitment: keep contributing to OpenTelemetry and OpenFeature, and steward OpenInference the way Arize has. Nothing changes immediately for customers, partners, or community members.

We didn't set out to acquire three companies. We set out to make sure whatever powers the next decade of autonomous operations speaks a language no one vendor owns.

---

*This post contains forward-looking statements regarding the proposed acquisition of Arize, including anticipated benefits, timing, and Dynatrace's plans regarding OpenInference and Phoenix. The acquisition is subject to customary closing conditions, including regulatory approvals, and there is no assurance it will be completed on the terms described, or at all.*
