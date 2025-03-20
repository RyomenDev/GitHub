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

```

```
