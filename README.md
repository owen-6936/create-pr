# 🤖 Automate Pull Request Creation

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/owen-6936/create-pr?style=for-the-badge)](https://github.com/owen-6936/create-pr/releases)  
[![Build Status - develop](https://img.shields.io/github/actions/workflow/status/owen-6936/create-pr/test-action.yml?branch=develop&style=for-the-badge)](https://github.com/owen-6936/create-pr/actions/workflows/test-action.yml)  
[![License](https://img.shields.io/github/license/owen-6936/create-pr?style=for-the-badge)](https://github.com/owen-6936/create-pr/blob/main/LICENSE)

A GitHub Action that programmatically creates a pull request from a branch — with optional metadata injection including labels and comments. Designed for CI workflows that prioritize clarity, authorship integrity, and reviewer experience.

---

## ✨ Features

- Creates a pull request from a source branch to a target branch
- Injects markdown-formatted body with workflow metadata
- Applies labels (auto-creates if missing)
- Posts a comment to the PR (optional)
- Outputs PR number and URL for downstream use

---

## 🚀 Usage

```yaml
name: Example Workflow

on:
  push:
    branches-ignore:
      - main

jobs:
  create-pr:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Create Pull Request
        id: pr-creation
        uses: owen-6936/create-pr@v1.1.0
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          branch: ${{ github.ref_name }}
          base-branch: 'main'
          title: 'Automated PR from ${{ github.ref_name }}'
          body: 'This PR was automatically created by a workflow.'
          labels: 'automated,ci-pending'
          comment-body: '✅ Code quality checks will run shortly. [View PR](${{ steps.pr-creation.outputs.pr_url }})'

      - name: Check the new PR
        run: |
          echo "Successfully created pull request #${{ steps.pr-creation.outputs.pr_number }}"
          echo "URL: ${{ steps.pr-creation.outputs.pr_url }}"
```

---

## 🔧 Inputs

| Name           | Description                                                  | Required | Default                                      |
|----------------|--------------------------------------------------------------|----------|----------------------------------------------|
| `github-token` | GitHub token for authentication                              | ✅       | —                                            |
| `branch`       | Source branch for the pull request                           | ✅       | —                                            |
| `base-branch`  | Target branch for the pull request                           | ✅       | —                                            |
| `title`        | Title of the pull request                                    | ❌       | `PR created by automated workflow`           |
| `body`         | Body content of the pull request                             | ❌       | `This pull request was automatically created by a workflow.` |
| `labels`       | Comma-separated list of labels to apply                      | ❌       | `automated`                                  |
| `comment-body` | Optional comment to post after PR creation                   | ❌       | *(none)*                                     |

---

## 🧪 Outputs

| Name       | Description                          |
|------------|--------------------------------------|
| `pr_number`| Number of the created pull request   |
| `pr_url`   | URL of the created pull request      |

---

## 🛡️ Integrity & Permissions

This action respects authorship boundaries:

- Labels are auto-created if missing
- Comments are only posted if explicitly provided
- No edits are made to existing PRs — this action only runs when it authors the PR

Make sure your workflow has **write permissions** enabled:

```yaml
permissions:
  contents: write
  pull-requests: write
```

You can configure this under **Settings > Actions > General > Workflow permissions**.

---

## 🤝 Contributing

All contributions are welcome! If you find a bug or have a feature request, feel free to open an issue or submit a pull request.

---

## 📄 License

This project is licensed under the MIT License.

---

## 👤 About the Author

Created by **Owen**, a full-stack developer focused on modular CI/CD, expressive automation, and reviewer-centric DX.  
Explore more of my work at [github.com/owen-6936](https://github.com/owen-6936)
