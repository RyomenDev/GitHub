### How to Create an Issue Template in GitHub

GitHub allows you to create **issue templates** to **standardize** bug reports, feature requests, or other issues.

**Steps to Create an Issue Template**
**1. Go to Your Repository**
**2. Navigate to the** `.github/ISSUE_TEMPLATE`** Directory** - If this folder doesn’t exist, create it inside the repository.
**3. Create a Markdown **(`.md`)** File for the Template** - Name the file descriptively, such as `bug_report.md` or `feature_request.md`.
**4. Define the Template Content**
**5. Commit and Push the Changes**

Alternatively, you can use GitHub's built-in interface:

- Go to **Settings → Issues → Set up templates → Add template**

---

## Examples of GitHub Issue Templates

## 1. Bug Report Template (`bug_report.md`)

```md
---
name: "Bug Report"
about: "Report a bug to help improve the project"
title: "[Bug] <short description>"
labels: "bug"
assignees: ""
---

### Describe the bug

A clear and concise description of what the bug is.

### Steps to reproduce

1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See the error

### Expected behavior

A clear and concise description of what you expected to happen.

### Screenshots

If applicable, add screenshots to help explain your problem.

### Environment

- OS: [e.g., Windows, Mac, Linux]
- Browser [e.g., Chrome, Safari]
- Version [e.g., v1.2.3]

### Additional context

Add any other context about the problem here.
```

### 2. Feature Request Template (`feature_request.md`)

```md
---
name: "Feature Request"
about: "Suggest a new feature or improvement"
title: "[Feature] <short description>"
labels: "enhancement"
assignees: ""
---

### Describe the feature

A clear and concise description of the feature you want to add.

### Why is it needed?

Explain why this feature would be useful and how it improves the project.

### Proposed Solution

Describe how this feature could be implemented.

### Additional context

Add any screenshots, links, or references that might help explain your request.
```

### 3. General Support or Question Template (`question.md`)

```md
---
name: "Question"
about: "Ask a question about the project"
title: "[Question] <your question>"
labels: "question"
assignees: ""
---

### What is your question?

A clear and concise question about the project.

### Where have you searched for answers?

Have you checked the documentation, previous issues, or other sources?

### Additional context

Provide any additional details or context.
```

# 🚀

## Using Multiple Templates

If you have multiple templates, GitHub will allow users to choose a template when opening an issue.

For further customization, you can add an `ISSUE_TEMPLATE/config.yml` file to define default issue labels, assignees, etc.

**Here’s a `config.yml `file in Markdown format explaining how to set it up:**

```yml
# .github/ISSUE_TEMPLATE/config.yml

blank_issues_enabled: false # Prevents users from creating blank issues
contact_links:
  - name: 💬 Community Discussion
    url: https://github.com/YOUR-REPO/discussions
    about: Ask questions, request features, or discuss ideas here.
  - name: 📖 Documentation
    url: https://github.com/YOUR-REPO/wiki
    about: Check the documentation before opening an issue.
  - name: 🚀 Feature Requests
    url: https://github.com/YOUR-REPO/issues/new?template=feature_request.md
    about: Request a new feature or improvement.
  - name: 🛠️ Bug Reports
    url: https://github.com/YOUR-REPO/issues/new?template=bug_report.md
    about: Report a bug with detailed information.
```

### How to Use It?

**1. Create the `.github/ISSUE_TEMPLATE` directory** if it doesn't exist.
**2. Inside this directory**, create a `config.yml` file.
**3. Copy and paste** the above content into `config.yml`.
**4. Push the file to GitHub.**

### What Does This Do?

- ✅ **Disables blank issues** (users must select a template).
- ✅ **Provides alternative resources** (like discussions and documentation).

# 🚀

```

```
