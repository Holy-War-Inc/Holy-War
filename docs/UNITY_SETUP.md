# Unity project setup

This repository currently contains repository scaffolding, not a Unity project. Create or copy the Unity project into the repository root so that `Assets/`, `Packages/`, and `ProjectSettings/` are at the root.

## Version control
- Commit `.meta` files alongside every Unity asset.
- Use text serialization and visible meta files in Unity Editor settings.
- Do not commit `Library/`, `Temp/`, `Obj/`, `Build/`, or `UserSettings/`.
- Install Git LFS on every developer machine before adding large binary assets. The committed `.gitattributes` defines the tracked extensions.
- Git LFS storage and bandwidth quotas are governed by the GitHub plan.

## Unity Smart Merge (UnityYAMLMerge)
Configure UnityYAMLMerge locally on each workstation; Git does not inherit a developer's local merge-driver configuration from the repository.

Example Git configuration (adjust the Unity Editor path for your OS and Unity version):

```ini
[merge "unityyamlmerge"]
    name = Unity SmartMerge (UnityYAMLMerge)
    driver = '"<UNITY_EDITOR>/Data/Tools/UnityYAMLMerge" merge -p "%O" "%B" "%A" "%A"'
```

On Windows, use the Unity installation's `Editor\Data\Tools\UnityYAMLMerge.exe`. On Linux/macOS, use the corresponding Unity Editor installation path. Confirm the exact command for your installed Unity version before applying it.

## CI secrets
Add these under Settings → Secrets and variables → Actions:
- `UNITY_LICENSE`: activated Unity license file contents (GameCI personal-license flow).
- `UNITY_EMAIL`, `UNITY_PASSWORD`: only if the selected GameCI license activation flow requires them.

For Android signing, add:
- `ANDROID_KEYSTORE_NAME`
- `ANDROID_KEYSTORE_BASE64`
- `ANDROID_KEYSTORE_PASS`
- `ANDROID_KEYALIAS_NAME`
- `ANDROID_KEYALIAS_PASS`

Never commit license files, keystores, passwords, tokens, or signing credentials. For local development, keep them outside the repository.
