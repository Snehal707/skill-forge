---
name: initialize-git-repository
description: Set up a new Git repository and make the first commit for version control
version: 1.0.0
metadata:
  skill_forge:
    domain: "git"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [git, version-control, repository, initialization]
    category: development
---

# Initialize Git Repository

## When to Use
Starting a new project that needs version control, or adding Git tracking to an existing project directory.

## Prerequisites
- Git installed on system (`git --version` to verify)
- Terminal/command prompt access
- Project directory exists

## Procedure
1. Navigate to project directory: `cd /path/to/your/project`
2. Initialize Git repository: `git init`
3. Configure user identity (if first time): 
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```
4. Add files to staging area: `git add .`
5. Create initial commit: `git commit -m "Initial commit"`
6. Check repository status: `git status`

## Verification
- `.git` directory exists in project folder
- `git status` shows "working tree clean"
- `git log` displays the initial commit

## Pitfalls
- Running `git init` in wrong directory creates unwanted repository
- Forgetting to configure user identity causes commit failures
- Adding sensitive files (use `.gitignore` to exclude them)

## Sources
- https://git-scm.com/
- https://www.atlassian.com/git/tutorials/what-is-git
- https://gitforwindows.org/
```