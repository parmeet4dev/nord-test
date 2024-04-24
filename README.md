
---

# SCA Integration for GitHub Repository

## Overview
This project successfully integrates a Software Composition Analysis (SCA) tool into a company's public GitHub repository. The SCA tool helps identify and manage security vulnerabilities in the project's dependencies, ensuring that the codebase remains secure and compliant with best practices.

## Requirements
- **SCA scan must be performed for each opened pull request.**
- **SCA scan must be performed on push to the main branch.**
- **Utilize the OWASP Dependency Check tool for vulnerability scanning.**
- **The repository must use NPM or Yarn package manager for managing project dependencies.**

## Integration Steps
To integrate the SCA tool into your GitHub repository, the following steps were followed:

1. **Installed OWASP Dependency Check:**
   - OWASP Dependency Check was successfully installed in the development environment.
   - Referenced the official documentation for installation instructions: [OWASP Dependency Check Documentation](https://jeremylong.github.io/DependencyCheck/)

2. **Configured SCA Workflow:**
   - Created a GitHub Actions workflow file (`.github/workflows/sca.yml`) to automate the SCA scanning process.
   - Utilized a provided workflow template and customized it according to the project's needs.

3. **Enabled GitHub Actions:**
   - Committed and pushed the workflow file to the repository.
   - Enabled workflows in the "Actions" tab of the GitHub repository.

4. **Reviewed SCA Reports:**
   - After each pull request or push to the main branch, OWASP Dependency Check generates an HTML report (`sca-report.html`).
   - Additionally, SARIF files are generated and pushed to GitHub's CodeQL action.
   - The SARIF files provide structured information about detected vulnerabilities.
   - These files are utilized by the CodeQL action to display active vulnerabilities in the "Security" -> "Code scanning alerts" tab for better visibility and management of security issues.