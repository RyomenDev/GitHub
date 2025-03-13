## How to Use GitHub Actions for CI/CD

GitHub Actions automates workflows like testing, building, and deploying code. This guide explains how to set up and use the provided **CI Pipeline** workflow.

## 🚀 Steps to Use This GitHub Actions Workflow

### 1️⃣ Enable GitHub Actions in Your Repository

1. Go to your GitHub repository.
2. Click on the **Actions** tab.
3. If not enabled, click **New Workflow** and create a `.github/workflows/` folder in your repo.

### 2️⃣ Add the Workflow File

1. In your repository, create a new directory:

```bash
.github/workflows/
```

2. Inside that folder, create a new YAML file, e.g., `ci-pipeline.yml`.

3. Copy and paste the optimized CI/CD pipeline code:

```yaml
name: CI Pipeline

on: [push, pull_request]

jobs:
build:
runs-on: ubuntu-latest
strategy:
matrix:
node-version: [14, 16, 18]
steps: - name: Checkout Repository
uses: actions/checkout@v3

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: ${{ matrix.node-version }}

      - name: Install Dependencies
        run: npm install

      - name: Run Tests
        run: npm test

      - name: Build Project
        run: npm run build  # Ensure your project has a build script

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./build

```

### 3️⃣ Commit and Push Changes

1. Save the file and commit the changes:

```sh
git add .github/workflows/ci-pipeline.yml
git commit -m "Added GitHub Actions CI Pipeline"
git push origin main
```

2. GitHub will automatically trigger the workflow on `push` or `pull_request`.

### 4️⃣ Monitor Workflow Execution

1. Go to **Actions** in your GitHub repo.
2. Click on the latest workflow run to see logs, errors, and results.

### 5️⃣ Deploy to GitHub Pages (Optional)

- If deploying to GitHub Pages, set the `GITHUB_TOKEN` secret:
  1. Go to **Settings > Secrets and Variables > Actions**
  2. Click **New Repository Secret**
  3. Add **Name:** `GITHUB_TOKEN`, **Value:** `your personal access token`

✅ Expected Results

- Automatically runs tests on Node.js 14, 16, and 18.
- Deploys the app to GitHub Pages if the build is successful.
- Provides logs and error messages in the **Actions** tab.

### 💡 Need Help?

- Check logs under the Actions tab for errors.
- Visit GitHub Actions Docs for more info.

# 🚀
