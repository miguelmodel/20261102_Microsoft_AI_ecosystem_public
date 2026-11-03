# Research Report: One Person Across Microsoft Agentic Tools

**Date:** 2026-11-03
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** cross-tool-journey
**Sources consulted:** 24 Microsoft Learn pages, 0 first-party GitHub documentation pages, 0 GitHub repositories, 0 code samples
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Reference count:** 24 unique official pages, fetched in full.
**Assignment:** cross-tool-journey-v10; Create mode; brief_version 27; slide 36.
**Review state:** user-waived review, no verdict. No review round applies and no reviewer approval is asserted.
**Evidence cutoff:** 2026-11-03. Retrieval/API-version dates are not launch dates.

## Scope and method

Read the brief, five assigned reports and header example. OWNERSHIP-01, SCENARIO-V10-01 and GRANT-V10-01 apply. Learn preflight succeeded. Only this report is modified.

Illustrative, not measured, mandatory or runtime-tested. Code-sample search is N/A. Statuses/dates are notes-only.

## Contents

1. Executive summary
2. IQ connection matrix
3. Feature status and documented handoffs
4. Two candidate journeys
5. Recommended slide copy and speaker notes
6. Access, cost, freshness and deployment caveats
7. Research limitations and reconciliation
8. Complete reference list

## 1. Executive Summary

**Recommend Alex, a solution builder:** understand feedback/metrics in Microsoft 365 Copilot, build/test with GitHub Copilot, then ground/share a Foundry agent. This needs configured connections, not automatic context or permission transfer. [1][2][6][12][16][17][19]

**End at team testing:** publishing is GA, selected grounding preview-dependent. [12][15]

## 2. IQ Connection Matrix

**Supported** = documented, not blanket GA. **Preview** = route-specific preview. **Not documented** = unverified, not impossible. Snapshot: **2026-11-03**.

| IQ / source | Microsoft 365 Copilot | GitHub Copilot | Microsoft Foundry |
|---|---|---|---|
| **Work IQ** | **Supported:** licensed Microsoft 365 Copilot experiences/agents, over accessible work content. [1][3] | **Supported:** **Microsoft Work IQ CLI** as local MCP in VS Code/CLI. Remote MCP is another API surface. [2][3][4] | **Preview:** **Work IQ** tool, `work_iq_preview`, uses A2A/user context. Toolkit packages selected options in MCP toolboxes. [5] |
| **Fabric IQ** | **Supported, GA:** **Fabric IQ in Microsoft 365 Copilot Chat** and **Fabric IQ plugin in Copilot Cowork**, scoped to Power BI reports/semantic models. [6][7][22] | **Supported, GA:** **Fabric IQ MCP server**, read-only report/model discovery, metadata and DAX. GitHub Copilot CLI setup is explicit. Other clients need Streamable HTTP/OAuth compatibility. [8][22] | **Preview:** **Fabric IQ** tool, `fabric_iq_preview`, connects to a published data agent, ontology or semantic model through item-specific paths. Not the GA report/model MCP route. [9] |
| **Foundry IQ** | **Not documented natively** in ordinary Chat. **Indirect, preview-dependent overall:** publish a knowledge-grounded Foundry agent to Microsoft Copilot/Teams. Studio routes below are separate. [10][11][12][19] | **Supported:** knowledge-base **`knowledge_base_retrieve`** MCP explicitly names GitHub Copilot. Stable `2026-04-01` returns minimal/extractive grounding. Advanced planning/synthesis is preview. [13][14] | **Preview-dependent:** **Connect a Foundry IQ knowledge base to Foundry Agent Service** uses MCP and a preview `RemoteTool` connection. Overall IQ readiness is **Partial GA**, portal preview. [12][15] |

**Foundry MCP Server** operates Foundry services. **Knowledge-base MCP** retrieves enterprise knowledge. Work IQ/Fabric IQ expose different tools. One connection does not grant the others. [3][8][13][18]

### Copilot Studio and native-source boundaries

Standard-harness **Connect to a Microsoft Foundry agent (preview)** requires a new-portal agent and enabled Activity endpoint. Separately, **Connect to Foundry IQ from an agent (GitHub Copilot)** adds a knowledge base directly as a Studio tool, one connection per agent. The latter is **preview in June 2026** release history. Its “GitHub Copilot” means the Studio harness, not the coding service. [10][20][21][24]

These connections do not establish native-source interchangeability. See the FAQ wording conflict in section 7. [11][20][21]

## 3. Feature Status and Documented Handoffs

### Notes-only status dates

- **Work IQ CLI:** supported GA builds, explicit **June 16, 2026** milestone. Native-M365 experience launch dates unestablished. Remote MCP **`retrieve`** is public preview. [1][2][4]
- **Fabric Chat, Cowork plugin and MCP:** individually GA, listed **September 2026**, no exact day established. Workload/ontology remain preview. [6][7][8][22]
- **Foundry IQ agent connection:** preview SDK or **`2026-08-01-preview` REST**, plus preview **`RemoteTool`**. Stable Search `2026-04-01` does not establish this route's GA. Planning/synthesis remain preview. [12][13][14][15]
- Other matrix/handoff statuses were observed **November 3, 2026**, with original launch dates unestablished. Toolkit/Skill has documented support but no independently established combined-path GA/preview label. API dates are contract identifiers. [5][9][16][17][18][19]

### Handoff evidence and slide-safe interpretation

| Transition | What is documented | Boundary for the proposed story |
|---|---|---|
| **M365 → development** | Work IQ retrieves SharePoint specifications in VS Code. Cowork produces/edits files. [2][23] | Person saves/selects the brief. No chat export, shared memory or label transfer claimed. |
| **GitHub Copilot → Foundry build/deploy** | Toolkit's **Code an agent with Copilot** and included **Microsoft Foundry Skill** cover development/deployment/evaluation. [16][17] | Review/test outputs. Coding assistance is not the business runtime. |
| **GitHub Copilot → Foundry tools** | **Foundry MCP Server**, public preview, connects to VS Code agent mode through Entra. [18] | Optional tooling, not IQ retrieval. |
| **Foundry → Microsoft Copilot / Teams** | GA publishing exposes a stable endpoint and enables Activity protocol. [15][19] | Organization scope needs approval. Separate distribution, not original-chat continuity. |

## 4. Two Candidate Journeys

Synthesized illustrations, not customer case studies or tested chains. Each has exactly three tool steps and an intended outcome, not measured benefits. [2][6][12][16][17][19]

### Candidate A — Alex, a solution builder for a product team — recommended

| Step | Tool → IQ / source used → action → output |
|---|---|
| **1. Understand the need** | **Microsoft 365 Copilot** → **Work IQ** emails/meetings/files + **Fabric IQ** Power BI → compare feedback/adoption metrics and check numbers → reviewed brief Alex saves in SharePoint. [1][2][6] |
| **2. Build and test** | **GitHub Copilot in VS Code** → **Work IQ MCP** specification + repository + **Microsoft Foundry Skill** → implement/review agent code and tests → reviewable implementation and test results. [2][16][17] |
| **3. Ground and share** | **Microsoft Foundry** → **Foundry IQ** product documentation in a search index → configure/deploy, connect knowledge, test and publish to Microsoft Copilot/Teams with approval → assistant for team testing. [10][12][14][19] |

**Final outcome:** **A grounded product assistant for team testing.** Recommend its clear need → implementation → assistant story and reviewed-specification handoff. [2][6][12][19]

### Candidate B — Sam, an operations solution engineer

| Step | Tool → IQ / source used → action → output |
|---|---|
| **1. Capture the recurring issue** | **Microsoft 365 Copilot** → **Work IQ** incident discussions/meetings/procedures → identify recurring questions and acceptance criteria → reviewed problem statement. [1][2][3] |
| **2. Build against business metrics** | **GitHub Copilot CLI** → **Fabric IQ MCP** support-metrics model + supplied brief/repository + **Microsoft Foundry Skill** → examine patterns and implement an assistant/test cases → reviewable code and tests. [8][17] |
| **3. Ground the operational answers** | **Microsoft Foundry** → **Foundry IQ** selected runbooks → connect/evaluate the agent and publish a tested version to Microsoft Copilot/Teams → runbook assistant for team testing. [10][12][19] |

**Final outcome:** **A grounded runbook assistant for team testing.** Developer-tool analytics adds introductory overhead. Grounding remains preview-dependent. [8][12][17]

## 5. Recommended Slide Copy and Speaker Notes

### Audience copy — candidate A

Proposed copy, not a product guarantee. Counts exclude separate product names. [1][2][6][12][16][19]

| Element | Exact proposed copy | Words |
|---|---|---:|
| Title | **Turn customer feedback into a grounded agent** | 7 |
| Optional subtitle | **Illustrative scenario** | 2 |
| Persona | **Alex, solution builder** | 3 |
| Source label 1 | **Work IQ · Emails, meetings and files** | — |
| Source label 2 | **Fabric IQ · Power BI business metrics** | — |
| Source label 3 | **Foundry IQ · Relevant product knowledge** | — |
| Step 1, beneath **Microsoft 365 Copilot** | **Understand the need** | 3 |
| Step 2, beneath **GitHub Copilot** | **Build and test** | 3 |
| Step 3, beneath **Microsoft Foundry** | **Ground and share** | 3 |
| Outcome | **A grounded product assistant for team testing** | 7 |

**Reveals:** sources/persona, steps 1, 2, 3, outcome, one group per click. Sources sit on one side. Connect Work IQ to 1/2, Fabric IQ to 1, Foundry IQ to 3. Arrows mean reviewed progression, not synchronization. Teams stays in notes. No visible semicolons/statuses. [2][6][12][19]

### Speaker notes — six sentences

1. “Alex illustrates one person choosing appropriate tools, not a mandatory journey or measured result.”
2. “Microsoft 365 Copilot combines accessible Work IQ context with Fabric IQ Power BI answers.” [1][6]
3. “Alex reviews a specification, then GitHub Copilot retrieves it through Work IQ and helps build and test using Foundry Toolkit and the Microsoft Foundry Skill.” [2][16][17]
4. “Microsoft Foundry grounds the agent in relevant knowledge through Foundry IQ and publishes the tested version to Microsoft Copilot and Teams with required approval.” [10][12][19]
5. “Licenses, consent, billing and permissions apply, and Power BI reflects the latest successful semantic-model refresh.” [2][3][6][8]
6. “Verified November 3, 2026, publishing is GA but the selected grounding connection is preview-dependent, so the outcome is team testing without automatic context or permission transfer.” [12][15][19]

**Notes provenance:** [1][2][6][12][15][16][17][19]. Dates/statuses remain notes-only.

## 6. Access, Cost, Freshness and Deployment Caveats

- **M365:** Chat analytics requires **Microsoft 365 Copilot Premium** plus licensed/permissioned Power BI access. RLS/OLS apply. A selected report does not exclusively constrain the answer. Data agents/ontologies need an explicitly published M365 agent. [6]
- **Work IQ:** APIs use Copilot Credits independently of M365 Copilot licensing. CLI needs billing assignment/admin consent. Delegated user context is required, app-only unsupported. GitHub access and Foundry permissions/resources are separate. [1][2][3][17]
- **Fabric:** GA report/model MCP is read-only, delegated OAuth, no service-principal/app-only authentication. Foundry's preview data-agent path requires a published agent on paid F2+ or Premium P1+ with Fabric enabled and source access. Do not transfer that capacity requirement to report/model MCP. [8][9]
- **Foundry IQ:** requires Azure AI Search. Document authorization is source-dependent and needs explicit configuration unless documented out-of-box. Prefer bearer-token MCP access with **Search Index Data Reader**, not an admin key. Publishing does not configure document trimming. [11][12][13]
- **Publishing:** requires **Foundry User**, separate Bot Service permissions such as **Azure Bot Service Contributor Role**, and registered `Microsoft.BotService`. Organization scope needs admin approval. Disabled public network access requires the documented API route, not portal publishing. [19]
- **Refresh:** Power BI reflects the last successful model refresh, indexed knowledge its indexer schedule. The reviewed specification is a point-in-time artifact, not synchronization. Recheck changed sources. [6][8][11]
- **Cost/regions:** no prices, sizing or universal quota claims. Check separate consumption, Azure Search/LLM charges and deployment quotas. Fabric IQ MCP excludes sovereign/Power BI-only regions. Chat analytics requires US/EU processing and cross-geo enablement elsewhere. Foundry IQ follows underlying Search/model availability. [3][6][8][11][17]
- **Data boundaries:** review the entire Work IQ/Fabric/Foundry/channel request path. Publishing introduces M365/Teams data handling. Do not promise identical residency, retention, labels or governance. [5][9][19]

## 7. Research Limitations and Reconciliation

1. **Owner alignment:** IQ statuses/scopes, preview dependencies and product handoffs reverified, no journey-blocking contradiction. [2][6][7][8][9][12][16][19][23]
2. **Additions:** direct Studio IQ and GitHub knowledge-base MCP expand owner coverage. Studio's release history establishes preview despite no how-to banner. [13][20][21][24]
3. **Official conflict:** FAQ noninteroperability wording can imply no Copilot consumption. Prefer specific Studio tool/agent procedures for route claims, retaining the owner's native-source portability warning. [10][11][20][21]
4. **GA boundary:** stable MCP behavior does not remove Foundry Agent Service preview dependencies or make preview sources/security GA. [12][13][14]
5. **Cowork conflict:** plugin says DLP unsupported and lacks report/model citations. Approved reports flag Purview disagreement. No universal DLP claim, A uses Chat. [6][7]
6. **Untested:** no tenant/client/identity/channel exercised. Ordinary Chat's native Foundry IQ attachment remains unverified. No GitHub surface-parity claim. Some REST-tab MCP snippets are unavailable. [8][11][13]
7. **Excluded:** measured savings, production approval, automatic export, exhaustive pricing/IQs, code and demos. Waiver is not reviewer approval.

## 8. Complete Reference List

**24 Microsoft Learn documents**, fully fetched **2026-11-03**, with relevant ranges inspected in long responses. No GitHub documentation, repositories or code samples consulted.

### Microsoft Learn Documentation

1. [Work IQ overview](https://learn.microsoft.com/microsoft-365/copilot/extensibility/work-iq/)
2. [Microsoft Work IQ CLI](https://learn.microsoft.com/microsoft-365/copilot/extensibility/work-iq/cli)
3. [Work IQ API overview](https://learn.microsoft.com/microsoft-365/copilot/extensibility/work-iq/api-overview)
4. [Work IQ MCP overview](https://learn.microsoft.com/microsoft-365/copilot/extensibility/work-iq/mcp/overview)
5. [Connect agents to Microsoft 365 with Work IQ (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/tools/work-iq)
6. [Fabric IQ in Microsoft 365 Copilot Chat](https://learn.microsoft.com/fabric/iq/connectors/microsoft-365-copilot-overview)
7. [Fabric IQ in Copilot Cowork](https://learn.microsoft.com/fabric/iq/connectors/cowork-overview)
8. [Get started with the Fabric IQ MCP server](https://learn.microsoft.com/fabric/iq/connectors/fabric-iq-mcp)
9. [Connect agents to Microsoft Fabric with Fabric IQ (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/tools/fabric-iq)
10. [What is Foundry IQ?](https://learn.microsoft.com/azure/foundry/agents/concepts/what-is-foundry-iq)
11. [Foundry IQ frequently asked questions](https://learn.microsoft.com/azure/foundry/agents/concepts/foundry-iq-faq)
12. [Connect a Foundry IQ knowledge base to Foundry Agent Service](https://learn.microsoft.com/azure/foundry/agents/how-to/foundry-iq-connect)
13. [Query a knowledge base using the retrieve action or MCP endpoint](https://learn.microsoft.com/azure/search/agentic-retrieval-how-to-retrieve)
14. [Migrate agentic retrieval code to the latest version](https://learn.microsoft.com/azure/search/agentic-retrieval-how-to-migrate)
15. [Microsoft Foundry portal general availability overview](https://learn.microsoft.com/azure/foundry/concepts/general-availability)
16. [Create an agent with Microsoft Foundry Toolkit for Visual Studio Code](https://learn.microsoft.com/azure/foundry/how-to/develop/create-agent-visual-studio-code)
17. [Use the Microsoft Foundry Skill in coding agents](https://learn.microsoft.com/azure/foundry/how-to/develop/use-microsoft-foundry-skill)
18. [Get started with Foundry MCP Server (preview) using Visual Studio Code](https://learn.microsoft.com/azure/foundry/mcp/get-started)
19. [Publish agents to Microsoft Copilot and Microsoft Teams in the Foundry portal](https://learn.microsoft.com/azure/foundry/agents/how-to/publish-copilot)
20. [Connect to a Microsoft Foundry agent (preview)](https://learn.microsoft.com/microsoft-copilot-studio/add-agent-foundry-agent)
21. [Connect to Foundry IQ from an agent (GitHub Copilot)](https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/foundry-iq-connect)
22. [What's new in Microsoft Fabric?](https://learn.microsoft.com/fabric/fundamentals/whats-new)
23. [Use Copilot Cowork](https://learn.microsoft.com/copilot/cowork/use-cowork)
24. [What's new in Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/whats-new)

### Official GitHub Documentation, Repositories and Code Samples

N/A — no secondary GitHub research or code examples were needed.
