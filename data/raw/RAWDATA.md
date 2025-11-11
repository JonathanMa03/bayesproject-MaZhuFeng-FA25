# Raw Data Directory

This folder contains the **original input data** used for analysis.  
Some files are tracked in GitHub, while others are stored locally due to size limits.

---

## Files

| File | Description | 
|------|--------------|
| **breastcancer.txt** | Large raw dataset (~800 MB). Too large for GitHub; stored locally only. |

---

##  Instructions for Teammates

To reproduce results or run scripts:
1. **Download** `breast_cancer_for_bayesian_hierarchical_model.txt` from the shared drive.  
    *[https://drive.google.com/file/d/1oiOPLsV4RNocBZy8q_eOPFsdZhK2MGMd/view?usp=sharing]*  
2. Rename the file to `breastcancer.text`
2. Place it in this same directory: `data/raw/breastcancer.txt`
3. Keep the file **untracked** — it’s listed in `.gitignore`.

---

## Notes

- Do **not** commit large data files to the repository.
- If new large datasets are added, update `.gitignore` and this README to document them.
- For Cleaned data, RERUN the whole EDA.md file so you don't commit the large file

---

*Maintained by: Jonathan Ma*  
*Last updated: 2025-11-10*