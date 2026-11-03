# Research Report: Tools, MCP and Plugins

**Date:** 2026-11-03
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** tools-mcp-plugins
**Sources consulted:** 23 Microsoft Learn pages, 4 GitHub documentation pages, 1 MCP-standard page used as evidence, 0 repositories, 0 code samples
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Reference count:** 28 cited pages. Discovery-only reads, snippets, duplicate redirects and local inputs are excluded.
**Assignment:** tools-mcp-plugins-v10; Create mode; brief_version 27; slide 20 of 38.
**Review state:** user-waived review, no verdict. No review round applies.
**Evidence cutoff:** 2026-11-03. Release dates are distinguished from observation dates.

Read-only inputs: `brief.md` v27, the four requested V10 decisions, Verified facts and the header exemplar. Learn search/full-fetch preflight passed. Steering wheel and numbering are caller-directed analogies/layout.

**Contents:** [Summary](#1-executive-summary) · [Definitions](#2-customer-friendly-definitions) · [Products](#3-product-findings--notes-and-provenance-only) · [Slide copy](#4-recommended-slide-copy) · [Speaker notes](#5-speaker-notes) · [Practical guidance](#6-practical-guidance) · [Caveats](#7-caveats-and-research-limitations) · [References](#8-numbered-references)

## 1. Executive Summary

Tools, MCP and plugins work together rather than compete. All four products provide verified examples, but packaging, authentication, protocol features and approvals differ. The steering-wheel slide should explain **how an agent acts**, not suggest extra permissions or guaranteed safety. [1][4][7][8][13][14][23][24][26][28]

## 2. Customer-Friendly Definitions

| Term | Customer explanation |
|---|---|
| **Tools** | Functions/actions an agent calls to retrieve information or do work. They can be read-only and need not use MCP. [1][5][8] |
| **MCP — Model Context Protocol** | An open standard connecting agents to tools and data exposed by MCP servers. It grants no automatic permissions. [4][19][23][28] |
| **Plugins / connectors** | Plugins package extensions. Connectors integrate services/data sources. A plugin can reference a connector or MCP server. They are not synonyms. [7][14] |

> "Tools: Functions that a language model can call to perform an action"
> - Source: [Extend your agent with Model Context Protocol][8]

Tools overlap Data grounding when retrieving relevant knowledge. This slide emphasizes external capabilities/actions, not a strict read/write boundary. [1][5][8][13]

## 3. Product Findings — Notes and Provenance Only

**Status key:** Observed **2026-11-03**. **Documented** = capability verified, formal GA/preview milestone and launch date **unverified**. No preview banner does not prove GA, and portal GA does not establish individual-tool GA. [3]

### Microsoft Foundry

| Current terms and capability | Status/date and qualification |
|---|---|
| **Tools**, **Toolboxes**: built-ins include web/file search and code interpreter. Toolbox exposes curated tools through a managed MCP endpoint. [1][2] | Tools discovery/build and Toolboxes: **GA portal experiences**, launch date unverified. Individual catalog tools vary. [3] |
| **MCP tool / MCP servers**: connect external tools/data with selected tools and configured authentication. [4] | **Documented**. Long-running **MCP tasks** support is preview. [4] |
| **OpenAPI tools**: REST APIs described by OpenAPI 3.0/3.1, directly or through Toolbox. [2][5] | **Documented**. Authentication, model/region and target permissions apply. [5] |
| MCP/toolbox approvals: explicit approval requests/responses. [4][6] | **Documented**. Hosted-agent runtime must enforce toolbox approvals. Endpoint alone does not block calls. [6] |

### Copilot Studio

| Current terms and capability | Status/date and qualification |
|---|---|
| **Tools / Power Platform connectors**: prebuilt/custom API wrappers expose operations as tools. [7] | **Documented**. User credentials default, maker credentials optional. Entitlements vary. [7] |
| Standard-harness **MCP**: onboarding wizard, tools/resources, generative orchestration required. [8][9] | **Documented**. Connector data policies apply. Streamable supported, SSE unsupported after August 2025. [9] |
| **MCP server as a tool (GitHub Copilot)**: separate **GitHub Copilot harness** route, not GitHub Copilot service. [11] | **Preview**, **July 2026** release history and current how-to. [11][12] |
| **Agent flows**: standard-harness automation with **When an agent calls the flow** can become tools. [10] | **Documented**. New-harness **workflow-as-tool** is separately **preview**, July 2026. [12] |

### Microsoft 365 Copilot

| Current terms and capability | Status/date and qualification |
|---|---|
| **MCP and API plugins for declarative agents**: REST/OpenAPI and remote-MCP custom **actions**. [13] | **Documented**. Actions inside declarative agents, not standalone experiences. MCP discovery can be dynamic or pinned. [13] |
| **Microsoft 365 Copilot plugin / Microsoft Copilot Cowork plugins**: packages combine capabilities. Cowork supports skills, connectors or both. [14][17] | **Documented**. Individual labels vary. Admin deployment does not authorize external-service sign-in. [17] |
| **Microsoft 365 Copilot connectors**: **synced** indexes into Microsoft Graph, **federated** uses MCP for live access. [15][16] | **Documented**. Conditional writes documented, Researcher read-only. General/specific guides conflict. Not Power Platform connectors. [7][15][16] |

### GitHub Copilot

| Current terms and capability | Status/date and qualification |
|---|---|
| **MCP servers**: IDE agent mode, **Copilot cloud agent** (assignment's coding-agent route), **GitHub Copilot CLI**. [24] | **Documented**. CLI supports local/remote servers. IDE/cloud OAuth and protocol subsets differ. [24] |
| **GitHub MCP server**: GitHub-maintained, built into CLI. [24] | **Documented**. Cloud defaults: read-only current-repository token. Broader access needs explicit credentials. [24] |
| **Plugins for GitHub Copilot**: bundles including MCP configurations. [26] | **Documented** in CLI, VS Code, Copilot app/cloud, with component-specific support. [26] |
| **Extensions for GitHub Copilot**: code-backed tools/commands. Distinct from IDE extensions and legacy **GitHub App-based Copilot Extensions**. [27] | CLI extensions **experimental**. Legacy integration **retired**, effective date unverified. Not a verified rename to plugins. [27] |

### Microsoft Servers: Hosted Versus Microsoft-Published

| Server and hosting | Status/date and qualification |
|---|---|
| **Microsoft Learn MCP Server**: remote documentation search, full fetch and sample search. [18] | **Publicly available**, formal GA/date unverified. Public content, no authentication or server-use charge. [18] |
| **Azure MCP Server**: Microsoft-published, commonly local or **self-hosted** remotely on Container Apps. [19][20] | **Documented**. Not automatically Microsoft-hosted SaaS. User/managed-identity Azure RBAC applies. [19][20] |
| **Foundry MCP Server**: **cloud-hosted** Foundry-service tools with Entra authentication, not an agent's MCP tool. [21] | **Public preview**, launch date unverified. [21] |
| **Microsoft-hosted MCP servers / Microsoft Agent 365**: workload tools/governance. [22] | **Mixed, server-specific**. Tenant/rollout/licensing/approval apply. Listed legacy Microsoft 365 workload servers are preview and unsuitable for new production projects. [22] |

## 4. Recommended Slide Copy

**Slide 20 title:** Tools, MCP and plugins

**Body — 9 words:**  
Tools turn agent decisions into actions across connected systems.

**Three bullets — 5, 7 and 5 words:**
- Tools: callable functions and actions
- MCP: standard connections to tools and data
- Plugins and connectors: packaged integrations

**Optional example — one named product:**  
Example: MCP servers in Microsoft Foundry.

**Provenance:** Synthesized from definitions. Notes separate plugins/connectors. No semicolons or status labels. Caller placement: steering wheel after Data grounding, before Observability. [1][4][7][8][14][28]

## 5. Speaker Notes

1. The steering wheel represents how an agent acts on the world. [1]
2. A tool can retrieve relevant knowledge or perform an action. [5][8]
3. MCP standardizes connections to servers that expose tools and data. [4][28]
4. Plugins package extensions, while connectors integrate specific services. [7][14][26]
5. Choose appropriate tools, limit access, and require approvals for consequential actions. [4][23]

Status/date details stay in section 3, not on the slide. Note 1 is the caller's teaching analogy.

## 6. Practical Guidance

- **Least privilege:** Check the actual user/agent/maker/managed identity, scope operations, enforce downstream authorization and test denials. Tool discovery is not extra permission. [6][7][19][23]
- **Approvals:** Review tool, arguments and target. Cloud delegation can invoke tools autonomously, CLI can preapprove, and declarative-plugin defaults can be overridden. Hosted runtimes must enforce approvals. Never promise a prompt before every call. [4][6][13][24][25]
- **Trust/selection:** Review third-party operators, data handling and updates. Names/descriptions affect selection but can contain prompt injection. Keep tool sets small, test, log and enforce permissions independently of model decisions. [4][5][11][13][23][24]

## 7. Caveats and Research Limitations

- **Milestones:** Unknown statuses/dates remain unverified. July 2026 Studio evidence is month-level. Do not inherit GA from a parent product. [3][12]
- **Connector conflict:** The overview forecasts writes from early October 2026 yet says read-only. Prefer the specific guide's conditional writes and Researcher exclusion, verifying connector/host/tenant support. [15][16]
- **Policy conflict:** GitHub's MCP overview describes policy broadly, but CLI guidance says MCP-enablement/registry-URL policies are unsupported. No uniform enforcement claim. [24][25]
- **Compatibility:** Studio standard harness supports tools/resources. Cloud agent supports tools, not MCP resources/prompts. Shared MCP names do not prove parity. [8][24]
- **Commercial/region context:** Entitlements, flow capacity and model/tool/external-service charges apply. Foundry tools depend on model/region. Agent 365 varies by tenant/region. No universal price/quota/availability promise. Only Learn MCP server use is explicitly free. [1][5][7][10][18][22][25]
- **Exclusions:** No code or sample search. Prompts/instructions/skills and IQ research stay with other owners. No logos, reviews, presentation or status files written.

## 8. Numbered References

Retrieved 2026-11-03. Learn pages fetched in full. Large pages inspected by relevant conceptual/security/limitation sections. No code reused.

### Microsoft Learn Documentation — 23 Pages

1. [Agents in Microsoft Foundry][1]
2. [What is Toolbox in Foundry?][2] — tool-catalog redirect, counted once.
3. [Foundry portal general availability overview][3]
4. [Connect agents to MCP servers][4]
5. [Connect agents to OpenAPI tools][5]
6. [Use a toolbox with a hosted agent][6]
7. [Power Platform connectors as tools][7]
8. [Extend your agent with MCP][8]
9. [Connect your agent to an existing MCP server][9]
10. [Agent flows overview][10]
11. [Add an MCP server as a tool (GitHub Copilot) (preview)][11]
12. [What's new in Copilot Studio][12] — July 2026.
13. [MCP and API plugins for declarative agents][13]
14. [What is a Microsoft 365 Copilot plugin?][14]
15. [Copilot connectors overview][15]
16. [Federated connectors overview][16]
17. [Use plugins with Copilot Cowork][17]
18. [Microsoft Learn MCP Server overview][18]
19. [What is the Azure MCP Server?][19]
20. [Deploy self-hosted Azure MCP Server with Copilot Studio][20]
21. [Get started with Foundry MCP Server (preview)][21]
22. [Understand MCP server options in Agent 365][22]
23. [Least privilege for AI agents][23]

### First-Party GitHub Documentation — 4 Pages

24. [Model Context Protocol (MCP)][24]
25. [GitHub Copilot CLI][25]
26. [Plugins for GitHub Copilot][26]
27. [Extensions for GitHub Copilot][27]

### MCP Standard — 1 Page

28. [What is the Model Context Protocol?][28] — resolved destination of `https://modelcontextprotocol.io/introduction`.

[1]: https://learn.microsoft.com/azure/foundry/agents/overview
[2]: https://learn.microsoft.com/azure/foundry/agents/concepts/toolbox-overview
[3]: https://learn.microsoft.com/azure/foundry/concepts/general-availability
[4]: https://learn.microsoft.com/azure/foundry/agents/how-to/tools/model-context-protocol
[5]: https://learn.microsoft.com/azure/foundry/agents/how-to/tools/openapi
[6]: https://learn.microsoft.com/azure/foundry/agents/how-to/tools/use-toolbox-hosted-agent
[7]: https://learn.microsoft.com/microsoft-copilot-studio/advanced-connectors
[8]: https://learn.microsoft.com/microsoft-copilot-studio/agent-extend-action-mcp
[9]: https://learn.microsoft.com/microsoft-copilot-studio/mcp-add-existing-server-to-agent
[10]: https://learn.microsoft.com/microsoft-copilot-studio/flows-overview
[11]: https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/tools-add-mcp-server
[12]: https://learn.microsoft.com/microsoft-copilot-studio/whats-new
[13]: https://learn.microsoft.com/microsoft-365/copilot/extensibility/overview-plugins
[14]: https://learn.microsoft.com/microsoft-365/copilot/extensibility/plugins-overview
[15]: https://learn.microsoft.com/microsoft-365/copilot/connectors/overview
[16]: https://learn.microsoft.com/microsoft-365/copilot/connectors/federated-connectors-overview
[17]: https://learn.microsoft.com/copilot/cowork/cowork-plugins
[18]: https://learn.microsoft.com/training/support/mcp
[19]: https://learn.microsoft.com/azure/developer/azure-mcp-server/overview
[20]: https://learn.microsoft.com/azure/developer/azure-mcp-server/how-to/deploy-remote-mcp-server-copilot-studio
[21]: https://learn.microsoft.com/azure/foundry/mcp/get-started
[22]: https://learn.microsoft.com/microsoft-agent-365/tooling-servers-overview
[23]: https://learn.microsoft.com/security/zero-trust/sfi/least-privilege-for-ai-agents
[24]: https://docs.github.com/en/copilot/concepts/customizations/mcp
[25]: https://docs.github.com/en/copilot/concepts/copilot-surfaces/copilot-cli
[26]: https://docs.github.com/en/copilot/concepts/customizations/plugins
[27]: https://docs.github.com/en/copilot/concepts/customizations/extensions
[28]: https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro.md
