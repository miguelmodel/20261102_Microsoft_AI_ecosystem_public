# Research Report: Microsoft Copilot Studio for Agent Authoring and Customization

**Date:** 2026-10-30
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** copilot-studio
**Sources consulted:** 41 Microsoft Learn pages, 0 GitHub repositories, 0 code samples
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Reference count:** 41 unique official documentation pages; metadata retrieval of the same pages is not counted again.
**Assignment:** copilot-studio; Revise mode; brief_version 3; revised for next valid overall review round 2, active cycle cap 3.
**Review state:** Canonical R1 NEEDS REWORK is the first counted review. Revised for caller-managed R2; post-revision lint/review has not run. This report is not self-approved.

## Scope and evidence conventions

This is research for an introductory customer session of 30 minutes plus five minutes of Q&A, not presentation content. It covers Copilot Studio's non-IQ capabilities, documented integrations, and product-specific boundaries. It intentionally excludes setup instructions, code, API walkthroughs, pricing tables, slides, and demos. Substantive Work IQ, Fabric IQ, and Foundry IQ claims are deferred to the ecosystem-foundations owner; no approved owner evidence was supplied.

All references were retrieved on **2026-10-30** through Microsoft Learn full-document fetch. Searches identified sources; snippets alone are not evidence for the conclusions. Official page HTML supplemented Learn retrieval only to capture publisher metadata. Reference dates below are the pages' `ms.date` values, not assumed launch dates; release milestones are separately attributed.

**Status vocabulary:** **GA** means an explicit feature-level general-availability statement; **documented shipping** means current operational documentation describes available functionality, without independent confirmation of a formal GA milestone; **preview** retains Microsoft's exact qualification; **announcement/planned** is not treated as available; **unknown** identifies an unresolved status or availability question. Tenant rollout is not guaranteed by documentation: Microsoft says releases roll out over several days. [R05]

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Overview, Audience, and Starting-Point Decisions](#2-overview-audience-and-starting-point-decisions)
3. [Authoring, Knowledge, and Actions](#3-authoring-knowledge-and-actions)
4. [Publishing and Channel Boundaries](#4-publishing-and-channel-boundaries)
5. [Testing, Evaluation, and Management](#5-testing-evaluation-and-management)
6. [Product-Specific Security and Governance](#6-product-specific-security-and-governance)
7. [Documented Integrations and Customer Examples](#7-documented-integrations-and-customer-examples)
8. [Feature-Level Availability Register](#8-feature-level-availability-register)
9. [Commercial, Capacity, and Regional Boundaries](#9-commercial-capacity-and-regional-boundaries)
10. [Research Limitations and Cross-Owner Handoff](#10-research-limitations-and-cross-owner-handoff)
11. [Complete Reference List](#11-complete-reference-list)

## 1. Executive Summary

**Microsoft Copilot Studio is a graphical, low-code studio for building and managing agents and workflows.** It serves business makers and professional developers working with organizational data, business systems, and internal or external audiences. Low-code does not mean business-user-only: the standard-harness Visual Studio Code extension is GA and supports local agent-definition editing, coding-assistant use, and Git/pull-request review. Customization does not require moving every part of a solution into a different product. [R01][R11][R21][R35][R05]

**Choose by the customer's required capabilities, not a mandatory product progression.** Microsoft's current decision guide recommends evaluating Copilot Studio for external channels, external-service actions, workflow logic, or structured lifecycle management. Agent Builder can remain appropriate for supported Microsoft 365 scenarios, including organizational distribution; audience size alone does not require Copilot Studio. Copying an Agent Builder agent into Copilot Studio is optional and creates an independent snapshot, not a synchronized upgrade. [R02][R24]

**The important current caveat is experience-specific support.** Documentation now distinguishes the standard harness, the GitHub Copilot harness, and the Customer Conversation harness. A harness is the runtime that coordinates model calls and tools. These choices do not have identical authoring, channels, authentication, evaluation, or billing. The new GitHub Copilot harness experience has a June 2026 **production-ready preview** milestone; the Customer Conversation overview is explicitly **preview**. Do not describe every Copilot Studio feature as GA. [R03][R04][R05][R06]

**Grounding and integration are useful but not guarantees.** Connected knowledge can support contextual answers; tools can read or change business-system data. The implementation still needs permissions, credential choices, channel validation, evaluation, and operational ownership. Standard-harness A2A connected agents have GA evidence, while the named standard-harness Foundry, Fabric data-agent, and Microsoft 365 Agents SDK connections have their own preview evidence. These are specific routes, not universal agent interoperability or portable governance. [R09][R11][R12][R23][R05][R25][R26][R36][R38]

## 2. Overview, Audience, and Starting-Point Decisions

### Who it serves

| Customer need | Copilot Studio fit | Important qualification |
|---|---|---|
| A business team wants an assistant for a focused process | Graphical authoring, instructions, knowledge, topics where supported, and reusable tools can combine conversation with business operations. [R01][R07][R11] | Information quality, data access, and operational ownership still require deliberate design. [R09][R12][R21] |
| A developer or integration team must connect enterprise systems | Prebuilt/custom connectors, API-based tools, automation, the standard-harness VS Code extension, and connected-agent routes provide extension points. [R11][R21][R35][R36][R38] | Authoring-tool GA does not make every integration GA. Each route, credential method, environment policy, and selected experience must support the intended operation. [R05][R12][R23][R25] |
| An organization wants an employee-facing agent in Microsoft 365 or Teams | A published agent can be distributed through supported Microsoft channels. [R15][R17] | Publishing, sharing, installation, and catalog approval are separate concerns; a channel is not a blanket grant of data access. [R15] |
| A customer-service team wants a public-facing assistant | Website channels and service-system tools support customer-facing scenarios; the Customer Conversation harness targets voice/chat and escalation. [R14][R06] | Channel and authentication support differ by harness; the Customer Conversation experience is preview. [R06][R17] |

### Runtime terminology that matters

- **Standard harness:** The established agent experience supports authored topics and both classic and generative orchestration. Despite the high-level harness overview's rule-based positioning, the detailed feature documentation says new standard agents default to **generative orchestration**, subject to prebuilt-agent configuration and administrator policy. It would be inaccurate to call all standard agents fixed scripts. [R03][R07]
- **GitHub Copilot harness:** A natural-language-first Copilot Studio authoring/runtime experience for reasoning-heavy, multistep work. Its feature comparison documents differences from standard agents, including unsupported channels and authentication options. The name does **not** mean the agent runs in the GitHub Copilot service. [R03][R04]
- **Customer Conversation harness:** A preview experience for voice/chat customer interactions, with a primary agent, specialist sub-agents, and escalation paths. The documentation calls an agent built on this harness a **Customer Assist Agent**. [R06]

> "The GitHub Copilot harness is a Microsoft Copilot Studio authoring and orchestration framework, not the GitHub Copilot service."
> - Source: [Harnesses in Copilot Studio][R03]

### Decision inputs, not a setup checklist

A useful customer assessment identifies the audience and channel, approved knowledge, operations the agent may perform, whose credentials those operations use, required human involvement, and who will monitor and update the solution. Environment access and licensing must be checked separately from end-user access. These are selection and readiness questions, not a requirement to use every ecosystem layer. [R02][R12][R14][R21][R29]

## 3. Authoring, Knowledge, and Actions

### Authoring and customization

In the standard experience, **topics** are designed portions of a conversation. Classic orchestration selects a topic from trigger phrases; generative orchestration can choose and combine topics, tools, knowledge, and other agents using their descriptions and context. Authors can retain explicit business logic while using generative behavior where useful. Clear, differentiated descriptions and instructions matter because overlapping descriptions can make selection unpredictable. [R07]

The GitHub Copilot harness instead brings instructions, knowledge, tools, model choice, and other components into a Build surface with natural-language-first authoring. Natural-language creation is explicitly preview. **Agents created with the GitHub Copilot harness cannot be transferred to the standard harness, or vice versa.** This is an explicit transfer boundary, not just a warning that some components differ. [R01][R04]

Harness selection is not a compulsory upgrade path. Microsoft's comparison guidance says a working standard agent need not move merely because another harness exists; when a change has a demonstrated scenario-level benefit, treat it as re-architecture rather than component conversion and validate the rebuilt agent's journeys. This differs from both cloning a standard agent definition for local editing and copying an Agent Builder snapshot into Studio. [R37][R35][R24]

The product overview distinguishes **workflows** from established **agent flows**. Workflows combine agents, tools, and logic; agent flows are a native Copilot Studio automation format with an experience similar to Power Automate and can be standalone or tools for agents. The safe introductory distinction is that an agent decides how to respond or act, while a flow/workflow organizes operations; the exact designer and supported behavior depend on the experience. [R01][R11]

Workflow status also needs subfeature precision. The overview does not provide an overall workflow GA label; the July 2026 release entry labels adding workflows as tools to GitHub Copilot harness agents **preview**, and the September entry labels the workflow Copilot node **preview**. These **Copilot Studio workflows** are not the **Microsoft Foundry declarative workflows** whose separate documentation announces retirement on **December 1, 2026**; do not transfer that retirement to Studio automation. [R01][R05][R41]

### Professional-developer extension paths

These are complementary choices within or alongside Studio, not a requirement to abandon graphical authoring. Keep the route, experience, and status together. [R35][R36][R38][R39]

| Route | What it enables at an introductory level | Status and boundary |
|---|---|---|
| **Copilot Studio extension for Visual Studio Code** | Clone the standard agent definition locally, edit YAML directly or with a coding assistant such as GitHub Copilot, apply changes for testing, and deploy to an environment. Git and pull requests support team review. [R35] | **GA**, explicitly in the overview and January 2026 release entry; the article scopes this extension to the **standard harness**. This is agent-definition development, not conversion to a different runtime. [R35][R05] |
| **Copilot Studio MCP with VS Code/GitHub Copilot or GitHub Copilot CLI** | A configured developer-tool connection exposes permitted Studio lifecycle operations after sign-in and environment selection. Proposing, saving, publishing, deploying, and executing remain distinct outcomes. [R39][R40] | **Documented configured route; GA/preview label not established by these pages.** Do not inherit the VS Code extension's GA label. Identity, permissions, service tool availability, organization policy, and action approvals still apply. [R39][R40] |
| **A2A connected agents, standard harness** | Delegate tasks to an external agent that actually implements the Agent2Agent protocol, using an appropriate endpoint and authentication. [R36] | **GA**, April 2026 release entry paired with the standard-harness connection article. This does not make the newer MCP/A2A client channels GA or every external-agent connection interchangeable. [R05][R36][R17] |
| **Microsoft 365 Agents SDK connected agents, standard harness** | Connect a code-built agent through its messaging endpoint and configured authentication so Studio can call it for a request or trigger. The A2A article identifies Activity Protocol as the SDK integration pattern. [R38][R36] | **Preview for this specific connection**, explicitly in the connection article and overview. Review external-agent data handling, permissions, reliability, and oversight. [R38][R25] |
| **Other named standard connections** | Foundry agents and Fabric data agents are separately documented connection options. [R25] | **Preview** for these named connections. Neither the GA A2A route nor another product's GA status supersedes their specific evidence. No named-IQ claim is implied. [R25][R26] |

### Grounding and knowledge

**Knowledge is information the agent can consult to support an answer.** The knowledge summary documents public websites, uploaded documents, SharePoint, Dataverse, and enterprise data through Microsoft Copilot connectors. Supported sources and search behavior differ between classic and generative orchestration and between harnesses. Do not imply that connecting a source means every file, format, query, or analytical operation is supported. [R09][R04][R28]

**Permissions depend on the source and access path.** For SharePoint, Dataverse, and enterprise data using Copilot connectors, the knowledge summary describes agent-user authentication and returning content the user can access. Directly uploaded documents use a different path: they are stored in Dataverse, and the summary lists no source authentication for that document category. An authenticated SharePoint connection and uploading a copy of a document are not equivalent permission models. Recommendation: use source-appropriate access controls and review the intended agent audience before choosing the ingestion path. [R09][R10]

**Grounding reduces neither the need for verification nor all model uncertainty.** In the standard experience, turning off **Allow ungrounded responses** blocks a turn that used no knowledge source or tool; it does not prevent the model from incorporating general knowledge alongside retrieved material. Missing citations can also cause an otherwise sourced answer to be withheld. These are reasons to evaluate representative questions and inspect citations rather than promise guaranteed correctness. [R09]

> "Turning the Allow ungrounded responses setting off doesn't guarantee that the agent never uses general knowledge."
> - Source: [Knowledge sources summary][R09]

Knowledge retrieval is not synonymous with unrestricted database analysis or document discovery. The limits page records unsupported SharePoint query patterns, source-specific size and ingestion limits, and weaker results for some analytical questions over structured files. Keep a customer example focused on supported question answering unless the exact analytical capability has been separately verified. [R28]

### Actions, tools, and connectors

**Tools let an agent do something, not just answer.** Documented examples include sending email, reading/writing Dataverse, and reading/posting Teams messages. In the standard experience, tools can come from connectors, agent flows, prompts, REST APIs, or MCP servers, among other mechanisms. A connector supplies access to a service/API; it is not itself a guarantee that every operation is permitted or supported in every channel. [R11][R12]

Authors can allow generative tool selection or invoke a tool explicitly from a topic. Tool settings include input handling, authentication, and asking the end user before execution; the documented confirmation default is **No**. Recommendation: explicitly review confirmation, validation, and permissions for consequential operations rather than assuming a confirmation is automatically present. An execution confirmation is not the same as a formal business-approval process. [R11]

**Agent-user sign-in and tool authorization are separate decisions.** A tool can use the author's connection or require user authentication. Microsoft's guidance recommends user authentication when access must be restricted to particular people or the operation is on their behalf. Channel support for this authentication is limited; for example, the tool-authentication table lists custom websites and Teams as supported but mobile apps and Azure Bot Service channels as unsupported. [R12]

### Autonomous operation, with a credential warning

Standard agents with generative orchestration can respond to configured **event triggers**, such as a new SharePoint item, a Dataverse change, or a schedule. The author defines available operations and instructions; the agent does not invent a new tool at runtime. Publishing activates the trigger's automatic reactions, and trigger activity contributes to consumption. [R13]

The critical boundary is that the documented standard-harness event-trigger path uses **maker credentials**; authenticated operations must have working maker authentication to run without user input. Microsoft warns that published agents with such triggers can expose access or actions under the author's authorization. Do not describe this path as automatically using the current employee's permissions. Narrow trigger scope, inspect payload data and outputs, and test before enabling it. [R13]

## 4. Publishing and Channel Boundaries

Publishing makes a version available outside the authoring experience; it does not automatically distribute the agent, grant users access, or make every channel available. In the standard experience, publishing updates associated channels, while changes not republished remain unpublished. The newer experience likewise separates draft, publication, and distribution. Validate the published agent on the actual target channel. [R14][R16]

| Experience | Documented distribution examples | Boundaries to preserve |
|---|---|---|
| Standard harness | Teams/Microsoft Copilot, websites, SharePoint, and other specifically supported channels. [R14][R15] | Organization policies and authentication can disable channels. The test/demo website is not a production customer endpoint. [R14] |
| GitHub Copilot harness | Current channel table lists Microsoft Copilot, Teams, demo website, and web app as available. [R17] | The same table lists SharePoint, WhatsApp, native apps, and listed contact-center channels as unavailable. MCP/A2A client channels are preview and restricted to early-release environments. [R17] |
| Customer Conversation harness | Preview documentation targets website chat and phone-based conversations with escalation paths. [R06] | Speech does not support end-user sign-in; knowledge requiring end-user credentials is usable for chat, not speech. [R06] |

For Teams and Microsoft 365, distinguish **publishing**, **sharing with intended users**, **installation**, and **organization-catalog approval**. A user can install or reach an agent and still be unable to chat if access was not shared. Making it available in Microsoft Copilot is an explicit channel choice; Teams distribution alone does not establish that choice. [R15]

A particularly important employee-data limitation: the current standard-harness Teams guidance says agents in **group chats and channels cannot use knowledge requiring end-user authentication, such as SharePoint**; that scenario is supported in **1:1 chats**. Therefore, an employee-policy assistant that works privately should not be assumed to provide the same behavior in a team channel. [R15]

Do not promise identical cards, citations, greetings, media, feedback, or escalation in every host. The standard publishing guidance records channel differences; the Microsoft Copilot channel specifically has unsupported nodes and message types. A published channel is a distinct product surface with its own limits. [R14][R15]

## 5. Testing, Evaluation, and Management

**Interactive testing and repeatable evaluation are complementary.** Test chat helps inspect an individual conversation and its orchestration; evaluations run test sets repeatedly and compare quality across changes. Standard-harness evaluation supports single-response and multi-turn conversation cases, expected responses where applicable, and inspection of transcripts/activity maps. Tests execute as the signed-in user, so testing one privileged maker account is not proof of all users' behavior. [R07][R18]

**Evaluation status differs by experience.** The release history explicitly records agent evaluations as GA in **March 2026**. The GitHub Copilot harness's separate evaluation page, however, labels its Evaluate experience **production-ready preview** and currently documents only **General quality**, which does not compare the response against an expected answer. Both pages limit evaluations to **No authentication** or **Authenticate with Microsoft**; manual authentication is unsupported. Do not borrow the standard evaluator's status or grader set for the newer experience. [R05][R18][R19]

The standard evaluation GA milestone is not a blanket status for every evaluation extension. For example, the April 2026 release history separately labels REST-API evaluation automation **preview**. No API implementation instructions or code are needed for this introductory distinction. [R05]

Safety evaluators in the standard evaluation documentation cover common harmful-content categories, but Microsoft explicitly says they do not guarantee that the agent is safe or appropriate for every scenario. Recommendation: combine quality tests with permission-denial cases, tool failure cases, unsafe-input cases, and review of consequential operations; passing a score is not a compliance certificate. [R18][R12][R13]

For operation, **Monitor** provides production metrics and component usage, with different views for conversational and event-triggered activity. Its standard-harness documentation excludes authoring test-panel activity from production analytics. An Analytics Viewer can receive limited analytics access, while transcript access additionally requires the Bot Transcript Viewer security role. Keep transcript visibility and retention as explicit administrative decisions. [R20]

For managed releases, Copilot Studio follows Power Platform ALM practices: development/test/production environments, solutions, connection references, environment-specific configuration, and appropriate pipelines/source control. Important exceptions require post-deployment attention: deployed channels, sharing, manual authentication, Direct Line/web-channel security, and Application Insights settings are not all transported by the normal solution deployment process. Deployment is therefore not equivalent to copying all security and channel settings. [R21]

## 6. Product-Specific Security and Governance

### Controls that are directly relevant to Copilot Studio

- **Environment and maker access:** Power Platform environments and role/access design provide boundaries for building and releasing agents. Keep production changes governed rather than treating a maker's ability to create an agent as production approval. [R21][R24]
- **Data policies:** Administrators can govern connector combinations, authentication requirements, HTTP requests, channels, and event triggers. Connectors are classified as Business, Non-business, or Blocked; data cannot be shared between connectors in different policy groups. The documentation states enforcement has applied to all tenants since early 2025 and exemption is no longer supported. [R23]
- **Runtime/tool identity:** Review whether each operation uses end-user or maker-provided credentials. Event-triggered standard agents have the maker-credential limitation described above. Sign-in to the chat surface does not resolve every downstream authorization decision. [R11][R12][R13]
- **Audit and oversight:** The security overview documents maker audit visibility through Microsoft Purview and monitoring integrations. Additional centralized controls through Microsoft Agent 365 are described for organizations that onboard it; this is not evidence that all cross-product controls are automatically configured. [R22]

### Limits of the protection story

Data policies govern supported connections and features; they should not be described as a semantic guarantee that every answer or action complies with every business rule. The security overview distinguishes harmful-content moderation from arbitrary administrator-defined subject blocking. Use instructions, allowed tools, authorization, testing, and appropriate human review together rather than claiming any one control eliminates agent risk. [R22][R11][R18]

**External connections retain responsibility boundaries.** The Foundry connection guidance makes the customer responsible for appropriate data flows, permissions, quality, security, traceability, observability, and human oversight when using an external agent. The residency guidance similarly assigns responsibility to the maker for connections to external non-Microsoft systems. These statements do not support automatic inheritance of Copilot Studio policies by a connected service. [R26][R27][R32]

Channel and telemetry flows also matter. The Teams publishing page warns that agent/chat data shared with Teams can cross the organization's compliance or geographic boundaries. The security overview separately states that configured Customer Lockbox coverage excludes the identified Purview security-audit logging pipeline and Agent 365 governance/audit events. Avoid an unqualified claim that every connected flow is covered by one residency or support-access control. [R15][R22][R31]

## 7. Documented Integrations and Customer Examples

### Specific integration claims that are supportable

| Connection | Supported claim | Status and non-claim |
|---|---|---|
| Microsoft 365 Copilot / Agent Builder to Copilot Studio | A supported **Copy to Copilot Studio** operation copies specified agent configuration; the original remains and subsequent updates do not synchronize. [R24] | Documented shipping. Some knowledge/capabilities are not copied or require reconfiguration. This is not a mandatory migration or a universal conversion path. [R02][R24] |
| Copilot Studio to Microsoft 365 / Teams | A published agent can be made available through the supported channels and distribution controls. [R15][R17] | Documented shipping within the selected experience. Not equivalent to turning every Microsoft 365 Copilot experience into that agent, and not identical across hosts. [R15][R17] |
| Power Platform / business services | Tools can use prebuilt/custom connectors and agent flows to retrieve information or perform operations; solutions and environment practices support managed release. [R11][R21] | Documented shipping building blocks. Verify the individual connector/tool's availability, credentials, policy, and channel support. [R11][R12][R23] |
| Standard-harness Studio to an A2A connected agent | Delegate a task to an external agent that implements A2A, with a configured endpoint and authentication. [R36] | **GA**, April 2026. Distinct from preview MCP/A2A client channels and from named Foundry/Fabric/SDK connection routes. Customer review of data flows, permissions, testing, and oversight remains required. [R05][R36][R17][R25] |
| Standard-harness Studio to a Microsoft 365 Agents SDK agent | Call a code-built agent through its messaging endpoint and configured authentication. [R38] | **Explicit preview for this connection.** Not a status verdict on the SDK as a whole, not the A2A GA route, and not automatic permission inheritance. [R38][R25][R36] |
| Standard-harness Studio to a Microsoft Foundry agent | Delegate to a specifically connected current-portal Foundry agent with **Activity protocol** enabled. [R26] | **Explicit preview** in this route's article, consistent with the approved Foundry-owner scope. Not every Foundry endpoint or universal governance portability. [R26] |
| GitHub Copilot harness Studio to a Microsoft Foundry agent | Separately documented route requiring a current-portal Foundry agent, Activity protocol, project endpoint, agent ID, and Entra user-login connection. [R27] | **Conservative preview classification, inferred from the June 2026 connected-agent entry; route-specific status label not established.** R27 itself has no preview banner; do not describe the standard route's label as direct evidence for this route. [R05][R27] |
| Standard Studio agent-definition development with GitHub Copilot | The **VS Code extension** supports cloning/editing definitions with coding assistants and Git/pull-request workflows. [R35] | **Extension GA**, January 2026; **standard-harness** scope. A configured development relationship, not GitHub Copilot becoming the business-agent runtime or automatically governing it. [R05][R35][R03] |
| Studio MCP with VS Code/GitHub Copilot and GitHub Copilot CLI | A separate configured connection exposes Studio lifecycle tools under the signed-in account and selected environment. [R39][R40] | **Documented route; GA/preview label unknown from these pages.** Keep client approvals and distinguish saved drafts from publication/execution. The extension's GA does not establish this route's status. [R39][R40] |
| GitHub-backed ALM and the similarly named runtime | Power Platform ALM can use GitHub integrations/Actions; separately, Studio offers a GitHub Copilot harness. [R21][R03] | Source control, developer assistance, MCP lifecycle access, and the Studio runtime are distinct relationships with distinct controls. None proves universal runtime integration or portable governance. [R21][R03][R35][R39] |

The Foundry connection also has a practical limitation worth retaining in customer Q&A: a connection can be added but fail when invoked if the required Activity protocol is absent. The newer, October-dated guidance describes automatic Activity-protocol enablement when publishing a **prompt agent** to Microsoft 365/Teams, as well as manual API enablement. Older standard-harness guidance describes programmatic enablement only. Retain the common prerequisite and the prompt-agent qualification; do not teach one universal enablement procedure from these differing pages. [R26][R27]

Multi-agent composition is optional. Microsoft's design guidance says it is not always necessary and can increase latency, testing, management, and governance surface area. It also warns that citations might not always be maintained across agent handoffs. A focused single agent with well-described tools can be a better starting point than a specialist network. [R25]

### Illustrative customer scenarios — not customer success claims

| Example | Useful capability combination | Limitation or decision |
|---|---|---|
| **Employee policy assistant:** A people-operations team wants answers from approved policy content. | Ground a focused agent in an authenticated SharePoint source and distribute privately through a supported Microsoft channel. [R09][R15] | Test employee access, unanswered questions, and citations. Do not assume the same authenticated knowledge works in Teams group/channel contexts. [R09][R15] |
| **Public customer-information assistant:** A service team wants website answers and selected business-system operations. | Use supported website publishing, curated knowledge, and explicitly configured tools. [R14][R11] | Public access is a deliberate authentication choice. A public conversation should not silently grant a customer the maker's broad business-system privileges. [R14][R12] |
| **Operational follow-up:** A team wants an agent to react to a new business record and perform configured follow-up. | Standard event triggers plus approved tools/automation can react without a chat prompt. [R13] | Maker credentials, payload sensitivity, frequency, capacity, and operational review are essential; autonomous does not mean unlimited authority. [R13][R23] |
| **Developer-team maintenance:** A team wants familiar editing, coding assistance, and review for an existing standard Studio agent. | Use the GA Studio VS Code extension to clone/edit definitions locally, optionally with GitHub Copilot, and review changes through Git/pull requests. [R35][R05] | Apply/test changes in the intended environment; this is not a harness transfer or automatic publication. The separately configured Studio MCP route has no established GA label in its cited pages. [R35][R04][R39][R40] |
| **Developer-supported specialist integration:** An enterprise team wants a standard-harness Studio agent to delegate a specialized task to an existing Foundry agent. | Use that route's documented connected-agent integration with an appropriate routing description. [R26] | **Explicit preview** for this standard route; Activity protocol, current-portal restriction, data handling, and end-to-end testing remain. A connection is not proof of equivalent governance. [R25][R26] |

These are alternative fits, not steps every customer should complete. The selection principle is to use the authoring, channel, integration, and operating model that meets the scenario; a supported Microsoft 365 Agent Builder configuration may already be sufficient, while Copilot Studio may be the starting point for a custom business workflow or external audience. [R02]

## 8. Feature-Level Availability Register

Evidence cut-off: **2026-10-30**. Status applies only to the named capability and experience. “Documented shipping” below is deliberately weaker than a formal GA claim.

| Capability | Evidence-based status | Evidence and caveat |
|---|---|---|
| Graphical low-code agent authoring; standard topics, knowledge, and tool configuration | **Documented shipping** | Current operational documentation. Individual sources, connectors, and newer subfeatures can have separate restrictions/status. [R01][R07][R09][R11] |
| Copilot Studio workflows and established agent flows | **Documented functionality; overall workflow GA label not established by R01; specified subfeatures preview** | July 2026: adding workflows as tools to GitHub Copilot harness agents is preview. September 2026: workflow Copilot node is preview. These are not the separate Foundry declarative workflows retiring December 1, 2026. [R01][R05][R41] |
| Standard generative orchestration | **GA**, with historical milestone evidence | Release plan records GA on **2025-03-17**; that page is now archived. Current operational documentation independently confirms ongoing support and the default for new standard agents. Do not use the archived page for current limits. [R08][R07] |
| Copilot Studio VS Code extension, standard harness | **GA** | January 2026 release entry and explicit overview GA statement. Local definition editing, coding assistants, and Git/pull-request workflows are documented; do not generalize this status to Studio MCP or other harnesses. [R05][R35] |
| Studio MCP with VS Code/GitHub Copilot or GitHub Copilot CLI | **Documented configured route; GA/preview label unknown from cited pages** | Lifecycle tool access is conditional on identity, environment permissions, client policy, and available operations; distinct from the extension and published-agent MCP channels. [R39][R40][R17] |
| A2A connected agents, standard harness | **GA** | April 2026 release entry plus the standard-harness A2A article. Does not promote the newer MCP/A2A client channels or other named external-agent routes to GA. [R05][R36][R17][R25] |
| Microsoft 365 Agents SDK connected-agent route, standard harness | **Explicit preview** | Connection article and external-agent overview. Status applies to the Studio connection, not the SDK as a whole. [R38][R25] |
| Fabric data-agent connection, standard route | **Explicit public preview** | R25 expressly names this external-agent connection. Not a named-IQ finding and not subsumed by A2A GA. [R25] |
| GitHub Copilot harness new experience | **Production-ready preview**, latest explicit overall milestone found | June 2026 release history uses this qualification. Current overview lists availability alongside standard agents but does not independently establish a later overall GA milestone. [R05][R04] |
| Natural-language solution creation | **Preview** | Explicitly labeled preview in the current product overview. Do not infer its status from basic agent authoring. [R01] |
| Customer Conversation harness / Customer Assist Agent | **Preview** | Experience-specific overview is prerelease documentation; no independent GA confirmation found. [R06] |
| Agent Builder copy to Copilot Studio | **Documented shipping** | Current copy instructions and November 2025 release-history entry; no independent feature-level GA milestone asserted here. [R24][R05] |
| Standard agent evaluations | **GA core; specific extensions separately preview** | March 2026 core GA milestone. April 2026 REST-API evaluation automation remains explicitly preview in its release entry; do not infer every evaluation subfeature's GA. [R05][R18] |
| GitHub Copilot harness Evaluate tab | **Production-ready preview** | Experience-specific page; only General quality is documented there. [R19] |
| Foundry connected-agent integration, standard harness | **Explicit preview** | Route-specific title/banner; Activity protocol and current-portal requirements. This status is not automatically transferred to another harness. [R26] |
| Foundry connected-agent integration, GitHub Copilot harness | **Conservative preview classification; route-specific status label unknown** | June 2026 connected-agent entry is preview, but R27 has no route-specific preview/GA label. This classification is inferred, not a direct R27 status statement. [R05][R27] |
| Microsoft/Teams/web channels | **Documented shipping**, selected-experience scope | Current channel-specific instructions/tables establish support, not parity across harnesses or hosts. [R14][R15][R17] |
| New-harness MCP/A2A client channels | **Preview**, early-release environments only | Explicit channel-table restriction. This concerns exposing an agent through those channels, not a blanket status for every use of either protocol. [R17] |
| Standard event triggers and core data-policy enforcement | **Documented shipping** | Current trigger guidance; data-policy documentation explicitly records enforcement since early 2025. No blanket GA assertion for every new governance feature. [R13][R23] |
| Specific tenant/model/region combinations not enumerated here | **Unknown until checked** | Availability depends on feature, capacity, geography, model, and tenant rollout. Do not infer feature availability from product availability. [R05][R03][R34] |

No announcement-only or planned capability is used as an available feature in the conclusions. Additional experimental models, computer-use variants, memory, skills, app creation, and detailed voice features are not required to explain the introductory agent-authoring use case and are not given an availability verdict by this report.

## 9. Commercial, Capacity, and Regional Boundaries

### Commercial boundary — no pricing table

Separate **maker access**, **permission to publish/use**, and **consumption**. Microsoft's selection guide says requirements depend on the capabilities, users, channel, billing configuration, and harness. The standard licensing page explicitly says its trial allows creation and test chat but not publishing. Do not generalize a trial or Microsoft 365 entitlement into unrestricted external deployment. Exact customer entitlement needs current licensing validation. [R02][R29]

Copilot Credits are the documented consumption unit, but metering differs by harness. The GitHub Copilot harness billing documentation says building, previewing/testing, and evaluation can consume credits, unlike its stated standard-harness billing-after-publication model. Therefore, “experimentation is always free” is not a safe claim. No prices, comparative cost estimates, or licensing matrix are supplied. [R29][R30]

### Capacity and scale

Quotas, monthly capacity, connector/downstream limits, and peak throughput are separate constraints. The standard-harness limits page applies quotas per Dataverse environment and warns that high-volume conversations, triggers, and downstream calls can reach throughput limits even if monthly volume appears manageable. Treat scale as a design/validation question, not “unlimited agents means unlimited traffic.” Numeric limits are intentionally not generalized to the other harnesses. [R28][R13][R29]

### Geography, data location, and models

Storage geography is not an all-data-stays-here guarantee. The data-location page documents replication and service exceptions, channel/external-service transfers, and Microsoft 365-powered activity storage under Microsoft 365 commitments. The geographic residency overview points to more detailed location and data-movement guidance. These distinctions must accompany any residency claim. [R31][R32]

The current Power Platform administration guidance states that some features need cross-region capacity, distinguishes Bing/Microsoft 365 service settings, and warns that **some Copilot Studio models may process data outside the environment's geography even when cross-geo movement is restricted**. Check the selected model and harness, not just the environment location or a single toggle. This report does not promise universal geography, language, or sovereign-cloud parity. [R34]

The older Studio-specific data-movement page uses broader wording about non-US data movement and an older administrator description. For current operational interpretation, prefer the October 2026 Power Platform administration guidance, while preserving its model-specific exceptions and internal qualifications. Do not turn either page into an unconditional residency guarantee. [R33][R34]

## 10. Research Limitations and Cross-Owner Handoff

### Documentation gaps and conflicts

1. **Overall new-experience GA is not independently established.** The June 2026 history explicitly says production-ready preview; newer overview prose describes availability without supplying an overall GA milestone. This report preserves the last explicit status rather than interpreting absence of a banner as GA. Evaluation and Customer Conversation status are independently documented. [R05][R04][R19][R06]
2. **High-level “rule-based” wording is incomplete for standard agents.** The harness overview positions the standard harness for structured/rule-based scenarios, while the detailed orchestration page explicitly supports generative orchestration and makes it the default for new standard agents. Use the detailed page for behavior, not a fixed-script-only interpretation. [R03][R07]
3. **Attachment guidance is inconsistent.** The standard general publishing page still contains a blanket no-attachments limitation, but the newer harness release history records file attachments as GA in September 2026, and the standard knowledge-upload page links separate user-file-input guidance. No universal attachment claim is made here; verify the exact experience, channel, and input type before using such an example. [R14][R05][R10]
4. **Foundry Activity enablement guidance differs.** The August-dated standard integration page says programmatic enablement only; the October-dated new-harness page also describes automatic enablement when publishing a **prompt agent** to Microsoft 365/Teams. The common Activity-protocol requirement and current-portal restriction are retained, but a universal enablement recipe is intentionally omitted. The standard connection's preview status is explicit; the newer route's conservative preview classification is inferred from a generic release entry, not a route-specific label in R27. [R26][R27][R05]
5. **Geography wording is not uniform.** The older Studio-specific movement page is broader than current Power Platform guidance. The current admin article includes both a general statement that clearing the setting prevents out-of-region data movement and an explicit Copilot Studio model exception. The report retains the specific exception and does not promise a blanket block on out-of-region processing. Model/region validation remains necessary. [R33][R34]
6. **Archived historical release evidence:** The generative-orchestration release plan now carries an October 2026 archive notice. It supports the recorded historical GA date, not present-day instructions, limits, or roadmap promises. Current feature behavior comes from operational documentation. [R08][R07]
7. **Copy versus older move wording:** The November 2025 release entry loosely describes moving Microsoft 365 agents into Studio. The current decision guide and copy article specify an independent snapshot that leaves the original in place. Use **copy**, not automatic migration, synchronization, or destructive move, when explaining this operation. [R05][R02][R24]
8. **Developer/protocol status is route-specific:** Extension GA and standard A2A connected-agent GA do not establish GA for Studio MCP lifecycle access, newer published-agent MCP/A2A channels, or the named standard Foundry/Fabric/SDK connections. The Studio MCP pages describe a configured route without a GA/preview label. The explicit harness-transfer prohibition concerns transfer of an agent, while the migration guidance discusses rebuilding/re-architecture; neither is a compulsory migration. [R35][R36][R05][R39][R40][R17][R25][R04][R37]

### Ownership and review handoff

- **Foundations:** All substantive named-IQ claims and shared ecosystem framing remain deferred. Sources encountered during this research contain such material, but those claims are not imported into this report. No approved foundations report was available.
- **Microsoft 365 owner:** Aligned with brief version 3's approved snapshot-copy fact: the original remains, updates are not synchronized, and audience size alone does not require Studio. Preserve these specific boundaries despite older release-history move wording. No additional Cowork capability is asserted here. [R02][R24][R05]
- **Foundry owner:** Aligned with the approved **standard-harness-only explicit preview** connection claim, Activity prerequisite, and current-portal boundary. The newer harness route is now split out with an explicitly inferred/conservative status basis. Automatic Activity enablement is limited to publishing a **prompt agent** in the cited procedure. Studio workflows are distinct from the separate Foundry declarative-workflow retirement. The source-level enablement discrepancy remains for any implementation follow-up. [R26][R27][R05][R01][R41]
- **GitHub Copilot owner:** Aligned with the approved distinction between the **Studio GitHub Copilot harness** and the separate service, and with the documented **configured Studio MCP development relationship** from VS Code/GitHub Copilot or GitHub Copilot CLI. Added the independently verified **GA standard-harness VS Code extension** for agent-definition editing with coding assistants and Git/pull-request review. Keep extension GA, unlabeled Studio MCP status, GitHub-backed ALM, and Studio runtime execution separate; none grants automatic access or portable controls. [R03][R35][R05][R39][R40][R21]
- **Governance owner:** Product-specific controls here are not a claim that one policy, identity, approval, transcript setting, or data boundary transfers unchanged across products or connected agents. [R21][R22][R26][R27]

Approved GitHub Copilot, Foundry, and Microsoft 365 peer facts are now available through brief version 3 and were checked against their relevant read-only report passages and underlying official sources. The revised claims above preserve those approved scopes; no conflicting approved claim is carried into this report. Source-level ambiguities are retained rather than resolved by borrowing another route's status. Tenant validation, live regional rollout, actual customer entitlements, end-to-end performance, and production behavior were not tested. No code-sample search was needed because no code or commands are part of the task.

**R2 revision record:** IMP-1(a–d) addressed through developer paths, integration rows, explicit transfer/re-architecture boundaries, and matching status entries. MIN-1 through MIN-4 addressed. Optional MIN-5 was not added; no new Entra Agent ID timing assertion is made. Seven official documentation references were added, none removed. This is a revision for caller-managed re-review, not approval.

## 11. Complete Reference List

### Microsoft Learn Documentation — 41 pages

All accessed **2026-10-30**, all fetched in full using the required Learn capability. Dates below are publisher `ms.date` metadata. Where especially relevant, a separate `updated_at` date is identified; neither is treated as an availability milestone.

- **R01. [Copilot Studio overview][R01]** — 2026-10-27. Product definition, building blocks, audience, preview natural-language creation.
- **R02. [Choose between Agent Builder and Copilot Studio to build your agent][R02]** — 2026-10-23; updated_at 2026-10-27. Capability-based selection, no audience-size-only rule, differing management controls.
- **R03. [Harnesses in Copilot Studio][R03]** — 2026-10-19. Runtime terminology and explicit GitHub Copilot service distinction.
- **R04. [Agents powered by the GitHub Copilot Harness overview][R04]** — 2026-10-19. Experience-specific authoring, feature comparison, and explicit bidirectional harness-transfer prohibition.
- **R05. [What's new in Copilot Studio][R05]** — 2026-10-05; updated_at 2026-10-22. Dated status evidence, including January extension GA, April A2A GA/evaluation API preview, and workflow subfeatures.
- **R06. [Agents powered by the Customer Conversation harness overview (preview)][R06]** — 2026-10-08. Customer Assist Agent name, preview scope, voice/chat authentication distinction.
- **R07. [Orchestrate agent behavior with generative AI][R07]** — 2026-08-26. Standard generative/classic behavior, defaults, descriptions, testing, limitations.
- **R08. [Use generative orchestration][R08]** — 2025-08-07. Historical GA date 2025-03-17; archived as of October 2026.
- **R09. [Knowledge sources summary][R09]** — 2026-07-21; updated_at 2026-10-29. Grounding, source authentication, search differences, ungrounded-response caveat.
- **R10. [Upload files as a knowledge source][R10]** — 2026-09-29. Dataverse storage, document ingestion path, limits and user-input distinction.
- **R11. [Add tools to custom agents][R11]** — 2026-10-01. Tool mechanisms, operations, confirmation defaults, credentials and policy restrictions.
- **R12. [Configure user authentication for tools][R12]** — 2026-10-14. Author/user connections and supported channels.
- **R13. [Event trigger overview][R13]** — 2026-09-09. Autonomous operation, consumption, maker credentials, data-protection warning.
- **R14. [Key concepts - Publish and deploy your agent][R14]** — 2026-09-16. Standard publication, channel restrictions, test-site warning and conflicting attachment limitation.
- **R15. [Connect and configure an agent for Teams and Microsoft 365][R15]** — 2026-10-29. Distribution, sharing, approvals, host limitations and 1:1/group knowledge boundary.
- **R16. [Publish overview for agents (GitHub Copilot)][R16]** — 2026-09-08. Draft/publication/distribution distinctions.
- **R17. [Available channels for agents (GitHub Copilot)][R17]** — 2026-06-23; updated_at 2026-10-16. Available/unavailable channels and early-release protocol channels.
- **R18. [About agent evaluation][R18]** — 2026-10-05. Standard test sets, user context, safety caveat and authentication limitations.
- **R19. [Evaluate an agent (preview)][R19]** — 2026-10-05; updated_at 2026-10-21. Production-ready preview, General quality-only method and its limitation.
- **R20. [Monitor agent performance in Copilot Studio][R20]** — 2026-10-21. Production metrics, views, test-data exclusion and transcript-access roles.
- **R21. [Establish an application lifecycle management strategy][R21]** — 2026-01-16; updated_at 2026-09-12. Environments, solutions, tooling and nontransported configuration.
- **R22. [Key concepts - Copilot Studio security and governance][R22]** — 2026-09-24; updated_at 2026-10-15. Product controls, optional Agent 365 onboarding context and Lockbox exceptions.
- **R23. [Configure data policies for agents][R23]** — 2026-10-01. Connector groups, enforcement, feature/channel/trigger restrictions.
- **R24. [Copy an agent from Agent Builder to Copilot Studio][R24]** — 2026-09-30. Independent snapshot, copied/uncopied configuration, environment and management requirements.
- **R25. [Add other agents overview][R25]** — 2026-05-15; updated_at 2026-10-15. Optional composition, preview integrations, latency/governance and citation limitations.
- **R26. [Connect to a Microsoft Foundry agent (preview)][R26]** — 2026-08-26. Standard integration, current portal, Activity prerequisite and customer responsibilities.
- **R27. [Add a Foundry agent as a connected agent (GitHub Copilot)][R27]** — 2026-10-14. New-experience prerequisites, routing, authentication, prompt-agent Activity enablement and responsibilities; no route-specific preview/GA label.
- **R28. [Quotas and limits][R28]** — 2026-10-27. Standard-harness capacity, source/query limits and throughput planning.
- **R29. [Licensing for agents powered by the standard harness][R29]** — 2026-08-03; updated_at 2026-10-22. Access, trial publication restriction, credits and capacity.
- **R30. [Overview of usage-based billing][R30]** — 2026-10-06. GitHub Copilot harness build/test/evaluation consumption.
- **R31. [Data locations in Copilot Studio][R31]** — 2026-04-29; updated_at 2026-10-17. Location exceptions, external/channel flows and Microsoft 365-powered activity storage.
- **R32. [Geographic data residency in Copilot Studio][R32]** — 2024-09-18; updated_at 2026-10-07. Residency overview and connector responsibility boundary.
- **R33. [Configure data movement across geographic locations for generative AI][R33]** — 2024-10-16; updated_at 2026-10-07. Older product-specific guidance retained as a documentation limitation.
- **R34. [Move data across regions for Copilots, AI agents, and generative AI features][R34]** — 2026-10-14. Current administrative settings, capacity and model-specific exceptions.
- **R35. [Overview of Microsoft Copilot Studio extension for Microsoft Visual Studio Code][R35]** — 2026-07-24; updated_at 2026-10-15. Explicit GA, standard-harness scope, local definitions, coding assistants, and Git/pull-request collaboration.
- **R36. [Connect an agent available over the Agent2Agent (A2A) protocol][R36]** — 2026-08-26; updated_at 2026-10-15. Standard-harness connected-agent route, protocol/authentication boundaries, Activity Protocol SDK distinction, and customer responsibilities.
- **R37. [Compare Copilot Studio agent harnesses][R37]** — 2026-09-30. Scenario-based choice, no compulsory move, and migration as re-architecture rather than component conversion.
- **R38. [Connect to a Microsoft 365 Agents SDK agent (preview)][R38]** — 2026-02-13; updated_at 2026-10-15. Standard-harness preview connection to a code-built agent, messaging endpoint/authentication and external-agent responsibilities.
- **R39. [Connect to Microsoft Copilot Studio with MCP][R39]** — 2026-10-16; updated_at 2026-10-19. Configured lifecycle tools, identity/environment/policy boundaries, distinct outcomes, and no GA/preview label established.
- **R40. [Connect to Copilot Studio MCP with Visual Studio Code and GitHub Copilot CLI][R40]** — 2026-10-16; updated_at 2026-10-19. Specifically documented development clients, trust, permissions and approvals; not extension-GA evidence.
- **R41. [Build a workflow in Microsoft Foundry (Preview)][R41]** — 2026-07-31; updated_at 2026-10-19. Foundry-owner-approved declarative-workflow retirement boundary, independently verified; not a retirement of Copilot Studio workflows.

### Official Microsoft GitHub Repositories

N/A — no repository was consulted as an evidence source; documentation metadata links to source repositories were not counted as repository research.

### Code Samples

N/A — introductory research scope; no code, commands, setup tutorial, or code-sample search was needed.

[R01]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/fundamentals-what-is-copilot-studio
[R02]: https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/copilot-studio-experience
[R03]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/harnesses-overview
[R04]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/overview
[R05]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/whats-new
[R06]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/overview-customer-conversation
[R07]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-generative-actions
[R08]: https://learn.microsoft.com/en-us/power-platform/release-plan/2024wave2/microsoft-copilot-studio/use-generative-actions-now-generally
[R09]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/knowledge-copilot-studio
[R10]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/knowledge-add-file-upload
[R11]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/add-tools-custom-agent
[R12]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/configure-enduser-authentication
[R13]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-triggers-about
[R14]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/publication-fundamentals-publish-channels
[R15]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/publication-add-bot-to-microsoft-teams
[R16]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/publication-fundamentals-publish-channels
[R17]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/publication-channels-overview
[R18]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/analytics-agent-evaluation-intro
[R19]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/analytics-agent-evaluation-intro
[R20]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/analytics-overview
[R21]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/alm
[R22]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/security-and-governance
[R23]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/admin-data-loss-prevention
[R24]: https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/copy-agent-to-copilot-studio
[R25]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-add-other-agents
[R26]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/add-agent-foundry-agent
[R27]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/add-agent-foundry
[R28]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-quotas
[R29]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/billing-licensing
[R30]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/billing-credit-overview
[R31]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/data-location
[R32]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/geo-data-residency
[R33]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/manage-data-movement-outside-us
[R34]: https://learn.microsoft.com/en-us/power-platform/admin/geographical-availability-copilot
[R35]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/visual-studio-code-extension-overview
[R36]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/add-agent-agent-to-agent
[R37]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/choose-harness
[R38]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/add-agent-microsoft-365-agents-sdk-agent
[R39]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/copilot-studio-mcp
[R40]: https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/copilot-studio-mcp-vscode-copilot-cli
[R41]: https://learn.microsoft.com/en-us/azure/foundry/agents/concepts/workflow
