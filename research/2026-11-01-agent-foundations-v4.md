# Research Report: Agent Evolution and Production Foundations

**Date:** 2026-11-01
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** agent-foundations-v4
**Sources consulted:** 16 Microsoft Learn pages, 0 other official Microsoft pages, 0 GitHub repositories, 0 code samples
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Reference count:** 16 unique official documentation pages. Searches, repeated citations, and read-only local inputs are not additional references.

**Assignment:** agent-foundations-v4, orchestrated Create mode, binding brief_version: 15.
**Review state:** Prepared for caller-managed first canonical overall R1, cycle 0/3. No review or approval verdict issued.
**Evidence currency:** All 16 referenced pages were fetched in full during this invocation on 2026-11-01. Large responses were inspected in relevant ranges. Retrieval dates are not publication dates, feature-launch dates, or runtime validation.
**Required-capability preflight:** Topic-relevant documentation search succeeded, followed by a meaningful full-document fetch of *Single agent or multiple agents* [R03]. No recovery retry or substitute research service was needed.
**Scope:** Conceptual opening and seven introductory foundations for the supplied v4 storyboard. This is an evidence report, not presentation content, a script, artwork, or a build. Forty minutes total is flexible guidance, with nominal 35-minute content and five-minute closing/Q&A metadata. No demos, code examples, setup tutorial, or pricing matrix.
**Ownership:** Approved unchanged facts are reused from the foundations, Foundry, and security/governance reports listed in section 5. Current named harness identity/history, GitHub productivity surfaces, and Foundry/model-choice deltas remain with authoring-options-v4. Quantitative chart and performance trends remain with metr-task-horizons-v4. No named IQ deltas or logo conclusions are introduced.

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Evolution Framing and the Requested Headline](#2-evolution-framing-and-the-requested-headline)
3. [Seven Foundations: Definitions and Essential Points](#3-seven-foundations-definitions-and-essential-points)
4. [Controls and Governance: Four-Service Alignment](#4-controls-and-governance-four-service-alignment)
5. [Approved Evidence Reuse and Deployment Caveats](#5-approved-evidence-reuse-and-deployment-caveats)
6. [Research Limitations and Reviewer Handoff](#6-research-limitations-and-reviewer-handoff)
7. [Complete Reference List](#7-complete-reference-list)

## 1. Executive Summary

- **Teach a conceptual progression, without years:** answer-first chatbot → task-performing agent → multiple specialized agents → a coordinated agentic system. The final step emphasizes their operation as one accountable process, not a separate Microsoft architecture category or a successor that makes single agents obsolete. Microsoft recommends the least complex architecture that reliably satisfies the task. [R01], [R03], [R04]
- **A capable model is necessary for its assigned task, but not sufficient for production success.** Context, tools, state, dependable dependencies, evaluation, authorized actions, ownership, and recovery all require deliberate design. The evidence establishes these requirements, not a universal ranking of bottlenecks or a finding that model limitations have disappeared. [R02], [R06], [R08], [R09]
- **Retaining the requested bottleneck headline requires an explicit production-readiness scope and thesis interpretation.** A concise proposed scope is “Production readiness, once the model meets the task’s needs.” Any added qualifier or changed wording must be a disclosed content decision, not a silent replacement of the user's supplied text. [R02], [R07], [R08], [R09]
- **The seven foundations are a teaching synthesis, not seven isolated components.** Harnesses can implement orchestration, telemetry, and approval handling. Governance cuts across the lifecycle. The car mapping is the user's analogy, not architectural evidence. The corresponding technical responsibilities have official support. [R01], [R02], [R05], [R06], [R09]
- **Entra, Purview, Defender, and Agent 365 retain their approved complementary roles.** Neither an agent identity, a registry entry, nor a protocol/feature name establishes identical protection across products and routes. Policy targeting, source permissions, onboarding, supported interactions, and audit-versus-block configuration remain material. [R10]–[R14], [R16]

## 2. Evolution Framing and the Requested Headline

### An evidence-backed progression, not a release timeline

The following is an explanatory synthesis for the evolution opening. “Chatbot” names the answer-first starting illustration here, not a claim that every chat interface lacks tools or that agents cannot answer questions. Microsoft's documented spectrum is direct model calls, single agents with tools, and multiagent orchestration. Its adoption guidance also includes information-retrieval agents, so “answers versus actions” is a useful emphasis rather than an exhaustive definition. [R01], [R04]

| Requested stage | Concise meaning for the opening | Essential distinction |
|---|---|---|
| **Chatbot** | A conversational starting point that responds to a person's question. | Illustrate an answer-first interaction, not a universal restriction on all chatbots. A direct model call can be enough for a bounded, single-step task. [R01], [R04] |
| **Agent** | Software that uses a model, instructions, context, and tools to work toward a task. | It can choose knowledge or tools and proceed through multiple steps. Autonomy is bounded by system design and permissions, not permission to do anything. [R01], [R02], [R09] |
| **Multiple agents** | Specialized agents divide responsibilities. | Separation can serve distinct domains, teams, or security boundaries, but adds handoffs, state management, cost, and failure modes. [R03], [R04] |
| **Coordinated agentic system** | Agents, tools, workflow logic, and people operate together toward an end-to-end outcome. | Emphasize routing, context sharing, validation, human checkpoints, and recovery. Multiagent systems already require coordination, so this is a zoom-out on the system, not a fourth standardized architecture level. [R02]–[R04] |

> “Use the lowest level of complexity that reliably meets your requirements.”
> - Source: [AI agent orchestration patterns][R04]

**No years are proposed.** Retrieved architecture guidance supports capability distinctions and decision criteria, not the dates when each stage began or universally replaced its predecessor. More agents are not inherently better: test a single-agent approach unless requirements justify separation. Distinct planner/reviewer roles alone do not establish the need for separate agents. [R03], [R04]

**Dog-years wording:** The supplied “AI years are like dog years. Two years feel like ten.” is a metaphor for perceived pace. It is not a numerical acceleration ratio, a dated chronology, or a conclusion derived from the neighboring chart. This is the binding brief's rhetorical treatment, not a research finding.

### Assessment of the exact bottleneck headline

**Requested text, preserved for the caller:** “Model capability is no longer the bottleneck. Management, context, governance and security are.”

**Assessment: defensible as a scoped production-readiness thesis, not as universal proof.** Microsoft requires task-fit model validation, explicitly documents inaccurate answers despite grounding, and directs teams to find bottlenecks across models, retrieval, orchestration, dependencies, and the user experience. These sources do not establish that model capability has ceased to constrain all tasks, or that the four named factors are always the limiting constraints. [R02], [R07], [R08]

**If retained, add an explicit concise scope:** “Production readiness, once the model meets the task’s needs.” Keep the supplied two sentences and their requested reveal order intact only as a rhetorical shift of attention under that scope. Notes should explain that this is not an empirical bottleneck ranking, that infrastructure and orchestration also matter, and that model adequacy must be evaluated for the actual task. Adding this scope is a recommendation requiring a disclosed caller/content-owner decision. [R02], [R04], [R08], [R09]

**If a literal factual claim is required instead of a scoped thesis, proposed fallback:** “Model capability alone does not establish production success. Management, context, governance and security matter too.” This is closer to the retrieved evidence, but changes the user's wording and must not be substituted silently. Nothing in this report derives either formulation from METR, establishes a percentage of production failures, or asserts that models are never the bottleneck. [R02], [R06]–[R09]

The strongest supporting security framing is a question about authorized operation, rather than a claim that all models are now sufficient:

> “As organizations adopt agentic AI, the security question shifts from whether an agent can complete a task to whether it should be allowed to perform each action, against which resources, and under whose authority.”
> - Source: [Least privilege for AI agents (agentic identities + RBAC)][R09]

## 3. Seven Foundations: Definitions and Essential Points

These are concise research definitions and essential points for later minimal conversion into one slide per foundation, not completed slide copy. **Analogy mapping supplied by the user:** motor=model, chassis=harness, gauge=observability, wheels=grounding, roads=infrastructure, lights=orchestration, signs=controls, checkpoint=governance. Eight mapped parts serve seven foundations because controls and governance share one foundation. The analogy does not define component boundaries, deployment topology, or Microsoft product taxonomy.

### 3.1 Model — motor

**Definition:** The AI component that interprets input and provides generation or reasoning capabilities for the task. In an agent, it works with instructions, knowledge, tools, and state rather than constituting the entire solution. [R01], [R02]

- Match capabilities to the job and validate with representative tasks and data. [R02], [R06]
- The most capable or largest model is not automatically the appropriate choice for every step. [R02], [R04]
- Evaluate the complete outcome, not only an isolated model response. [R06], [R08]

**Boundary:** Model-choice freedom is task-fit choice among supported options, not a promise that every model runs in every product or supports every tool. No new model catalog, version, named routing option, or availability comparison is supplied here. Those deltas remain with authoring-options-v4. [R02], [R15]

### 3.2 Harness / runtime scaffolding — chassis

**Definition:** The surrounding software that makes a model usable as a working agent: it drives model/tool calls, maintains context and conversation state, handles approvals, and supports progress through a multistep task. [R05]

> “An *agent harness*, sometimes called an *AI harness*, is the runtime scaffolding that turns a language model into an agent that can perform work.”
> - Source: [Agent Harness][R05]

- Connect the model to instructions, available tools, and the current task state. [R01], [R05]
- Manage the execution loop and preserve enough context to continue work. [R04], [R05]
- Make approval handling and execution limits deliberate rather than assuming unrestricted autonomy. [R04], [R05], [R09]

**Boundary:** This is the generic definition only. The cited implementation's defaults are not universal harness requirements or guarantees. A harness is software behavior, not merely compute hosting, and a named framework/harness example or its history must come from authoring-options-v4. [R05], [R08]

### 3.3 Observability: evaluate, trace, monitor — gauge

**Definition:** The ability to measure, understand, and troubleshoot model and agent behavior throughout development and operation. Evaluation, tracing, and monitoring answer complementary questions. [R06]

- **Evaluate:** Does the outcome meet quality, safety, and task-completion criteria? Test before deployment and reevaluate changes. [R02], [R06]
- **Trace:** Which model calls, tool invocations, dependencies, and handoffs occurred? Use execution evidence to diagnose failures. [R04], [R06]
- **Monitor:** Are quality and operational health holding up over time? Watch latency, errors, usage, and quality signals with actionable alerts. [R02], [R06]

**Boundary:** Traces are execution telemetry, not guaranteed access to every internal model reasoning step. A quality score or a green dashboard is not certification of every future outcome. Govern captured conversations and outputs as potentially sensitive data. Product-specific observability status remains in section 5, not audience captions. [R06], [R08], [R15]

### 3.4 Data grounding — wheels

**Definition:** Supplying relevant information and business context to the model so it can answer or act using the organization's information, rather than relying only on learned knowledge. Retrieval-augmented generation (RAG) is one pattern: retrieve relevant content and include it in the model input. [R01], [R07]

- Use relevant, high-quality sources and an update process appropriate to the job. [R02], [R07], [R08]
- Retrieve only information authorized for the actual user or agent. Grounding itself grants no access rights. [R07], [R09], [R11]
- Preserve useful source references and test retrieval quality as well as the final answer. [R06], [R07]

**Boundary:** Grounded does not mean guaranteed correct. Irrelevant, incomplete, or malicious retrieved content can still produce unsafe or inaccurate results. Treat retrieved content as untrusted input and enforce access during retrieval. No substantive new IQ claims are introduced. [R07], [R09]

### 3.5 Reliable production infrastructure — roads

**Definition:** The hosting, storage, network, and dependent services that keep the end-to-end application available, responsive, and recoverable in real use. Reliability is a property of the whole workload, not just its model endpoint. [R04], [R08]

- Plan capacity and test realistic load across the model, retrieval, tools, and application dependencies. [R04], [R08]
- Handle failures explicitly with timeouts, appropriate retries, and graceful degradation instead of hiding errors. [R04], [R08]
- Preserve progress where needed and test recovery from interruptions. [R04], [R08]

**Boundary:** Managed services reduce operational burden but do not eliminate end-to-end design, testing, or customer-owned integration responsibilities. Do not promise universal private networking, unlimited capacity, or a cross-product SLA. The technical emphasis here is dependable operation, not Azure resource scaffolding or a hosting-product recommendation. [R08], [R15]

### 3.6 Agent orchestration — lights

**Definition:** Coordination of who does what, in what order, with what context, and how results are combined or passed on. It can structure a single agent's work or coordinate multiple agents and deterministic workflow steps. [R02]–[R04]

- Use a sequence for dependent steps, parallel work for independent steps, and handoffs when a different specialist should take over. [R04]
- Define context/state transfers, completion conditions, output validation, and escalation to people. [R03], [R04]
- Choose the simplest coordination that meets the requirements and measure the whole process. [R03], [R04]

**Boundary:** Orchestration is not synonymous with multiple agents, a protocol, or fully autonomous operation. A deterministic workflow can control routing while agent outputs remain nondeterministic. Added agents can increase latency, cost, context growth, and failure points rather than improve the result. [R03], [R04]

### 3.7 Controls and governance — signs and checkpoint

**Definition:** **Controls** are the enforced boundaries on access, data use, tools, and actions. **Governance** establishes purpose, accountable ownership, policies, reviews, and lifecycle oversight for those boundaries. Both apply before, during, and after execution, not only at one final checkpoint. [R02], [R09], [R16]

- Define the permitted job, accountable owner, approved data, and allowed actions. [R02], [R09]
- Apply least privilege and appropriate approval gates, and validate authorization in downstream systems. Instructions guide behavior but do not replace enforced access checks. [R02], [R09], [R11]
- Keep an audit trail, review changes and access, and test stopping or revoking the agent when necessary. [R09], [R14]

**Four-service awareness:** Entra supplies identity/access capabilities, Purview data protection/compliance capabilities, Defender threat protection, and Agent 365 centralized oversight through complementary services. This is not one universal security switch or a claim that one policy/license provides identical protection everywhere. [R10]–[R14], [R16]

## 4. Controls and Governance: Four-Service Alignment

Reuse the approved security/governance roles without adding a deep dive. The following qualifications are provenance/speaker-note material. They should not become an exhaustive feature matrix on the foundation slide. [R10], [R16]

| Service | Plain-language responsibility | Material boundary to retain |
|---|---|---|
| **Microsoft Entra** | Establish who the agent is and control access. | Conditional Access evaluates the actual token subject and target resource. Delegated user access, agent identity, and agent-user access require appropriate targeting. API-key paths bypass this Entra token pipeline. [R11] |
| **Microsoft Purview** | Protect data and support compliance. | Agent 365-specific controls require documented sharing and policy scope. New Agent 365 content does not inherit source sensitivity labels. A supported audit interaction is not proof of an equivalent DLP blocking interaction. [R12] |
| **Microsoft Defender** | Detect threats and protect supported runtime interactions. | Default cloud runtime rules audit rather than block. Custom rules provide scoped blocking, and coverage depends on supported routes, tools, and onboarding. [R13] |
| **Microsoft Agent 365** | Observe, govern, and secure the agent environment through centralized oversight and complementary controls. | The registry can include unmanaged agents without Agent 365 risk protection/observability. Onboarding guidance warns that policies or protections might not be enabled. Visibility is not proof of enforcement. [R14], [R16] |

**Feature/protocol names do not imply universal control parity.** “Uses MCP,” “connects agents,” “registered,” and “has an agent identity” do not establish the effective permission, the inspected interaction, or the blocking outcome. Verify each path from orchestrator to tool to downstream system. Entra's API-key exclusion, Purview's different audit/DLP scopes, Defender's unsupported-tool exclusion, and Agent 365's unmanaged inventory are concrete counterexamples to automatic parity. [R09], [R11]–[R14]

## 5. Approved Evidence Reuse and Deployment Caveats

### Read-only baseline reused, not reassigned

| Approved local report | Unchanged findings reused here | Underlying official references |
|---|---|---|
| `research\2026-10-30-ai-ecosystem-foundations.md` | Agent components, task-fit model evaluation, governed knowledge/tools/memory, least privilege, traceability, and revocation. No IQ deltas. | [R01], [R02], [R09] |
| `research\2026-10-30-foundry.md` | Evaluate/trace/monitor distinction and feature-specific availability. No changed authoring/catalog claims. | [R06], [R15] |
| `research\2026-10-31-agent-security-governance.md` | Four complementary roles, actual-principal policy targeting, explicit sharing/policy scope, audit versus blocking, and registry visibility versus enforcement. | [R10]–[R14], [R16] |

Eleven cited pages underpin reused baseline facts. Five additional pages supply the single/multi-agent decision guidance, orchestration patterns, generic harness definition, RAG limitations, and AI workload reliability principles: [R03]–[R05], [R07], [R08]. All 16 were retrieved independently in this invocation. This is targeted foundation research, not a rerun of the approved product, IQ, or security surveys.

### Material feature status, notes only — retrieved 2026-11-01

- **Foundry observability:** The readiness table lists evaluations GA with some evaluators/features preview, tracing GA for prompt/hosted agents with workflow/external-agent tracing preview, and monitoring preview. It also lists agent guardrails preview. Teaching evaluation/tracing/monitoring as principles must not imply uniform GA or coverage in every product. These unchanged distinctions belong in notes/provenance. [R15]
- **Defender runtime routes:** The runtime guide explicitly identifies Copilot Studio and Foundry routes as preview. Other supported routes have their own coverage conditions. No whole-service or all-route GA inference is made. [R13]
- **Agent 365:** Its overview explicitly states Commercial general availability from May 1, 2026 and per-user licensing. This does not establish every constituent control's GA, tenant enablement, or universal agent coverage. Updated registry risk details are rolling out gradually by region. [R14], [R16]
- **Harness terminology:** The generic definition is supported, but the source's capability matrix distinguishes defaults, optional capabilities, language differences, and experimental additions. No implementation-wide status or uniform default is transferred to the generic foundation, and no named current harness recommendation is made. [R05]

### Getting started, pricing, limits, quotas, and regions

**N/A — Detailed setup, API usage, pricing, and licensing/region matrices are outside this introductory/no-code-example assignment.** For implementation planning, the essential checks are task-fit evaluation, appropriate identity/policy scope, supported feature paths, capacity under real load, and recovery. Actual limits and regional availability must be checked for the selected model, service, and route rather than inferred from the ecosystem or analogy. [R02], [R04], [R08], [R11], [R15]

## 6. Research Limitations and Reviewer Handoff

1. **Chronology not established:** No launch-year labels or historical era boundaries are proposed. The progression is a teaching synthesis. “Coordinated agentic system” emphasizes end-to-end operation rather than identifying a separately dated Microsoft architecture category. [R01], [R03], [R04]
2. **Bottleneck ranking not established:** Official guidance supports necessary production responsibilities, not “models are never the bottleneck” or a quantitative ranking of failure causes. The content owner must explicitly resolve retention-with-scope versus the proposed factual fallback. Chart data, trend interpretation, and quantitative comparisons are intentionally excluded. [R02], [R07], [R08]
3. **Broad overview language is materially qualified:** The Agent 365 security overview says agents inherit/honor labels, while the specialist Purview page explicitly says newly created Agent 365 content does not inherit source labels. Likewise, broad “every agent” protection language does not override registry, policy, and runtime coverage limitations. Prefer specialist interaction-specific guidance, as the approved security report already does. This report preserves the conflict rather than claiming universal inheritance/protection. [R10], [R12]–[R14], [R16]
4. **Conceptual pattern guidance is not a named implementation recommendation:** Generic workflows and harnesses remain useful concepts. Broad CAF build guidance links visual Foundry workflows, but the feature-readiness source explicitly records their preview status and December 1, 2026 retirement. No new-development recommendation for that named feature is made here. Current named implementation identity/history stays with authoring-options-v4. [R02], [R05], [R15]
5. **Documentation currency is retrieval-based:** No independent source modification timestamps were extracted, and report filenames are not treated as evidence of currency. No cited full-document retrieval was unavailable. No tenant configuration, protection, integration, regional deployment, service health, or measured business outcome was tested.
6. **Intentional exclusions:** No METR claims, model-release chronology/catalog deltas, GitHub productivity deltas, new IQ comparisons, logo/rights findings, pricing tutorial, code samples, or visual artifacts. The transportation and dog-years metaphors supply no empirical evidence. Existing approved owner caveats remain intact.
7. **Paired-review focus:** Check the load-bearing definitions, progression/category caveat, headline scope, seven-foundation coverage with eight-part analogy, and four-service boundary fidelity. Minor aesthetic or template preferences are not research findings. This report issues no reviewer verdict and does not authorize content promotion.

**Caller-managed review target:** `[local-user]\OneDrive - Microsoft\Desktop\Repositories\20261030_Microsoft_AI_ecosystem\agent-reviews\2026-11-01-ms-docs-research-reviewer-agent-foundations-v4.md`. This report is ready for that first independent review, not self-approved.

## 7. Complete Reference List

### Microsoft Learn Documentation — 16 pages

All entries were fetched in full on **2026-11-01**. The baseline/new labels describe claim reuse, not a page's publication or release date. Search-only discoveries are not counted or used as final evidence.

| ID | Official full-document citation | Evidence used / status |
|---|---|---|
| R01 | [AI agent adoption][R01] | Model, instructions, retrieval, actions, memory, agent categories. Baseline reused. |
| R02 | [Process to build agents across your organization][R02] | Task-fit model strategy, charters, instructions, knowledge/tools/state, evaluation, controls. Baseline reused. |
| R03 | [Single agent or multiple agents][R03] | Decision criteria, specialization, overhead, single-agent testing, workflow coordination. Added conceptual evidence and MCP preflight fetch. |
| R04 | [AI agent orchestration patterns][R04] | Complexity spectrum, sequences/parallelism/handoffs, context, reliability, human participation. Added conceptual evidence. |
| R05 | [Agent Harness][R05] | Generic runtime-scaffolding definition, boundaries between composition and implementation-specific capabilities. Added definition only. |
| R06 | [Observability in generative AI][R06] | Evaluation, tracing, monitoring, lifecycle and quality/task measures. Baseline reused. |
| R07 | [Retrieval augmented generation (RAG) and indexes][R07] | Grounding flow, access controls, untrusted retrieved input, inaccuracies despite grounding. Added conceptual evidence. |
| R08 | [Design principles for AI workloads on Azure][R08] | End-to-end reliability, dependent components, capacity, recovery, operations and bottleneck evaluation. Added conceptual evidence. |
| R09 | [Least privilege for AI agents (agentic identities + RBAC)][R09] | Authorized actions, named ownership, least privilege, downstream checks, audit and revocation. Baseline reused. |
| R10 | [Secure AI agents at scale using Microsoft Agent 365][R10] | Complementary services, distributed security/central visibility, broad language qualified by specialist pages. Baseline reused. |
| R11 | [Conditional Access for agents][R11] | Token subjects, policy targeting and resource/API-key boundaries. Baseline reused. |
| R12 | [Use Microsoft Purview to manage data security & compliance for Microsoft Agent 365][R12] | Explicit sharing, policy inclusion, label noninheritance, audit/DLP scope distinctions. Baseline reused. |
| R13 | [Protect AI agents in real time using Microsoft Defender][R13] | Supported runtime routes, previews, onboarding, default audit and configured blocking. Baseline reused. |
| R14 | [Manage agent registry in Microsoft 365 admin center][R14] | Unmanaged inventory, owner gaps, protections not necessarily enabled, regional risk-detail rollout. Baseline reused. |
| R15 | [Microsoft Foundry portal general availability overview][R15] | Feature-specific observability/guardrail statuses and workflow retirement caveat. Baseline reused. |
| R16 | [Overview of Microsoft Agent 365][R16] | Observe/govern/secure roles, Commercial GA date, per-user licensing and bounded overview interpretation. Baseline reused. |

### Other Official Microsoft Sources — 0

N/A — Microsoft Learn provided the required evidence. No secondary web source was used.

### Official Microsoft GitHub Repositories — 0

N/A — No repository was independently consulted. Links inside documentation are not counted as consulted repositories.

### Code Samples — 0

N/A — No commands or code examples are produced. Code-sample search is not applicable to this introductory conceptual assignment.

[R01]: https://learn.microsoft.com/azure/cloud-adoption-framework/ai-agents/
[R02]: https://learn.microsoft.com/azure/cloud-adoption-framework/ai-agents/build-secure-process
[R03]: https://learn.microsoft.com/azure/cloud-adoption-framework/ai-agents/single-agent-multiple-agents
[R04]: https://learn.microsoft.com/azure/architecture/ai-ml/guide/ai-agent-design-patterns
[R05]: https://learn.microsoft.com/agent-framework/concepts/harness
[R06]: https://learn.microsoft.com/azure/foundry/concepts/observability
[R07]: https://learn.microsoft.com/azure/foundry/concepts/retrieval-augmented-generation
[R08]: https://learn.microsoft.com/azure/well-architected/ai/design-principles
[R09]: https://learn.microsoft.com/security/zero-trust/sfi/least-privilege-for-ai-agents
[R10]: https://learn.microsoft.com/security/security-for-ai/agent-365-security
[R11]: https://learn.microsoft.com/entra/identity/conditional-access/agent-id
[R12]: https://learn.microsoft.com/purview/ai-agent-365
[R13]: https://learn.microsoft.com/defender-xdr/security-for-ai/ai-agent-real-time-protection
[R14]: https://learn.microsoft.com/microsoft-agent-365/admin/agent-registry-overview
[R15]: https://learn.microsoft.com/azure/foundry/concepts/general-availability
[R16]: https://learn.microsoft.com/microsoft-agent-365/overview
