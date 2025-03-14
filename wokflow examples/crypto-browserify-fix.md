Here is a **GitHub Actions YAML** file (`.github/workflows/ci.yml`) for your **MERN CI/CD pipeline** that:

1. ***Checks out the repository***
2. ***Installs dependencies*** for both client (React + Vite) and server (Express.js)
3. ***Builds the client*** (React + Vite)
4. ***Runs the backend server*** (Node.js + Express)
5. ***Caches dependencies*** to speed up workflows

```
name: MERN CI Pipeline

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 18
          cache: npm

      # Install Client Dependencies
      - name: Install Client Dependencies
        working-directory: mern-ci-example/client
        run: |
          npm ci
          npm install crypto-browserify --save-dev

      # Build Client (React + Vite)
      - name: Build Client
        working-directory: mern-ci-example/client
        env:
          NODE_ENV: production
        run: npm run build

      # Install Server Dependencies
      - name: Install Server Dependencies
        working-directory: mern-ci-example/server
        run: npm ci

      # Run Server (Node.js + Express)
      - name: Start Server
        working-directory: mern-ci-example/server
        run: npm start &

```

### Key Features

✅ Uses `npm ci` for faster, reliable installs (requires `package-lock.json`)
✅ **Caches dependencies** for faster workflows
✅ **Runs both client and server** as part of CI/CD
✅ Fixes `crypto$2.getRandomValues` error by installing `crypto-browserify`
