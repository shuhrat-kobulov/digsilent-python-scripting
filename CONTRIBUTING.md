# Contributing to Python Scripting in DIgSILENT

We welcome contributions to this repository! Whether it's improvements to the documentation, bug fixes, or new features, your help is appreciated. Please read and follow these guidelines to make the process smooth for everyone.

## Table of Contents

1. [How to Contribute](#how-to-contribute)
2. [Reporting Issues](#reporting-issues)
3. [Submitting Pull Requests](#submitting-pull-requests)
4. [Development Guidelines](#development-guidelines)
5. [Style Guide](#style-guide)

---

## How to Contribute

There are several ways you can contribute to this project:

- **Submit Bug Reports**: Help us identify issues or suggest feature requests by submitting issues.
- **Fix Bugs**: Look through our [issues](https://github.com/your-repo/issues) and help us resolve them.
- **Improve Documentation**: If you spot typos, unclear explanations, or missing information, feel free to improve the documentation.
- **Contribute Code**: Add new features or enhance existing functionality.

### Steps to Contribute:

1. **Fork** the repository.
2. **Create a branch** for your contribution: `git checkout -b feature/your-feature-name`.
3. **Commit** your changes: `git commit -m 'Add some feature'`.
4. **Push** to the branch: `git push origin feature/your-feature-name`.
5. **Open a Pull Request**: Once your changes are reviewed, they will be merged.

---

## Reporting Issues

If you encounter any issues with the project, please check the existing [Issues](https://github.com/your-repo/issues) to see if it's already being addressed. If not, feel free to create a new issue with the following information:

- Description of the issue
- Steps to reproduce
- Expected and actual behavior
- Any error messages or screenshots, if applicable

When reporting an issue, please be as detailed as possible to help us understand and resolve the problem faster.

---

## Submitting Pull Requests

Follow these steps to submit a pull request (PR):

1. Ensure your PR addresses a single feature or fix.
2. **Include tests** where necessary.
3. **Provide a clear description** of what the PR changes and why.
4. Ensure the PR is up-to-date with the `main` branch.
5. Reference any related issues in the PR description.
6. We will review your PR and either suggest changes or merge it into the codebase.

---

## Development Guidelines

Before contributing, please follow these general guidelines to keep the codebase consistent and maintainable:

1. **Ensure compatibility** with DIgSILENT PowerFactory’s Python API and consider compatibility with different versions (e.g., Python 3.8).
2. **Test your code** thoroughly. If you are adding a new feature, make sure to include tests that verify its functionality.
3. **Write clean, maintainable code**: Comments, clear variable names, and modular design are important.

---

## Style Guide

To ensure consistency in the project, follow these style rules:

1. **PEP 8**: Adhere to [PEP 8](https://www.python.org/dev/peps/pep-0008/) for Python code style.
2. **Docstrings**: Include docstrings for any function, class, or module you add or modify.
3. **Indentation**: Use 4 spaces per indentation level.
4. **Function and Variable Names**: Use `snake_case` for function and variable names.
5. **Import Statements**: Group imports into three sections (standard libraries, third-party libraries, local imports) and alphabetize them within each section.
6. **File Names**: Use meaningful names that describe the file’s content.

Example of good Python code style:

```python
import sys
import powerfactory as pf

def run_load_flow(app):
    """Executes load flow in DIgSILENT PowerFactory."""
    lf = app.GetFromStudyCase('ComLdf')
    return lf.Execute()
```
