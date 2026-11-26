# Branching and pull request policy

## Branches
- `main`: stable branch; release-ready code.
- `develop`: integration branch for the next release.
- `feature/<short-name>`: gameplay and product features; branch from `develop`.
- `bugfix/<short-name>`: non-urgent fixes; branch from `develop`.
- `hotfix/<short-name>`: urgent production fixes; branch from `main`.
- `release/<version>`: release stabilization.

## Pull requests
- Feature and bugfix PRs target `develop`.
- Release PRs target `main`.
- Hotfix PRs target `main`, then are merged/cherry-picked back to `develop`.
- Keep PRs focused and use the repository PR template.
- Require CI to pass before merge.
- Prefer squash merge for feature work; preserve merge commits for release integration when useful.

## Recommended repository rules (owner action)
Create rulesets for `main` and `develop`:
- Require pull requests before merging.
- Require the CI / Repository checks status.
- Require conversation resolution.
- Block force pushes and branch deletion.
- Require linear history if the team chooses squash/rebase-only merges.
- For `main`, require at least one approval once additional reviewers exist.

GitHub may not allow a meaningful one-person approval requirement. Do not require approvals until another reviewer is available.
