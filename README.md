# MSR - Apache Ignite API Collection

This repository contains an API collection for the **Mining Software Repositories (MSR)** course, using [Apache Ignite](https://ignite.apache.org/) as the sample open-source project. It covers data extraction from both **GitHub** (source code history, code review, issues) and **Apache Jira** (defect tracking, bug lifecycle, releases).

## Getting Started with Bruno

This collection is designed for [Bruno](https://www.usebruno.com/) ([GitHub](https://github.com/usebruno/bruno)), an open-source, Git-friendly API client that stores collections and requests directly as human-readable `.bru` plain-text files in version control.

### How to Open the Collection

1. Install [Bruno](https://www.usebruno.com/downloads) (available for Linux, macOS, and Windows).
2. Launch Bruno and click **Open Collection** (or `Ctrl+O` / `Cmd+O`).
3. Select this folder (`MSR - Apache Ignite`).

### Configuring Environments & Authentication

Bruno manages collection-level variables via environments:

1. In the upper-right corner of Bruno, ensure the **Apache Ignite** environment is selected.
2. **GitHub Rate Limits**: Unauthenticated calls to the GitHub API are limited to 60 requests/hour. To raise the limit to 5,000 requests/hour, generate a [GitHub Personal Access Token (classic)](https://github.com/settings/tokens) and supply it to the `github_token` environment variable in Bruno.
3. **Secrets & Git**: The `environments/` folder is intentionally excluded by `.gitignore` so your personal access tokens and local configuration are never committed to Git.

## Collection Overview

The collection is organized into high-level suites corresponding to typical MSR mining tasks:

* **GitHub Repository & Activity**: High-level repository metrics, contributor workload distributions (Gini / Pareto analysis), weekly commit rhythms, and punch-card commit timing.
* **GitHub Commits & Code Churn**: Commit log mining with date/path filtering, single commit diff inspection for lines added/deleted, and cross-release comparison deltas.
* **GitHub Pull Requests & Code Review**: PR review lifecycles, approval states, inline code review discussions, and review rework commits.
* **GitHub Issues & Discussions**: Issue tracking, discussion threads, and timeline event logs.
* **Jira Project Metadata & Versions**: Apache Ignite architectural subsystems (components) and release milestone scheduling.
* **Jira Issue Mining & Changelogs**: Structured JQL queries for bug mining, defect survival/fix-time metrics, release defect density, and full issue changelogs (state-transition tossing graphs).
* **MSR Traceability**: Cross-linking Jira issue keys (`IGNITE-xxxx`) across Git commits and GitHub pull requests for end-to-end bug-to-fix tracing.
