Agentic investigations just got a lot smarter

**When something breaks in production, you need to get from
\"something\'s wrong\" to \"here\'s why, and here\'s the fix\" --- fast.
The latest release of Assist and Dynatrace Intelligence makes that jump
shorter: sharper reasoning, Dynatrace expertise built in, and deeper
data intelligence on every investigation. Whether you\'re chatting with
Assist, running an autonomous agentic workflow, or connecting an
external agent through Model Context Protocol (MCP), the same upgraded
foundation runs through all of it.**

## Investigations, reimagined from the ground up

Production incidents don\'t wait for you to figure out where to look. A
latency spike might trace two hops upstream to a service you didn\'t
initially suspect. A log anomaly might only make sense in context of a
recent deployment and a shift in a downstream dependency. Following that
trail, correlating signals, holding the thread coherent, knowing when
the evidence is strong enough to act, is what separates a fast
resolution from a long one.

Dynatrace has the foundation for this:
[Grail](http://www.dynatrace.com/platform/grail) as a unified data store
across every signal type, Smartscape as a live map of your
environment\'s dependencies, and deep telemetry across every layer of
your stack. [This release
brings](https://docs.dynatrace.com/docs/shortlink/release-notes-saas-sprint-338#dynatrace-assist-gets-even-smarter-than-before)
a significantly improved reasoning engine that can follow that
dependency graph as far as the evidence leads, proprietary Dynatrace
expertise encoded into every investigation, and an interface that keeps
the thread alive as you work. The gap between \"something is wrong\" and
\"here\'s the root cause, here\'s the evidence, here\'s what to do\"
just got a lot shorter.

![](media/image1.png){width="6.5in" height="3.4791666666666665in"}

*Figure 1: See how the upgraded Assist reasons across complex
investigations.*

## AI that knows Dynatrace, not just AI

When a general-purpose model tries to analyze your environment, it
reasons from broad training and whatever context you hand it. That gets
you part of the way. What it can\'t give you is fluency in Dynatrace\'s
data structures, the investigation patterns of an experienced SRE, or
the ability to navigate
[Smartscape](http://www.dynatrace.com/platform/smartscape) topology the
way a practitioner would.

This release closes that gap in two ways.

### A reasoning engine built for complex investigations

The foundation model behind [Dynatrace
Assist](https://www.dynatrace.com/hub/detail/ask-davis-copilot/) (and
through it, every agentic workflow and MCP-connected agent) switches to
the latest model from Anthropic. The difference shows up most clearly in
exactly the situations that matter most during an incident: multi-step
reasoning that doesn\'t lose the thread, accurate tool use across a long
investigation, and the ability to follow a dependency graph upstream
without losing the context of where it started.

In practice, that means investigations go further before you have to
redirect them. An assisted investigation can trace a problem across
service boundaries without you re-explaining the context at each step.
An autonomous workflow can correlate signals across metrics, traces, and
logs and arrive at a remediation proposal grounded in actual evidence
from every step along the way. The model is the engine. Dynatrace is
what grounds it.

### Analytics that understand your data, not just your question

Asking a question in natural language and getting back a reliable answer
requires more than a capable reasoning model. It requires deep fluency
in how your data is actually structured: what your metrics mean, how
your logs are shaped, what a meaningful query looks like for a given
signal type.

Behind that experience is a purpose-built Dynatrace model, trained on
hundreds of thousands of real DQL queries. It has internalized the
structure of Dynatrace data the way a fluent practitioner would, not by
looking up examples, but by understanding the underlying patterns.

In zero-context scenarios (the hardest cases, where there\'s no guiding
example to retrieve) our custom model produces valid analytical queries
roughly 85% of the time, where leading general purpose models succeed
less than half the time. It returns answers two to three times faster
than previous implementations.

That capability now runs through Dynatrace Assist,
[Notebooks](https://www.dynatrace.com/hub/detail/notebooks/),
[Dashboards](https://www.dynatrace.com/hub/detail/dashboards), and the
[Dynatrace MCP
server](https://docs.dynatrace.com/docs/dynatrace-intelligence/dynatrace-mcp).
Ask a data question anywhere in Dynatrace, in natural language, and the
intelligence behind it is the same.

Together, these two model changes mean Dynatrace now brings proprietary,
environment specific intelligence to every investigation.

![](media/image2.png){width="6.5in" height="3.6506944444444445in"}

*Figure 2: Get all the answers you need, from a single prompt.*

## The investigation playbook, encoded

A more capable reasoning engine still needs to start from the right
place. This release adds a curated set of Dynatrace investigation
skills, encoding how experienced practitioners actually approach
problems, so every investigation starts from the right entry point
without you having to point it there. The skills cover advanced root
cause analysis, telemetry correlation, and hyperscaler-specific
observability across AWS, Azure, and Kubernetes, among others.

This matters equally whether you\'re working interactively in Assist, or
for autonomous agents, whether they run inside Dynatrace or connect via
MCP. In both cases, the investigation opens with the same structured
expertise a senior SRE would apply, not reasoning from scratch every
time.

Later this year, you\'ll be able to contribute your own skills alongside
ours. Your team\'s investigation patterns, the institutional knowledge
of how your specific environment behaves, will run through the same
engine. The expertise stops being \"what Dynatrace knows\" and becomes
\"what your team knows,\" compounding over time.

## From alert to root cause, reimagined

What you get: faster root cause identification with evidence-backed
remediation.

Sharper reasoning, encoded investigation expertise, and deeper data
intelligence: this release upgrades the intelligence layer behind every
investigation in Dynatrace. Assist gets smarter. Agentic workflows run
further. Agents connecting via MCP or [Dynatrace
CLI](https://www.dynatrace.com/news/blog/dtctl-the-dynatrace-observability-cli-thats-built-for-ai-agents-and-humans/)
start from the same playbook a senior SRE would. The path from alert to
remediation has never been shorter.

## Try it on your next incident

Enable agentic mode and put it to work on a real problem. Ask Assist
what\'s wrong: it reasons through the problem, calls Dynatrace tools,
applies curated expertise, and follows the dependency graph upstream as
far as the evidence leads. You stay in control; Assist does the
analytical heavy lifting, correlating signals, tracing root cause, and
proposing a remediation for your approval before applying it
autonomously.

All the new capabilities mentioned in this blog post are available with
[SaaS release
338](https://docs.dynatrace.com/docs/shortlink/release-notes-saas-sprint-338#dynatrace-assist-gets-even-smarter-than-before)
(May 2026). Do you have feedback or questions? Join the conversation in
the [Dynatrace Community](https://community.dynatrace.com/).
