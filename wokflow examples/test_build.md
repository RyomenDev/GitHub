##### When needs to ensure that it correctly finds the `package-lock.json` files in both the `client/ and server/ directories`. Here's a properly configured GitHub Actions workflow:

```
name: CI Pipeline

on: [push, pull_request]

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
          cache-dependency-path: |
            mern-ci-example/client/package-lock.json
            mern-ci-example/server/package-lock.json

      - name: Install Client Dependencies
        working-directory: mern-ci-example/client
        run: npm ci

      - name: Build Client
        working-directory: mern-ci-example/client
        env:
          NODE_ENV: production
        run: npm run build

      - name: Install Server Dependencies
        working-directory: mern-ci-example/server
        run: npm ci

      - name: Build Server (Optional)
        working-directory: mern-ci-example/server
        run: npm run build

    #   - name: Run Server Tests (If available)
    #     working-directory: mern-ci-example/server
    #     run: npm test
```

### Key Fixes:

1. cache-dependency-path Fix:

- Ensures GitHub caches `node_modules` properly for both `client/` and` server/`, avoiding dependency issues.

2. `npm ci` Instead of `npm install`:

- `npm ci` ensures the exact dependencies from `package-lock.json` are installed, preventing version mismatches.

3. Correct Working Directories:

- Ensures that all commands execute in the right folders.

# 🚀
