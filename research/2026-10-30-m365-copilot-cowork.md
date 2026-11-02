# Research Report: Microsoft 365 Copilot and Copilot Cowork

**Date:** 2026-10-30
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** m365-copilot-cowork
**Sources consulted:** 25 Microsoft Learn pages, 1 other official Microsoft page, 0 GitHub repositories, 0 code samples — 26 unique references.
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Assignment:** m365-copilot; Create mode; brief_version: 1.
**Evidence cutoff:** Retrieved on 2026-10-30. Publication dates, documentation dates, and retrieval dates are distinguished below.
**Review state:** Initial lint/review not yet run; ready for caller-managed review, not self-approved.

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Overview, Naming, and Feature Status](#2-overview-naming-and-feature-status)
3. [Ready-to-Use Work and Customer Examples](#3-ready-to-use-work-and-customer-examples)
4. [Agents, Extensibility, and Complementary Products](#4-agents-extensibility-and-complementary-products)
5. [How Cowork Fits and Operates](#5-how-cowork-fits-and-operates)
6. [Product-Specific Security and Governance](#6-product-specific-security-and-governance)
7. [Cost, Limits, and Availability Boundaries](#7-cost-limits-and-availability-boundaries)
8. [Research Limitations and Evidence Conflicts](#8-research-limitations-and-evidence-conflicts)
9. [Complete Reference List](#9-complete-reference-list)

## 1. Executive Summary

- **The M365 pillar is the ready-to-use work experience, with customization available when needed.** Microsoft 365 Copilot brings assistance into familiar apps and chat: drafting, summarizing, analyzing information, and working across permitted organizational content. Experience depth depends on licensing, application, and tenant configuration; it is not one identical feature set everywhere. [R01], [R02]
- **Cowork is within that pillar, not a separate fifth platform.** Current Learn documentation uses **Microsoft Copilot Cowork**, shortened to **Copilot Cowork**. It describes an agentic system for delegating multi-step work across Microsoft 365. The June 16, 2026 announcement explicitly established general availability; current documentation confirms GA for work or school accounts. [R03], [R04], [R05]
- **Distinguish four things:** Copilot Chat is the conversational experience; Microsoft 365 Copilot adds broader licensed work capabilities; agents specialize assistance for a domain or process; Cowork executes delegated, multi-step tasks. These categories overlap in user experience but are not interchangeable product entitlements or architectures. [R01], [R02], [R03], [R16]
- **Governance must be checked at the actual feature and integration boundary.** Permissions, approvals, agent data flows, model terms, and Cowork-specific Purview support matter. Cowork GA does not make every skill or control GA: the App skill remains Frontier preview, and sensitive-prompt DLP is separately documented as preview. [R03], [R12], [R14], [R22], [R23]

**Scope:** Research for an introductory, mixed no-code/pro-code customer session; not slides, a script, a demo, or deployment instructions. All substantive Work IQ, Fabric IQ, and Foundry IQ findings are intentionally deferred to ecosystem-foundations and require later approved-source reuse. No approved sibling report was available at launch.

## 2. Overview, Naming, and Feature Status

### Practical distinctions

| Term | Customer-relevant meaning | Boundary to preserve |
|---|---|---|
| **Copilot Chat** | Secure conversational assistance for research, rewriting, uploaded-file analysis, image creation, and interaction with agents. | Primarily web-grounded outside supported app contexts, not universally “web only.” Current documentation describes bounded organizational grounding in Outlook for eligible users without the add-on license. [R02] |
| **Microsoft 365 Copilot** | Licensed work experience with broader reasoning across accessible emails, meetings, chats, files, and other Microsoft 365 content, plus deeper app integration and priority access. | Current documentation also uses Basic/Premium/Pro experience labels. Do not equate any Copilot icon or app name with the full add-on entitlement. [R01], [R02] |
| **Agents** | Specialized assistants configured or developed for particular knowledge, tasks, and actions. Microsoft offers declarative and custom engine approaches. | An agent can answer questions or take actions; “agent” does not guarantee autonomous operation, custom hosting, or the same governance model. [R16] |
| **Copilot Cowork** | An agentic system that plans and carries out multi-step work across Microsoft 365, with visible progress and action controls. | Not merely another name for Chat or for an agent made in Agent Builder. Cowork has its own access, consumption, feature, and compliance guidance. [R03], [R08], [R09] |

### Exact naming

The current Cowork overview and application card use **Microsoft Copilot Cowork**. Microsoft’s June Partner Center material also uses **Microsoft 365 Copilot Cowork**, and Purview retains that longer form. Recommended report terminology is **Copilot Cowork, within Microsoft 365 Copilot**; preserve the exact longer name when identifying a particular source. The requested “Microsoft 365 Cowork” should not be presented as the verified standalone official name. [R03], [R05], [R07], [R12]

Naming is changing elsewhere in the experience: the current M365 overview explicitly says the **Microsoft 365 Copilot app is now called Microsoft Copilot**, and the Chat app is now **Microsoft Copilot Chat**. The report retains the caller’s Microsoft 365 Copilot pillar name while distinguishing the current app label and licensed experience. This is not a claim that every SKU, interface, or document has already adopted identical branding. [R01], [R02]

### Dated status evidence

| Capability | Evidence and safe status wording as of 2026-10-30 |
|---|---|
| **Cowork for work or school accounts** | **Generally available.** The June 16, 2026 Microsoft announcement explicitly announces GA; June 16 and June 29 Partner Center entries corroborate it. Learn’s June 2026 release-history entry and current overview confirm the status. This is direct Cowork evidence, not an inference from the parent product. [R03], [R04], [R05], [R23] |
| **Cowork App skill** | **Frontier preview.** The September 2026 release-history entry names the App skill as Frontier; the overview explicitly applies preview terms and Frontier-program requirements. Do not call no-code app creation GA because Cowork is GA. [R03], [R23] |
| **Cowork local browser use** | **Moved from Frontier to GA in August 2026**, according to Cowork’s release history. Still requires admin enablement and the supported local Edge environment; it is not available on every Cowork surface. [R19], [R23] |
| **Sensitive-prompt blocking with Purview DLP** | **Preview, rolling out**, explicitly stated in the DLP documentation dated October 16, 2026. Other DLP capabilities have their own support descriptions; avoid a single blanket DLP GA label. [R22] |
| **Cowork for personal accounts** | **Preview**, explicitly stated in the overview with documentation date September 29, 2026. Personal-account behavior and consumer protections are outside this organizational report. [R03] |
| **Other app and agent capabilities** | Described as currently documented support, not individually certified GA here. The service description differentiates capabilities and clouds; absence of a preview badge is not treated as proof of feature GA. [R25] |

Source-date context: Cowork’s release-history page has documentation date **2026-10-28** and update timestamp **2026-10-29**; the Cowork overview has documentation date **2026-09-29** and update timestamp **2026-10-29**. These dates identify the inspected documents, not the original launch dates of every item they describe. [R03], [R23]

## 3. Ready-to-Use Work and Customer Examples

### Principal user jobs

The most useful introductory framing is familiar work rather than model selection: catch up on information, find answers, create a first draft, analyze data, prepare for a meeting, and communicate the result. Microsoft documents Word drafting and summarization, Excel analysis and formulas, PowerPoint creation and editing, Outlook drafting and thread summaries, and Teams meeting summaries and action items. Specific availability remains app-, license-, and configuration-dependent. [R01], [R25]

Broader licensed organizational grounding can connect information across permitted emails, meetings, chats, and documents. Chat without that add-on is still useful for web research and user-provided content, and current Outlook-specific grounding can go beyond the open email. Avoid the outdated simplification “Chat has no work data; paid Copilot has all work data.” Neither experience grants additional source permissions. [R02], [R10]

### Illustrative customer scenarios

These are synthesized use-case examples based on documented capabilities, not customer case studies, measured outcomes, or promises of unattended completion. [R01], [R03], [R07], [R14], [R15]

| Audience and job | Example application of the capability | Important boundary |
|---|---|---|
| **Business user — communicate clearly** | Turn a rough account update into a concise Outlook email or rewrite a Word briefing for an executive audience. | Review facts, tone, recipients, and sensitive content before sharing. [R01], [R10] |
| **Project manager — regain context** | Ask the licensed experience to synthesize the latest project discussion across accessible messages, meetings, and files, then identify follow-ups. | Source completeness and permissions affect the answer; generated summaries are not guaranteed factual. [R02], [R10] |
| **Analyst or team lead — explain information** | Analyze a spreadsheet, create useful visuals, and draft a presentation explaining the findings. | Treat calculations, interpretation, and generated presentation content as reviewable work, not an audited conclusion. [R01], [R10] |
| **Operations user — delegate a work package** | Ask Cowork to research an internal topic, create a briefing document, draft a stakeholder email, and schedule a follow-up meeting. | This combines documented Cowork skills; approve sensitive actions and check the artifacts and calendar details. [R03], [R07], [R21] |
| **Business maker — reuse approved expertise** | Configure an onboarding or project-information agent using instructions and approved SharePoint knowledge. | Sharing an agent does not automatically grant access to all its source files. Agent Builder has source-sharing limitations. [R14], [R15] |
| **Maker — prototype an interactive tool** | Ask Cowork’s App skill for a lightweight team coordination app and refine it conversationally. | Frontier preview, not a general production-app platform promise. The usage guide warns that anyone with a shared app link can use the app, including its data; sharing needs deliberate review. [R03], [R06], [R23] |

### A sensible starting approach

Recommended adoption sequence—not a mandatory product migration path—is to select one low-risk job, identify authorized source material and a desired output, use the relevant chat or app experience, and review the result. When delegating to Cowork, specify the outcome, sources, recipients, formatting, and approval expectations; Microsoft’s guidance emphasizes clear instructions and human review. Broader rollout should follow a controlled pilot and plugin review rather than assumed correctness or security. [R07], [R21]

No Azure provisioning, CLI commands, code samples, or Python walkthrough is necessary for this overview. The assignment concerns end-user capabilities and high-level maker choices, not implementation of an SDK solution.

## 4. Agents, Extensibility, and Complementary Products

### From consuming assistance to tailoring it

**Agent Builder** provides guided, natural-language configuration of declarative agents in Microsoft 365 Copilot, with instructions, supported knowledge sources, and testing before sharing or publishing. It fits focused scenarios such as team onboarding or writing guidance. It does **not** support authoring actions that integrate external services; that need can lead to Copilot Studio or a separate pro-code approach. [R14], [R15]

**Declarative versus custom engine** is an architecture distinction, not simply no-code versus code. Declarative agents use Copilot’s orchestrator and models, with configurable instructions, knowledge, and actions. Custom engine agents bring custom orchestration and model choices and require attention to the hosting, security, and compliance responsibilities of that implementation. Both can have Microsoft 365 user experiences; appearing in the same interface does not mean they have identical back ends or protections. [R16], [R17]

**Cowork customization** includes user-authored skills and plugins that add skills, connectors, or both. Skills teach reusable expertise or workflows; plugins package extensions that admins can make available through the Microsoft 365 App Store. This is a separate extensibility surface from simply creating an Agent Builder agent. Review the publisher, requested access, and outputs rather than assuming every extension is Microsoft-validated. [R03], [R07], [R08]

### Complementary roles supported by documentation

| Product relationship | Supported interpretation | Do not imply |
|---|---|---|
| **Microsoft 365 Copilot + Copilot Studio** | M365 supplies the work experience; Studio is an authoring option when workflow logic, external-service actions, channels, or lifecycle controls are required. Agent Builder can support organizational distribution too: audience size alone is not the decision criterion. [R15] | That all Studio capabilities apply to every selected experience, or that copying an agent is a synchronized upgrade. Microsoft documents a separate snapshot with possible reconfiguration and testing. [R15] |
| **Microsoft 365 Copilot + Foundry** | Microsoft documents making Foundry-built agents available through Microsoft Copilot and Teams. M365 is an interaction/distribution surface while the custom implementation retains its own orchestration and service responsibilities. [R17], [R18] | That publishing transfers all context, authorizations, residency commitments, or compliance controls. The publishing guide explicitly requires evaluation of the resulting data flows and applicable Microsoft 365/Teams terms. [R18] |
| **Microsoft 365 Copilot + GitHub Copilot** | The M365 overview identifies GitHub Copilot as an independently licensed AI coding assistant. This supports a high-level distinction between everyday organizational work and software-development assistance. [R01] | Any automatic integration, shared context, shared license, or shared governance. Detailed GitHub feature/status claims remain with the github-copilot assignment. |

For a mixed-skill customer, a reasonable decision aid is: use the ready-made work experience for an individual work outcome; configure a focused agent for repeatable organizational knowledge; evaluate Studio when integration and managed workflows are needed; evaluate a custom engine route when orchestration or models must be owned. These are recommendations derived from Microsoft’s decision guides, not a requirement to use every product. [R15], [R16], [R17]

## 5. How Cowork Fits and Operates

Cowork turns a requested outcome into a series of actions across Outlook, Calendar, Teams, OneDrive, SharePoint, and supported connected services. Documented jobs include creating and editing documents, preparing meeting intelligence, researching a topic, organizing communications, and scheduling prompts. The user can see progress, add instructions while work proceeds, pause, resume, or cancel. It is not limited to returning suggested next steps, but successful completion is not guaranteed. [R03], [R06], [R07]

The normal interaction is to describe the desired result, provide relevant context, follow the progress, approve sensitive actions when requested, and review the output. The current entry point is the **Cowork** toggle next to **Chat** in Microsoft Copilot; the getting-started guide lists browser, desktop, mobile, Outlook, and Teams experiences, with platform differences documented separately. [R06], [R07], [R21]

**Approval wording needs care.** Sensitive actions normally request approval, but users can approve similar actions for the current conversation and review or revoke those preferences. Automated tasks can also be pre-authorized. Therefore, “you approve every single action immediately before it happens” is too absolute, even though the overview’s opening wording is broad. Use: **“You direct the work and control sensitive-action approvals, including any permissions you choose to pre-authorize.”** [R03], [R06], [R08]

Cowork supports scheduled prompts and event-driven tasks, including tasks triggered by matching email or Teams messages. Automated tasks run with the creator’s permissions; the admin guide documents default approval controls, rate limits, loop protection, and audit visibility. These are governed user-delegated automations, not unrestricted authority to act across the tenant. [R06], [R08], [R23]

The cloud-based experience should not be confused with optional local browser automation. Microsoft’s launch announcement describes cloud tasks continuing with the laptop off, but the browser guide says local Edge tasks pause if the device sleeps, the tab closes, or connectivity is lost. For browser work, tenant enablement, supported Edge, the right signed-in profile, and existing site policies are necessary; the desktop app and mobile are not equivalent browser-task surfaces. [R04], [R19]

## 6. Product-Specific Security and Governance

### 6.1 Permissions and source hygiene

Microsoft 365 Copilot uses the underlying user-access model and surfaces content the user can access. That protects against granting new access through Copilot; it does not repair overly broad permissions already assigned in SharePoint or elsewhere. Review source permissions and intended audiences before expanding usage. Sharing an agent is also distinct from authorizing access to each knowledge source. [R10], [R14]

### 6.2 Enterprise data protection, with explicit exceptions

Microsoft documents enterprise data protection for organizational Copilot and Copilot Chat: contractual protections under the DPA and Product Terms, encryption, tenant isolation, and a commitment not to use prompts, responses, or Graph-accessed data to train foundation models. Specific controls depend on subscription and configuration. This is a scoped description of those organizational experiences, not a universal promise for every extension or independently processed model. [R10], [R11], [R13], [R26]

Web queries generated for Bing have separate data-handling practices; the EDP article states that the Bing search service operates separately from Microsoft 365 and that EU Data Boundary and HIPAA-related commitments do not apply to those web queries in the same way. An answer grounded in the web should not be described as proof that no data crossed a service boundary. [R11]

### 6.3 Cowork access and human control

Cowork’s current access guide treats a **spending policy selecting Cowork as an access grant**, not just a budget. A low credit limit or disabled discovery setting is not a reliable denial of access; overlapping policies can grant access through any applicable Cowork-selecting policy. Credit enforcement is asynchronous. Current admin guidance says the former preview agent-entry access control is deprecated. Keep this distinction in admin follow-up rather than turning the introductory explanation into setup instructions. [R08], [R09]

Users remain responsible for reviewing recipients, dates, content, and potentially consequential actions. The application card says generated content can be inaccurate, ambiguous instructions can lead to incorrect actions, and complex tasks may fail. Its mitigations and evaluation descriptions are not guarantees of correctness or immunity to prompt injection. [R06], [R07]

### 6.4 Cowork-specific Purview support

Microsoft explicitly documents Cowork separately because long-running, multi-step work can have different behaviors and feature support. Its current matrix lists audit, sensitivity labels, DLP, eDiscovery, retention, and other supported capabilities, but marks data classification and Compliance Manager unsupported for AI interactions. Cowork interactions appear in activity explorer, while the page identifies gaps in other DSPM dashboards. Do not summarize this as “every Purview control automatically applies.” [R12]

For newly created **Word, PowerPoint, and Outlook** content, the Cowork Purview guide documents inheritance of the source sensitivity label and its protection, using the highest-priority label when multiple sources contribute. Do not extend that specific inheritance statement to every file format or destination. Encrypted-source handling has conflicting documentation, recorded in Section 8. [R12], [R07]

DLP is capability-specific: label-based restrictions can exclude supported file/email content from processing; prompt blocking for sensitive information types is preview and rolling out. The detailed guide also states that direct file uploads into prompts are not content-scanned by this DLP control and that its labeled-email/file coverage does not include calendar invites. These boundaries prevent a defensible claim of universal sensitive-content inspection. [R22]

### 6.5 Models, plugins, and data-processing boundaries

Cowork is now documented as multi-model, not Anthropic-only. Current model guidance identifies both subprocessor-backed options and an independently processed option. Anthropic guidance separately distinguishes Microsoft-subprocessor arrangements from opt-in **models with Data Retention**, for which different terms and provider retention apply. Review the selected model, eligibility, region, provider role, and applicable terms before making residency or retention assurances. This report does not promise identical protections for every selectable model. [R08], [R13], [R23], [R26]

Custom skills and plugins require publisher and data-access review. Agent Builder also has documented data flows between Microsoft 365 and Copilot Studio, governed by the respective product terms; custom engine publishing introduces further service boundaries. A shared front end or successful publication is not evidence that controls, source authorization, or context automatically transfer between products. [R07], [R14], [R15], [R18]

## 7. Cost, Limits, and Availability Boundaries

**Keep the cost message short:** eligible users can access baseline Copilot Chat without the Microsoft 365 Copilot add-on; the broader licensed work experience is different. Organizational Cowork requires the Microsoft 365 Copilot license plus enabled usage-based billing. Cowork consumption is separate from the predictable per-user subscription, so do not present Cowork as unlimited usage included with the license. No currency prices or licensing matrix are needed for this assignment. [R02], [R04], [R08], [R21]

**Practical limits:** Cowork does not freely browse or edit arbitrary local-device files; users can explicitly upload a file as context, while connected cloud-file operations are separately supported. The application card documents a 200 MB per-file upload limit, no deletion of OneDrive/SharePoint files or folders, and limitations around encrypted/rights-protected files. It also documents up to 50 custom skills. These are support details, not material that every introductory customer explanation needs to enumerate. [R06], [R07]

**Availability is not uniform:** the GA announcement uses “worldwide,” while current service documentation differentiates commercial and government-cloud capabilities. Its table does not establish a Cowork-specific government-cloud entitlement. Model availability has further regional and tenant restrictions. Do not infer Cowork availability in every government or sovereign cloud from broader Copilot availability. [R04], [R25], [R26]

**Residency is distinct from availability:** the dedicated residency page dated October 8, 2026 specifies Cowork prompts/responses-at-rest commitments for tenants with Default Geography in Australia, Brazil, Canada, France, Germany, India, Japan, Norway, South Africa, South Korea, Sweden, Switzerland, United Arab Emirates, United Kingdom, or United States. Workspace files and custom skills follow the relevant SharePoint/OneDrive storage commitments. This is not a universal in-country inference-processing guarantee; model-specific exclusions must also be assessed. [R13], [R24], [R26]

**Language and device expectations:** the application card describes Cowork as optimized for English and warns that platform feature availability can vary. The release history describes the GA launch in tier-1 languages, without enumerating them there. This English introductory assignment does not establish a complete supported-language matrix. [R07], [R23]

## 8. Research Limitations and Evidence Conflicts

### Material conflicts and safe handling

| Issue | Retrieved evidence | Research treatment |
|---|---|---|
| **Approval generalization** | The overview opens with approval of each action; detailed usage supports session-scoped approval preferences, and the admin guide supports pre-authorized automated actions. [R03], [R06], [R08] | Prefer the detailed operational guidance. Say sensitive actions are controlled through approval settings, not that every action always requires a fresh click. |
| **Encrypted-file handling** | The Cowork application card says encrypted/rights-protected files cannot be read. The Cowork-specific Purview page describes VIEW/EXTRACT rights, label protection, and encryption support. [R07], [R12] | Unresolved scope conflict. Do not promise processing of protected files. Validate the specific file type, encryption mode, and experience before customer deployment; no tenant test was performed. |
| **Model-control granularity** | Cowork access and model pages call the Anthropic setting tenant-wide. The admin-governance page and Anthropic-provider guide describe user/group scoping. [R08], [R09], [R13], [R26] | Separate the well-supported access-policy rule from disputed model scoping. Validate current admin controls; do not make a blanket “tenant-only” or “per-user everywhere” claim. |
| **EU model availability** | Cowork’s model guide says only GPT models are supported within the EU Data Boundary; the broader Anthropic guide describes EU/EFTA/UK opt-in and boundary exclusions. [R13], [R26] | Prefer the Cowork-specific restriction for Cowork planning; broader opt-in documentation does not prove availability in Cowork. Seek tenant-specific confirmation before commitments. |
| **Model and memory descriptions evolve** | The application card names older Anthropic models and describes conversation-scoped memory. Later release history and model guidance document additional providers, projects, and explicit reference to past chats/tasks. [R07], [R23], [R26] | Do not present Cowork as Anthropic-only, freeze model-version examples, or claim that earlier work can never be referenced. Do not infer persistent autonomous memory either. |
| **Launch-time versus current controls** | The June 16 blog called DLP “coming soon”; later Purview documentation lists Cowork DLP support, with individual functions and preview qualifications. [R04], [R12], [R22] | Use the announcement for the historical GA date, and newer specialist documentation for current control coverage. No blanket DLP GA date is asserted. |
| **Cloud task versus local browser execution** | The launch blog says tasks can continue with the laptop off; the local-browser guide documents pausing on sleep or interruption. [R04], [R19] | Different execution contexts. Retain the local-device dependency when discussing browser automation. |

### Boundaries, dependencies, and research method

- **IQ ownership dependency:** no substantive Work IQ, Fabric IQ, or Foundry IQ capabilities, comparisons, availability, or named integrations are established here. Later incorporation must use ecosystem-foundations findings after caller-managed approval. The presence of those names in retrieved Microsoft pages is not permission to reuse their claims independently.
- **Not tenant-validated:** no licensed tenant, rollout, policy enforcement, plugin authorization, generated app, billing transaction, or agent publication was tested. “Documented” support is not proof of readiness for a particular customer.
- **No blanket status transfer:** the report independently establishes Cowork GA, App-skill preview, browser-use GA, and the sensitive-prompt DLP preview described above. It does not certify every agent, integration, model, or app feature GA. Dated release-history entries and explicit specialist status wording take precedence over parent-product availability. [R03], [R22], [R23], [R25]
- **Discovery drift:** search results for the legacy extensibility root described an older general overview, while full fetch returned a plugin lifecycle navigation page. Detailed agent and authoring pages, fetched in full, support this report’s claims instead of relying on the stale search snippet. Redirected overview and publishing URLs are counted once per document, not as extra sources. [R14], [R15], [R16], [R17], [R20]
- **Source dates:** the references record verified document dates where collected and otherwise explicitly record retrieval date only. Documentation `ms.date` and `updated_at` metadata are not treated as feature release dates. The June 16 announcement and monthly Cowork release-history entries supply dated shipping evidence. [R04], [R23]
- **Intentional exclusions:** consumer-account governance, exhaustive licensing/pricing/setup, complete regional/language matrices, SDK/API implementation, detailed partner catalog claims, and unsupported cross-product integration assumptions. Source gaps and conflicts are not filled with competitor material or third-party guidance.
- **MCP validation:** the required topic-relevant Learn search returned results; full fetch of the Cowork overview returned substantive documentation. Subsequent important Learn sources were fetched in full. Secondary official web retrieval was used for the Microsoft GA announcement and page-date/redirect metadata, not as an MCP substitute.

## 9. Complete Reference List

**Count:** 26 unique sources: **25 Microsoft Learn documents + 1 official Microsoft blog; 0 GitHub repositories; 0 code samples**. All were retrieved on **2026-10-30**. Search snippets, duplicate aliases, page-metadata rereads, and the binding brief are not additional references. Titles below follow retrieved document headings; HTML titles can differ.

### Microsoft Learn Documentation — 25 documents

| ID | Official document | Verified source-date context |
|---|---|---|
| R01 | [Microsoft Copilot overview][R01] | Documentation date 2026-10-28; updated 2026-10-28. Legacy overview URL redirects to this canonical document. |
| R02 | [Overview of Microsoft Copilot Chat][R02] | Documentation date 2026-09-09; updated 2026-10-21. |
| R03 | [Copilot Cowork overview][R03] | Documentation date 2026-09-29; updated 2026-10-29. |
| R05 | [June 2026 announcements][R05] | Relevant Partner Center entries dated 2026-06-16 and 2026-06-29. |
| R06 | [Use Copilot Cowork][R06] | Retrieved 2026-10-30; original publication date not established. |
| R07 | [Application card: Microsoft Copilot Cowork][R07] | Documentation date 2026-09-22; updated 2026-10-29. |
| R08 | [Manage Copilot Cowork for your organization][R08] | Documentation date 2026-09-14; updated 2026-10-30. |
| R09 | [Determine access controls for Copilot Cowork][R09] | Documentation date 2026-08-21; updated 2026-10-21. |
| R10 | [Data, Privacy, and Security for Microsoft Copilot][R10] | Retrieved 2026-10-30; original publication date not established. |
| R11 | [Enterprise data protection in Microsoft Copilot and Microsoft Copilot Chat][R11] | Retrieved 2026-10-30; original publication date not established. |
| R12 | [Use Microsoft Purview to manage data security & compliance for Microsoft 365 Copilot Cowork][R12] | Documentation date 2026-09-30; updated 2026-10-05. |
| R13 | [Anthropic models in Microsoft Online Services][R13] | Documentation date 2026-09-18; updated 2026-10-23. |
| R14 | [Agent Builder overview][R14] | Retrieved 2026-10-30; original publication date not established. |
| R15 | [Choose between Agent Builder and Copilot Studio to build your agent][R15] | Documentation date 2026-10-23; updated 2026-10-27. |
| R16 | [Compare declarative and custom engine agents][R16] | Retrieved 2026-10-30; original publication date not established. |
| R17 | [Custom engine agents for Microsoft 365 overview][R17] | Retrieved 2026-10-30; original publication date not established. |
| R18 | [Publish agents to Microsoft Copilot and Microsoft Teams in the Foundry portal][R18] | Documentation date 2026-09-23; updated 2026-09-28. Redirect target used below. |
| R19 | [Use the local browser with Copilot Cowork][R19] | Retrieved 2026-10-30; includes a note about Edge release week 2026-08-24, not a Cowork launch date. |
| R20 | [Extending Microsoft 365 Copilot with plugins][R20] | Retrieved 2026-10-30; navigation document used only to record discovery drift. |
| R21 | [Get started with Copilot Cowork][R21] | Retrieved 2026-10-30; original publication date not established. |
| R22 | [Learn about using Microsoft Purview Data Loss Prevention to protect interactions with Microsoft 365 Copilot, Copilot Chat, and Cowork][R22] | Documentation date 2026-10-16; updated 2026-10-27. |
| R23 | [What's new in Copilot Cowork][R23] | Documentation date 2026-10-28; updated 2026-10-29; contains dated monthly release entries. |
| R24 | [Data Residency for Microsoft 365 Copilot (including Cowork)][R24] | Documentation date 2026-10-08; updated 2026-10-08. |
| R25 | [Microsoft Copilot — service description][R25] | Retrieved 2026-10-30; current support matrix, not a release-date ledger. |
| R26 | [Choose a model for Copilot Cowork][R26] | Retrieved 2026-10-30; tenant-dependent current model guidance. |

### Other Official Microsoft Sources — 1 page

| ID | Official page | Date and evidence use |
|---|---|---|
| R04 | [Copilot Cowork is now generally available][R04] | Published 2026-06-16. Retrieved through the official Learn-linked `aka.ms/CoworkGA` redirect. Used for historical GA and launch-context evidence, not to override later specialist documentation. |

### Official Microsoft GitHub Repositories and Code Samples

N/A — no repository or code sample was used; this is a product overview without implementation code.

[R01]: https://learn.microsoft.com/en-us/microsoft-365/copilot/copilot-overview
[R02]: https://learn.microsoft.com/copilot/overview
[R03]: https://learn.microsoft.com/copilot/cowork/
[R04]: https://www.microsoft.com/en-us/copilot/blog/2026/06/16/copilot-cowork-is-now-generally-available/
[R05]: https://learn.microsoft.com/partner-center/announcements/2026-june
[R06]: https://learn.microsoft.com/copilot/cowork/use-cowork
[R07]: https://learn.microsoft.com/copilot/cowork/responsible-ai/copilot-cowork-application-card
[R08]: https://learn.microsoft.com/copilot/cowork/cowork-admin-governance
[R09]: https://learn.microsoft.com/copilot/cowork/cowork-access
[R10]: https://learn.microsoft.com/microsoft-365/copilot/microsoft-365-copilot-privacy
[R11]: https://learn.microsoft.com/microsoft-365/copilot/enterprise-data-protection
[R12]: https://learn.microsoft.com/purview/ai-copilot-cowork
[R13]: https://learn.microsoft.com/microsoft-365/copilot/connect-to-ai-subprocessor
[R14]: https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder
[R15]: https://learn.microsoft.com/microsoft-365/copilot/extensibility/copilot-studio-experience
[R16]: https://learn.microsoft.com/microsoft-365/copilot/extensibility/agents-overview
[R17]: https://learn.microsoft.com/microsoft-365/copilot/extensibility/overview-custom-engine-agent
[R18]: https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/publish-copilot
[R19]: https://learn.microsoft.com/copilot/cowork/cowork-local-browser
[R20]: https://learn.microsoft.com/microsoft-365-copilot/extensibility/
[R21]: https://learn.microsoft.com/copilot/cowork/get-started
[R22]: https://learn.microsoft.com/purview/dlp-microsoft365-copilot-location-learn-about
[R23]: https://learn.microsoft.com/copilot/cowork/whats-new
[R24]: https://learn.microsoft.com/microsoft-365/enterprise/m365-dr-service-copilot?view=o365-worldwide
[R25]: https://learn.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/microsoft-365-copilot
[R26]: https://learn.microsoft.com/copilot/cowork/cowork-models
