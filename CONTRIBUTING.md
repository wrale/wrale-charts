# Contributing to Wrale Charts

Thank you for your interest in contributing to Wrale Charts! This document provides guidelines and instructions for contributing.

## Table of Contents
- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Environment](#development-environment)
- [Contributing Process](#contributing-process)
- [Chart Guidelines](#chart-guidelines)
- [Testing Requirements](#testing-requirements)
- [Documentation](#documentation)
- [Submission Process](#submission-process)

## Code of Conduct

By participating in this project, you agree to follow our standard open source code of conduct:
- Be respectful and inclusive
- Accept constructive criticism
- Focus on what is best for the community
- Show empathy towards other community members

## Getting Started

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/wrale-charts.git
   cd wrale-charts
   ```
3. Add upstream remote:
   ```bash
   git remote add upstream https://github.com/wrale/wrale-charts.git
   ```

## Development Environment

### Prerequisites
- Kubernetes cluster (1.19+)
- Helm (3.13.0+)
- kubectl
- Docker (for local testing)
- helm-docs
- yamllint
- chart-testing (ct)

### Installation
1. Install required tools:
   ```bash
   # Install helm-docs
   GO111MODULE=on go get github.com/norwoodj/helm-docs/cmd/helm-docs

   # Install yamllint
   pip install yamllint

   # Install chart-testing
   wget https://github.com/helm/chart-testing/releases/download/v3.7.1/chart-testing_3.7.1_linux_amd64.tar.gz
   tar xzvf chart-testing_3.7.1_linux_amd64.tar.gz
   sudo mv ct /usr/local/bin/
   ```

## Contributing Process

### For New Charts
1. Create a new branch:
   ```bash
   git checkout -b add-chart-name
   ```

2. Create chart directory:
   ```bash
   mkdir -p charts/chart-name
   ```

3. Add required files:
   - Chart.yaml - Chart definition and metadata
   - values.yaml - Default configuration values
   - README.md - Chart documentation
   - templates/ - Chart templates
   - NOTES.txt - Post-installation notes
   - .helmignore - Files to ignore

### For Existing Charts
1. Create a feature/fix branch:
   ```bash
   git checkout -b feature-description
   ```

2. Make your changes following our [Chart Guidelines](docs/GUIDELINES.md)

## Chart Guidelines

### Versioning
- Follow [SemVer](https://semver.org/)
- Increment chart version for any changes
- Document changes in CHANGELOG.md

### Chart Structure
- Use consistent naming conventions
- Include comprehensive documentation
- Provide sensible defaults
- Follow Helm best practices

### Dependencies
- Minimize external dependencies
- Document all dependencies
- Use specific versions
- Test dependency compatibility

## Testing Requirements

### Local Testing
1. Run unit tests:
   ```bash
   ct lint --config .github/ct.yaml --charts charts/your-chart
   ```

2. Run integration tests:
   ```bash
   ct install --config .github/ct.yaml --charts charts/your-chart
   ```

### Required Tests
- Chart installation
- Upgrade from previous versions
- Configuration validation
- Resource creation
- Custom values

## Documentation

### Required Documentation
- README.md with:
  - Description
  - Prerequisites
  - Installation instructions
  - Configuration options
  - Examples
- NOTES.txt for post-installation information
- Well-commented templates
- Up-to-date CHANGELOG.md

### Documentation Style
- Clear and concise
- Include examples
- Keep current
- Use proper formatting

## Submission Process

1. Ensure all tests pass
2. Update documentation
3. Create pull request
4. Address review comments
5. Update changelog
6. Await approval

### Pull Request Guidelines
- Use meaningful titles
- Follow the PR template
- Include test results
- Link related issues

### Review Process
1. Automated checks must pass
2. Documentation must be complete
3. At least one maintainer approval required
4. All comments must be addressed

## Need Help?

- Create an issue for questions
- Join our community discussions
- Read our [FAQ](docs/FAQ.md)
- Contact maintainers

Thank you for contributing to Wrale Charts! Your efforts help make our project better for everyone.