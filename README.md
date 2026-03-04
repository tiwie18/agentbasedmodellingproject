# Supplementary Materials  
## ABM–LLM–ML Platform for Indonesia’s Power-Sector Carbon Tax Simulation

This repository contains the supplementary materials for the MSc Research Paper:

**AN AI-ENHANCED AGENT-BASED SIMULATION FRAMEWORK FOR CARBON PRICING: AN INDONESIA POWER SECTOR CASE STUDY**
Pratiwi Eka Sugiarti and Peer-Olaf Siebers
School of Computer Science, University of Nottingham (UK)

The materials support transparency, reproducibility, and inspection of the full workflow:
1. an Agent-Based Simulation (ABS) for hybrid carbon pricing,
2. LLM-assisted rule extraction (pre-simulation) and policy brief generation (post-simulation), and
3. ML-based plant clustering (offline) for heterogeneous retrofit multipliers.

# 1. Repository Structure
```
project_supplementary_materials/
├── README.md
│
├── core_simulation/
│   ├── core_abs.ipynb
│   ├── gov_rules_llm.json
│   ├── company_rules_llm.json
│   ├── Indonesia_Coal_Plants.csv
│   └── annual_energy_by_zone_2015_2024_FIXED.csv
│   └── coal_plants_with_kprototypes.csv     
│
├── llm_prompts/
│   ├── gov_rule_extraction_prompt.txt
│   └── company_rule_extraction_prompt.txt
│
├── ml_clustering/
│   ├── Clustering_Plants.ipynb
│   ├── coal_plants_indonesia_enriched.csv
│   ├── coal_plants_with_clusters.csv
│   ├── plant_cluster_centroids.csv
│   └── plant_cluster_summary.csv
│
├── regulations/
│   ├── UU Nomor 7 Tahun 2021.pdf
│   └── PERPRES_110_2025.pdf
│
└── figures/
    ├── ABS.png
    ├── LLM.png
    └── ML.png
```    

# 2. Contents Overview

## a. **Running the Simulation**
Open: core_simulation/core_abs.ipynb

Make sure the following files are in the same folder:

- `gov_rules_llm.json`
- `company_rules_llm.json`
- `Indonesia_Coal_Plants.csv`
- `annual_energy_by_zone_2015_2024_FIXED.csv`

Then:

1. Open the notebook in **Jupyter / VSCode**
2. Run **all cells**
3. The simulation runs **30-year policy scenarios**

The model is **deterministic**, so repeated runs produce identical results.

---

## b. **Simulation Outputs**

Running the simulation generates:

**Plots** plot_total_emission.png, plot_gov_rev_cum.png, plot_profit_cum.png
**Structured results** decision_report_brief.json
**AI-generated policy brief** decision_policy_brief.docx

The policy brief summarizes the simulation results in **plain language for policymakers**, including:
- emissions outcomes
- government revenue
- company profits
- policy trade-offs
- recommended actions

The LLM is used **only after the simulation completes**, so the model itself remains fully reproducible.

---

## c. Plant Clustering

Plant heterogeneity is introduced through clustering.
Open: ml_clustering/Clustering_Plants.ipynb, Required dataset: coal_plants_indonesia_enriched.csv
Running the notebook produces: coal_plants_with_clusters.csv, plant_cluster_centroids.csv, plant_cluster_summary.csv

Cluster labels can be merged into the plant dataset used by the ABS.

## d. Software Requirements

Python **3.9+**
Required libraries: mesa, numpy, pandas, scikit-learn, matplotlib, jupyter, python-docx


The ABS runs independently of the LLM during simulation to ensure **reproducibility and auditability**.


# Citation

If you use this repository, please cite:

Sugiarti, P. E., & Siebers, P.-O. (2026).  
**An AI-Enhanced Agent-Based Simulation Framework for Carbon Pricing: An Indonesia Power Sector Case Study.**

GitHub repository:  
https://github.com/tiwie18/agentbasedmodellingproject
