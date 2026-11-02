# Research Report: Microsoft 365 Copilot and Cowork Connected Work

**Date:** 2026-10-31
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** m365-connected-work
**Sources consulted:** 9 Microsoft Learn pages, 1 official Microsoft Support page, 0 GitHub repositories, 0 code samples — 10 unique official references
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Assignment:** m365-connected-work | brief_version: 8 | overallR1/cycle1 research assignment
**Evidence cutoff:** Retrieved 2026-10-31, the invocation date. Documentation/update dates below are not inferred launch dates.
**Deliverable scope:** Evidence for one introductory connectivity slide, new slide 7 after original content-v2 slide 6 and before Copilot Studio. This report is not a slide draft.
**Read-only dependencies:** `brief.md` Verified facts; `research/2026-10-30-m365-copilot-cowork.md` and its final approved round-1 review; foundation report sections 3–4 and 7–8, including its Fabric connectivity boundaries. Existing IQ ownership remains unchanged. Security-service facts and logos remain with agent-security-governance.

## 1. Executive Summary

Three **takeaway choices for the content owner**, not proposed slide copy:

- **Familiar work first:** Copilot assistance is available within supported Microsoft 365 apps, while the Microsoft Copilot app provides a conversational work surface. Word documents, PowerPoint presentations, and Teams work are defensible examples, not evidence of identical functionality in every app. [R01], [R02]
- **Context and execution are different connections:** Licensed Copilot can reason across organizational content the user can access. Cowork adds delegated multi-step execution, including document creation, edits to supported shared Office files, and Teams communications. Permission-scoped grounding is not unrestricted access, and working on a PowerPoint file is not proof that Cowork is embedded inside PowerPoint. [R02], [R03], [R04], [R05]
- **Specialization is available through explicit routes:** Users can discover and open available agents in the Agent Store. Cowork can use enabled plugins containing skills and connectors. These are documented extension paths, not automatic interoperability among every application, agent, and system. [R06], [R08], [R09], [R10]

**Evidence-safe synthesis:** Frame AI as adapting to existing work through familiar app experiences, authorized context, delegated tasks, and available extensions. Keep those mechanisms distinct rather than drawing one universal integration fabric. [R01], [R02], [R03], [R06], [R08], [R10]

## 2. Overview and Key Concepts: What Connected Means

| Connection | Load-bearing finding | What it does not establish |
|---|---|---|
| **App-native assistance** | Microsoft documents Word drafting, rewriting, and summarization, PowerPoint creation and editing, and Teams meeting summaries/action items. Chat depth varies with licensing and tenant configuration. [R01], [R02] | Every Copilot button has the same capabilities, grounding, or entitlement. |
| **Permitted work-data grounding** | The licensed experience can synthesize across accessible emails, meetings, chats, and documents. Baseline Chat can also use user-provided content and supported app context, with additional bounded organizational grounding in Outlook. [R02] | Baseline Chat is universally web-only, or licensed Copilot can see all tenant content. |
| **Cowork task execution** | Cowork carries out multi-step work. Users can reference work context, create artifacts, and edit an existing Word, Excel, or PowerPoint file in OneDrive/SharePoint, saving changes to the same shared file with its version history retained. [R03], [R04], [R07] | Cowork replaces every native app or operates on arbitrary local files without upload. Editing a shared cloud file does not mean an identical Cowork interface is embedded in its native app. |
| **Agent discovery and invocation** | In the Microsoft Copilot app, users expand **Agents**, select **All agents** to explore the Agent Store, then choose an agent and **Add** or **Open** before entering a prompt. Availability depends on account, subscription, and organization settings. [R10] | Opening one agent automatically invokes all other agents or grants their source-data permissions. No general Cowork-to-every-Agent-Store-agent invocation route is established here. |
| **Documented service connections** | Cowork plugins can contain skills, connectors, or both. Copilot connectors can index external content into Microsoft Graph or fetch it at query time. The target experience, connector implementation, authorization, and exposed tools determine support. [R06], [R08], [R09] | A connector, skill, and agent are interchangeable, or installing one makes every external system available everywhere. |

The product pillar remains **Microsoft 365 Copilot**. Current documentation calls the application **Microsoft Copilot** and the delegated-task experience **Microsoft Copilot Cowork**, shortened to **Copilot Cowork**. Use these distinctions in notes rather than treating the app rename as a rename of every license or experience. [R01], [R03], [R05]

## 3. Supported Apps and Examples

Use the first three rows as the strongest familiar-work examples. The remaining rows provide optional notes, not a requirement to expand the slide into a catalog. These are capability illustrations, not tested end-to-end workflows or customer outcome claims. [R01], [R03], [R04], [R06], [R10]

| Example | App-native Copilot evidence | Cowork or connected-work evidence |
|---|---|---|
| **Word document** | Draft, rewrite, or summarize a document. [R01] | Create a Word document or edit a selected existing file in OneDrive/SharePoint. Review it in Cowork or open it in Word at its existing cloud location. [R03], [R04] |
| **PowerPoint presentation** | Create a presentation from a prompt or existing content, summarize it, or edit it. [R01] | Create a deck, edit a selected shared PowerPoint file, and open the result in PowerPoint for review. This is file/workflow continuity, not identical Cowork embedding in the app. [R03], [R04], [R05] |
| **Teams collaboration** | Meeting summaries and action items are documented high-level app capabilities. [R01] | Reference Teams chats, channels, or meetings as context and post messages to supported channels or chats. Posting requires the applicable approval choices. This differs from summarizing a meeting inside Teams. [R03], [R04] |
| **Outlook and meetings** | Draft an email, summarize a thread, or use supported Outlook organizational grounding. [R01], [R02] | Draft/send communications, schedule meetings, and prepare meeting intelligence. [R03], [R04], [R05] |
| **Organizational specialist** | Discover and open an available agent in the Microsoft Copilot app, then ask a task-specific question. [R10] | Separately, enable an available Cowork plugin for expertise or service access, completing connector sign-in where required. Do not describe this as Cowork invoking that same agent. [R06] |

**Synthesized work-package illustration:** Use accessible project material to prepare a Word briefing and PowerPoint deck, then ask Cowork to prepare or post a Teams update. Each component is documented, but successful unattended completion of that entire chain was not tested or guaranteed. The person supplies direction, checks artifacts and recipients, and controls applicable approvals. [R02], [R03], [R04], [R05]

**Minimal usage context for notes:** Start Cowork in Microsoft Copilot using the **Cowork** toggle next to **Chat**. Add relevant work context or attach supported cloud files, specify the desired outcome, follow progress, respond to approvals, and review results. The getting-started guide also documents Outlook and Teams access, but this report establishes no parity matrix across web, desktop, mobile, and app entry points. No code, commands, or demo is needed. [R04], [R05]

## 4. Research Limitations and Notes-Only Qualifications

### Feature status, access, and deployment boundaries

| Item | Evidence-safe qualification as of 2026-10-31 |
|---|---|
| **Cowork work/school status** | Explicitly GA in the overview and June 2026 release history. The approved base report's June 16 launch date remains unchanged. Personal-account Cowork is preview and outside this organizational slide. [R03], [R07] |
| **Shared Office-file editing** | Documented in the usage guide and September 2026 enhancements. No independent feature-level GA date is established here, so use documented support rather than transferring Cowork's overall GA label. [R04], [R07] |
| **App skill** | Explicit Frontier preview. It is not needed for the Word/PowerPoint/Teams examples and should not be confused with ordinary Office-file creation. [R03], [R07] |
| **Agents, plugins, and connectors** | Availability is account-, subscription-, configuration-, host-, and extension-specific. This research does not establish blanket GA or uniform cloud availability for all extensions. The inspected federated overview documents support, not an explicit whole-feature GA date. [R06], [R08], [R09], [R10] |
| **Cowork prerequisites and cost** | Requires an assigned Microsoft 365 Copilot license, enabled Cowork, and usage-based billing. No price figures, unlimited-use promise, quota recommendation, or universal regional availability claim is made. [R01], [R05], [R07] |

**Permissions and connections:** Copilot does not grant additional source access. An admin-deployed Cowork plugin can still require the user's own one-time service sign-in. Federated connectors use source-system permissions and only expose actions supported by that connector. Permission and connection requirements belong in notes, not a new security-services deep dive. [R02], [R06], [R09]

**Approvals are not necessarily a fresh click for every action:** Cowork usage permits session-scoped approval choices and their review/revocation. The approved base report also retains pre-authorized automated-task qualifications. The separately documented federated connector experience has individual-tool choices, including persistent **Always allow** until settings or the tool change. Do not transfer that persistence to every Cowork plugin, or promise identical approval behavior across these routes. [R04], [R09]

### Concrete conflicts and promotion handling

- **Grounding conflict reaffirmed, not silently superseded:** R01's summary license table says baseline Chat uses web data only and later passages restrict organizational use to uploaded/open content or agents. That is too broad if applied to the Outlook grounding described in R02 and already approved in the brief. Prefer R02's dedicated, detailed grounding guidance for the Outlook boundary. Do not promote a universal web-only claim or infer that all app contexts receive that same Outlook grounding. R01's newer page update does not resolve this content disagreement. [R01], [R02]
- **Connector approval scope ambiguity:** R09 includes Cowork among supported hosts but its detailed federated tool-approval guidance includes persistent permission choices, whereas Cowork's own usage guidance describes session-scoped choices. These may be distinct host/tool settings. The evidence does not establish identical behavior in all Cowork plugin paths. Retain the approved Cowork wording, flag the distinction for path-specific validation, and do not promote universal approval persistence. [R04], [R09]
- **No IQ contradiction promoted:** Existing foundation-owned Fabric routes, report/model scope, and unresolved plugin-DLP questions remain read-only dependencies. This assignment does not introduce new IQ capability, status, citation-inheritance, or protection claims. The familiar-app/agent examples above do not depend on promoting any IQ integration.

### Scope and validation limits

- **No tenant testing:** No customer account, client build, rollout, source permissions, connector consent, agent invocation, or shared-file edit was exercised. The app list is introductory evidence, not a complete meeting/client/format eligibility checklist.
- **No universal agent orchestration established:** Agent Store discovery/invocation and Cowork skill/plugin use are distinct documented mechanisms. No retrieved evidence establishes that all Store agents, third-party apps, and Cowork automatically interoperate. [R06], [R08], [R09], [R10]
- **Deliberate exclusions:** New security-service roles/logos, IQ research, SDKs, agent authoring/deployment tutorials, browser automation, exact models, exhaustive partner catalogs, pricing/licensing matrices, and consumer experiences. Approved encrypted-file and model-policy conflicts remain with the base report and are not resolved here.
- **Research method:** The required topic-relevant Learn search returned results, and a full Cowork-overview fetch returned meaningful content before report creation. Subsequent important Learn pages were fetched in full, with large responses inspected in relevant ranges. Searches converged on established sources. The official Support agent guide was discovered in Learn, its redirect was followed, and its complete meaningful content was read. Secondary web retrieval also verified Learn date metadata. No MCP retry was required.

## 5. Complete Reference List

**Count:** 10 unique official references: **9 Microsoft Learn documents + 1 Microsoft Support document; 0 GitHub repositories; 0 code samples**. All were retrieved **2026-10-31**. Metadata rereads, search snippets, redirect aliases, and read-only project inputs are not additional references. `ms.date` is a documentation date and `updated_at` is a page-update timestamp, not necessarily a feature release date.

### Microsoft Learn Documentation — 9 pages

| ID | Official document | Verified source dates and evidence use |
|---|---|---|
| R01 | [Microsoft Copilot overview][R01] | `ms.date` 2026-10-28; `updated_at` 2026-10-31. App capabilities, app naming, licensing/configuration boundaries, and grounding conflict. |
| R02 | [Overview of Microsoft Copilot Chat][R02] | `ms.date` 2026-09-09; `updated_at` 2026-10-30. Experience-specific grounding and permitted organizational content. |
| R03 | [Copilot Cowork overview][R03] | `ms.date` 2026-09-29; `updated_at` 2026-10-29. Current naming, tasks, Teams communications, work/school GA, App-skill preview. |
| R04 | [Use Copilot Cowork][R04] | `ms.date` 2026-09-14; `updated_at` 2026-10-21. Context selection, shared-file editing, artifact review, skills, session approvals. |
| R05 | [Get started with Copilot Cowork][R05] | `ms.date` 2026-09-14; `updated_at` 2026-10-21. Prerequisites, entry points, task flow, and opening outputs. |
| R06 | [Use plugins with Copilot Cowork][R06] | `ms.date` 2026-08-27; `updated_at` 2026-10-29. Skills versus connectors, enabled plugins, scoped availability, user authorization. |
| R07 | [What's new in Copilot Cowork][R07] | `ms.date` 2026-10-28; `updated_at` 2026-10-29. June 2026 GA entry, September shared-file editing and App-skill Frontier entries. |
| R08 | [Microsoft 365 Copilot connectors overview][R08] | `ms.date` 2026-09-30; `updated_at` 2026-09-30. Indexed versus query-time content access and model/host/authentication boundaries. |
| R09 | [Federated connectors overview][R09] | `ms.date` 2026-10-19; `updated_at` 2026-10-28. Supported hosts, source permissions, connector/tool-dependent actions, and approval-scope distinction. Whole-feature GA date not established. |

### Other Official Microsoft Documentation — 1 page

| ID | Official document | Source-date context and evidence use |
|---|---|---|
| R10 | [Get started with agents in the Microsoft Copilot app][R10] | Retrieved 2026-10-31; publication/update date not established. Full Support document, redirected from the Learn-discovered topic URL. Agent Store discovery, Add/Open invocation, and availability qualifications. |

### Official Microsoft GitHub Repositories and Code Samples

N/A — this bounded end-user connectivity overview includes no repository research, substantive code, or commands.

[R01]: https://learn.microsoft.com/en-us/microsoft-365/copilot/copilot-overview
[R02]: https://learn.microsoft.com/en-us/copilot/overview
[R03]: https://learn.microsoft.com/en-us/copilot/cowork/
[R04]: https://learn.microsoft.com/en-us/copilot/cowork/use-cowork
[R05]: https://learn.microsoft.com/en-us/copilot/cowork/get-started
[R06]: https://learn.microsoft.com/en-us/copilot/cowork/cowork-plugins
[R07]: https://learn.microsoft.com/en-us/copilot/cowork/whats-new
[R08]: https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/overview-copilot-connector
[R09]: https://learn.microsoft.com/en-us/microsoft-365/copilot/connectors/federated-connectors-overview
[R10]: https://support.microsoft.com/en-us/microsoft-365-copilot/get-started-with-agents-in-the-microsoft-365-copilot-app
