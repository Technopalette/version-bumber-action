# 🚀 Automatic Version Bumper

Automatically bumps your project version and creates GitHub Releases based on **Pull Request title conventions**.  
Designed to follow **semantic versioning** rules in a simple, automated way.

---

## 📌 What it does

✅ Detects the correct version bump (major, minor, patch) from your PR title  
✅ Updates the version based on the previous version you provide  
✅ Creates a Git tag for the new version  
✅ Extracts release notes from your `CHANGELOG.md`  
✅ Creates a GitHub Release with those release notes

---

## 🗂️ PR Title Conventions

| Prefix                 | Version bump |
|------------------------|---------------|
| `feat!:` or `fix!:`    | Major         |
| `BREAKING CHANGE`      | Major         |
| `feat:`                | Minor         |
| `fix:`                 | Patch         |
| _(any other)_          | No bump       |

---

## ⚙️ Inputs

| Name             | Required | Description                               |
|------------------|----------|-------------------------------------------|
| `token`          | ✅        | A GitHub token for creating releases. Usually `${{ secrets.GITHUB_TOKEN }}` |
| `initial_version` | ✅       | The current version, e.g., `1.2.3`        |
| `force_initial`  | ❌        | Whether to force use of the initial version. Default is `false` |

---

## 🏷️ Outputs

| Name         | Description                  |
|--------------|------------------------------|
| `new_version` | The new calculated version number |

---

## 📖 How it works

1. Reads the PR title when a pull request is **closed** or **merged**.
2. Checks if the title matches semantic prefixes (`feat:`, `fix:`, `feat!:`).
3. Bumps the version accordingly.
---
