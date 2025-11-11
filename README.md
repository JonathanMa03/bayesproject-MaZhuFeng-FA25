# Bayesian Hierarchical Modeling and Clustering of Malignant Cancer Diagnoses 

This repository hosts the R Project for **EN.553.632 Bayesian Statistics (Fall 2025)** at Johns Hopkins University.

**Authors:** Jonathan Ma, Chelsea Zhu, Amber Feng  
**Instructor:** Dr. Luhao Zhang

---

## Project Overview

The goal of this project is to build a **Bayesian hierarchical model** to investigate how tumor severity indicators (e.g., stage, grade, size) vary by **patient-level** and **region-level** characteristics. Using **individual-level cancer records** from the **SEER Public Use Research Database**, the project focuses on:

- **Characterizing tumors** by stage, grade, and size across diverse patient demographics  
- **Quantifying variation** across patients and geographic regions using multilevel models  
- **Estimating uncertainty** in severity indicators via full Bayesian inference  
- **Clustering patients or regions** based on posterior summaries to identify latent risk structures  
- **Validating** model fit through posterior predictive checks and MCMC diagnostics 

---

## Data Source

**Dataset:** SEER Breast Cancer Dataset for 2016-2017, obtained by [SEER*Stat](https://seer.cancer.gov/)  
**Direct Data Download:** [SEER Breast Cancer](https://drive.google.com/file/d/1oiOPLsV4RNocBZy8q_eOPFsdZhK2MGMd/view?usp=sharing)  


Each row in the dataset represents an individual tumor with variables on tumor severity, treatment, patient demographics, and region classification. These support a **three-level hierarchy**:

1. **Level 1 – Tumor:** Stage, grade, surgical treatment, tumor size  
2. **Level 2 – Patient:** Sex, race/ethnicity, age group, marital status  
3. **Level 3 – Region:** Urban vs. rural location categories (metropolitan, non-metro, etc.)

---

## 🔍 Methodology

### 1. Bayesian Hierarchical Modeling

- **Outcome:** Tumor stage, grade, or size (modeled separately or jointly)  
- **Levels:** Tumor (observed), nested within Patient ID, nested within Region  
- **Priors:** Weakly informative Normal and Half-Cauchy priors for regression and variance terms  
- **Software:** `brms` (via Stan), with option to export to JAGS

### 2. Posterior Inference & Prediction

- Extract posterior distributions of severity indicators  
- Compare across race, sex, marital status, and regional types  

### 3. Latent Structure Discovery

- Cluster patients or regions based on posterior means or medians  
- Identify demographic or geographic segments with higher predicted severity  

### 4. Diagnostics and Model Validation

- Assess convergence (R-hat, ESS), trace plots, and posterior predictive checks  
- Cross-validation via LOO or WAIC for model comparison  

---


## Structure

```text
bayesproject-MaZhuFeng-FA25/
├── R/                     # Analysis scripts and RMarkdown modules
│   ├── EDA.Rmd            # Exploratory data analysis and cleaning
│   ├── Model.Rmd          # Model specification and fitting
│   ├── Posterior.Rmd      # Posterior sampling and summaries
│   ├── Clustering.Rmd     # Clustering or grouping analysis
│   ├── Diagnostics.Rmd    # Convergence and model diagnostic checks
│   └── Dashboard.Rmd      # (Optional) Shiny or visualization dashboard
│
├── data/
│   └── raw/               # Immutable input datasets
│       ├── RAWDATA.md.    # Instructions on how to download the data
│   └── cleaned/           # Versions of cleaned data
│       ├── seer_nov10.csv    # cleaned data subset
│
├── docs/                  # Documentation and team coordination
│   ├── CHANGELOG.md       # Project updates and version history
│   ├── Contributions.md   # Collaboration guidelines and author credits
│   ├── SETUP.md           # Environment setup and package requirements
│   └── TODO.md            # Pending tasks and milestones
│
├── .gitignore             # Files and folders excluded from Git tracking
├── LICENSE                # Usage license
├── README.md              # Project overview 
└── bayesproject-MaZhuFeng-FA25.Rproj  # RStudio project file (don't commit this)
```
