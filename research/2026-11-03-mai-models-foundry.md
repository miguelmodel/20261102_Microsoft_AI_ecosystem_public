# Research Report: Microsoft MAI Models in Foundry

**Date:** 2026-11-03
**Researcher:** Copilot MS Docs Researcher Agent
**Topic slug:** mai-models-foundry
**Sources consulted:** 12 Microsoft Learn pages, 9 other official Microsoft pages, 0 GitHub repositories, 0 code samples (cited evidence set).
**Required MCP:** verified - microsoft-learn; tools used: microsoft_docs_search, microsoft_docs_fetch
**Reference count:** 21 official pages, excluding discovery-only pages, duplicate retrievals, snippets and local inputs.
**Assignment:** mai-models-v10; Create mode; brief_version 27; slide 16 delta only.
**Review state:** user-waived review, no verdict. No review round applies.
**Evidence cutoff:** 2026-11-03. Status observations are as of this date. Model-version dates are not release dates.

Read-only inputs: `brief.md` v27 (including the four named decisions), logo `source-map.json`, v9 `slide-016.html` and the header example. Learn preflight search/full fetch succeeded. Only this report was written; code-sample search is not applicable.

## 1. Executive Summary and Card Decision

**Recommended card: Microsoft / Phi · MAI.** “Phi and MAI models” is also accurate. Foundry explicitly groups MAI and Phi under Microsoft. These are illustrative, not Microsoft's entire portfolio. [2][12]

**MAI means Microsoft AI**, whose models span reasoning, images, speech, coding and cybersecurity. MAI is not one model or a Phi rename; availability differs by model and route. [2][13][18]

**Keep the unchanged Microsoft parent mark**, heading `Microsoft` and asset `model-phi.svg`, per MODELS-V10-01 and the supplied source map. This is a provider mark, not a MAI-specific logo or new rights grant. Today's product page includes a Microsoft AI card; the source map records historical asset provenance, not an unchanged live layout. No asset was downloaded. [21]

## 2. Verified MAI Names, Modalities and Availability

Publisher: **Microsoft AI**, grouped under **Microsoft** in Foundry. No current route below has independently verified GA status here. Preview labels are route-specific; undated observations use the 2026-11-03 cutoff. [2]–[9][18]

| Exact official model name(s) | Modality / purpose | Verified Foundry route, status and date context |
|---|---|---|
| **MAI-Thinking-1** | Text → text reasoning | Azure-sold, **public preview**, Global Standard. Version **2026-06-01**; availability announcement **2026-08-12**. [2][3][16] |
| **MAI-Image-2.6**, **MAI-Image-2.6-Flash** | Text/image → image generation and editing | Azure-sold models, **preview**, Global Standard. Both model versions **2026-07-31**. [2][4] |
| **MAI-Image-2.5**, **MAI-Image-2.5-Flash**, **MAI-Image-2.5-Pro** | Text/image → image generation and editing | Azure-sold models, **preview**, Global Standard. Versions **2026-06-02** for 2.5/Flash and **2026-06-19** for Pro. [2][4] |
| **MAI-Voice-2.1**, **MAI-Voice-2.1-Flash** | Text → speech; optional consented voice reference | Azure Speech in Foundry Tools, **public preview**. Release date unverified. Voice cloning is gated. [2][5] |
| **MAI-Transcribe-2**, **MAI-Transcribe-1.5** | Audio → text | Azure Speech in Foundry Tools, **preview** documentation. Launch dates unverified. **MAI-Transcribe-1** deprecated **2026-08-20**. [2][6] |
| **MAI-Transcribe-2-Streaming** | Streaming audio → text | **Public preview**; Learn documents Foundry base-model deployment and Realtime transcription. Launch date unverified. [7] |
| **MAI-Code-1.1-Flash** | Coding, including screenshot-driven coding | **Preview reinforcement fine-tuning**, with Global Standard serverless customized-model deployment. Not proof of unrestricted base inference. Also in GitHub Copilot. Launch date unverified. [8][19] |
| **MAI-Cyber-1.1-Flash** | Code-security analysis; formal I/O unverified | Foundry deployment for **MAI Cyber (Preview)** in MDASH; verified customers only. Announcement **2026-10-27**, not unrestricted catalog access. [9][20] |
| **MAI-Image-2.7** | Image editing; text-to-image coming later | **Preview** announced **2026-10-27**, Playground/evaluation access. Not in fetched Foundry model/image lists: **Foundry availability unverified**, not disproved. [2][4][17] |

### Earlier names in the request: preserve history, not stale availability

- **MAI-1-preview**: text foundation model announced **2025-08-28** for public testing, trusted API testers and planned Copilot rollout. Current Foundry deployment **unverified**; its name is not an Azure status label. [13]
- **MAI-Voice-1**: speech generation announced **2025-08-28** in Copilot. The **2026-04-02** announcement, updated **2026-06-09**, documents Foundry availability for it, **MAI-Transcribe-1** and text-to-image **MAI-Image-2**. “Voice-1 is Copilot-only” is therefore wrong. That history does not establish their current lifecycle/GA status. [13][15]
- **MAI-Image-1**: text-to-image, announced **2025-10-13**; the **2025-11-04** update documents Bing/Copilot use, not Foundry deployment. **MAI-DS-R1**: historical Microsoft text-reasoning entry, **retired 2026-02-27**, not a current deployment recommendation. Its precise Microsoft team attribution remains unverified here. [10][11][14]

**Boundary:** Copilot use does not prove or exclude Foundry availability. Use Thinking/Image as the clean catalog examples. Speech, customization and MDASH have distinct routes; Global Standard does not mean every resource region is eligible. [2]–[9][12][15]

## 3. Other Provider Labels and Suggested Speaker Notes

**Retain:** **OpenAI — GPT family**, **Anthropic — Claude**, **Meta — Llama**, **Mistral AI — Mistral**, **DeepSeek — DeepSeek**. The current overview names these providers and Claude; the Azure-sold catalog confirms the other families. This is illustrative, not exhaustive. [1][2]

Suggested speaker notes — four sentences:

1. “Microsoft's own model choices in Foundry include Phi and MAI.” [2][12]
2. “MAI is Microsoft AI's family spanning reasoning, images, speech and coding, with availability depending on the particular model and access route.” [2][18][19]
3. “For example, MAI-Thinking-1 and selected MAI-Image models are available in preview, while MAI Voice and Transcribe also have Azure Speech routes.” [2]–[7]
4. “These six cards are examples, not an exhaustive catalog or a promise that every model is available in every region or agent runtime.” [1][12]

These are proposed wording, not documentation quotations. Keep versions/status/dates in notes. MODELS-V10-01 separately requires six cards on first Next and the closing line on second.

## 4. Research Limitations

- **Conflict:** the Responses guide still lists MAI-DS-R1. Prefer the explicit retirement page over that stale usage list. [10][11]
- **Dates:** Thinking's June version and August availability announcement are different events. Image-2.7's announcement does not verify its Foundry deployment. [3][4][16][17]
- **Access:** Code/Cyber evidence is restricted to the routes above. No live entitlement, deployment, quota or capacity test was performed. [8][9]
- **Excluded:** exhaustive release history, benchmarks, pricing/licensing matrices, setup/code and new assets/rights. Regional tables are referenced, not reproduced. No paired-review approval is claimed.

## 5. Complete Reference List

Retrieved 2026-11-03; key Learn pages fetched in full.

### Microsoft Learn Documentation — 12 pages

1. [Overview of Microsoft Foundry Models](https://learn.microsoft.com/azure/foundry/concepts/foundry-models-overview)
2. [Foundry Models sold by Azure](https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure)
3. [Deploy and use MAI-Thinking-1 (preview)](https://learn.microsoft.com/azure/foundry/foundry-models/how-to/use-foundry-models-mai-thinking)
4. [Deploy and use MAI image models (preview)](https://learn.microsoft.com/azure/foundry/foundry-models/how-to/use-foundry-models-mai-image)
5. [MAI-Voice in Azure Speech](https://learn.microsoft.com/azure/ai-services/speech-service/mai-voices)
6. [MAI-Transcribe in Azure Speech (preview)](https://learn.microsoft.com/azure/ai-services/speech-service/mai-transcribe)
7. [Use MAI-Transcribe-2-Streaming with the Realtime API](https://learn.microsoft.com/azure/ai-services/speech-service/mai-transcribe-2-streaming-realtime)
8. [Fine-tuning in Microsoft Foundry](https://learn.microsoft.com/azure/foundry/fine-tuning/overview)
9. [Connect Microsoft Foundry (Preview): MDASH integration](https://learn.microsoft.com/security-exposure-management/mdash-foundry-integration)
10. [Retired Foundry Models](https://learn.microsoft.com/azure/foundry/openai/concepts/retired-models)
11. [Generate text responses with Foundry Models](https://learn.microsoft.com/azure/foundry/foundry-models/how-to/generate-responses)
12. [Region availability for Foundry Models sold by Azure](https://learn.microsoft.com/azure/foundry/foundry-models/concepts/models-sold-directly-by-azure-region-availability)

### Other Official Microsoft Pages — 9 pages

13. [Two in-house models in support of our mission](https://microsoft.ai/news/two-new-in-house-models/)
14. [Introducing MAI-Image-1](https://microsoft.ai/news/introducing-mai-image-1-debuting-in-the-top-10-on-lmarena/)
15. [Three MAI models available in Foundry](https://microsoft.ai/news/today-were-announcing-3-new-world-class-mai-models-available-in-foundry/)
16. [Introducing MAI-Thinking-1](https://microsoft.ai/news/introducing-mai-thinking-1/)
17. [MAI Image 2.7 debut](https://microsoft.ai/news/mai-image-2-7-debut/)
18. [Microsoft AI current model collection](https://microsoft.ai/models/)
19. [MAI-Code-1.1-Flash](https://microsoft.ai/models/mai-code-1-flash/)
20. [MAI Cyber 1.1 Flash inside MDASH](https://microsoft.ai/news/mai-cyber-1-1-flash/)
21. [Foundry Models product page](https://azure.microsoft.com/en-us/products/ai-foundry/models)
