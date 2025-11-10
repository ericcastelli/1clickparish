# Contributing to OneClickParish 🕊️

First off, thank you for considering contributing to OneClickParish. It’s people like you that make this mission-driven project possible. Every contribution, no matter how small, helps us connect priests with their parishioners in parts of the world where it's needed most.

This document provides guidelines for contributing to the project. Please feel free to propose changes to this document in a pull request.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Submitting Pull Requests](#submitting-pull-requests)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Style Guides](#style-guides)
  - [Git Commit Messages](#git-commit-messages)
  - [Python Styleguide](#python-styleguide)

## Code of Conduct

This project and everyone participating in it is governed by the [OneClickParish Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior.

## How Can I Contribute?

### Reporting Bugs

If you find a bug, please ensure it hasn't already been reported by searching the GitHub Issues. If you can't find an open issue addressing the problem, [open a new one](https://github.com/your-repo/oneclickparish/issues/new).

When filing a bug report, please include:
*   A clear and descriptive title.
*   A detailed description of the problem.
*   Steps to reproduce the bug.
*   The expected behavior and what happened instead.
*   Screenshots or logs, if applicable.

### Suggesting Enhancements

We welcome suggestions for new features or improvements to existing functionality. To suggest an enhancement:

1.  Search the GitHub Issues to see if the enhancement has already been suggested.
2.  If not, [open a new issue](https://github.com/ericcastelli/1clickparish/issues/new) to start a discussion. Please provide as much context and detail as possible.

### Submitting Pull Requests

Code contributions are the primary way to help the project grow. If you have an idea for a fix or a new feature, please follow the [Pull Request Process](#pull-request-process) below.

## Development Setup

The core of OneClickParish is a serverless application running on AWS. To get your local development environment set up, follow these steps.

**Prerequisites:**
*   [Git](https://git-scm.com/)
*   [Python 3.9+](https://www.python.org/) & `pip`
*   An AWS Account
*   AWS CLI, configured with your credentials.
*   AWS SAM CLI (or AWS CDK, as specified by the project's IaC choice).

**Setup Steps:**

1.  **Fork the repository** on GitHub.

2.  **Clone your fork** locally:
    ```bash
    git clone https://github.com/ericcastelli/1clickparish.git
    cd oneclickparish
    ```

3.  **Create a virtual environment** for Python:
    ```bash
    python -m venv .venv
    source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
    ```

4.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

5.  You can now run the Python SSG script locally or test the Lambda function using AWS SAM:
    ```bash
    # Example of invoking the function locally (will depend on your template.yaml)
    sam local invoke YourLambdaFunctionName --event events/event.json
    ```

## Pull Request Process

1.  Ensure any install or build dependencies are removed before the end of the layer when doing a build.
2.  Create a new branch from `main` for your changes:
    ```bash
    git checkout -b feature/your-amazing-feature
    ```
3.  Make your changes in your local repository.
4.  Commit your changes, following our Git Commit Messages style guide.
5.  Push your branch to your fork on GitHub:
    ```bash
    git push origin feature/your-amazing-feature
    ```
6.  Open a pull request to the `main` branch of the original `oneclickparish` repository.
7.  Provide a clear title and description for your pull request. Explain the "why" and "what" of your changes. Link to any relevant issues.
8.  A project maintainer will review your PR. They may request changes. Please be responsive to feedback.

## Style Guides

### Git Commit Messages

*   Use the present tense ("Add feature" not "Added feature").
*   Use the imperative mood ("Move cursor to..." not "Moves cursor to...").
*   Limit the first line to 72 characters or less.
*   Reference issues and pull requests liberally in the body of the commit message.

### Python Styleguide

All Python code must adhere to PEP 8. We recommend using an autoformatter like `black` to ensure your code meets this standard.

To format your code, you can run:
```bash
pip install black
black .
```

---

Thank you again for your interest in making OneClickParish a success!