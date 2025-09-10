# Automate Pull Request Creation 🤖

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/owen-6936/create-pr?style=for-the-badge)](https://github.com/owen-6936/create-pr/releases) [![Build Status - develop](https://img.shields.io/github/actions/workflow/status/owen-6936/create-pr/test-action.yml?branch=develop&style=for-the-badge)](https://github.com/owen-6936/create-pr/actions/workflows/test-action.yml) [![License](https://img.shields.io/github/license/owen-6936/create-pr?style=for-the-badge)](https://github.com/owen-6936/create-pr/blob/main/LICENSE)

This GitHub Action automates the creation of a new pull request. It is designed to be used in continuous integration workflows to programmatically create a pull request from a branch, including setting the title, body, and base branch.

---

## Usage

This action is used within a GitHub Actions workflow. The simplest use case involves calling the action with its required inputs.

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
        uses: owen-6936/create-pr@v1.0.0
        with:
          branch: ${{ github.ref_name }}
          base-branch: 'main'
          title: 'Automated PR from ${{ github.ref_name }}'
          body: 'This PR was automatically created by a workflow.'

      - name: Check the new PR
        run: |
          echo "Successfully created pull request #${{ steps.pr-creation.outputs.pr_number }}"
          echo "URL: ${{ steps.pr-creation.outputs.pr_url }}"
````

---

### Inputs

| Input | Description | Required | Default |
|---|---|---|---|
| `branch` | The branch from which the pull request is created. | `true` | |
| `base-branch` | The base branch to create the pull request against. | `true` | |
| `title` | The title for the new pull request. | `false` | `PR created by automated workflow` |
| `body` | The body content for the new pull request. | `false` | `This pull request was automatically created by a workflow.` |

---

### Outputs

| Output | Description |
|---|---|
| `pr_number` | The number of the created pull request. |
| `pr_url` | The URL of the created pull request. |

---

### Contributing

All contributions are welcome\! If you find a bug or have a feature request, please open an issue or submit a pull request.

---

### License

This project is licensed under the MIT License.

---

### About the Author

This project was created by **Owen**, a full-stack developer passionate about automation and JavaScript(Typescript). You can find more of my work on my GitHub profile: [https://github.com/owen-6936](https://github.com/owen-6936).
