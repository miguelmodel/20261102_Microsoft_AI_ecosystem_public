# Research Report: METR Task Horizons — Verified Chart Snapshot and Boundaries

**Date:** 2026-11-01
**Researcher:** Copilot Web Researcher Agent
**Topic slug:** metr-task-horizons-v4
**Sources consulted:** 15 cited primary resources: 4 METR articles/pages, 2 metr.org data/code assets, 8 METR GitHub resources (1 repository README, 3 Python files, 1 release-date file, 3 pipeline/configuration files), and 1 academic abstract/metadata page. Two additional GitHub directory listings were navigation-only. The read-only brief and two supplied local reference artifacts were scope/visual inputs, not quantitative evidence. Search-only results and alternate representations of the same resource are not additional references.
**Required MCP:** verified - WebIQ-MCP; tools used: web, browse, news
**Binding scope:** brief_version 15, SOURCES-V4-01 and OWNERSHIP-V4-01. Quantitative evidence and methodology for the requested v4 slide-5 graph only. Create-mode handoff for caller-managed overall review R1, not a research approval.

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Overview and Exact Metric Methodology](#2-overview-and-exact-metric-methodology)
3. [Dataset Currency and Chart-Ready Values](#3-dataset-currency-and-chart-ready-values)
4. [Ceiling, Uncertainty and Newer Evaluations](#4-ceiling-uncertainty-and-newer-evaluations)
5. [Trend and Precise Reference-Deck Corrections](#5-trend-and-precise-reference-deck-corrections)
6. [Practical Chart Guidance and Attribution](#6-practical-chart-guidance-and-attribution)
7. [Research Limitations](#7-research-limitations)
8. [Complete Reference List](#8-complete-reference-list)

## 1. Executive Summary

**An evidence-bounded redraw is possible.** The first-party numeric file contains 23 TH1.1 records released from 2023 onward, including 15 `is_sota: true` records. Fourteen are eligible for a below-ceiling frontier connector. Claude Mythos Preview (early), the fifteenth, must remain a separate unreliable/saturated marker or be omitted. All 23 estimates, release dates and published confidence bounds are preserved in [chart-data.json](assets/metr-task-horizons-v4/chart-data.json). Values were independently read from [METR's YAML](https://metr.org/assets/benchmark_results_1_1.yaml), not imported from the reference deck.

**The currency correction is material.** METR's live page now says it is **no longer actively updated**, with a **September 8, 2026** page date. The last logged model addition remains **May 8, 2026**, and the latest release date in the numeric file is **April 7, 2026**. Present this as METR's published historical TH1.1 series retrieved November 1, not a complete November frontier census. [METR page and update log](https://metr.org/time-horizons/)

**The metric measures task difficulty, not autonomous elapsed runtime.** Its p50 is the human-expert duration where fitted agent success probability reaches 50% on the evaluated software-oriented distribution. It does not establish a business-task success guarantee, job automation, or a universal conclusion that model capability has ceased to be a bottleneck. [METR definition and FAQ](https://metr.org/time-horizons/)

## 2. Overview and Exact Metric Methodology

### Definition, units and human baseline

> "The task-completion time horizon is the task duration (measured by human expert completion time) at which an AI agent is predicted to succeed with a given level of reliability."
> - Source: [Task-Completion Time Horizons of Frontier AI Models](https://metr.org/time-horizons/)

The **50% task-completion time horizon** is a fitted threshold, not the median of agent runtimes and not a 95% confidence level. The YAML stores horizon estimates and bounds in **minutes**; METR's chart divides them by 60 to display hours. The 50% success threshold and the 95% uncertainty interval describe different things. [METR definition](https://metr.org/time-horizons/), [chart conversion and tooltip](https://metr.org/assets/js/time-horizon-chart.js)

For most tasks, METR contracts relevant human experts, supplies generally the same instructions and affordances as agents, asks for quick completion, and takes the **geometric mean of successful human completion times**. Some durations instead use expert estimates or QA completion times. These are low-context task attempts, not the time a familiar employee would necessarily take on their own project. The TH1.1 announcement reports that only **5 of 31 tasks estimated at 8h+** had measured human baselines. [Human-time methodology and FAQ](https://metr.org/time-horizons/), [TH1.1 announcement](https://metr.org/blog/2026-01-29-time-horizon-1-1/)

### Task domain and evaluated system

TH1.1 expanded the suite from **170 to 228 tasks**, including **31 estimated at 8h+**, drawn from RE-Bench, HCAST and short novel software tasks. The evaluated distribution primarily covers software engineering, machine learning and cybersecurity, with short software/reasoning tasks. Tasks are self-contained and well specified, with automatically scoreable success criteria. Do not describe it as representative of all customer business work. [TH1.1 changes](https://metr.org/blog/2026-01-29-time-horizon-1-1/), [current task-distribution description](https://metr.org/time-horizons/)

The evaluated object is **a model plus a scaffold, tools and evaluation conditions**, not the model in isolation. METR describes development-set elicitation, a separate test set, typically six independent runs per task subject to time/token limits, and checks for reward hacking and insufficient budgets. The YAML records different ReAct, Triframe and legacy scaffold combinations. These exact combinations are retained as referenced scaffold sets in the JSON. [Evaluation workflow](https://metr.org/time-horizons/), [primary scaffold records](https://metr.org/assets/benchmark_results_1_1.yaml)

### Fit and uncertainty

In mathematical notation synthesized from METR's implementation, let \(t\) be human-expert minutes and \(P(t)=1/(1+\exp[-(\alpha+\beta\log_2 t)])\). The p50 threshold is \(t_{50}=2^{-\alpha/\beta}\). This is the point where predicted success equals 0.5, not a claim that every task of that duration independently has the same success probability. The source README specifies `log2(human_minutes)` and the logistic utility implements the inverse quantile calculation. [Analysis README](https://github.com/METR/eval-analysis-public), [logistic utility](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/src/horizon/utils/logistic.py), [task-specific success variation](https://metr.org/time-horizons/)

The public headline configuration uses diversity-adjusted `invsqrt_task_weight`, regularization **0.00001**, and a **0.95** confidence level. The weighting implementation assigns each run weight proportional to \(1/(n_{\text{runs in task}}\sqrt{n_{\text{tasks in family}}})\), then normalizes per agent. Its logistic utility uses scikit-learn `C = 1 / regularization`. These document the public pipeline, not a claim that this research reran it or established its exact generation revision for every later website addition. [Headline configuration](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/fig_params/figs.yaml), [weight computation](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/src/horizon/compute_task_weights.py), [logistic utility](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/src/horizon/utils/logistic.py)

Published model bounds are **95% confidence intervals** from hierarchical bootstrapping over task families, tasks and runs. The export maps `ci_low`/`ci_high` to `p50q0.025`/`p50q0.975`; the website labels them “95% CI”. The public report configuration sets **1,000 bootstrap samples**, and its DVC pipeline exports the headline fits. A shaded area interpolated between point bounds would **not** automatically be a confidence band for the historical trend. [TH1.1 bootstrap explanation](https://metr.org/blog/2026-01-29-time-horizon-1-1/), [export mapping](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/src/horizon/generate_benchmark_results.py), [report parameters](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/params.yaml), [DVC pipeline](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/dvc.yaml), [chart labels](https://metr.org/assets/js/time-horizon-chart.js)

## 3. Dataset Currency and Chart-Ready Values

### Source and version

Use `benchmark_results_1_1.yaml`, with `benchmark_name: METR-Horizon-v1.1`, `long_tasks_version: 799cc9c4b4483a93fc3445623a49ea1bd74fdeb2` and `swaa_version: f6cc84052e2a79dd540766c8a1b15ff399696371`. The live page's embedded TH1.1 object was also inspected and agrees with the selected numeric fields. The hashes identify task versions, **not an immutable revision or checksum of the result file**. [Primary YAML](https://metr.org/assets/benchmark_results_1_1.yaml), [live page](https://metr.org/time-horizons/)

The page still labels TH1.1 “Current”, meaning its selected benchmark version, while explicitly disclaiming active updates. September 8 is the page's maintenance clarification, not a newly added model observation. Distinguish **model release date**, **measurement-publication/update date**, and **retrieval date**. For example, Opus 4.6 is dated February 5 in the YAML but was added to the page February 20. [METR page/update log](https://metr.org/time-horizons/), [release fields](https://metr.org/assets/benchmark_results_1_1.yaml)

### Frontier table

All figures below are **unrounded source minutes**, including both 95% CI endpoints. Model labels come from METR's chart metadata. Dates are independently verified **METR-recorded release dates**, not separate vendor-announcement verification. Fourteen rows can be connected, ending at Opus 4.6. The last row is retained for provenance but excluded from that connector and the source ceiling-filtered fit. [YAML](https://metr.org/assets/benchmark_results_1_1.yaml), [model labels/frontier rules](https://metr.org/assets/js/time-horizon-chart.js)

| Model | METR release date | p50 minutes | 95% CI lower | 95% CI upper | Treatment |
|---|---|---:|---:|---:|---|
| GPT-4 | 2023-03-14 | 3.987428 | 1.93292 | 7.995283 | Frontier |
| GPT-4 Nov '23 | 2023-11-06 | 4.044959 | 1.866859 | 8.443226 | Frontier |
| GPT-4o | 2024-05-13 | 6.991195 | 4.001482 | 12.905741 | Frontier |
| Claude 3.5 Sonnet (Old) | 2024-06-20 | 11.395377 | 5.489734 | 22.384214 | Frontier |
| o1-preview | 2024-09-12 | 20.326586 | 11.716193 | 33.379877 | Frontier |
| Claude 3.5 Sonnet (New) | 2024-10-22 | 20.522872 | 10.144026 | 40.82028 | Frontier |
| o1 | 2024-12-05 | 38.831588 | 21.164512 | 64.95249 | Frontier |
| Claude 3.7 Sonnet | 2025-02-24 | 60.388937 | 33.006168 | 104.226017 | Frontier |
| o3 | 2025-04-16 | 119.732634 | 74.615398 | 190.943818 | Frontier |
| GPT-5 | 2025-08-07 | 203.012577 | 112.641357 | 405.551565 | Frontier |
| Gemini 3 Pro | 2025-11-18 | 224.325884 | 139.565157 | 379.235434 | Frontier |
| Claude Opus 4.5 | 2025-11-24 | 292.994594 | 161.717714 | 623.704698 | Frontier |
| GPT-5.2 (high) | 2025-12-11 | 352.249302 | 198.067494 | 815.177445 | Frontier |
| Claude Opus 4.6 | 2026-02-05 | 718.80683 | 316.685725 | 3633.786163 | Below ceiling, very wide CI |
| Claude Mythos Preview (early) | 2026-04-07 | 1044.780145 | 508.876789 | 3304.261235 | Above ceiling, unreliable |

**Machine artifact:** [assets/metr-task-horizons-v4/chart-data.json](assets/metr-task-horizons-v4/chart-data.json), provenance **adapted numeric transcription**. It contains all **23** ordered post-2023 TH1.1 points, including eight non-frontier points for optional secondary dots, original precision, separate source frontier and rendering flags, scaffold sets, source URLs, version hashes and retrieval date. All point uncertainty bounds are available. Missing metadata/uncertainty elsewhere remains `null`, including the stitched doubling interval and the excluded newer evaluation's chart fields. Source: [METR numeric file](https://metr.org/assets/benchmark_results_1_1.yaml) and [chart metadata](https://metr.org/assets/js/time-horizon-chart.js).

The separate METR [release-date file](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/data/external/release_dates.yaml) corroborates 20 of the 23 dates. It does not contain Gemini 3.1 Pro, GPT-5.4 or Mythos Preview (early); their dates were verified directly in the [benchmark YAML](https://metr.org/assets/benchmark_results_1_1.yaml). The three pre-2023 records in that YAML retain TH1.0 measurements and are intentionally excluded from the chart snapshot.

## 4. Ceiling, Uncertainty and Newer Evaluations

> "Measurements above 16 hrs are unreliable with our current task suite"
> - Source: [METR time-horizons page](https://metr.org/time-horizons/)

The source rule is **central p50 >16 hours**, or **>960 minutes**, not a universal hard limit on agent capability and not a boundary between safe and unsafe business deployment. METR's script removes such points from frontier fitting, renders them as saturated, and substitutes **“Likely at least 16 hrs”** in the tooltip. Preserve that qualifier. It is **not a statistical lower confidence bound**: Mythos's published interval actually starts below 16h. [Ceiling and tooltip implementation](https://metr.org/assets/js/time-horizon-chart.js), [published interval](https://metr.org/assets/benchmark_results_1_1.yaml)

Opus 4.6 is the largest eligible frontier estimate **in this published table**: 718.80683 minutes, approximately **12h** after conversion/rounding. Its interval is approximately **5.28–60.56h**, extending far above the ceiling. “Below ceiling” therefore does not mean precisely measured or operationally reliable. The JSON explicitly flags this interval crossing. [Opus 4.6 primary results](https://metr.org/assets/benchmark_results_1_1.yaml)

**Do not append GPT-5.6 Sol as a normal point.** METR's June 26, 2026 evaluation reports approximately **11.3h [5–40h, 95% CI]** when cheating attempts count as failures, **>270h** when they count as successes, and **71h [13–11,400h, 95% CI]** when discarded. METR explicitly says none represents a robust capability measurement. This newer publication is a methodology limitation, not evidence for extending the ordinary frontier curve. It is recorded as `not_robust_do_not_plot`, with null chart values and no invented release date. [METR GPT-5.6 Sol evaluation](https://metr.org/blog/2026-06-26-gpt-5-6-sol/)

## 5. Trend and Precise Reference-Deck Corrections

### Verified historical doubling statements

The current numeric artifact publishes the following estimates and explicitly excludes points whose central p50 exceeds 16h. The approximate month conversions below are **derived**, using days ÷30.4375, not source units. These are retrospective estimates, not predictions of continuing progress. [METR doubling fields](https://metr.org/assets/benchmark_results_1_1.yaml)

| Source field | Days per doubling | Published bounds, days | Derived months | Scope |
|---|---:|---|---|---|
| `from_2023_on` | 128.744 | 104.428–158.012 | ≈4.23 | Post-2023 frontier, ceiling-filtered |
| `all_time_stitched` | 187.778 | Not supplied | ≈6.17 | Includes TH1.0 pre-2023 records |

The source artifact does not annotate the doubling interval's confidence level. The public export implementation uses 0.95, but its exact generation revision for the later ceiling-filtered website file was not established. Accordingly, the JSON preserves the supplied interval endpoints and leaves its confidence level `null`. It does not invent an all-time stitched interval. [Current YAML](https://metr.org/assets/benchmark_results_1_1.yaml), [public exporter](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/src/horizon/generate_benchmark_results.py)

The January TH1.1 post's **130.8-day** post-2023 and **196.5-day** stitched estimates differ from the current YAML. The original paper's approximately seven-month statement describes its older data, even though the abstract/metadata page now lists **v4, July 10, 2026**. Use the YAML for this chart's numerical annotation, not the date of an article revision or historical README prose. [January announcement](https://metr.org/blog/2026-01-29-time-horizon-1-1/), [paper abstract/version history](https://arxiv.org/abs/2503.14499), [current YAML](https://metr.org/assets/benchmark_results_1_1.yaml)

### Corrections to the supplied local slide-007/reference research

| Prior treatment | Verified disposition for this invocation |
|---|---|
| Page “last updated May 8, 2026”, implicitly maintained | Replace page date with **September 8, 2026** and record **no longer actively updated**. Keep May 8 separately as last logged model addition. [METR](https://metr.org/time-horizons/) |
| “How long can an agent work on its own?” | Do not retain it as the literal metric definition. The axis measures human-expert task duration at fitted 50% success, not autonomous runtime. [METR FAQ](https://metr.org/time-horizons/) |
| “Doubling about every 4 months since 2023” | The number remains compatible with **128.744 days**, but bound it to this **historical TH1.1 estimate**. Eligible frontier releases run March 2023–February 2026, not through November 2026. [YAML](https://metr.org/assets/benchmark_results_1_1.yaml) |
| “≥16h” reliable-limit band | Label the source warning **above 16h**. It is measurement saturation, not a proved capability maximum or operational-reliability guarantee. [Implementation](https://metr.org/assets/js/time-horizon-chart.js) |
| Hollow Mythos marker labeled “16h+” | A distinct unconnected marker remains appropriate, but prefer METR's **“Likely at least 16 hrs”** with an unreliable-measurement warning. Do not imply a hard lower confidence bound. [Implementation](https://metr.org/assets/js/time-horizon-chart.js), [YAML](https://metr.org/assets/benchmark_results_1_1.yaml) |
| Fourteen “reliable” frontier points without displayed uncertainty | Use **below-ceiling** rather than blanket “reliable”. Provide published uncertainty, especially Opus 4.6's wide interval. [YAML](https://metr.org/assets/benchmark_results_1_1.yaml) |
| “Capability is no longer the bottleneck” in reference notes | **Not established by this graph.** No customer-business or universal bottleneck inference is authorized by its task distribution. [METR limits](https://metr.org/time-horizons/) |

The prior deck's 15 central frontier estimates and recorded dates match the freshly read primary YAML; no numerical replacement was necessary. The important changes are currency, interpretation, explicit uncertainty and saturation treatment. The JSON retains `source_is_sota: true` for Mythos while setting `include_in_frontier_line: false`; filtering only on `is_sota` would incorrectly include it. [Primary values](https://metr.org/assets/benchmark_results_1_1.yaml), [frontier/saturation implementation](https://metr.org/assets/js/time-horizon-chart.js)

## 6. Practical Chart Guidance and Attribution

**Research-derived implementation guidance, not a presentation build:** use release date on the horizontal axis and human-expert task duration at predicted 50% success on a logarithmic vertical axis. Store minutes and only format display units. Suitable sparse ticks are 6min, 1h, 4h and 16h. An optional connector through the 14 eligible point estimates is a visual guide, **not METR's fitted exponential regression**. Do not synthesize regression coordinates from the doubling rate alone. [METR axes, units and fitting implementation](https://metr.org/assets/js/time-horizon-chart.js)

For the requested light redraw, prefer legible dark labels, restrained blue-purple emphasis, subtle grid lines, and a clearly labeled hatched or otherwise distinguishable >16h region. Reveal point/line geometry without changing values. Keep the saturated marker visually distinct and unconnected. If confidence whiskers are clipped to the plot boundary, indicate truncation and expose the original endpoints through keyboard-accessible details or a data table. Do not create a decorative “confidence ribbon” from unrelated point bounds. These are design recommendations grounded in the source's distinction between point uncertainty and saturation, not copied chart artwork. [METR interval and saturation implementation](https://metr.org/assets/js/time-horizon-chart.js)

**Rights/provenance:** this deliverable is an original organization of published numerical facts, not a copied protected chart image or copied rendering code. The benchmark YAML supplies no explicit license identifier, and the repository README says “See LICENSE file for details.” An applicable website/data reuse license was not established in this invocation. The arXiv page links **CC BY 4.0 for the article**; do not transfer that label to the live chart or data. Preserve the license uncertainty and attribution, and obtain applicable permission before reusing METR's original image/code or claiming an open-data license. This is a provenance boundary, not legal advice. [Benchmark YAML](https://metr.org/assets/benchmark_results_1_1.yaml), [repository license section](https://github.com/METR/eval-analysis-public), [article license link](https://arxiv.org/abs/2503.14499)

The JSON attribution identifies METR, the chart title, TH1.1, the September page date, the May model-addition date and the November retrieval date. Retain a link to the primary page and dataset with any redraw. The original announcement invites others to build on its publicly shared data/analysis; the repository requests citation of its time-horizon paper. Neither statement was treated as a specific license grant for every website asset. [METR citation metadata](https://metr.org/time-horizons/), [original announcement](https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/), [repository attribution request](https://github.com/METR/eval-analysis-public)

## 7. Research Limitations

- **No complete November frontier dataset established.** The requested page disclaims active updates. This is the first-party historical graph snapshot still served on retrieval, not an assertion that every newer model has been evaluated or that no newer METR research exists. Targeted Web IQ web/news discovery located the later Sol evaluation, which is explicitly unsuitable for a robust added point. [Page status](https://metr.org/time-horizons/), [Sol evaluation](https://metr.org/blog/2026-06-26-gpt-5-6-sol/)
- **Reader freshness conflict resolved.** The first successful Web IQ browse of a tracking-parameter variant returned an older May-dated capture. A later successful canonical browse (October 31 crawl) and direct live HTML both returned September 8 and the maintenance disclaimer. The current canonical page controls the report; the older capture was not evidence that the page was still maintained. [Canonical source](https://metr.org/time-horizons/)
- **Reproducibility scope.** The YAML was read in full, and the JSON is a precision-preserving transcription, not a claim of downloading raw run files or executing METR's DVC pipeline. Task-version hashes are retained, but no immutable result-file revision/hash was established. The public configuration's model list lacks the last three website additions, so it is methodology evidence, not sufficient to regenerate the complete current website snapshot unchanged. [Primary results](https://metr.org/assets/benchmark_results_1_1.yaml), [public report parameters](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/params.yaml), [pipeline](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/dvc.yaml)
- **Remaining uncertainty.** The current doubling interval level is not explicit in the numeric artifact. No stitched interval was supplied. Wide model intervals, estimated long-task human durations, scaffold variation and limited external validity remain material even below the ceiling. [YAML](https://metr.org/assets/benchmark_results_1_1.yaml), [TH1.1 discussion](https://metr.org/blog/2026-01-29-time-horizon-1-1/), [FAQ](https://metr.org/time-horizons/)
- **Source conflicts are not silently blended.** The page's GPT-5 FAQ example still says roughly 2h17m; its current YAML instead has 203.012577 minutes. Historical paper/announcement prose and some public plot titles also differ from the current bounds. Use the YAML's numerical fields. The March 3 regularization correction is verified from the update log, but no precise causal allocation of every numerical change was established. [FAQ/update log](https://metr.org/time-horizons/), [YAML](https://metr.org/assets/benchmark_results_1_1.yaml), [public plot configuration](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/fig_params/figs.yaml)
- **Dates and rights.** All plotted release dates are verified within METR evidence; vendor availability verification is outside this METR-only assignment. No broader website/data license was established, and the prior report's repository-license/API conclusions were not adopted without fresh verification. The academic source was read as an abstract/metadata/license page, not as a full independent reanalysis of the paper. [Release records](https://metr.org/assets/benchmark_results_1_1.yaml), [README](https://github.com/METR/eval-analysis-public), [article metadata](https://arxiv.org/abs/2503.14499)
- **Intentional exclusions.** No protected graph image was copied, no p80 series or future forecast was generated, and no product, foundation, governance or universal bottleneck claims were added. This respects the quantitative owner's scope and METR's explicit external-validity warnings. [METR limitations](https://metr.org/time-horizons/)

## 8. Complete Reference List

All resources below were read on **2026-11-01**. Fifteen distinct primary resources are cited; canonical/redirected representations count once.

### METR Documentation and Articles — 4

1. [Task-Completion Time Horizons of Frontier AI Models](https://metr.org/time-horizons/) — page updated **2026-09-08**, no longer actively updated; last logged model addition **2026-05-08**. Read with direct fetch, raw HTML and successful Web IQ browse.
2. [Time Horizon 1.1](https://metr.org/blog/2026-01-29-time-horizon-1-1/) — **2026-01-29**; suite changes, human baselines, bootstrap explanation and historical estimates. The non-zero-padded search URL redirected to this canonical page, which was also fetched.
3. [Summary of METR's predeployment evaluation of GPT-5.6 Sol](https://metr.org/blog/2026-06-26-gpt-5-6-sol/) — **2026-06-26**; explicitly non-robust horizon treatments. Used only for methodology/exclusion.
4. [Measuring AI Ability to Complete Long Tasks](https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/) — **2025-03-19** announcement, presently clarifying that TH1.1 model updates have stopped; historical trend, bootstrap and attribution context.

### First-Party Data and Chart Implementation — 2

5. [benchmark_results_1_1.yaml](https://metr.org/assets/benchmark_results_1_1.yaml) — `METR-Horizon-v1.1`; numeric results, confidence endpoints, release dates, scaffold records, task-version hashes and doubling estimates. No independent publication timestamp in the file.
6. [time-horizon-chart.js](https://metr.org/assets/js/time-horizon-chart.js) — complete current script read in paginated sections; units, names, running frontier, >16h saturation and 95% CI labels. An implementation reference, not copied into the asset.

### Primary Academic Publication Metadata — 1

7. [Kwa et al., Measuring AI Ability to Complete Long Software Tasks, arXiv:2503.14499](https://arxiv.org/abs/2503.14499) — first submitted **2025-03-18**, latest listed **v4, 2026-07-10**, NeurIPS 2025. Abstract/version/license metadata only.

### METR GitHub Repository, Data and Methodology Files — 8

8. [METR/eval-analysis-public README](https://github.com/METR/eval-analysis-public) — methodology, data format, citation and license reference.
9. [data/external/release_dates.yaml](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/data/external/release_dates.yaml) — corroborating METR-recorded dates. GitHub file view/read fallback and its linked raw destination were checked.
10. [src/horizon/generate_benchmark_results.py](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/src/horizon/generate_benchmark_results.py) — confidence quantile export, date fields, frontier selection and stitched estimate handling.
11. [src/horizon/compute_task_weights.py](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/src/horizon/compute_task_weights.py) — per-run diversity weighting and normalization.
12. [src/horizon/utils/logistic.py](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/src/horizon/utils/logistic.py) — logistic regression and threshold inversion.
13. [reports/time-horizon-1-1/params.yaml](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/params.yaml) — task versions, 1,000 bootstrap samples and public model coverage.
14. [reports/time-horizon-1-1/dvc.yaml](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/dvc.yaml) — headline analysis/export dependencies and TH1.0 stitching.
15. [reports/time-horizon-1-1/fig_params/figs.yaml](https://raw.githubusercontent.com/METR/eval-analysis-public/refs/heads/main/reports/time-horizon-1-1/fig_params/figs.yaml) — headline weighting, regularization and confidence configuration.

The two GitHub directory listings used to find implementation files are navigation-only, not additional substantive citations. The supplied October research report and latest local `slide-007.html` were read solely to identify intended graph scope and precise corrections; neither supplies verified numbers here.
