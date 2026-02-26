---
name: install-python-environment
description: Install and configure a Python development environment with package management
version: 1.0.0
metadata:
  skill_forge:
    domain: "python"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [python, programming, development, setup]
    category: programming
---

# Install Python Development Environment

## When to Use
When you need to set up a Python development environment on a new machine or want to ensure proper Python installation with package management capabilities.

## Prerequisites
- Administrative access to your system
- Internet connection for downloading packages

## Procedure
1. Download Python installer: Visit `https://www.python.org/downloads/` and download the latest stable version for your OS
2. Run installer with PATH option: `python-3.x.x.exe` (Windows) or use package manager on Linux/macOS
3. Verify installation: `python --version` and `python -m pip --version`
4. Upgrade pip: `python -m pip install --upgrade pip`
5. Create virtual environment: `python -m venv myproject`
6. Activate virtual environment: `myproject\Scripts\activate` (Windows) or `source myproject/bin/activate` (Linux/macOS)
7. Install common packages: `pip install requests numpy pandas`
8. Create requirements file: `pip freeze > requirements.txt`

## Verification
- `python --version` shows Python 3.x.x
- `pip list` shows installed packages
- `python -c "import sys; print(sys.executable)"` shows correct Python path
- Virtual environment prompt appears when activated

## Pitfalls
- Not adding Python to PATH during installation
- Using system Python instead of virtual environment
- Forgetting to activate virtual environment before installing packages
- Installing packages globally instead of in virtual environment

## Sources
- https://www.python.org/
- https://www.w3schools.com/python/
- https://en.wikipedia.org/wiki/Python_(programming_language)