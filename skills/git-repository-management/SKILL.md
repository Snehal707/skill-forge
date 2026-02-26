---
name: git-repository-management
description: Initialize, clone, and manage Git repositories for version control
version: 1.0.0
metadata:
  skill_forge:
    domain: "git"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [git, version-control, repository, development]
    category: development
---

# Git Repository Management

## When to Use
When you need to start tracking code changes, collaborate on projects, or manage different versions of files in a software development workflow.

## Prerequisites
- Git installed on your system (`git --version` should work)
- Basic command line familiarity
- Text editor configured for Git commits

## Procedure
1. **Initialize new repository**: `git init project-name`
2. **Navigate to project**: `cd project-name`
3. **Configure user identity**: 
   - `git config user.name "Your Name"`
   - `git config user.email "your.email@example.com"`
4. **Add files to staging**: `git add .` or `git add filename`
5. **Create first commit**: `git commit -m "Initial commit"`
6. **Check repository status**: `git status`
7. **View commit history**: `git log --oneline`
8. **Clone existing repository**: `git clone https://github.com/username/repo.git`

## Verification
Run `git status` to confirm repository is properly initialized and tracking files. Check `git log` shows your commits with correct author information.

## Pitfalls
- Forgetting to configure user.name and user.email before first commit
- Adding sensitive files (use .gitignore to exclude them)
- Working directly on main/master branch without creating feature branches
- Not writing meaningful commit messages

## Sources
- https://git-scm.com/
- https://github.com/
- https://en.wikipedia.org/wiki/Git
- https://gitforwindows.org/
- https://www.atlassian.com/git/tutorials/what-is-git