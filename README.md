# GitHub Learning Guide

## 📌 Introduction

GitHub is a platform for version control and collaboration. It allows developers to manage and track changes in their projects using Git.

---

## 📁 Setting Up GitHub

### 1️⃣ **Create an Account**

- Visit [GitHub](https://github.com/) and sign up.
- Set up two-factor authentication (2FA) for security.

### 2️⃣ **Install Git**

- Download from [git-scm.com](https://git-scm.com/)
- Set up your username and email:
  ```sh
  git config --global user.name "Your Name"
  git config --global user.email "you@example.com"
  ```

### 3️⃣ **Create a Repository**

- Click **New Repository** on GitHub.
- Initialize with README, `.gitignore`, and license.
- Clone the repository:
  ```sh
  git clone https://github.com/your-username/repo-name.git
  ```

---

## 📌 Working with GitHub

### 1️⃣ **Branches**

- Create a new branch:
  ```sh
  git branch feature-branch
  git checkout feature-branch  # Switch to branch
  ```
- Merge changes:
  ```sh
  git checkout main
  git merge feature-branch
  ```

### 2️⃣ **Commits**

- Make changes, then stage and commit:
  ```sh
  git add .
  git commit -m "Added new feature"
  ```
- Push changes:
  ```sh
  git push origin feature-branch
  ```

### 3️⃣ **Pull Requests (PRs)**

- Go to **Pull Requests** tab on GitHub.
- Click **New Pull Request**, compare branches, and submit.
- Merge the PR after review.

### 4️⃣ **Issues & Discussions**

- Report bugs or suggest features in **Issues**.
- Use labels, milestones, and assignments.
- Start discussions under the **Discussions** tab.

### 5️⃣ **Forking & Cloning**

- **Fork**: Make a copy of a repository.
- **Clone**: Copy a repository locally.
  ```sh
  git clone https://github.com/original-owner/repo.git
  ```

### 6️⃣ **GitHub Actions**

- Automate workflows using CI/CD.
- Example `.github/workflows/main.yml`:
  ```yaml
  name: CI Workflow
  on: push
  jobs:
    build:
      runs-on: ubuntu-latest
      steps:
        - name: Checkout code
          uses: actions/checkout@v2
  ```

### 7️⃣ **Releases & Tags**

- Use **Releases** to version your project.
- Create a tag:
  ```sh
  git tag -a v1.0 -m "Initial release"
  git push origin v1.0
  ```

### 8️⃣ **GitHub Pages**

- Host static websites directly from a repository.
- Go to **Settings → Pages**, choose the branch, and deploy.

### 9️⃣ **Security & Insights**

- Enable **Dependabot** for vulnerability alerts.
- Use **Code Scanning** to detect issues.

### 🔟 **Collaborating on GitHub**

- Invite collaborators.
- Use team reviews and protected branches.

---

## 🚀 Advanced GitHub Features

### 1️⃣ GitHub CLI

- Install GitHub CLI `(gh)`
- Authenticate with `gh auth login`
- Clone, create, and manage repositories from the terminal

### 2️⃣ GitHub Actions (CI/CD)

- Automate workflows with `.github/workflows/`
- Run tests, deployments, and scripts automatically
- Example: Auto-deploy a React app to GitHub Pages

### 3️⃣ GitHub Projects

- Create a Kanban board for task management
- Assign issues to project milestones
- Track progress with automation

### 4️⃣ GitHub Discussions

- Engage with the community on projects
- Start discussions, ask questions, and share ideas

### 5️⃣ GitHub Copilot (AI-Powered Coding)

- Use AI-based code suggestions
- Works with VS Code, JetBrains, and Neovim

### 6️⃣ GitHub Pages

- Host static websites using `gh-pages` branch
- Free hosting for portfolios and documentation

### 7️⃣ GitHub Security Features

- **Dependabot:** Automatically updates dependencies
- **Code Scanning:** Detect security vulnerabilities
- **Secret Scanning:** Protect sensitive information

---

## 🚀 Conclusion

GitHub is a powerful tool for software development. Mastering its features helps in efficient collaboration, version control, and automation.

📌 Need more? Refer to the [GitHub Docs](https://docs.github.com/)
