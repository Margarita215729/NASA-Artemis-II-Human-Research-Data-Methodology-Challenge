# NeuroBridge-S4 - Reviewer Packet

**NeuroBridge-S4: A Small-N Human Adaptation Management Framework for Artemis II Proxy Data**
NASA Artemis II - Human Research Data Methodology Challenge

This packet is self-contained for review. **You do not need to run any code.**

## Start here

1. Open **`NeuroBridge_S4_Proxy_Data_Demonstration.html`** in any web browser (no software needed), or open the
   `.ipynb` in Jupyter / Colab / GitHub. **All outputs are already embedded.**
2. Read the **Reviewer Quick Start** and **Plain-language Project Summary** at the top of the notebook.
3. Follow the built-in **"How to review this notebook in 10 minutes"** guide.

## What to inspect first

1. Reviewer Quick Start
2. Plain-language Project Summary
3. Control Ladder
4. Reference Deviation Heatmap
5. BACI and BACI sensitivity
6. The three graph types (conceptual knowledge graph, observed proxy graph, decision-support graph)
7. Individual Adaptation Profiles (`results/adaptation_profiles.txt`)
8. Crew-Level Summary (`results/crew_level_summary.csv`)

## What this is (and is not)

- A **proxy-data demonstration** using **real public NHANES 2017-2018** data - **not** actual Artemis II astronaut data.
- The **n = 4 pseudo-crew are real NHANES participants**, not synthetic subjects.
- NHANES is a **health-filtered terrestrial reference approximation**, not astronaut-equivalent data.
- **BACI** is a **transparent signal-triage metric**, not a validated diagnostic score.
- All outputs are **decision-support** (monitoring priorities, follow-up data streams, countermeasure considerations).
- This is **not** a medical diagnostic tool and provides **no treatment guidance**.

## Packet contents

- `README_for_reviewers.md` - this file
- `NeuroBridge_S4_Proxy_Data_Demonstration.ipynb` - executed notebook with embedded outputs
- `NeuroBridge_S4_Proxy_Data_Demonstration.html` - browser-openable report (same content)
- `requirements.txt` - Python packages, only needed if reproducing
- `results/figures/` - all generated figures (`.png`)
- `results/adaptation_profiles.txt` - per-member adaptation profile reports
- `results/crew_level_summary.csv` - crew at a glance
- `results/baci_sensitivity.csv` - BACI across thresholds (robustness check)
- `results/layer_value_analysis.csv` - what each analytic layer adds

## Reproducing (optional)

```bash
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute --inplace NeuroBridge_S4_Proxy_Data_Demonstration.ipynb
```
Or open in Google Colab and choose *Runtime -> Run all*. Internet access is required on the first run to download the
public NHANES files from the CDC.
