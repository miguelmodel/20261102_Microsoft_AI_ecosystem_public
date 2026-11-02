# Research Report: Agent Security and Governance Awareness

**Date:** 2026-10-31
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** agent-security-governance
**Sources consulted:** 17 Microsoft Learn pages, 1 other official Microsoft page, 0 GitHub repositories, 0 code samples — 18 unique documentation/web references retained from the initial research. Logo files downloaded by this assignment: 0.
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch

**Assignment:** agent-security-governance. Create-mode report, now aligned to brief_version: 9. Prepared for caller-managed first overall R1/cycle 1 of cap 3. Not reviewed or self-approved.
**Structural repair:** Ownership clarification before the first review, zero review rounds counted. Repair invocation: 2026-11-01 UTC (2026-10-31 caller-local date). Report date/path remain fixed to the initial October 31 research. No substantive claims changed.
**Evidence cutoff:** Service findings retain the initial 2026-10-31 documentation evidence. This repair invocation re-established the required topic-relevant Learn search and full-document fetch of R01; it did not repeat the full research or asset discovery. Status statements below concern the named feature, not its parent brand.
**Scope and ownership:** This assignment now owns **only the four-service security/governance facts** for one introductory awareness slide after original slide 17. Research thesis options are supplied, not presentation content or a build. The approved foundations and M365/Cowork reports and brief Verified facts remain immutable context. IQ ownership stays with ecosystem-foundations. New M365 work/apps connectivity stays with m365-connected-work. **microsoft-ai-product-logos owns all requested logo identity, selection, downloaded catalog, use guidance, and asset provenance across the deck**, with orchestrator-provided byte-download/extraction/hash capability for identified official packs.
**Historical assets, not a review prerequisite:** The earlier `research/assets/2026-10-31-agent-security/logo-source-map.json` remains unchanged as historical provisioning context, **not a build input or current logo catalog**. Its earlier asset gaps do not block this facts-only report's first review. Separate logo research/catalog approval remains required before Content.
**Future canonical review:** `agent-reviews/2026-11-01-ms-docs-research-reviewer-agent-security-governance.md` — first actual review on November 1, caller-managed.

## Contents

1. [Executive Summary](#1-executive-summary)
2. [Four-Service Evidence Matrix](#2-four-service-evidence-matrix)
3. [Slide-Safe Research Thesis Options](#3-slide-safe-research-thesis-options)
4. [Notes-Only Boundaries and Feature Status](#4-notes-only-boundaries-and-feature-status)
5. [Logo Ownership and Historical Source Context](#5-logo-ownership-and-historical-source-context)
6. [Research Limitations](#6-research-limitations)
7. [Complete Reference List](#7-complete-reference-list)

## 1. Executive Summary

**The four names identify complementary responsibilities, not four interchangeable security products or four switches.** Microsoft Entra supplies identity/access controls, Microsoft Purview supplies data security/compliance controls, Microsoft Defender supplies threat protection/investigation, and Microsoft Agent 365 supplies a control plane for observing, governing, and securing agents through these capabilities. Microsoft explicitly describes a distributed security model with centralized visibility. Actual protection depends on the principal, resource, policy, telemetry, and supported integration. [R01], [R03], [R06], [R09], [R12]

**An awareness statement can be simple without promising universal coverage.** Keep the four service names and one conceptual sentence on screen. In notes, preserve the distinctions between agent identities and delegated users, explicit sharing/policy scope, configured audit versus blocking, managed versus unmanaged agents, and feature-specific availability. The specialist pages materially qualify the broader overview language. [R01], [R03], [R06], [R09], [R13]

## 2. Four-Service Evidence Matrix

All names below are current official names. Short labels may omit “Microsoft” when the surrounding context is unmistakable, but the full names are recommended for the four on-screen labels. This identifies product families, not exact licensing SKUs. [R01], [R12]

| Service / distinct introductory role | Load-bearing agent-specific evidence | Boundary and status for speaker notes |
|---|---|---|
| **Microsoft Entra** — identity and access | **Microsoft Entra Agent ID** provides purpose-built agent identities and identity blueprints. Conditional Access evaluates the identity requesting a token and the target resource. Agents can use delegated user access, their own agent identity, or an agent user account. [R02], [R03] | Entra Agent ID has explicit **GA** evidence in its current release summary. **Agent user targeting and agent risk are Preview** in the agent-user policy guide. Policies must target the actual token subject, and API-key access bypasses Entra Conditional Access. Do not say agents automatically inherit all human-user policies. [R03]–[R05] |
| **Microsoft Purview** — data protection and governance/compliance | The **Agent 365-specific** matrix supports auditing, classification, sensitivity labels, DLP, risk/compliance solutions, retention, and eDiscovery. Agent instances must be explicitly included in most policies; files must be explicitly shared with them. [R06] | Label-encrypted files require explicit agent VIEW and EXTRACT rights. New Agent 365 content does **not** inherit source labels. DLP's documented Agent 365 interaction scope is not every tool/action. Matrix support is not an independently established GA label for every control. Cowork has a different matrix and a separately **preview/rolling-out** sensitive-prompt DLP feature. [R06]–[R08] |
| **Microsoft Defender** — threat protection and investigation | Agent-specific documentation distinguishes runtime intervention from near-real-time detection/investigation. Supported runtime routes inspect agent interactions and can block matching threats through configured rules. Detection uses Agent 365 observability data. [R09], [R10] | **Detection/investigation is public preview. Copilot Studio and Foundry runtime routes are Preview.** The Agent 365 tool route excludes unsupported tools. The default cloud rule audits rather than blocks. Connectors/onboarding matter, and unpublished Foundry playground agents are excluded from the documented detection support. [R09]–[R11] |
| **Microsoft Agent 365** — agent oversight/control plane | The official overview organizes Agent 365 around **observe, govern, secure**. Its Microsoft 365 admin-center registry supports agent inventory, ownership-gap identification, lifecycle actions, and consolidated security risk signals from Entra, Purview, and Defender. [R12], [R13] | Explicit **GA from May 1, 2026 for the Commercial segment**, licensed per user. Registry visibility is not proof of enforcement: the registry includes unmanaged agents without Agent 365 risk protection/observability, and onboarding guidance warns that policies/protections might not be enabled. Updated registry risk details are rolling out gradually. [R12], [R13] |

## 3. Slide-Safe Research Thesis Options

These are evidence-backed thesis candidates for the content owner, not a completed slide. Choose **one**, with exactly the four names above. Neither option includes a semicolon or implies a universal protection guarantee. The presentation's verified-local-logo requirement is separately owned by microsoft-ai-product-logos and is not a prerequisite to this facts-only review. [R01], [R12]; binding scope: brief_version 9.

- **Preferred:** “Agent security and governance bring identity, data protection, threat defense and oversight together.” [R01], [R12]
- **Alternative:** “Governed agents need controlled access, protected data, threat awareness and accountable oversight.” [R01], [R03], [R06], [R09], [R13]

Do not add role bullets, feature lists, availability badges, dates, or caveat paragraphs to the face. This is the binding awareness-only presentation contract, not a finding about the products.

## 4. Notes-Only Boundaries and Feature Status

### Identity and access are not automatic permission inheritance

For a delegated call, the user is the token subject. For application-only access, it is the agent identity. For an agent-user call, it is the agent's user account. An agent can use more than one pattern, requiring appropriately targeted policies for each. Entra evaluates policies at token issuance/refresh, while the resource validates the token and makes authorization decisions. “The agent has an Entra ID” does not establish which permissions execute every downstream action or that every resource is protected. [R03]

The particularly useful warning is that policies targeting “all users” do not include agent user accounts. Separately, Conditional Access protects only Entra-secured resources and does not cover an API-key path. Agent user targeting, agent risk, and agent execution-environment targeting have explicit preview evidence in the agent-user guide. Agent ID's GA statement must not erase these feature-level labels. [R03]–[R05]

### Purview's agent-instance controls differ from Cowork controls

For Agent 365, audit, sensitive-data classification, and inclusion in AI regulatory assessments are automatically enabled when an agent instance is created. Other capabilities require policy inclusion. DLP requires explicit agent-instance or containing-security-group scope and supports block/audit for agent-to-human and human-to-agent interactions in the documented Teams, OneDrive/SharePoint, and email locations. The owner must monitor blocking because the agent instance is unaware of a DLP block and later workflow steps can be affected. These are specific defaults and boundaries, not “Purview automatically protects all agent activity.” [R06]

> “Newly created content from Agent 365 doesn't inherit sensitivity labels from the source items.”
> - Source: [Use Microsoft Purview to manage data security & compliance for Microsoft Agent 365][R06]

Keep that warning separate from **Cowork**, whose specialist page documents label inheritance for specified newly created Word, PowerPoint, and Outlook content. Cowork's matrix marks data classification and Compliance Manager unsupported for AI interactions, unlike the Agent 365 matrix. Cowork interactions appear in activity explorer but not the documented Apps and agents dashboard or AI observability page. A shared Purview brand does not make these experiences equivalent. This comparison preserves, rather than replaces, the approved M365 owner's feature-specific caveats. [R06], [R07]

Cowork sensitive-prompt blocking remains **preview and rolling out**. The documented DLP control does not scan directly uploaded prompt-file contents, and labeled-content coverage excludes calendar invites. Do not extrapolate the Agent 365 matrix to Cowork, every plugin, or a downstream data platform. The existing owners' encrypted-file and Fabric-plugin DLP uncertainties remain unresolved and are not re-decided here. [R07], [R08]; read-only context: approved M365/Cowork and foundations reports.

### Defender: observe, detect, and block are different outcomes

The runtime guide documents a built-in **Default** cloud rule that audits without stopping an action. Custom blocking rules must be configured and scoped for supported threats. Runtime coverage differs among Agent 365 supported/onboarded MCP tool invocations, connected Copilot Studio agents, Foundry agents, and separately onboarded endpoint agents. Studio and Foundry runtime paths are explicitly Preview; no independent GA assertion is established here for the other runtime paths. This report establishes a security-route boundary, not new IQ capabilities or comparisons. [R09]

Detection/investigation is explicitly **public preview** and depends on observability data plus the Microsoft 365 connector. Other-platform agents need an Agent 365 SDK observability integration. Foundry threat detection supports published agents, not unpublished/playground-only agents. Local agents require separate endpoint onboarding and Defender for Endpoint in active mode. Discovery or appearing in inventory does not establish identical detection/blocking everywhere. [R10], [R11]

### Oversight and deployment prerequisites

Agent 365 offers a central registry and risk view while security professionals continue configuring controls in their respective products. The registry explicitly counts **unmanaged agents** without Agent 365 risk protection and observability. Its security-template onboarding step says to check each protection's status because policies/protections might not be enabled. Risk counts can lag security portals by up to an hour, and a zero count is no active detected signal, not a security certification. The updated risk-details experience is rolling out by region. [R01], [R13]

For customer follow-up, check entitlement and administrative authority separately. Agent 365 is per-user/Commercial GA. Its overview says at least one qualifying licensed user enables the service, not that one license covers everyone or every control. The Entra Conditional Access guide specifies E7 or Agent 365 paired with at least Entra P1/M365 E3. The agent-user guide requires Conditional Access Administrator; Defender setup requires Security Administrator or higher plus Power Platform administrator collaboration for Studio runtime protection; Purview needs appropriate security/compliance permissions. No complete license matrix, price, quota, government-cloud, or all-region availability promise is established or needed for this awareness slide. [R03], [R05], [R06], [R11], [R12]

## 5. Logo Ownership and Historical Source Context

**Current owner:** microsoft-ai-product-logos owns all logo identity, selection, usage conclusions, reusable downloaded assets, and the reviewed catalog. The orchestrator may provision exact identified first-party bytes and extraction/hash capability. This facts-only assignment performs no further asset research or downloads and makes no current catalog/variant decisions. Separate asset approval remains a before-Content gate, not a prerequisite to this report's first review.

**Historical manifest path:** `research/assets/2026-10-31-agent-security/logo-source-map.json`. Retained unchanged and **not build-consumable**. In the initial attempt, **0 of 4** logos were downloaded/selected; actual file paths, individual asset URLs, retrieval UTC, detected MIME, image inspection, and SHA256 were null/not performed. These describe that earlier attempt, not the status of the new owner's assets or catalog.

The following archived discoveries and caveats preserve the original source record. They are historical provisioning leads, **not approved selections, current logo ownership, or new asset research**.

| Earlier requested basename | Archived official discovery and use guidance | Earlier unresolved variant caveat, not a current selection |
|---|---|---|
| `entra` | The Microsoft Entra architecture-icons page links an official October 2023 ZIP with Entra product icons, a Security visual-identity playbook, and terms. [R14] | The earlier intended label was the **Entra parent brand**, not legacy Azure Active Directory or narrower Entra Agent ID. Package members were not retrieved or inspected, so no exact variant/file was selected. The new logo owner determines the authentic mapping. |
| `purview` | The Entra collection's Security branding playbook and the official Azure/M365 SVG collections were discovery leads only. The retrieved pages did **not** prove which archive member was the requested Purview family logo. [R14], [R16], [R17] | No exact official Purview family image URL was established in the initial attempt. Its caveat excluded unsupported substitutions such as old Azure Purview, a catalog icon, a sensitivity-label icon, or a generic shield. Further source/variant decisions belong to the new logo owner. |
| `defender` | The same official collection leads were available, but the retrieved pages did **not** establish an exact Microsoft Defender family logo member. [R14], [R16], [R17] | No exact official Defender family image URL was established in the initial attempt. Its caveat excluded unsupported substitution of Defender for Cloud, Defender for Endpoint, Windows antivirus, or an unbranded shield. Further source/variant decisions belong to the new logo owner. |
| `agent-365` | The Power Platform icons page explicitly says its **December 2025 update added Microsoft Agent 365**, and supplies an official SVG ZIP. [R15] | The product icon was documented in that collection, not absent from Microsoft sources. The package was not downloaded/extracted in the initial attempt, so the exact member and integrity were not verified. Copilot/Copilot Studio substitutions were not established. Selection and verification belong to the new logo owner. |

Exact collection URLs discovered during the initial research and retained for historical provenance:

- **Entra:** https://download.microsoft.com/download/3/1/a/31a56038-856a-4489-88e4-ee5a1c4352be/Microsoft%20Entra%20architecture%20icons%20-%20Oct%202023.zip?wt.mc_id=microsoftentraicons_downloadmicrosoftentraicons_content_cnl_csasci [R14]
- **Agent 365 / Power Platform:** https://download.microsoft.com/download/498606aa-6d27-4f13-aa5c-1401078c153b/Power-Platform-icons-scalable.zip [R15]
- **Azure discovery lead:** https://arch-center.azureedge.net/icons/Azure_Public_Service_Icons_V24.zip [R16]
- **M365 discovery lead:** https://go.microsoft.com/fwlink/?linkid=869455 [R17]

These are **collection/archive URLs, not four individual logo asset URLs**. They were not saved as image files by this assignment. No archive member, redirect target of the M365 download, image MIME, transparency, or checksum was inferred from the URL. Nothing in this historical list is a build input.

**Historical use caveats retained, current assessment delegated.** The official icon terms permit architectural diagrams, training materials, and documentation, reserve other rights, and require that icons not be distorted or used to represent the customer's own product. Entra also explicitly prohibits use in **Marketing communications**. The initial report did not grant general marketing/public-promotion permission and cautioned against cropping, recoloring, flipping, rotating, or synthesizing substitutes. Those source restrictions are unchanged. Brief_version 9 now explicitly defines this presentation as technical customer education/training with unmodified marks beside service names. The new logo owner assesses source-specific use guidance under that clarified purpose and submits it for independent review. [R14]–[R17]; binding scope: brief_version 9.

The official Agent 365 product page was inspected in the initial research as a secondary discovery source. Its retrieved HTML included promotional artwork containing the icon, not a verified reusable isolated logo asset. No hero/video-thumbnail crop was selected or copied. The page's FAQ also says agents outside Microsoft 365 publishing/Entra-registration environments require additional inventory steps; it does not justify universal automatic onboarding. This service boundary remains part of the facts-only evidence. [W01]

**Handoff boundary:** All active asset work and the final catalog are owned by microsoft-ai-product-logos, with orchestrator capability provisioning. The old manifest stays unchanged as historical context; it is not to be repaired into the new build catalog by this assignment. Separately reviewed asset identity, actual bytes/hashes, and source/use provenance remain required before Content. This report can proceed to its first facts-only paired review independently of that asset work.

## 6. Research Limitations

- **Historical asset attempt, not an active facts-review blocker:** The initial invocation lacked binary-transfer, archive-extraction, and checksum capability, wrote the report and a gap manifest, and established no downloaded logo files. Purview/Defender exact-family-source uncertainty was recorded for that attempt. The manifest is unchanged historical context, not a current catalog. No asset tools were retried or assets inspected/modified in this repair. All active logo research and catalog approval now belong to microsoft-ai-product-logos.
- **Logo-use ownership and retained restrictions:** The icon terms and Entra marketing restriction remain relevant historical source caveats. Brief_version 9 confirms a technical customer-education/training purpose; the new logo owner assesses source-specific terms and usage. This facts-only report grants no trademark permission and is not an asset approval. [R14]–[R17]; binding scope: brief_version 9.
- **Search/index drift:** The search snippet for the old Entra overview said Agent ID was preview. Full fetch redirected to the current overview, and the current release summary explicitly says Agent ID is GA. The full current documents take precedence. Agent user targeting/risk remain explicitly Preview. No exact Agent ID launch date is claimed. [R02], [R04], [R05]
- **Broad overview versus operational guidance:** The cross-cutting page says agents inherit/honor sensitivity labels; the Agent 365-specific Purview page says new content does not inherit them. Use the specialist statement for newly created Agent 365 content. Similarly, use Defender's supported-route and audit/block descriptions rather than generalized “every agent is protected” overview language. [R01], [R06], [R09], [R12]
- **Defender log-detail conflict:** The runtime page says Studio Prompt Shields block events are recorded as behaviors; the detection page says this is not yet supported for Studio. No promise about those specific block records is made here. This does not negate the separately documented detection and protection routes. [R09], [R10]
- **No tenant testing:** No customer license, regional rollout, effective permission, policy enforcement, connector, or telemetry path was tested. Feature-specific status is documentation evidence observed on 2026-10-31, not tenant readiness. Pricing, complete regional/sovereign-cloud matrices, SDK tutorials, exhaustive features, and new IQ/connectivity facts are intentionally excluded.
- **Review/Content boundary:** This report's four-service facts require the caller's first paired review at `agent-reviews/2026-11-01-ms-docs-research-reviewer-agent-security-governance.md`. Logo downloads/catalog approval are not prerequisites to that facts-only review; all asset approval remains separately required before Content. This ownership repair counts zero review rounds and does not constitute reviewed rework or self-approval. Only this report was edited. No manifest, catalog, presentation content, build, diagram, reviewer verdict, validators, or lint were created/modified/run.

## 7. Complete Reference List

**Count:** **18 unique documentation/web references: 17 Microsoft Learn pages + 1 other official Microsoft page.** 0 GitHub repositories, 0 code samples, **0 logo asset files downloaded by this assignment**. Each Learn reference below was fetched in full through the required MCP during the initial research; repeated canonical/redirect fetches count once. This structural-repair invocation successfully repeated the topic-relevant required search and full-document fetch of R01, adding no unique reference or substantive claim. R14–R17 and the asset-discovery part of W01 are retained historical source context, not current logo selections or catalog approval. Search snippets, collection links nested in these pages, immutable project context, and the unchanged historical JSON are not additional documentation references.

### Microsoft Learn Documentation — 17 pages

| ID | Official page | Load-bearing use |
|---|---|---|
| R01 | [Secure AI agents at scale using Microsoft Agent 365][R01] | Four roles, distributed security model, centralized visibility. |
| R02 | [What is Microsoft Entra Agent ID?][R02] | Current name, identities/blueprints, configured third-party integration, entitlement boundary. Old overview redirected here. |
| R03 | [Conditional Access for agents][R03] | Token subject/resource, three access patterns, licensing, API-key and policy-targeting limits. |
| R04 | [What's new in Microsoft Entra Agent ID][R04] | Explicit Agent ID GA evidence, feature-specific preview exception. |
| R05 | [Secure agents that act as users with Conditional Access][R05] | Explicit agent-user/risk preview, all-users exclusion, role prerequisites. |
| R06 | [Use Microsoft Purview to manage data security & compliance for Microsoft Agent 365][R06] | Agent-specific matrix, policy scope, explicit sharing/encryption rights, no new-content label inheritance. |
| R07 | [Use Microsoft Purview to manage data security & compliance for Microsoft 365 Copilot Cowork][R07] | Separate support matrix, label-inheritance and observability boundaries. |
| R08 | [Learn about using Microsoft Purview Data Loss Prevention to protect interactions with Microsoft 365 Copilot, Copilot Chat, and Cowork][R08] | Sensitive-prompt preview/rollout and uploaded-file/calendar exclusions. |
| R09 | [Protect AI agents in real time using Microsoft Defender][R09] | Supported runtime routes, Studio/Foundry preview, default audit versus configured blocking. |
| R10 | [Detect and investigate threats to AI agents using Microsoft Defender (Preview)][R10] | Public preview, observability/connector requirements, published-Foundry-only detection. |
| R11 | [Enable security for AI agents using Microsoft Defender][R11] | Onboarding/connector/role requirements, separate local-agent setup. |
| R12 | [Overview of Microsoft Agent 365][R12] | Observe/govern/secure, Commercial GA May 1, 2026, per-user licensing. |
| R13 | [Manage agent registry in Microsoft 365 admin center][R13] | Unmanaged/ownerless agents, risk-rollout/latency, policy-enablement and third-party boundaries. |
| R14 | [Microsoft Entra architecture icons][R14] | Official icon ZIP, Security playbook, terms including marketing restriction. |
| R15 | [Microsoft Power Platform icons][R15] | Explicit Agent 365 icon inclusion in December 2025, official SVG ZIP and terms. |
| R16 | [Download Azure icons to use in architecture diagrams and documentation][R16] | Official SVG collection discovery lead and use terms. No Purview/Defender member inferred. |
| R17 | [Microsoft 365 architecture templates and icons][R17] | Official SVG collection discovery lead and use terms. No Purview/Defender member inferred. |

### Other Official Microsoft Web Documentation — 1 page

| ID | Official page | Use |
|---|---|---|
| W01 | [Microsoft Agent 365: The Control Plane for Agents][W01] | Secondary official asset discovery; promotional artwork not selected. FAQ onboarding boundary. |

### Official Microsoft GitHub Repositories / Code Samples / Downloaded Assets

N/A — 0 repositories, 0 code samples, and 0 logo files downloaded by this assignment. This facts-only awareness assignment needs no implementation commands. The earlier four-entry JSON remains unchanged as historical asset-gap context, not a build input. The new logo owner manages the separate active asset catalog and its review.

[R01]: https://learn.microsoft.com/security/security-for-ai/agent-365-security
[R02]: https://learn.microsoft.com/entra/agent-id/what-is-microsoft-entra-agent-id
[R03]: https://learn.microsoft.com/entra/identity/conditional-access/agent-id
[R04]: https://learn.microsoft.com/entra/agent-id/whats-new-agent-id
[R05]: https://learn.microsoft.com/entra/identity/conditional-access/policy-agent-user
[R06]: https://learn.microsoft.com/purview/ai-agent-365
[R07]: https://learn.microsoft.com/purview/ai-copilot-cowork
[R08]: https://learn.microsoft.com/purview/dlp-microsoft365-copilot-location-learn-about
[R09]: https://learn.microsoft.com/defender-xdr/security-for-ai/ai-agent-real-time-protection
[R10]: https://learn.microsoft.com/defender-xdr/security-for-ai/ai-agent-detection-protection
[R11]: https://learn.microsoft.com/defender-xdr/security-for-ai/get-started-defender-security-for-ai
[R12]: https://learn.microsoft.com/microsoft-agent-365/overview
[R13]: https://learn.microsoft.com/microsoft-agent-365/admin/agent-registry-overview
[R14]: https://learn.microsoft.com/entra/architecture/architecture-icons
[R15]: https://learn.microsoft.com/power-platform/guidance/icons
[R16]: https://learn.microsoft.com/azure/architecture/icons/
[R17]: https://learn.microsoft.com/microsoft-365/solutions/architecture-icons-templates
[W01]: https://www.microsoft.com/en-us/microsoft-agent-365
