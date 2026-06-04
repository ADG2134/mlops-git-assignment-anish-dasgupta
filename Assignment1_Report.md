# Assignment 1 Report – Git & Version Control

**Name:** Anish Dasgupta
**Student ID:** 136059250
**Course Code:** MAI204 – MLOps
**Date:** 2026-06-04

---
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/5c8ea205-2855-414d-905d-5c7a63024a1d" />

## 1. GitHub Network Graph

> Screenshot showing all branches and merges (paste from GitHub → Insights → Network):
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/657f92c3-f3f7-41b1-a485-7e50293afd15" />
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/02af24bc-d858-450d-b501-605665d02ca5" />
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/e688a933-53ac-4f21-aa65-6e929e553f87" />

The repository was created with the correct naming convention: `mlops-git-assignment-anish-dasgupta`.
The `develop` branch was successfully created from `main` and set as the default branch for pull requests.
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/bbe9badd-c80d-4338-92be-e4c39b5d7504" />

All feature branches were branched from `develop`, had at least 2 commits each, and were merged back into `develop` via pull requests:

- `feature/add-readme-details` → PR #1 → merged into `develop`
- `feature/add-dockerignore` → PR #2 → merged into `develop`
- `feature/add-code-of-conduct` → PR #3 → merged into `develop`
- `feature/update-readme` → PR #4 → merged into `develop` (with conflict resolution)

---

## 2. Branch Protection Rules

Branch protection rules configured for the `main` branch:
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/78567b09-f7de-4c78-88e9-76759ef274a2" />
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/5b5e3b78-046e-451b-b796-722ebe2af30b" />
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/d93f6020-9881-40d1-a787-ca880b1f10d1" />
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/860e997b-8074-44a8-bc11-433ab8a21379" />

- ✅ Require a pull request before merging
- ✅ Require at least 1 approval
- ✅ Dismiss stale pull request approvals when new commits are pushed
- ✅ Require linear history
- ✅ Disable force pushes (Allow force pushes — unchecked)
- ✅ Disable branch deletion (Allow deletions — unchecked)

*(Attach branch protection screenshot here from: GitHub → Settings → Branches → main rule)*

---

## 3. Git Commit History

Output of `git log --oneline --graph --all`:

```
*   c7f95a4 (HEAD -> develop, origin/develop) Merge pull request #4 feat: add student name Anish Dasgupta and ID 136059250 to README
|\
| * 2753700 (feature/update-readme) Rename Add student name and ID to README to README.md
| * 2b433cf Update and rename README.md to Add student name and ID to README
|/
*   0e2e424 Add course code and submission date to README
*   a3ee1b7 Merge pull request #3 feat: add CODE_OF_CONDUCT.md using Contributor Covenant
|\
| * 65c22dd (feature/add-code-of-conduct) Add contact and reporting guidelines to Code of Conduct
| * 5d0a9f0 Create CODE_OF_CONDUCT.md
|/
*   7e9d3c8 Merge pull request #2 feat: add .dockerignore with Python project exclusions
|\
| * ded3931 (feature/add-dockerignore) Add CI/CD and secrets exclusions to .dockerignore
| * 4f6cab2 Create .dockerignore
|/
*   96303b4 Merge pull request #1 feat: add detailed README with setup, contributing and license sections
|\
| * 4ff8bc2 (feature/add-readme-details) Add license and acknowledgements sections to README
| * a4c093d Add contributing and troubleshooting sections to README
|/
*   538254e (main) Add README.md with project details and setup instructions
```
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/8bdc01d4-e6a9-4a36-83e1-dcec68337afd" />

---

## 4. Reflection on Merge Conflicts
<img width="1512" height="982" alt="image" src="https://github.com/user-attachments/assets/5ae6a0ce-575f-42dc-a010-851d95cd7649" />

Resolving the merge conflict in `README.md` between `feature/update-readme` and `develop` was the most challenging part of this assignment. Both branches had modified the same file in overlapping regions — `feature/update-readme` added the student name and ID (136059250), while `develop` had the course code (MAI204) and submission date added at approximately the same location in the file.

Git could not automatically determine which changes to keep since both edits touched the end of the file. The conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) made it clear which version came from which branch, but resolving it required carefully editing the file to preserve both sets of changes.

Using GitHub's web-based conflict editor made the process more visual — the "Accept both changes" option allowed both the student information and course details to coexist in the final merged file without losing either change.

**Key lessons learned:**
- Always pull and sync the latest `develop` before starting a new feature branch to minimise divergence
- Small, focused commits in specific file sections reduce the risk of overlapping conflicts
- Clear commit messages and PR descriptions help collaborators understand intent, making conflict resolution faster in team settings
- The gap between branching and merging should be kept short in active projects
