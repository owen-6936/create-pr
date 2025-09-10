# Contributing to `create-pr`

First and foremost, thank you for your interest in contributing to the `create-pr` GitHub Action! Your help is invaluable in making this tool more reliable and feature-rich.

This guide outlines the steps for contributing—whether you're filing a bug report, suggesting a feature, or submitting code.

---

## 🐞 Reporting Bugs

If you find a bug:

1. Check the [Issues](../../issues) to see if it's already been reported.
2. If not, [open a new issue](../../issues/new).
3. Provide a **clear and concise** description of the problem.
4. Include:
   - Steps to reproduce the issue
   - Relevant logs or screenshots
   - Your environment (OS, Node.js version, etc.)

---

## ✨ Suggesting Enhancements

New features and enhancements are always welcome! Here's how to suggest one:

1. [Open a new issue](../../issues/new) with the `enhancement` label.
2. Describe your idea, use case, and why it would be useful.
3. Wait for feedback or discussion before submitting code. This ensures alignment with the project's goals and avoids wasted effort.

---

## 💻 Code Contributions

We welcome and encourage code contributions! This is a great way to get hands-on experience with **vanilla JavaScript** and **Node.js** in a real-world GitHub Action.

### Prerequisites

- [Git](https://git-scm.com/)
- [Node.js & npm](https://nodejs.org/)

---

### 🚀 Getting Started

1. **Fork** the repository on GitHub.
2. **Clone** your fork:

   ```bash
   git clone https://github.com/YOUR_GITHUB_USERNAME/create-pr.git
   cd create-pr
    ````

3. **Install dependencies**:

   ```bash
   npm install
   ```

4. **Create a new branch** for your feature or fix:

   ```bash
   git checkout -b feature/your-feature-name
   ```

---

### ✅ Commit Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification. Examples:

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation changes
- `ci`: CI/CD changes

If you're writing a **multi-line commit message**, follow this format:

```bash
feat: add support for new config option

This feature allows users to override the default base branch
using an optional input parameter in the action.
```

> 💡 Your commit message will be parsed and used in pull request titles and descriptions, so make it meaningful!

---

## 🔁 Pull Request Process

1. Ensure your branch is up-to-date with `main`.
2. Push your changes:

   ```bash
   git push origin feature/your-feature-name
   ```

3. Open a pull request (PR) against the `main` branch.
4. Fill out the PR template and link to any related issues.
5. 🎉 Your pull request will automatically be formatted using the `create-pr` action itself!

---

## 📄 License

By contributing to this project, you agree that your contributions will be licensed under the [MIT License](LICENSE).

---

### 🙌 Thank You

Thank you again for helping improve `create-pr`. We look forward to your contributions — happy coding!
