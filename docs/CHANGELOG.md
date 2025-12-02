Added
  - JM 11/7: Initial repository creation; established directory structure for docs/ and data/.
  - JM 11/8: Added raw data files; initialized .Rproj file for RStudio project management.
  - JM 11/8: Added local backup file for redundancy.
  - JM 11/9: Integrated SEER dataset and committed corresponding updates.
  - JM 11/14: Created functions for missingness indicators and generated missingness tables and proportion summaries.
  - JM 11/18: Created model files and chunked exploratory modeling scripts.
  - JM 11/20: Added posterior summaries and model diagnostics (e.g., odds ratio plots, ICC plots, shrinkage plots).
  - JM 11/23: Added code for clustering analysis
  - JM 12/1: Added Presentation File

Changed 
  - JM 11/8: Updated Contributions.md with clearer formatting and task guidelines.
  - JM 11/8: Conducted initial EDA, merged datasets, and selected preliminary variables.
  - JM 11/9: Switched from original data source to SEER for consistency and better coverage.  
  - JM 1/12: Finalized list of predictors for multilevel modeling; transformed and standardized covariates (size_z, year_z).
  - JM 11/20: Reorganized model output for professionalism—separated hyperparameters, regression coefficients, and visualizations.
  - JM 11/21: Filtered regression summary to only display statistically significant effects with confidence intervals and stars.
  - JM 11/22: Updated plots for patient- and region-level random effects, shrinkage, and posterior ICC distributions.

Analyzed 
  - JM 11/14: Ran logistic regression to assess MCAR assumption; created summary tables with glm() and broom::tidy().
  - JM 11/15: Visualized missingness patterns across demographic subgroups (e.g., race, region).
  - JM 11/17: Interpreted posterior odds ratios and marginal effects from multilevel logistic regression model.
  - JM 11/21: Conducted shrinkage analysis at patient and region levels; visualized raw vs. posterior probabilities.
  - JM 11/22: Summarized posterior predictive checks using ppc_dens_overlay() to assess model fit.
  - JM 11/25: Polished notebook descriptions
