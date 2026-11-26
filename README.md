# Holy-War

Mobile game project built with Unity.

> Repository bootstrap is in progress. The Unity project itself has not yet been added.

## Repository layout
- `.github/workflows/` — CI and Android build workflows.
- `.github/ISSUE_TEMPLATE/` — bug and feature request forms.
- `docs/` — branching and Unity setup guidance.
- `Assets/`, `Packages/`, `ProjectSettings/` — add the Unity project here.

## Branches
- `main` — stable / release-ready.
- `develop` — integration.
- `feature/*`, `bugfix/*`, `hotfix/*`, `release/*` — short-lived work branches.

See [branching policy](docs/BRANCHING.md) and [Unity setup](docs/UNITY_SETUP.md).

## CI/CD
Repository checks run on pushes and pull requests. Unity tests and Android builds activate automatically once a Unity project with `ProjectSettings/ProjectVersion.txt` is committed.

Android builds can also be started manually from Actions or by pushing a `v*` tag. Configure the required repository Actions secrets before running licensed Unity jobs.
