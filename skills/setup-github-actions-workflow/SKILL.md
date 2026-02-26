---
name: setup-github-actions-workflow
description: Create and configure a basic GitHub Actions CI/CD workflow for automated testing and deployment
version: 1.0.0
metadata:
  skill_forge:
    domain: "github-actions"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [github-actions, ci-cd, automation, devops]
    category: devops
---

# Setup GitHub Actions Workflow

## When to Use
When you need to automate testing, building, or deployment processes for a GitHub repository.

## Prerequisites
- GitHub repository with push access
- Basic understanding of YAML syntax
- Code project that can be built/tested

## Procedure
1. Create workflow directory: `mkdir -p .github/workflows`
2. Create workflow file: `touch .github/workflows/ci.yml`
3. Add basic workflow structure:
   name: CI Pipeline
   
   on:
     push:
       branches: [ main, develop ]
     pull_request:
       branches: [ main ]
   
   jobs:
     test:
       runs-on: ubuntu-latest
       
       steps:
       - uses: actions/checkout@v4
       - name: Setup environment
         uses: actions/setup-node@v4
         with:
           node-version: '18'
       - name: Install dependencies
         run: npm install
       - name: Run tests
         run: npm test
   ```
4. Commit and push: `git add . && git commit -m "Add CI workflow" && git push`
5. Navigate to repository Actions tab to view workflow execution

## Verification
Check that the workflow appears in the Actions tab and runs successfully on the next push or pull request.

## Pitfalls
- Incorrect YAML indentation will cause workflow failures
- Missing required secrets for deployment steps
- Workflow triggers may not fire if file is in wrong directory

## Sources
- https://docs.github.com/actions
- https://github.com/features/actions
- https://github.com/actions
- https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-github-actions
- https://learn.microsoft.com/en-us/training/paths/github-actions/
```