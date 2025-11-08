# Contributions Guide

This guide explains how each team member can clone the project, make changes in RStudio, keep the repository up to date, and record updates in the changelog.

---

##  1. Getting Started

### Step 1 – Accept the repository invitation
You’ll receive an invite to join the project on GitHub.  
Accept it, then you’ll have permission to push and pull.

### Step 2 – Clone the project into RStudio
1. In RStudio:  
   **File → New Project → Version Control → Git**  
2. Paste the repository URL, e.g.  https://github.com//bayesproject-MaZhuFeng-FA25.git
3. Choose a local folder (e.g., `~/Documents/RProjects/`).
4. Click **Create Project**.

RStudio will open the project automatically and show the **Git** tab.

---

## 2. Keeping Your Copy Up-to-Date

Before starting any work **always pull the latest version**:

```bash
git pull origin main
```
or click the "Pull" button in RStudio’s Git tab. This prevents merge conflicts and ensures you’re working on the newest files.

---
## 3. Branching and Collaboration

### Why Use Branches?

Branching allows everyone to work on new features, analyses, or documentation **without changing the stable main branch**.

**In short:**
- Keeps `main` clean and functional.  
- Prevents overwriting teammates’ work.  
- Makes it easy to review and merge code safely.  

Think of branches as “temporary workspaces” for specific tasks (e.g., `feature/eda-update`, `feature/model-improvement`).

---

### How to Create and Use a Branch

#### Option A — In RStudio (GUI)
1. Click the **Git** tab → open the **branch dropdown** (top toolbar near “main”).  
2. Select **New Branch**.  
3. Name it descriptively, for example: `model-update`
4. Make your changes, then commit and push as usual.  
RStudio will track that branch automatically.

#### Option B — In the Terminal
```bash
# Make sure main is up-to-date
git checkout main
git pull origin main

# Create and switch to a new branch
git checkout -b model-update
```

When you finish your work:

```bash
git add .
git commit -m "feat: add model diagnostic plots"
git push origin model-update
```

Then, go to GitHub → Open a Pull Request (PR) → request review → Merge into main once approved. (we can double check eachothers work)

Getting updates:

If teammates have updated main, you can sync those changes into your branch:

```bash
git checkout main
git pull origin main
git checkout model-update
git merge main
```

---

## 4. Making and Committing Changes

1. Save your modified files (`.Rmd`, `.md`, etc.).  
2. In the **Git** tab:
   - Check the boxes for the files you changed or added.
   - Click **Commit**.  
3. Enter a short, clear message
4. Click **Commit**, then **Push (↑)**.
5. Verify changes by refreshing the repository

### 🆕 If You Create a New File or Folder

If you add a new file (for example, `R/NewAnalysis.Rmd`) or a new folder (like `data/cleaned/` or `figures/`):

1. **Make sure it appears in the Git tab.**  
- If you don’t see it, click the **🔄 Refresh** icon.
2. **Stage it manually** by checking its box.  
3. **Commit** it with a clear message describing the addition
4. **Push** your changes so the new files are available to the team.  
5. If the new folder doesn’t show up because it’s empty, add a small `.keep` file inside it so Git tracks it:
```r
file.create("figures/.keep")
```
Tip: Always check that your .gitignore file isn’t excluding your new folder type before committing.

---

##  5. Commiting to the ChangeLog

Once you make any change, it would be helpful to

1.	Open docs/CHANGELOG.md.
2.	Under "Added" or "Changed", add a bullet for your update:

```markdown
### Added
- JM 11/7: Initial Repository Creation, added directories for docs and data.
- JM 11/8: Added data files and RProject Initialization

### Changed
- JM 11/8: Changed formatting and instructions in Contributions.md.
```

