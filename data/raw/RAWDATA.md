# Raw Data Directory

This folder contains the **original input data** used for analysis.  
Some files are tracked in GitHub, while others are stored locally due to size limits.

---

## Files

| File | Description | Tracked on GitHub? |
|------|--------------|--------------------|
| **DataGuide.xlsx** | Reference or documentation guide for dataset variables and codes. | 
| **seer_data.txt** | Large raw dataset (~300 MB). Too large for GitHub; stored locally only. |

---

##  Instructions for Teammates

To reproduce results or run scripts:
1. **Download** `seer_data.txt` from the shared drive.  
    *[https://drive.google.com/file/d/1FbhTfxlywWUmSxzpZoeGiDsCV27GWnB9/view?usp=sharing]*  
2. Place it in this same directory: `data/raw/seer_data.txt`
3. Keep the file **untracked** — it’s listed in `.gitignore`.

---

## Notes

- Do **not** commit large data files to the repository.
- If new large datasets are added, update `.gitignore` and this README to document them.
- The `DataGuide.xlsx` file is safe to version-control and can be updated as variable definitions change.

---

*Maintained by: Jonathan Ma*  
*Last updated: 2025-11-09*