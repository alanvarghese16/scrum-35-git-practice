# SCRUM-35 Git Practice

This repository is used to practice a standard Git branching and collaboration workflow, covering branch creation, pull requests, code reviews, and merging.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/alanvarghese16/scrum-35-git-practice.git
cd scrum-35-git-practice
```

### 2. If You Already Have the Repo

```bash
git pull origin master
```

### 3. Create a Feature Branch

```bash
git switch -c feature/issue-2-getting-started
```

## Git Workflow

### 1. Branch Creation

- Always branch off the latest `main` (or `master`) branch:

  ```bash
  git checkout main
  git pull origin main
  git checkout -b feature/short-description
  ```

- Use clear, prefixed branch names so purpose is obvious at a glance:

  | Prefix       | Use case                          |
  |--------------|------------------------------------|
  | `feature/`   | New functionality                  |
  | `fix/`       | Bug fixes                          |
  | `chore/`     | Maintenance, tooling, docs         |
  | `hotfix/`    | Urgent production fixes            |

  Example: `feature/update-readme`, `fix/login-error`

### 2. Making Changes

- Keep commits small and focused on a single change.
- Write descriptive commit messages explaining *why*, not just *what*.
- Push the branch to the remote regularly:

  ```bash
  git push -u origin feature/short-description
  ```

### 3. Pull Requests

- Open a pull request (PR) from your branch into `main` once the work is ready for feedback.
- Every PR should include:
  - A clear title summarizing the change.
  - A description of what changed and why.
  - A link to the related ticket (e.g., SCRUM-35).
  - A test plan or notes on how the change was verified.
- Keep PRs small and scoped to a single concern to make review easier.

### 4. Code Reviews

- At least one reviewer should approve a PR before it is merged.
- Reviewers check for:
  - Correctness and edge cases.
  - Code clarity and adherence to project conventions.
  - Adequate test coverage.
- Authors should respond to review comments, push follow-up commits, and re-request review as needed.
- Resolve conversations only once the concern has actually been addressed.

### 5. Merge Workflow

- Ensure the branch is up to date with `main` before merging (rebase or merge `main` into the branch to resolve conflicts).
- Confirm all required checks (CI, review approvals) pass.
- Prefer **squash merging** to keep the `main` history clean, unless the team agrees otherwise.
- Delete the feature branch after merging to keep the repository tidy:

  ```bash
  git branch -d feature/short-description
  git push origin --delete feature/short-description
  ```

## Summary

```
main
 └── feature/xyz  →  commits  →  push  →  Pull Request  →  Review  →  Merge  →  branch deleted
```
