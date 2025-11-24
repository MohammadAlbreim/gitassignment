# GIT_STEPS – Git Assignment (Java Training)

Project: Git Assignment – Java Training Course  
Student: Mohammad Albreim  
GitHub Repository: https://github.com/MohammadAlbreim/gitassignment  

---

## Part 1 – Introduction & Setup

- Git is a distributed version control system used to track changes and manage different versions of code locally.
- GitHub is an online hosting service for Git repositories that makes collaboration easier with pull requests, issues, and a web interface.
- Developers use Git to keep history, experiment safely with branches, and work together without losing their work.

- I installed **Git for Windows** and verified the installation with:

  - `git --version`

- I configured my global username and email:

  - `git config --global user.name "Mohammad Albreim"`
  - `git config --global user.email "myemail@example.com"`

- I checked the configuration using:

  - `git config --global --list`

---

## Part 2 – Starting a Project

- I created a new repository called **gitassignment** using GitHub Desktop (Create a New Repository).
- I chose my Desktop as the local path.
- I checked the option **“Initialize this repository with a README”**, so the file `README.md` was created automatically.
- GitHub Desktop created the first commit with the README file.
- Then I pressed **Publish repository** to upload the repository to GitHub.

- Remote repository information:
  - URL: `https://github.com/MohammadAlbreim/gitassignment`
  - Default branch: `main`

---

## Part 3 – Branching & Merging

- I created a new branch from `main` called **`feature-intro`**:
  - From GitHub Desktop: *Current branch → New branch → feature-intro*.

- On branch `feature-intro` I added a new file:

  - File: `intro.txt`
  - Content: a simple line that says this is an intro file for the assignment.

- I committed the new file on the branch using GitHub Desktop with the message:

  - `Add intro file`

- I pushed the branch to GitHub using **Push origin**.

- Then I switched back to `main` and merged the branch:
  - *Current branch → main*
  - *Branch → Merge into current branch… → select feature-intro*
  - After the merge I pushed the updated `main` branch to GitHub.

- The file `intro.txt` now exists in the `main` branch on GitHub.

---

## Part 4 – Collaboration (Simulated)

- I created another branch from `main` called **`mohammad-collab`** using GitHub Desktop.
- On this branch I added a shared collaboration file:

  - File: `team_notes.txt`
  - Example content:
    - `Contribution by Mohammad (student 1)`
    - `I added my notes in the shared collaboration file.`

- I committed the file with the message:

  - `Add team_notes with my collaboration line`

- I pushed the branch to GitHub.

- On GitHub I opened a **Pull Request**:
  - Base branch: `main`
  - Compare branch: `mohammad-collab`
  - PR title: *Add team_notes with my collaboration line*.

- The pull request showed **“No conflicts with base branch”**, so I merged it using:
  - **Merge pull request → Confirm merge**.

- Back in GitHub Desktop I used **Fetch origin** and then **Pull** so that my local `main` branch included the `team_notes.txt` file.

---

## Part 5 – Merge Conflicts

- On branch `main` I created a file to test conflicts:

  - File: `conflict.txt`
  - Initial content: `Original line for conflict test`

- I committed the file with message:

  - `Add conflict base file`
  - Then I pushed it to GitHub.

### Branch A – `conflict-a`

- I created a new branch from `main` called **`conflict-a`**.
- On this branch I edited `conflict.txt` so that it contained:

  - `Line from branch A`

- I committed and pushed with message:

  - `Update conflict.txt from branch A`

### Branch B – `conflict-b`

- I went back to `main` and created another branch called **`conflict-b`**.
- On this branch I edited the same file `conflict.txt` and changed the line to:

  - `Line from branch B`

- I committed and pushed with message:

  - `Update conflict.txt from branch B`

### Creating and resolving the conflict

- While on branch `main` in GitHub Desktop, I merged `conflict-a` into `main` first (no conflict).
- Then I tried to merge `conflict-b` into `main`:
  - *Branch → Merge into current branch… → conflict-b*.

- GitHub Desktop reported a merge conflict in `conflict.txt` and showed conflict markers:

  Line from branch A
  Line from branch B
