# GitHub Actions Guide

## 📌 Introduction

GitHub Actions is a powerful CI/CD (Continuous Integration and Continuous Deployment) tool that automates workflows in your repositories. This guide will help you understand, set up, and optimize GitHub Actions for automating builds, tests, and deployments.

---

## 🏁 Getting Started with GitHub Actions

### 1️⃣ **What is GitHub Actions?**
- GitHub Actions allows you to automate tasks like testing, building, and deploying code.
- Workflows are defined using YAML files stored in `.github/workflows/`.
- Can be triggered on events like push, pull requests, issue creation, etc.

### 2️⃣ **Enabling GitHub Actions in a Repository**
- Navigate to your GitHub repository.
- Click on the `Actions` tab.
- Choose a pre-built workflow or create a new one.

### 3️⃣ **Understanding Workflow Structure**
A GitHub Actions workflow consists of:
- **Event Triggers**: Define when the workflow runs (`push`, `pull_request`, `schedule`, etc.).
- **Jobs**: Define tasks that run in the workflow.
- **Steps**: Actions performed within a job, such as installing dependencies and running tests.
- **Runners**: The environment where workflows execute (Ubuntu, macOS, Windows).

---

## 🚀 Creating Your First GitHub Actions Workflow

### **Step 1: Creating a Workflow File**
- Navigate to `.github/workflows/` in your repository.
- Create a new file (e.g., `ci.yml`).

### **Step 2: Writing a Simple Workflow**
```yaml
name: CI Pipeline

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3
      
      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '16'

      - name: Install Dependencies
        run: npm install

      - name: Run Tests
        run: npm test
```

### **Step 3: Committing and Running the Workflow**
- Commit and push the workflow file.
- Navigate to the `Actions` tab to see the workflow run.

---

## 🔥 Advanced GitHub Actions Features

### 4️⃣ **Using Secrets and Environment Variables**
- Store API keys, passwords, or tokens securely in **GitHub Secrets**.
- Access them in workflows using `secrets.MY_SECRET`.
```yaml
- name: Use Secret
  run: echo "${{ secrets.MY_SECRET }}"
```

### 5️⃣ **Matrix Builds (Testing Multiple Environments)**
```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [14, 16, 18]
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm install
      - run: npm test
```

### 6️⃣ **Deploying with GitHub Actions**
- Example: Deploying a React app to GitHub Pages
```yaml
- name: Deploy to GitHub Pages
  uses: peaceiris/actions-gh-pages@v3
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    publish_dir: ./build
```

### 7️⃣ **Scheduled Jobs (Cron Jobs)**
- Automate tasks like data backups or periodic scripts using cron expressions.
```yaml
on:
  schedule:
    - cron: "0 0 * * *"  # Runs daily at midnight
```

### 8️⃣ **Reusable Workflows**
- Share workflows across multiple repositories.
```yaml
jobs:
  call-workflow:
    uses: owner/repo/.github/workflows/shared.yml@main
```

---

## 📖 Additional Resources
- [GitHub Actions Docs](https://docs.github.com/en/actions)
- [Marketplace Actions](https://github.com/marketplace?type=actions)
- [GitHub Actions Examples](https://github.com/actions)

Master GitHub Actions and automate your workflow efficiently! 🚀