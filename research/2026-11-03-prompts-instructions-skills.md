# Research Report: Prompts, Instructions and Skills

**Date:** 2026-11-03
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** prompts-instructions-skills
**Sources consulted:** 22 Microsoft Learn pages, 8 first-party GitHub documentation pages, 0 GitHub repositories, 0 code samples
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Reference count:** 30 distinct official pages. Search-only snippets, redirects and local binding inputs are not additional references.
**Assignment:** prompts-instructions-skills-v10; Create mode; brief_version 27; focused evidence for new slide 18.
**Review state:** user-waived review, no verdict. No review round applies.
**Evidence cutoff:** 2026-11-03. All references retrieved on this date. Release milestones are identified separately.

Binding inputs read: `brief.md` frontmatter, including GRANT-V10-01, REVIEW-WAIVER-V10-01, SCENE-V10-01 and NUMBERING-V10-01, its complete Verified facts section, and the earlier authoring-options report's header/source conventions. Caller decisions place the GPS foundation at slide 18, between Harness (17) and Data grounding (19). No binding input is changed.

Learn preflight search and full fetch of the Foundry harness guide returned meaningful content. Key pages were fetched in full. No code or code-sample search is needed.

**Contents:** [1. Summary](#1-executive-summary-and-definitions) | [2. Products](#2-product-findings-and-status) | [3. Slide copy](#3-recommended-slide-copy) | [4. Notes](#4-speaker-notes) | [5. Guidance](#5-practical-guidance-and-security-caveats) | [6. Limitations](#6-research-limitations) | [7. References](#7-numbered-references)

## 1. Executive Summary and Definitions

**Distinguish request, standing guidance and packaged know-how.** These overlap: prompts and skills both contain instructions. Products differ in how they store and apply them. [04][05][13][26][28]

| Foundation | Customer-friendly definition | Important distinction |
|---|---|---|
| **Prompts** | Express the task, context and desired output. | Typed requests or saved templates, not necessarily one-off messages. [04][08][28] |
| **Instructions** | Set role, ongoing behavior, boundaries and response style. | Agent/custom instructions are not universally interchangeable with system instructions. Studio makers cannot edit its fixed orchestrator system prompt. GitHub custom instructions apply automatically within supported scopes. [13][21][26] |
| **Skills** | Package reusable task-specific know-how, optionally with scripts/resources. | Agent Skills-style packages require `SKILL.md`. Runtimes can load relevant content on demand or inject it at startup. Skills may guide tool use without being the tool. [02][05][15][29] |

The GPS analogy explains **direction and know-how**, not guaranteed execution or security. The harness executes work, knowledge grounds it, and configured tools provide actions. Instructions cannot create unconfigured capabilities or grant resource access. [01][03][13][17]

## 2. Product Findings and Status

**Status:** **D** = documented on 2026-11-03, formal GA/preview milestone or release date **unverified**. No preview badge does not prove GA. Explicit statuses apply only to the named route. [01][04][09][18][27]

### Microsoft Foundry

| Capability | Verified finding | Status and date |
|---|---|---|
| **Prompt agents**, **Instructions** | Saved definitions version model, instructions and tools. **Agent Builder in Microsoft Foundry Toolkit for Visual Studio Code** supports versions, local prompts and dataset variables. [13][19] | D. |
| **Skills**, **Microsoft Copilot harness** | Versioned Skills API stores `SKILL.md` packages. Direct prompt-agent use requires the Copilot harness and same-project skills. Agent versions store immutable skill versions. Hosted/local loading differs. [01][05] | Skills **preview**, harness **public preview**, checked 2026-11-03. Launch dates unverified. |
| Prompt templates | Jinja **Prompt tool** templates belong to **Foundry (classic)** hub-based Prompt flow, not new Foundry projects. Avoid this legacy recommendation. [14] | Retirement **2027-04-20**. Containers no longer updated. |

### Microsoft Copilot Studio

| Capability | Verified finding | Status and date |
|---|---|---|
| **Instructions**, **generative orchestration** | Instructions guide configured capabilities. Generative orchestration dynamically selects topics, knowledge and actions and defaults on for new standard agents, subject to configuration. [03][10][11] | Orchestration **GA 2025-03-17**, historical released milestone. [20] |
| **Prompts**, **prompt builder**, prompt tool | Build/test/save reusable prompts with variables and knowledge. Prompt tools/nodes have a library, lifecycle management, access control and sharing, separate from the orchestrator system prompt. [04][21] | D. Overview scopes these prompts to the **standard harness**. |
| **Skills** | **GitHub Copilot harness**: Markdown or ZIP packages with `SKILL.md` and optional files. **Customer Conversation harness**: generative and deterministic Topic skills. No blanket format/harness parity. [02][17][22] | June **2026** skills introduction within the **production-ready preview** experience. Separate skills GA unverified. [18] |

### Microsoft 365 Copilot

| Capability | Verified finding | Status and date |
|---|---|---|
| Declarative-agent instructions | **Agent Builder in Microsoft 365 Copilot** and **Microsoft 365 Agents Toolkit**: purpose, guidelines, workflows and high-level references to configured skills. [07][09] | D. |
| **Prompt Gallery in Copilot** | Microsoft-curated, user-saved and team-shared prompts support discovering and reusing requests, not persistent agent instructions. [08] | D. |
| **Skills in declarative agents** | Both authoring routes support `SKILL.md` packages loaded on demand. **8 skills/agent**. Agent Builder requires a complete ZIP, maximum **50 MB**. [12][15] | D. ISV publication through Partner Center not yet supported. [15] |
| **Microsoft Copilot Cowork** skills | Built-in/custom skills. Custom authoring uses guided creation, chat or OneDrive `SKILL.md`, distinct from declarative agents. [06][16] | Cowork **GA June 2026**, including listed guided skill builder/upload. Not every skill inherits GA: **App skill** remains **Frontier**, listed September 2026. Custom skills unsupported on mobile. [06][16] |

### GitHub Copilot

| Capability | Verified finding | Status and date |
|---|---|---|
| Custom instructions | Repository-wide `.github/copilot-instructions.md`, path-specific `.github/instructions/NAME.instructions.md`, and `AGENTS.md`. Support varies by client/task. `AGENTS.md` is not a custom-agent profile. [24][26][30] | D. No universal surface parity. |
| **Prompt files** | Explicitly invoked `.prompt.md` templates, typically in `.github/prompts/`, unlike automatic custom instructions. [28] | D. IDE/version-dependent. |
| **Custom agents** | `.github/agents/NAME.agent.md` profiles configure expertise, instructions and tool selection. [23][27] | Cloud route: D. JetBrains, Eclipse, Xcode: **public preview**, checked 2026-11-03. Launch dates unverified. [27] |
| **Agent skills / Agent Skills** | Required `SKILL.md`, optional scripts/resources. Project location includes `.github/skills/`. Selection uses the request and description. [25][29] | D for documented CLI/cloud/app/supported IDE routes. Separate `gh skill` management command: **public preview**, not all skills. [25][29] |

## 3. Recommended Slide Copy

Editorial synthesis, not an official quotation. Keep citations, counts and statuses off the slide. [04][13][25][26]

**Title:** Prompts, instructions and skills

**Body — 12 words:** Like GPS, prompts, instructions and skills give agents direction and practical know-how.

- Prompts describe the task
- Instructions guide ongoing behavior
- Skills package reusable know-how

**Example:** Agent Skills in GitHub Copilot

Bullets: four words each. Audience copy contains no semicolons. Copy/example provenance: [04][13][25][26][29].

## 4. Speaker Notes

1. Prompts express a request, while agent instructions set a standing role, boundaries and response style. [04][13]
2. Skills package task-specific instructions with optional scripts and resources, loaded when relevant in supported runtimes. [02][15][29]
3. Microsoft Foundry documents versioned skills with its Microsoft Copilot harness in public preview, checked on 3 November 2026. [01][05]
4. Copilot Studio and Microsoft 365 Copilot also document skills, with different authoring, runtime and availability boundaries. [02][12][15][18]
5. Instructions do not grant service permissions, and scripts or approval-changing skill metadata require review. [13][25]

## 5. Practical Guidance and Security Caveats

- **Instructions:** Specify purpose, users, scope, output, missing-input handling and escalation. Use clear verbs, atomic steps and examples. Reference only relevant knowledge and appropriate tools actually configured. [03][07][10][19]
- **Version/test:** Keep sources in version control and review changes like code. Test normal/edge cases, missing inputs, overlapping descriptions and incorrect skill activation. Re-test after model changes. Foundry has immutable agent/skill versions and pinned prompt-agent skill references. [01][05][06][07][13][23][26]
- **Small skills:** Describe one purpose and its activation conditions. Include only needed steps/resources. Reuse is not universal live sharing: Studio supports adding skills to multiple agents, while M365's declarative-agent support matrix says cross-agent reuse is unsupported. [02][15][25]
- **Authorization:** Prose grants no service/data permissions. Identity, connections, roles and approvals remain separate. Never bundle credentials. GitHub `allowed-tools` metadata can pre-approve terminal use, so review metadata as well as prose. [01][13][25]

> "Treat skill instructions, scripts, and assets as code. Review and version them before attaching them to an agent."
> - Source: [Use the Microsoft Copilot harness with prompt agents](https://learn.microsoft.com/azure/foundry/agents/how-to/use-tools-skills-copilot-harness) [01]

Enable scripts only from reviewed, trusted sources. Inspect dependencies and destinations. GitHub warns that shared skills are unverified and can contain malicious scripts or prompt injections. M365 declarative skill scripts have no runtime network access, package installation or authenticated network calls. Do not generalize sandbox controls across products. [01][15][25]

## 6. Research Limitations

- **Milestones:** “D” deliberately preserves uncertainty, not inferred GA. The archived orchestration plan establishes historical shipping only. [04][08][09][20][27]
- **Loading/portability:** Foundry's hosted direct-injection example loads at startup. Common packaging does not prove compatible scripts, controls or limits. M365's “reusable” wording is qualified by its unsupported cross-agent-reuse row. [05][15]
- **Terminology:** M365 distinguishes packages from older inline task descriptions called skills. Studio's GitHub Copilot harness is neither the GitHub Copilot service nor an established rename of Foundry's Microsoft Copilot harness. [01][07][15][17]
- **Scope/availability:** Tool protocols and plugin architecture belong to the separate assignment. Detailed pricing/region matrices are excluded. Foundry requires supported regions/models, Studio prompts require Dataverse/Copilot Credits and supported environments, and M365 requires applicable licensing/admin settings. No universal availability or cost claim. [01][04][09][12]
- **Validation:** Documentation only, no runtime/import tests. Paired review is user-waived, not an approval verdict.

## 7. Numbered References

### Microsoft Learn Documentation — 22 pages

1. **[01]** [Use the Microsoft Copilot harness with prompt agents](https://learn.microsoft.com/azure/foundry/agents/how-to/use-tools-skills-copilot-harness)
2. **[02]** [Skills overview for agents (GitHub Copilot)](https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/skills-overview)
3. **[03]** [Write agent instructions](https://learn.microsoft.com/microsoft-copilot-studio/authoring-instructions)
4. **[04]** [Overview of prompts](https://learn.microsoft.com/microsoft-copilot-studio/prompts-overview)
5. **[05]** [Use skills in Foundry (preview)](https://learn.microsoft.com/azure/foundry/agents/how-to/tools/skills)
6. **[06]** [Use Copilot Cowork](https://learn.microsoft.com/copilot/cowork/use-cowork)
7. **[07]** [Write effective instructions for declarative agents](https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-instructions)
8. **[08]** [Understand Prompt Gallery in Copilot](https://learn.microsoft.com/microsoft-365/copilot/copilot-prompt-gallery)
9. **[09]** [Agent Builder overview](https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder)
10. **[10]** [Configure high-quality instructions for generative orchestration](https://learn.microsoft.com/microsoft-copilot-studio/guidance/generative-mode-guidance)
11. **[11]** [Orchestrate agent behavior with generative AI](https://learn.microsoft.com/microsoft-copilot-studio/advanced-generative-actions)
12. **[12]** [Add skills to your declarative agent in Agent Builder](https://learn.microsoft.com/microsoft-365/copilot/extensibility/agent-builder-add-skills)
13. **[13]** [What are prompt agents?](https://learn.microsoft.com/azure/foundry/agents/concepts/prompt-agents)
14. **[14]** [Prompt tool for flows in Microsoft Foundry portal (classic)](https://learn.microsoft.com/azure/foundry-classic/how-to/prompt-flow-tools/prompt-tool)
15. **[15]** [Skills in declarative agents](https://learn.microsoft.com/microsoft-365/copilot/extensibility/declarative-agent-skills)
16. **[16]** [What's new in Copilot Cowork](https://learn.microsoft.com/copilot/cowork/whats-new)
17. **[17]** [Harnesses in Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/harnesses-overview)
18. **[18]** [What's new in Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/whats-new)
19. **[19]** [Create a prompt agent with Microsoft Foundry Toolkit for Visual Studio Code](https://learn.microsoft.com/azure/foundry/how-to/develop/create-prompt-agent-visual-studio-code)
20. **[20]** [Use generative orchestration — archived release milestone](https://learn.microsoft.com/power-platform/release-plan/2024wave2/microsoft-copilot-studio/use-generative-actions-now-generally)
21. **[21]** [Use agent tools to extend, automate, and enhance your agents — AI prompts section only](https://learn.microsoft.com/microsoft-copilot-studio/guidance/agent-tools)
22. **[22]** [Add and manage an uploaded skill (GitHub Copilot)](https://learn.microsoft.com/microsoft-copilot-studio/agents-experience/skills-add-existing)

### First-party GitHub Documentation — 8 pages

23. **[23]** [Customize Copilot for your project](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-copilot-overview)
24. **[24]** [Adding repository custom instructions for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/add-custom-instructions/add-repository-instructions)
25. **[25]** [Adding agent skills for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills)
26. **[26]** [Custom instructions for GitHub Copilot](https://docs.github.com/en/copilot/concepts/prompting-and-context/custom-instructions)
27. **[27]** [Creating custom agents for Copilot cloud agent](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/create-custom-agents)
28. **[28]** [Prompt files for GitHub Copilot](https://docs.github.com/en/copilot/concepts/prompting-and-context/prompt-files)
29. **[29]** [Agent skills — resolved canonical page](https://docs.github.com/en/copilot/concepts/customizations/agent-skills)
30. **[30]** [Support for different types of custom instructions](https://docs.github.com/en/copilot/reference/custom-instructions-support)

### Official GitHub Repositories and Code Samples

N/A - No repository or code sample was used as report evidence. The report contains no code.
