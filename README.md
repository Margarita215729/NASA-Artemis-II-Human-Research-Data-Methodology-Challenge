# NeuroBridge-S4: A Small-N Human Adaptation Management Framework for Artemis II Proxy Data

**Proxy-Data Demonstration for Small-N Human Adaptation Management**
NASA Artemis II - Human Research Data Methodology Challenge

---

## For reviewers who do not code

You do **not** need to run any code to review this project.

- **Open the notebook** `NeuroBridge_S4_Proxy_Data_Demonstration.ipynb` (or the `.html` export, if included).
- **Outputs are already embedded** - every figure, table, and report is visible without running anything.
- **Read the Markdown sections and inspect the figures.** Each major figure is followed by a short **"Reviewer note"**
  that explains what it shows, why it matters for HRP, and the takeaway.
- **Running the notebook is optional.** To verify reproducibility, run all cells in Google Colab or locally; the
  notebook downloads the public NHANES data automatically. If a download fails, check internet access.

### What to inspect first

1. **Reviewer Quick Start** (top of the notebook)
2. **Plain-language Project Summary**
3. **Control Ladder** (how reference layers stack)
4. **Reference Deviation Heatmap** (how unusual each person is)
5. **BACI and BACI sensitivity** (cross-system coherence + robustness)
6. **The three graph types** (conceptual knowledge graph, observed proxy graph, decision-support graph)
7. **Individual Adaptation Profiles** (`results/adaptation_profiles.txt`)
8. **Crew-Level Summary** (`results/crew_level_summary.csv`)

---

## What NeuroBridge-S4 does

NeuroBridge-S4 is a methodology for converting **sparse, high-dimensional, multimodal** human spaceflight-like data into
**individualized adaptation management profiles**. Instead of asking whether four people can prove a population-level
effect, it asks what can be learned from **each individual's biological pattern** when compared with a real reference
population and interpreted through **connected biological systems**.

> **Central message:** NeuroBridge-S4 turns rare human spaceflight-like data from *"too small for conventional
> population statistics"* into *"deep enough for individualized biological interpretation and adaptation management."*

## Why the Artemis II challenge is small-N and multimodal

Artemis II carries a **very small crew (n = 4)**, with **many measurements per person** across multiple domains, limited
sampling, and **no conventional statistical power** and no large astronaut control group. Each individual trajectory is
therefore highly valuable. NeuroBridge-S4 is designed for exactly this structure: it treats each crew member as a
longitudinal biological system anchored to a real terrestrial reference space.

## What HRP gets from the method

- **Individual Adaptation Profiles** (one per crew member)
- **Cross-System Biological Coherence Maps**
- **Crew-Level Adaptation Summary** (without averaging away individuals)
- **Recovery and Follow-Up Data Priorities**
- **Monitoring Priority Matrix** and **Countermeasure Consideration Map**
- **A reusable analytic workflow** for Standard Measures, ARCHeR, and Immune Biomarkers

It helps HRP answer: *What changed? In which system? Is the signal isolated or coherent? Is recovery progressing? What
should be monitored next? Which countermeasure category should be considered?*

## How graph representation is used

Human adaptation is **relational**. A flat table of biomarkers loses the connections between sleep, autonomic
regulation, stress biology, immune signaling, cognition, and psychology.

> **Tables break a human system into columns; graph representation helps assemble those columns back into a biological
> and operational system.**

The notebook uses **three clearly distinct graph types**, which must not be confused:

1. **Biological Knowledge Graph** - **conceptual / literature-plausible** structure. *Not* computed from NHANES, *not*
   causal proof.
2. **Observed Proxy Coherence Graph** - **data-derived** co-variation computed from the real proxy reference space.
   Shows co-variation, *not* causation.
3. **Decision / Management Graph** - translates biological patterns into **monitoring priorities and countermeasure
   considerations**. Decision-support, *not* treatment guidance.

## What BACI is and is not

**BACI = Biological Adaptation Coherence Index.** It is a **transparent signal-triage metric** (0-100) that asks whether
multiple biological domains are shifting together strongly enough to justify closer review. It combines breadth (number
of shifted domains), magnitude, and spread across independent systems (and, in future longitudinal use, temporal
alignment and recovery delay). The notebook also runs a **sensitivity analysis** across thresholds (0.75 / 1.00 / 1.25).

- BACI **is**: a prioritization aid that answers "what should HRP look at more closely?"
- BACI **is not**: a diagnosis, a validated clinical score, or a prediction of health outcomes.

## Dataset used

The demonstration uses the U.S. CDC **National Health and Nutrition Examination Survey (NHANES)**, cycle **2017-2018**,
downloaded directly from public CDC URLs as SAS transport (`.xpt`) files: demographics, body measures, blood
pressure/pulse, fasting glucose, total/HDL/LDL cholesterol and triglycerides, complete blood count (CBC),
high-sensitivity CRP, standard biochemistry, and the smoking questionnaire.

## Why NHANES is only a health-filtered terrestrial reference approximation

NHANES is **not** astronaut data and **not** a substitute for Artemis II. It is used as **one lower rung of the Control
Ladder** - a population-scale reference space that we filter into a healthier adult subset (a **health-filtered
terrestrial reference approximation**). It is **not** astronaut-equivalent. Its role is to provide a reference coordinate
system against which each pseudo-crew member can be compared.

## How to run

**Option A - Google Colab (no setup):** upload the notebook to [Colab](https://colab.research.google.com) and choose
*Runtime -> Run all*. NHANES data downloads automatically.

**Option B - local Jupyter:**
```bash
pip install -r requirements.txt
jupyter notebook NeuroBridge_S4_Proxy_Data_Demonstration.ipynb
```
Internet access is required on the first run; downloaded files are cached under `results/nhanes_cache/` for fast,
reproducible re-runs.

**Option C - just read it:** open `NeuroBridge_S4_Proxy_Data_Demonstration.html` (if included) in any web browser, or
view the `.ipynb` on GitHub / in Jupyter / in Colab. Outputs are already embedded.

## Required Python packages

`pandas`, `numpy`, `matplotlib`, `networkx`, `requests`, and optionally `seaborn` (used only for styling if already
installed). Standard-library `pathlib` and `textwrap` are also used. See `requirements.txt`.

## Outputs generated

**Tables / reports (`results/`):** `reference_cohort_summary.csv`, `pseudo_crew.csv`, `deviation_scores.csv`,
`domain_scores.csv`, `baci_scores.csv`, `baci_sensitivity.csv`, `layer_value_analysis.csv`, `crew_level_summary.csv`,
`adaptation_profiles.txt`.

**Figures (`results/figures/`):** control ladder, cohort filtering funnel, pseudo-crew overview, reference deviation
heatmap, biological domain heatmap, BACI bar chart, BACI sensitivity, biological knowledge graph, observed proxy
coherence graph, decision/management graph, four individual adaptation networks (plus a combined panel), countermeasure
priority map, layer value analysis, Artemis II translation map, acute cognitive-perceptual layer, and the crew-level
summary.

## Real participants, not synthetic subjects

The four pseudo-crew members are **real NHANES participants** drawn from the health-filtered reference cohort and
withheld from the reference distribution used for scoring. They are identified only by their anonymized NHANES sequence
number (SEQN). **No synthetic subjects are used.**

## Actual Artemis II data is not included

Artemis II astronaut data is not available for the challenge. This notebook is explicitly a **proxy-data demonstration**
and states so throughout.

## How the method transfers to Standard Measures, ARCHeR, and Immune Biomarkers

NeuroBridge-S4 is purpose-built for the three Artemis II streams:

- **Standard Measures** -> reference deviation + biological domains (which systems deviate, and how unusually).
- **ARCHeR** -> behavioral signals interpreted into autonomic/cognitive context (sleep/circadian and workload).
- **Immune Biomarkers** -> inflammation/immune domain + stress-immune coherence.

In real use, NHANES would be only a reference rung; the value would come from an **individual pre-mission baseline**,
**in-mission** and **post-mission recovery** data, **actigraphy/sleep**, **immune/stress biomarkers**, **cognitive
performance**, and **validated psychological self-report**, integrated longitudinally.

## Limitations

- **NHANES is cross-sectional** (a single snapshot per person), so this notebook demonstrates the **reference-space and
  small-N logic**, not mission-phase dynamics.
- **Actual Artemis II longitudinal data is unavailable** for the challenge.
- A **full Artemis II implementation** would integrate Standard Measures, ARCHeR, and Immune Biomarkers longitudinally,
  climbing the Control Ladder to each astronaut's own baseline.

## No medical diagnosis / no treatment disclaimer

NeuroBridge-S4 is a **decision-support and adaptation-management** framework. It does **not** diagnose medical or
psychiatric conditions, does **not** prescribe treatment, does **not** infer brain chemistry directly from NHANES, and
does **not** claim NHANES is astronaut-equivalent. The correct interpretation of every output is: **"What systems should
HRP look at more closely?"**
