---
name: python-environment-setup
description: Set up a Python development environment with package management and virtual environments
version: 1.0.0
metadata:
  skill_forge:
    domain: "python"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [python, development, environment, virtual-env]
    category: development
---

# Python Environment Setup

## When to Use
When starting a new Python project or setting up a development machine for Python programming.

## Prerequisites
- Administrative access to install software
- Internet connection for downloads

## Procedure
1. Download Python installer: Visit `https://www.python.org/downloads/` and download the latest version
2. Install Python: `python-3.x.x.exe` (Windows) or follow platform-specific instructions
3. Verify installation: `python --version`
4. Verify pip is installed: `pip --version`
5. Create project directory: `mkdir my-python-project && cd my-python-project`
6. Create virtual environment: `python -m venv venv`
7. Activate virtual environment:
   - Windows: `venv\Scripts\activate`
   - Linux/Mac: `source venv/bin/activate`
8. Upgrade pip: `pip install --upgrade pip`
9. Create requirements file: `touch requirements.txt`
10. Test environment: `python -c "print('Python environment ready!')"`

## Verification
- `python --version` shows installed version
- `pip list` shows installed packages
- Virtual environment prompt shows `(venv)` prefix
- Can run Python scripts without errors

## Pitfalls
- Forgetting to activate virtual environment before installing packages
- Using system Python instead of virtual environment
- Not updating pip before installing packages
- Mixing Python 2 and Python 3 commands

## Sources
- https://www.python.org/
- https://www.w3schools.com/python/
- https://en.wikipedia.org/wiki/Python_(programming_language)