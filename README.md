# Bayesian Hierarchical Modeling and Clustering of Cancer Incidence and Mortality Patterns Across U.S. Counties

This repository hosts the R Project for **EN.553.632 Bayesian Statistics (Fall 2025)** at Johns Hopkins University.

**Authors:** Jonathan Ma, Chelsea Zhu, Amber Feng  
**Instructor:** Dr. Luhao Zhang

---

## Project Overview

The goal of this project is to develop a **Bayesian hierarchical modeling framework** to understand geographic and demographic variation in cancer incidence and mortality across U.S. counties. Using publicly available data from the **U.S. Cancer Statistics (USCS)** database, the project aims to:

- **Model** age-adjusted cancer incidence and mortality rates across counties and states.
- **Account** for multi-level structure (county ⟶ state ⟶ national) using Bayesian hierarchical modeling.
- **Estimate** uncertainty and posterior distributions of incidence and mortality rates with full Bayesian inference.
- **Cluster** posterior summaries to identify latent regional or demographic patterns in cancer risk and outcomes.
- **Evaluate** convergence and goodness-of-fit through posterior predictive checks and MCMC diagnostics.

---

## Data Source

**Dataset:** [U.S. Cancer Statistics Public Use Database (1999–2022)](https://www.cdc.gov/cancer/uscs/public-use/index.htm)  
**Direct Data Download:** [USCS ASCII Data (Nov 2023)](https://www.cdc.gov/cancer/uscs/USCS-1999-2022-ASCII.zip)  
**Dictionary:** `Data Dictionary USCS ASCII Nov_2023 submission.xlsx`

The dataset contains state- and county-level age-adjusted cancer incidence and mortality rates, stratified by sex, race, site, and event type. These data support a natural **three-level hierarchical structure**:

1. **Level 1 – County:** Observations of incidence/mortality rates, counts, and populations  
2. **Level 2 – State:** Geographic grouping variable  
3. **Level 3 – National:** Aggregate U.S. level (implicit hyperprior pooling)

---

## 🔍 Methodology

1. **Bayesian Hierarchical Modeling**  
   - Outcome: Age-adjusted incidence or mortality rate  
   - Levels: County (random effects), nested within State  
   - Priors: Weakly informative Normal priors on fixed effects; Half-Cauchy on variance components  
   - Implementation: `brms`, `rstanarm`, or `cmdstanr`

2. **Posterior Summaries & Prediction**  
   - Extract posterior means, intervals, and predictive distributions for each county  
   - Summarize uncertainty and compare across states

3. **Clustering and Pattern Discovery**  
   - Apply frequentist clustering (e.g., `kmeans`, `mclust`) to posterior summaries  
   - Identify latent spatial or demographic clusters  
   - Visualize spatial risk groups across the U.S.

4. **Diagnostics and Validation**  
   - Trace plots, R-hat values, effective sample sizes  
   - Posterior predictive checks and leave-one-out cross-validation (LOO-CV)

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
│       ├── DataGuide.xlsx # Variable Guide
│       ├── RAWDATA.md.    # Instructions on how to download the data
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
