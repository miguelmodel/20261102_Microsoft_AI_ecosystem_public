# Research Report: Current Authoring Options, Harness Identity, GitHub Productivity, and Model Choice

**Date:** 2026-11-01
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** authoring-options-v4
**Sources consulted:** 23 Microsoft Learn pages, 9 first-party GitHub documentation pages, 2 official product/announcement pages, 0 GitHub repositories, 0 code samples
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Reference count:** 34 distinct official pages. Repeated retrievals, URL aliases, search snippets, and local binding inputs are not additional references.
**Assignment:** authoring-options-v4; Create mode; brief_version 15; new active cycle 0/3; intended first valid review and canonical overall round R1.
**Review state:** Initial research handoff for caller-managed paired review. No approval or review verdict is asserted.
**Evidence cutoff:** 2026-11-01. All listed pages were retrieved on this date. Explicit release milestones below are distinguished from retrieval dates.

## Scope and evidence conventions

This is a focused delta report, not a replacement ecosystem survey or presentation draft. Binding inputs read: `brief.md` version 15 and the approved `2026-10-30-copilot-studio.md`, `2026-10-30-github-copilot.md`, and `2026-10-30-foundry.md`. Their citations supplied research starting points, and changed conclusions were independently checked. The required Learn preflight search returned relevant harness documentation, and full-document fetch returned meaningful content from **Harnesses in Copilot Studio**. Important Learn sources were fetched in full, not treated as snippet-only evidence. [L01]

The assignment covers named product/model claims for v4 foundation slides 15–16, the changed GitHub Copilot and Foundry material at slides 27–28, and the option comparison at slide 34. Slide 34 reuses **latest v3 slide 22, previously original slide 20**. The binding sequence remains the clean 35-slide primary deck, including v3 slides 4–15 reused at v4 slides 22–33 and the repeated title at slide 35. Flexible pacing is retained. These are binding brief facts, not product-documentation claims.

General evolution, conceptual foundations, infrastructure, observability, orchestration, and controls framing remain with `agent-foundations-v4`. Quantitative METR claims, IQ ownership, and logo identity/rights are excluded. No code, commands, setup walkthrough, pricing matrix, or implementation artifacts are generated, so code-sample search is not applicable.

**Status convention:** “Documented availability” means operational documentation describes a capability as available, not that an independent formal GA milestone was established. Explicit GA, preview, and dated shipping evidence apply only to the named feature and route. Qualifications in this report are for research/notes/provenance, not proposed audience status blocks. [L02][L04][L12][G01][G04][G05][G09]

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Harness Identity, Ownership, and Verified Runtime Contribution](#2-harness-identity-ownership-and-verified-runtime-contribution)
3. [GitHub Copilot App and Broader Productivity](#3-github-copilot-app-and-broader-productivity)
4. [Copilot Studio and Foundry: Overlapping Business-Process Options](#4-copilot-studio-and-foundry-overlapping-business-process-options)
5. [Evidence-Bounded Model Choice](#5-evidence-bounded-model-choice)
6. [Availability, Commercial, Capacity, and Regional Notes](#6-availability-commercial-capacity-and-regional-notes)
7. [Research Limitations and Owner Handoff](#7-research-limitations-and-owner-handoff)
8. [Complete Reference List](#8-complete-reference-list)

## 1. Executive Summary

- **Use the exact documented name and owning experience.** Microsoft Foundry documents the **Microsoft Copilot harness**, an optional managed runtime for prompt agents, in public preview. Copilot Studio continues to document the **GitHub Copilot harness**. Retrieved evidence does not establish that one was renamed to the other, nor a universal product called “Microsoft harness.” [L01][L02][L05][L07][L12]
- **Broaden GitHub Copilot through supported tasks, not an invented audience restriction or runtime promise.** The **GitHub Copilot app** is a desktop application whose core positioning remains agent-driven development. Its documented Projects and canvases also support repository-free feedback analysis, recurring summaries, personal planning, and collaboration on documents, spreadsheets, and slide decks. These support developer-adjacent and low-code-style productivity framing without equating the app with Microsoft 365 Copilot. [G02][G04][G05][G08]
- **Both Copilot Studio and Microsoft Foundry can tailor agents for business processes.** Studio emphasizes graphical low-code authoring and integrated business automation. Foundry spans visual/configuration-based prompt agents through hosted custom code. Explain different authoring/customization emphases, not exclusive classes of jobs. Foundry's retiring declarative workflow designer is not the evidence to use for a durable new-development recommendation. [L03][L05][L10][L11][L22]
- **Model freedom is route-specific.** Foundry documents Azure OpenAI, Anthropic Claude, and open/community model choices. Claude hosting, licensing, APIs, and regions differ from Azure-sold models. Copilot Studio model selection and the GitHub app's preview BYOK route have separate provider and administrative boundaries. A catalog listing does not establish support in every agent runtime. [L06][L08][L09][L15][L17][L19][G09]

## 2. Harness Identity, Ownership, and Verified Runtime Contribution

### Exact current names and history

| Documented term | Owning product/experience | Verified interpretation |
|---|---|---|
| **Microsoft Copilot harness**, shortened to **Copilot harness** | Microsoft Foundry prompt agents | An optional service-operated runtime selected when creating a new prompt agent. Foundry operates its execution environment. The resource remains a prompt agent, invoked through the Responses API. Explicit public preview. [L05][L07][L12] |
| **GitHub Copilot harness** | Microsoft Copilot Studio agents and workflows | A natural-language-first authoring and orchestration framework/runtime. Its current overview and product overview retain this exact name. It is not the GitHub Copilot service. [L01][L02][L03] |
| **GitHub Copilot app** | GitHub Copilot desktop experience | A desktop client built on GitHub Copilot CLI for directing agent work. A client/surface is not the same thing as a Studio or Foundry harness. [G01][G04] |

**Verified naming decision:** “Microsoft Copilot harness in Microsoft Foundry” is supported wording for the requested current Microsoft example. “Formerly the GitHub Copilot harness” is **not verified**. Topic-relevant searches and retrieved Foundry/Studio pages establish two current documented names in different experiences, but contain no explicit rename announcement, effective date, or statement that their implementations are identical. Preserve that history gap rather than correcting the brief into an invented rebrand. [L01][L02][L03][L05][L07]

The June 2026 Studio release history calls its new GitHub Copilot harness experience **production-ready preview**. Foundry's Microsoft Copilot harness guidance independently describes an **initial public preview**. These are distinct status statements, not evidence of a release sequence or product-wide rename. [L04][L07]

### What the named harness contributes

The Studio harness overview explicitly distinguishes the designed agent/workflow, the selected model, and the runtime between them. That runtime decides when to call the model, what components to send, interprets the result, and calls tools. The newer Studio authoring surface configures instructions, knowledge, tools, skills, model choice, connected agents, and memory. This grounds an introductory explanation in actual product behavior rather than treating a harness as another model. [L01][L02]

> “The harness is a runtime that exists between the two: it determines when to call the model, what components to send it, interprets what comes back, and calls the right tools.”
> - Source: [Harnesses in Copilot Studio][L01]

For the **Foundry Microsoft Copilot harness**, the evidence supports four concrete contributions:

- **Instructions and task context:** The prompt-agent definition still contains the model, instructions, and supported tools/capabilities. The runtime coordinates those capabilities rather than requiring customers to deploy harness code. [L07]
- **Tool execution:** Built-ins read/write workspace files, execute shell commands, fetch web content, and delegate to subagents. Supported skills, function tools, web search, and compatible declared tools can extend the agent. Their authentication and regional requirements remain applicable. [L07][L12]
- **State:** Conversations preserve interaction history. Each conversation has a separate workspace for files and execution state, which survives normal sandbox idle/resume/replacement. This is not an unrestricted long-term memory service: Foundry Memory is unsupported on this preview route, and important outputs need durable storage. [L07][L12][L16]
- **Execution boundaries and control:** Foundry manages the sandbox and the approval policy for built-in harness tools during preview. Project roles, agent identity, connections, and policies still control access. Tool enablement is not a complete security boundary when Shell remains enabled, because permitted shell commands can independently read/write files and access networks. These are product-specific caveats, not a replacement controls/governance framework. [L07][L12]

### Difference from GitHub Copilot and other frameworks

> “The GitHub Copilot harness is a Microsoft Copilot Studio authoring and orchestration framework, not the GitHub Copilot service.”
> - Source: [Harnesses in Copilot Studio][L01]

Microsoft also expressly says customer data is not sent to or processed by the GitHub Copilot service **when these agents run in Copilot Studio**, although technology and SDK components are shared. Preserve that scoped service distinction. It does not establish the data handling of every configured external tool, nor automatically describe the Foundry harness's underlying technology. [L01][L02]

Foundry's choice between its managed Copilot harness and a **hosted agent** is not an Agent Framework rename. Microsoft directs customers toward hosted agents when they need to own the framework, orchestration, middleware, runtime policy, dependencies, or process model. Framework selection and managed harness selection are related implementation choices, not interchangeable product identities. [L05][L07]

## 3. GitHub Copilot App and Broader Productivity

### Exact surfaces

The current documentation name is **GitHub Copilot app**. GitHub's product page also uses **GitHub Copilot Desktop App** as a descriptive surface label. The documented application supports Windows, macOS, and Linux and is built on GitHub Copilot CLI. **GitHub Desktop** is a separate entry in the surface guide, with commit-message/summary assistance, and should not be substituted for the new app's name. The supplied download/product URL redirected successfully to GitHub's current Copilot product page. [G02][G04][W01]

**Copilot in the cloud** is a separate documented execution/session experience on GitHub.com and GitHub Mobile. Cloud-sandbox sessions can continue across supported clients including the app, IDE, and CLI. GitHub distinguishes the **client**, the **session**, and the **environment** where execution occurs. App access alone therefore does not imply that every task runs in the cloud or has the same cloud entitlement. [G01][G04]

### Supported broader audience and examples

The app is still positioned as purpose-built for agent-driven development, but its documented capabilities extend beyond manually writing professional software. Projects can start **without a repository**, work from supplied documents, produce artifacts, and coordinate recurring tasks. Canvases provide prompt-customized work surfaces. It is supportable to include business users working alongside development teams, technically curious individuals, and people using low-code-style delegation, while not claiming GitHub markets the entire product as a general-purpose no-code office suite. [G04][G05][G08]

| Supportable productivity example | First-party evidence | Boundary to retain in notes |
|---|---|---|
| Analyze a customer-feedback document and summarize themes without changing code | The Projects guide explicitly supplies this repository-optional example, using project Library material and an instruction not to make code changes. [G05] | Projects are public preview. Results need review, and the prompt's specified material bounds the example. [G05] |
| Produce a recurring weekly feedback summary | The Projects guide documents scheduling a summary of Library feedback, reviewing its next run, and changing or pausing its schedule. [G05] | Do not infer access to an unconnected corporate document store or an unattended M365 permission model. [G05][G01] |
| Plan one's day and coordinate issues, pull requests, and agent sessions | Markdown canvases are documented for personal planning and prioritization. [G08] | This is app/canvas productivity, not evidence of universal Outlook/calendar access. [G08] |
| Collaborate on documents, spreadsheets, and slide decks | Document canvases explicitly support opening, editing, and collaborating on these artifacts directly in the app. [G08] | File/artifact support is not proof that the app is embedded inside Word, Excel, or PowerPoint, or that it inherits M365 permissions. [G08][G04] |
| Prototype a tailored work interface | The canvas guide documents generating and iterating an agentic kanban interface and agent-callable actions from a prompt. [G08][G06] | Say “prototype a work surface,” not “deploy any business app without development or integration work.” [G08] |
| Automate developer-adjacent follow-up | App automations can triage issues daily or check PR review status each morning, with local/cloud options. [G07] | Cloud settings, selected tools, repository access, action identity, and log visibility differ. [G07] |

The defensible audience expansion is **developer assistance plus supported personal/work productivity and developer-adjacent tasks**, including document collaboration and recurring work. It is not accurate to retain a professional-developers-only implication for those documented capabilities. Equally, “GitHub Copilot is the same office-work runtime as Microsoft 365 Copilot” is unsupported by these sources. [G02][G04][G05][G08]

### Capability versus eligibility and safeguards

The app overview says it is available for **all Copilot plans**. Business/Enterprise use requires the app policy to remain enabled, and that policy is separate from CLI policy. The quickstart requires a GitHub account and either a Copilot plan or a configured own-model provider. Its BYOK guide explicitly says no Copilot plan is required when using one's own provider, but that route is public preview and still requires GitHub sign-in and applicable provider setup. “Not just professional developers” is an audience/capability statement, not a promise of unrestricted free usage. [G03][G04][G09]

The app supports Interactive, Plan, and Autopilot session modes, so “people remain in control for review and approval” must not become “every operation requires a new approval.” The automation guide further distinguishes personal/shared action identities and warns that cloud automation prompts and session logs are visible to repository readers. Do not transfer M365 access policies, cloud-agent review gates, or local sandbox protections indiscriminately across these routes. [G04][G07][G01]

### Dated release evidence, without an invented app launch

GitHub documents the newer **Copilot in the cloud** experience as available starting **October 28, 2026** to paid-plan users, subject to policies; Free users retain the older web chat experience. That date is not an app launch or blanket GA date. Independently, Microsoft's **August 27, 2026** Azure DevOps announcement describes its plugin as already available in the GitHub Copilot app, and current Azure DevOps release documentation corroborates supported work-item/PR operations. This establishes first-party shipping evidence for an app extension and app existence by that date, not a formal launch milestone for the whole app. [G01][W02][L13]

## 4. Copilot Studio and Foundry: Overlapping Business-Process Options

### Introductory comparison

| Option | Authoring/customization emphasis | Overlap, not an exclusive job class |
|---|---|---|
| **Microsoft Copilot Studio** | Graphical low-code authoring, natural-language solution creation, connectors, agents, established agent flows, and visual workflows. Professional makers can extend the solution with custom connectors and sophisticated logic. [L03][L11] | Supports conversations and actions within business processes. The harness overview's accounts-payable example includes invoice reading, purchase-order matching, and exception routing for approval. [L01] |
| **Microsoft Foundry** | Visual/configuration-based prompt agents alongside SDK/API authoring and hosted custom code/frameworks. Greater runtime/application customization is an emphasis, not a code-only prerequisite. [L05][L07] | Also supports business-process agents. Its toolbox guidance explicitly illustrates employee onboarding involving guidance retrieval, account creation, provisioning, email drafting, and Teams messaging, each requiring configured tools and authentication. [L22] |

Studio's workflows combine triggers, agents, AI/document actions, branching/looping, connectors, and human-in-the-loop actions on a visual canvas. They can run on demand, on a schedule, or from events. The workflow overview qualifies predictable execution: the defined sequence and rules are predictable, but results can vary when AI or changing data is involved. Avoid promising deterministic business outcomes merely because authoring is visual. [L03][L11]

Foundry can configure an internal business agent through the portal without customer-maintained runtime application code, or host custom code when deeper orchestration/integration behavior is needed. The Microsoft Copilot harness adds a preview managed path for supported multistep tools, skills, files, and commands. These are current alternatives to custom implementation, not evidence that Foundry has only professional-code authoring or that Studio alone can tailor a process. [L05][L07]

For the final decision comparison, retain **start with the job, evaluate options**. Useful selection inputs are the desired authoring style, existing business-system connections, supported channel, need to own custom runtime behavior, and operational responsibilities. Do not divide the customer jobs into “business processes = Studio” and “custom agents = Foundry,” or prescribe a mandatory migration ladder. This recommendation is a synthesis of the documented overlapping paths. [L01][L03][L05][L07][L11][L22]

### Retiring route: preserve the exact boundary

> “Microsoft Foundry is retiring workflows on December 1, 2026.”
> - Source: [Build a workflow in Microsoft Foundry (Preview)][L10]

This refers to the **Foundry declarative/UI workflow experience** described by that page. Microsoft directs new workflows to **Microsoft Agent Framework** and provides migration paths for existing workflows. Do not use that retiring designer as an unqualified starting-point recommendation, and do not transfer its retirement to Copilot Studio workflows or agent flows. Foundry's portal prompt-agent configuration independently establishes its visual path. [L10][L05][L03][L11]

## 5. Evidence-Bounded Model Choice

### Short foundation-level wording

**Microsoft Foundry offers model choice across OpenAI, Anthropic Claude, and open-weight options. Choose the model that fits the task.** This is a bounded fact formulation for the model foundation, not a new slide draft or a claim that every Microsoft product exposes every provider. The task-fit recommendation follows Foundry's documented model comparison using real tasks/customer data and its model-card/deployment filters. [L06][L08][L19]

### What “open” does and does not establish

**Open-source** concerns accessible source and license-granted rights to inspect, modify, and redistribute. **Open-weight** identifies availability of model weights, not by itself an identical license, complete training-source availability, or unrestricted deployment entitlement. Learn explicitly labels OpenAI's **gpt-oss** family as open-weight, while Foundry requires inspection of each model card's License tab and provider terms. Use the narrower documented label rather than calling every nonproprietary-looking catalog entry “open-source.” This is a terminology distinction, not certification of individual AI models against an open-source standard. [L23][L19][L06]

Foundry's broader catalog includes community/open-model options and weight-based managed compute, including documented Phi and Meta Llama choices. Their presence does not certify one common license or guarantee agent-tool support. For the short foundation wording, **open-weight options** is safer than an unqualified “all open-source models.” [L06][L09][L19][L21]

### Route-specific evidence and deployment boundaries

| Route | Verified choice | Availability/deployment boundary |
|---|---|---|
| **Foundry Models sold by Azure** | Azure OpenAI and selected Microsoft/partner model families, including documented open-weight gpt-oss. [L19] | Models, versions, clouds, and deployment types vary. The regional matrix is the authority for the selected combination, not a promise that all OpenAI models work in all Azure locations. Serverless processing can be global, data-zone, or geography-based according to type. [L14][L20] |
| **Claude in Foundry: Hosted on Azure** | Claude models running on Azure infrastructure end-to-end. [L08][L17] | Model-specific availability. Global Standard and selected **Data Zone Standard (US)** options. Anthropic remains seller/operator and independent data processor under Anthropic terms; Azure hosting does not make these Azure-sold OpenAI models. [L08][L17][L18] |
| **Claude in Foundry: Hosted on Anthropic infrastructure** | A separate Claude hosting version operating outside Azure. [L08][L17] | Global Standard only in the hosting comparison. Data can be processed outside Azure and the selected Azure region. Messages/Token Counting are supported; additional API features differ by hosting route. Do not infer support in every Foundry prompt-agent/harness path. [L08][L17][L18] |
| **Open/community models on documented classic managed compute** | Model weights deployed to dedicated managed VM compute; Phi is the deployment guide's example, and catalog choices include other community models. [L06][L21] | This cited route uses a **Foundry (classic) hub-based project** and regional VM/SKU quota. It is not the serverless Global/Data Zone deployment taxonomy. This does not assert that every current Foundry managed-compute offering is classic-only. [L14][L21] |
| **Copilot Studio, GitHub Copilot harness** | Documented OpenAI GPT and Anthropic Claude selection, with other experimental choices. [L15] | The harness-specific regional matrix, early-access environment flags, cross-geo processing, external-provider approval, and model lifecycle apply. No blanket open-weight/BYOM capability is established for Studio by this evidence. [L15] |
| **GitHub Copilot app BYOK** | Documented external-provider options include OpenAI, Azure OpenAI, Foundry, Anthropic, Ollama, Foundry Local, LM Studio, and OpenAI-compatible HTTP endpoints. [G09] | Public preview. Local/cloud providers require their own setup and entitlement where applicable. Endpoint compatibility is not proof that every model supports every agent capability, or that GitHub-hosted model terms apply to external providers. [G09][G04] |
| **Foundry Microsoft Copilot harness** | A deployed prompt-agent model supporting reasoning and tool calling in the project region. [L07][L12] | **BYOM is unsupported in the initial preview.** Catalog breadth and app BYOK do not establish arbitrary-model selection for this harness. [L07][L12] |

The Claude concept page establishes custom-agent use with Microsoft Agent Framework or the Claude Agent SDK and documents the Messages API. It does not establish that every listed Claude model/hosting version can be selected in a Foundry prompt agent or Microsoft Copilot harness. Maintain the distinction between **Foundry model access**, **custom agent/framework integration**, and **specific managed agent compatibility**. [L08][L05][L12][L18]

## 6. Availability, Commercial, Capacity, and Regional Notes

### Feature-level status evidence

| Capability | Evidence at 2026-11-01 |
|---|---|
| Studio GitHub Copilot harness new experience | June 2026 **production-ready preview** milestone. No later overall GA milestone established in the retrieved release history/overview. Natural-language creation remains explicitly preview. [L04][L02][L03] |
| Foundry Microsoft Copilot harness | Explicit **public preview**. New prompt agent required, harness fixed at creation, narrower regional and capability support. [L07][L12] |
| GitHub Copilot app | Current documentation says available across all plans. No formal whole-app GA milestone or original launch date established here. [G04][W02] |
| GitHub app Projects / own-model provider support | Both explicitly **public preview** in their dedicated guides. [G05][G09] |
| Copilot in the cloud on GitHub.com/Mobile | Documented availability starting **2026-10-28**, paid plans and policies required. This is dated shipping evidence, not an independently established blanket GA label. [G01] |
| Azure DevOps app plugin | First-party announcement dated **2026-08-27** says available, with bounded work-item/PR functionality; current Learn release notes corroborate it. Not an app-wide release milestone. [W02][L13] |
| Studio workflows | Documented visual functionality. Overall workflow GA not established by the retrieved overview. July workflow-as-agent-tool and September Copilot-node release entries have their own preview labels. [L11][L04] |
| Foundry declarative workflows | Explicit preview, retiring **2026-12-01**. [L10] |
| Claude hosting versions in Foundry | Current Claude concept page expressly labels Azure-hosted versions GA; Anthropic-hosted model status varies, including preview/gated research preview entries. Keep model/version-specific labels. [L08] |
| gpt-oss on the retrieved Azure-sold model capability page | Its base model entries are labeled **preview** and describe differing serverless/managed-compute paths. Do not infer all gpt-oss routes or fine-tuned variants share one status. [L19] |

### Regions and processing locations

The Foundry Microsoft Copilot harness preview lists exactly **Australia East, Canada Central, Central US, Germany West Central, Japan East, Sweden Central, UK South, West Europe, and West US**. The model and tools must also support the chosen project region. Wider prompt-agent availability does not expand this nine-region list, and sovereign-cloud parity is not established for this harness. [L12]

The Claude regional matrix lists model/hosting-specific Global Standard availability in selected US regions and Sweden Central. The current Data Zone table lists selected Azure-hosted versions in US regions and says **Not available** in its Europe, Asia Pacific, and Middle East/Africa sections. The Claude guide independently specifies **Data Zone Standard (US)**, not a general EU Data Zone offering. Some model/hosting combinations are absent from this matrix despite being acknowledged in the concept/hosting pages, so verify the exact selection in the portal rather than treating an absent row as proof of permanent unavailability. [L09][L08][L17][L18]

For Azure-sold serverless models, deployment location and inference-processing location are not synonyms. Global processing can occur across Azure regions; Data Zone processing stays within the specified supported zone; Standard/Regional Provisioned processing has geography-based qualifications in the dedicated deployment-types article. The regional-matrix introduction instead describes Standard/Regional processing as deployment-region-bound. This inconsistency remains unresolved: use the deployment-specific article's more explicit geography qualification, and do not promise strict single-region processing without service confirmation. [L14][L20]

For the documented classic managed-compute route, regional availability depends on the selected model's compatible VM SKU and subscription VM-core quota. Model-artifact access across Azure regions does not establish deployable compute capacity everywhere. The guide's production-capable infrastructure statement is not a model-level GA designation. [L06][L21]

### Eligibility, consumption, and pricing scope

Claude in Foundry requires a paid Azure subscription, supported billing-account country/region, Azure Marketplace access/terms, and deployment permissions. The current guide excludes CSP subscriptions, enterprise accounts in South Korea, and subscriptions without active pay-as-you-go billing, including student/free-trial/credit-only examples. These are offer/subscription restrictions, not model-quality limits. Both Claude hosting options use Claude Consumption Units billed on the Azure invoice. No exact rates or customer-specific commercial recommendation is supplied. [L18][L17][L09]

Studio's GitHub Copilot harness consumes Copilot Credits, including possible authoring, testing, and evaluation consumption. Studio workflows consume capacity for executed actions. GitHub app access is separately governed by GitHub plan/policy or preview own-provider setup, while the paid cloud experience has its own access statement. Do not describe one subscription, free tier, or quota as covering all these products/routes. Detailed prices and licensing matrices remain outside the brief. [L01][L02][L11][G01][G03][G04][G09]

## 7. Research Limitations and Owner Handoff

1. **Rename/history unresolved.** Current official documentation establishes “Microsoft Copilot harness” in Foundry and “GitHub Copilot harness” in Studio. No explicit rename/history connection was retrieved. Use the Foundry-scoped current name, and omit “formerly” unless separately verified. Do not attach Studio's explicit GitHub-service data statement to Foundry without Foundry-specific evidence. [L01][L02][L05][L07]
2. **App launch/whole-app GA unresolved.** Documentation establishes the app's current name, availability, and broader capabilities. The August 27 plugin announcement proves app existence by that date, and the October 28 cloud statement supplies a separate recent shipping milestone. Neither establishes the app's original launch or a blanket GA status. [G01][G04][W02]
3. **Open-model license certification excluded.** Catalog provider identity, downloadable weights, and an “open” label are not treated as one shared license. No individual model is certified here against an open-source AI definition. The report uses the explicitly documented gpt-oss open-weight label and directs licensing decisions to model cards. [L06][L19][L23]
4. **gpt-oss regional gap.** The Azure-sold capability page documents a preview serverless path for one gpt-oss base model, but the retrieved separate regional matrix contains no gpt-oss row. Therefore no exact serverless region guarantee is established for that family. Managed-compute guidance remains separately scoped. [L19][L20][L21]
5. **Claude matrix and broad hosting prose require care.** Some hosting combinations acknowledged in the concept/hosting comparison lack corresponding matrix rows. The broader Foundry overview's generic Azure-hosted/serverless prose cannot override Claude-specific evidence that one version runs outside Azure and that Anthropic operates both versions. Prefer the provider/hosting-specific sources and preserve exact-combination uncertainty. [L06][L08][L09][L17]
6. **Classic/current managed compute are not collapsed.** The retrieved overview and classic how-to provide a hub-based route. The approved base report already records that newer Foundry material also discusses other managed-compute experiences. This bounded report verifies the cited classic route, not an exhaustive modern compute inventory or a classic-only rule. [L06][L21]
7. **No runtime or tenant validation.** No account eligibility, app installation, administrator policy, provider authorization, quota, model selection, tool execution, or rollout was tested. Published documentation is evidence of supported concepts/routes, not proof of this customer's live entitlement. [L07][L12][L15][L18][G01][G03][G09]
8. **Handoff ownership and fidelity.** Promote only the reviewed named-product deltas into v4 slides 15, 16, 27, 28, and 34 as applicable. Keep Studio's low-code emphasis and Foundry's visual/pro-code overlap. The short model formulation is supplied for the foundation owner's combination with its task-fit principles. No IQ, METR, general foundations, security-service, or logo claims are superseded. No unassigned artifact was modified.

## 8. Complete Reference List

All references were retrieved **2026-11-01**. Dates supplied below are explicit source milestones only, not inferred page-update or product-launch dates. All 23 Learn pages were fetched with `microsoft_docs_fetch`; first-party GitHub and official non-Learn pages were retrieved with `web_fetch`.

### Microsoft Learn Documentation — 23 pages

| ID | Official page | Evidence used |
|---|---|---|
| L01 | [Harnesses in Copilot Studio][L01] | Required-MCP preflight fetch, exact Studio name, runtime role, accounts-payable example, GitHub-service distinction. |
| L02 | [Agents powered by the GitHub Copilot Harness overview][L02] | Current authoring components, harness-transfer boundary, memory/tools, scoped service distinction. |
| L03 | [Copilot Studio overview][L03] | Graphical low-code authoring, business processes, agents/workflows/agent flows, preview natural-language creation. |
| L04 | [What's new in Copilot Studio][L04] | June 2026 production-ready preview and workflow subfeature milestones. |
| L05 | [Agents in Microsoft Foundry][L05] | Portal/configuration and hosted-code paths, Microsoft Copilot harness preview, supported-model boundary. |
| L06 | [Overview of Microsoft Foundry Models][L06] | Provider/catalog choice, model cards, licenses, deployment options, classic managed-compute scope. |
| L07 | [Use the Microsoft Copilot harness with prompt agents][L07] | Exact Foundry name, public preview, instructions/tools/state/control, fixed creation choice, BYOM restriction. |
| L08 | [Claude models in Microsoft Foundry][L08] | Hosting versions, status, APIs/custom agents, model-specific Data Zone US support. |
| L09 | [Foundry Models from partners and community][L09] | Claude/model deployment-region matrices, Marketplace restrictions, model/provider boundaries. |
| L10 | [Build a workflow in Microsoft Foundry (Preview)][L10] | Declarative visual workflow scope, retirement on December 1, 2026, new-workflow direction. |
| L11 | [Workflows overview (GitHub Copilot)][L11] | Studio visual workflows, actions/triggers, human-in-the-loop, capacity, predictable sequence qualification. |
| L12 | [Foundry Agent Service limits, quotas, and regional support][L12] | Nine harness-preview regions, model requirements, unsupported BYOM/Memory/settings, sandbox/state boundaries. |
| L13 | [GitHub Copilot Code Review for Azure Repos now in public preview][L13] | Azure DevOps release documentation corroborating app-plugin work-item/PR operations. |
| L14 | [Deployment types for Microsoft Foundry Models][L14] | Serverless versus managed compute, global/data-zone/geography processing, model-specific availability. |
| L15 | [Model availability and controls (GitHub Copilot)][L15] | Studio harness-specific GPT/Claude selection, cross-geo/early-access and provider-admin restrictions. |
| L16 | [Build with agents, conversations, and responses][L16] | Foundry's persisted conversation history versus individual responses. |
| L17 | [Compare hosting options for Claude models in Microsoft Foundry][L17] | Seller/operator/data processor, Azure versus Anthropic processing, API differences, purchasing/billing. |
| L18 | [Deploy and use Claude models in Microsoft Foundry][L18] | Subscription/Marketplace/region prerequisites and Messages API route. |
| L19 | [Foundry Models sold by Azure][L19] | Azure OpenAI/selected provider families, gpt-oss open-weight label and preview base-model paths. |
| L20 | [Region availability for Foundry Models sold by Azure][L20] | Model/version/deployment regional matrix and identified processing-description/gpt-oss gaps. |
| L21 | [How to deploy and infer with a managed compute deployment (classic)][L21] | Phi example, classic hub-based route, VM quota and production-capable compute. |
| L22 | [What is Toolbox in Foundry?][L22] | Employee-onboarding business-process example with configured heterogeneous tools. |
| L23 | [What is open-source software?][L23] | Source availability and license-granted inspection/modification/redistribution distinction only. |

### First-Party GitHub Documentation — 9 pages

| ID | Official page | Evidence used |
|---|---|---|
| G01 | [GitHub Copilot on GitHub.com and GitHub Mobile][G01] | Copilot in the cloud, October 28, 2026 paid-plan availability, client/session/environment boundaries. |
| G02 | [Where to use GitHub Copilot][G02] | App versus CLI/IDE/web/mobile/GitHub Desktop, qualified cross-surface support. |
| G03 | [Getting started with the GitHub Copilot app][G03] | Account/plan-or-provider prerequisites, app-specific policy, repository/local-folder setup. |
| G04 | [GitHub Copilot app][G04] | Exact name, desktop/CLI relationship, operating systems, all-plan availability, modes and capabilities. |
| G05 | [Working with projects in the GitHub Copilot app][G05] | Public preview, repository-optional feedback analysis, Library artifacts and recurring summaries. |
| G06 | [Built-in skills for the GitHub Copilot app][G06] | Documented create-canvas capability, distinct from plugin/repository skills. |
| G07 | [Using automations in the GitHub Copilot app][G07] | Local/cloud recurring work, identities, policies, selected tools and log visibility. |
| G08 | [Working with canvas extensions in the GitHub Copilot app][G08] | Personal planning, document/spreadsheet/slide collaboration, prompt-built work interfaces. |
| G09 | [Adding LLM models to the GitHub Copilot app][G09] | Preview BYOK, supported providers, GitHub sign-in without a required Copilot plan on this route. |

### Official Product and Announcement Pages — 2 pages

| ID | Official page | Evidence used |
|---|---|---|
| W01 | [GitHub Copilot product page][W01] | Current descriptive “GitHub Copilot Desktop App” surface label. Reached by redirect from the supplied/discovered app feature URL. |
| W02 | [Azure DevOps in the GitHub Copilot App][W02] | Microsoft Developer Blog announcement dated August 27, 2026. Bounded initial app-plugin release evidence. |

### Official Microsoft/First-Party GitHub Repositories — 0

N/A — linked repositories were not independently consulted as evidence.

### Code Samples — 0

N/A — no code or commands generated. Code-sample search was not applicable.

[L01]: https://learn.microsoft.com/microsoft-copilot-studio/harnesses-overview
[L02]: https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/overview
[L03]: https://learn.microsoft.com/microsoft-copilot-studio/fundamentals-what-is-copilot-studio
[L04]: https://learn.microsoft.com/microsoft-copilot-studio/whats-new
[L05]: https://learn.microsoft.com/azure/foundry/agents/overview
[L06]: https://learn.microsoft.com/azure/foundry/concepts/foundry-models-overview
[L07]: https://learn.microsoft.com/azure/foundry/agents/how-to/use-tools-skills-copilot-harness
[L08]: https://learn.microsoft.com/azure/foundry/foundry-models/concepts/claude-models
[L09]: https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-from-partners
[L10]: https://learn.microsoft.com/azure/foundry/agents/concepts/workflow
[L11]: https://learn.microsoft.com/microsoft-copilot-studio/workflows-experience/flows-overview
[L12]: https://learn.microsoft.com/azure/foundry/agents/concepts/limits-quotas-regions
[L13]: https://learn.microsoft.com/azure/devops/release-notes/2026/sprint-279-update
[L14]: https://learn.microsoft.com/azure/foundry/foundry-models/concepts/deployment-types
[L15]: https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/authoring-agent-model-availability
[L16]: https://learn.microsoft.com/azure/foundry/agents/concepts/runtime-components
[L17]: https://learn.microsoft.com/azure/foundry/foundry-models/concepts/claude-models-hosting-comparison
[L18]: https://learn.microsoft.com/azure/foundry/foundry-models/how-to/use-foundry-models-claude
[L19]: https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure
[L20]: https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure-region-availability
[L21]: https://learn.microsoft.com/azure/foundry-classic/how-to/deploy-models-managed
[L22]: https://learn.microsoft.com/azure/foundry/agents/concepts/toolbox-overview
[L23]: https://learn.microsoft.com/training/modules/implement-open-source-software-azure/3-what-open-source-software
[G01]: https://docs.github.com/en/copilot/concepts/copilot-surfaces/copilot-on-github
[G02]: https://docs.github.com/en/copilot/get-started/where-to-use-github-copilot
[G03]: https://docs.github.com/en/copilot/get-started/quickstart-copilot-app
[G04]: https://docs.github.com/en/copilot/concepts/copilot-surfaces/github-copilot-app
[G05]: https://docs.github.com/en/copilot/how-tos/github-copilot-app/working-with-projects
[G06]: https://docs.github.com/en/copilot/reference/github-copilot-app-reference/built-in-skills
[G07]: https://docs.github.com/en/copilot/how-tos/github-copilot-app/using-automations
[G08]: https://docs.github.com/en/copilot/how-tos/github-copilot-app/working-with-canvas-extensions
[G09]: https://docs.github.com/en/copilot/how-tos/github-copilot-app/add-llm-models
[W01]: https://github.com/features/copilot
[W02]: https://devblogs.microsoft.com/devops/azure-devops-in-the-github-copilot-app/
