# Bayesian Hierarchical Modeling and Clustering of Malignant Cancer Diagnoses 

This repository hosts the R Project for **EN.553.632 Bayesian Statistics (Fall 2025)** at Johns Hopkins University.

**Authors:** Jonathan Ma, Chelsea Zhu, Amber Feng  
**Instructor:** Dr. Luhao Zhang

---

## Project Overview

The goal of this project is to utilize a **Bayesian Hierarchical Logistic Regression** to investigate how tumor severity indicators (e.g., stage, grade, size) vary by **patient-level** and **region-level** characteristics. Using **individual-level cancer records** from the **SEER Public Use Research Database**, the project focuses on:

- **Characterizing tumors** by stage, grade, and size across diverse patient demographics  
- **Quantifying variation** across patients and geographic regions using multilevel models  
- **Estimating uncertainty** in severity indicators via full Bayesian inference  
- **Clustering patients or regions** based on posterior summaries to identify latent risk structures  
- **Validating** model fit through posterior predictive checks and convergence diagnostics 

---

## Data Source

**Dataset:** SEER Breast Cancer Dataset for 2016-2017, obtained by [SEER*Stat](https://seer.cancer.gov/)  
**Direct Data Download:** [SEER Breast Cancer](https://drive.google.com/file/d/1oiOPLsV4RNocBZy8q_eOPFsdZhK2MGMd/view?usp=sharing)  


Each row in the dataset represents an individual tumor with variables on tumor severity, treatment, patient demographics, and region classification. These support a **three-level hierarchy**:

1. **Level 1 – Tumor:** Stage, grade, surgical treatment, tumor size  
2. **Level 2 – Patient:** Sex, race/ethnicity, age group, marital status  
3. **Level 3 – Region:** Urban vs. rural location categories (metropolitan, non-metro, etc.)

---

## Methodology

### 1. Bayesian Hierarchical Modeling

- **Outcome:** Tumor Stage, either early (I/II) or late (III/IV) 
- **Levels:** Tumor (observed), nested within Patients (Random EFfect), nested within Regions (Random Effect)
- **Priors:** Weakly informative Normal and Student-t priors for regression and variance terms  
- **Software:** `brms` (via Stan) in R

### 2. Posterior Inference & Prediction

- Extract posterior distributions of severity indicators  
- Look at Marginal, Random, and Fixed Effects
- Check Odds Ratios for marginal interpretations
- Compare across race, sex, marital status, and regional types  
- Predict with 100 predictive draws

### 3. Latent Structure Discovery

- Cluster patients or regions based on posterior means
- Identify demographic or geographic segments with higher predicted severity  

### 4. Diagnostics and Model Validation

- Assess convergence (R-hat, ESS), variance inflation, and posterior predictive checks  

---


## Structure

```text
bayesproject-MaZhuFeng-FA25/
├── R/                            # Analysis scripts and RMarkdown modules
│   ├── EDA.Rmd                   # Exploratory data analysis and cleaning
│   ├── Model.Rmd                 # Model specification and fitting
│   ├── Posterior.Rmd             # Posterior sampling and summaries
│   ├── Clustering.Rmd            # Clustering or grouping analysis
│   ├── breast_model.rds          # Model file to save on computation time
│   └── Diagnostics.Rmd           # Convergence and model diagnostic checks
│
├── data/
│   └── raw/                      # Immutable input datasets
│       ├── RAWDATA.md.           # Instructions on how to download the data
│   └── cleaned/                  # Versions of cleaned data
│       ├── seer_nov10.csv        # cleaned data subset
│       ├── seer_df2.csv          # Standardized subset of data
│       └── dfRE_P.csv            # Patient Random EFfects for Clustering
│
├── docs/                         # Documentation and team coordination
│   ├── CHANGELOG.md              # Project updates and version history
│   ├── Contributions.md          # Collaboration guidelines and author credits
│   ├── SETUP.md                  # Environment setup and package requirements
│
├── Reports/                      # Knitted and polished RMD Files
│   ├── DataCleaning.pdf          # Exploratory data analysis and cleaning
│   ├── ModelSpecification.pdf    # Model specification and fitting
│   ├── ModelDiagnostics.pdf      # Posterior sampling and summaries
│   ├── PosteriorAnalysis.pdf     # Clustering or grouping analysis
│   └── ClusteringAnalysis.pdf    # Convergence and model diagnostic checks
├── .gitignore                    # Files and folders excluded from Git tracking
├── 01_Ma_Zhu_Feng.pdf            # Presentation Slides
├── LICENSE                       # Usage license
├── README.md                     # Project overview 
└── bayesproject-MaZhuFeng-FA25.Rproj  # RStudio project file (don't commit this)
```
