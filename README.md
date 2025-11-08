# Bayesian Hierarchical Modeling and Clustering of Adolescent Mental Health Risk Profiles

This repository is for hosting the R-Project associated with JHU's EN.553.632 Bayesian Statistics, Fall 2025.

Authors: Jonathan Ma, Chelsea Zhu, Amber Feng

Aim: The goal of this project is to develop a Bayesian hierarchical modeling framework for understanding and predicting adolescent mental health outcomes using survey data from the Youth Risk Behavior Surveillance System (YRBS). Specifically, we aim to:
- Model the likelihood that a student reports persistent feelings of sadness or hopelessness, using individual-level behavioral, lifestyle, and psychosocial risk factors as predictors.
- Account for group-level variation across demographic categories (e.g., race/ethnicity, grade level) through hierarchical (multilevel) modeling.
- Identify latent subgroups of adolescents with similar risk profiles using Bayesian clustering techniques.
- Estimate and interpret posterior distributions of both model parameters and latent group assignments using modern MCMC methods, with appropriate diagnostics and model checking to ensure convergence and fit.

Data Source: https://www.cdc.gov/yrbs/data/index.html. 

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
│       ├── yrbs2019.csv
│       └── yrbs2021.csv
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
