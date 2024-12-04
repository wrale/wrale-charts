# Release Process

## Overview

This document outlines the process for releasing new versions of Helm charts in this repository.

## Repository Structure

- `main` branch: Source code and chart development
- `gh-pages` branch: Helm repository hosting packaged charts

## Release Types

- Patch (0.0.X): Bug fixes and minor changes
- Minor (0.X.0): New features, backward compatible
- Major (X.0.0): Breaking changes

## Release Steps

### 1. Preparation

1. Update Chart Version:
   ```yaml
   # Chart.yaml
   version: X.Y.Z  # New version
   ```

2. Update CHANGELOG.md:
   ```markdown
   ## [X.Y.Z] - YYYY-MM-DD
   ### Added
   - New feature A
   ### Changed
   - Modified behavior B
   ### Deprecated
   - Old feature C
   ### Removed
   - Removed feature D
   ### Fixed
   - Bug fix E
   ### Security
   - Security fix F
   ```

3. Update Documentation:
   - README.md if needed
   - values.yaml documentation
   - Any other relevant docs

### 2. Testing

1. Run Local Tests:
   ```bash
   ct lint --config .github/ct.yaml --charts charts/my-chart
   ct install --config .github/ct.yaml --charts charts/my-chart
   helm template --debug charts/my-chart
   ```

2. CI/CD Checks:
   - Wait for all checks to pass
   - Address any issues

### 3. Release Process

1. Create Pull Request:
   - Title: `Release: Chart-Name vX.Y.Z`
   - Description: Include changelog
   - Ensure Chart.yaml version is updated

2. Review:
   - Get required approvals
   - Address feedback
   - All CI checks must pass

3. Merge:
   - Squash and merge to main
   - GitHub Actions will automatically:
     - Package the chart
     - Create a GitHub Release
     - Update the Helm repository index
     - Push changes to gh-pages branch

### 4. Post-Release

1. Verify:
   - Chart is published to https://wrale.github.io/wrale-charts
   - GitHub Release is created with proper tags
   - Chart can be installed via `helm install`
   - Documentation is updated

2. Announce:
   - Update release notes if needed
   - Notify users of significant changes

## Rollback Process

If issues are found after release:

1. Create hotfix branch from the release tag
2. Fix the issue
3. Follow release process for patch version
4. Document the issue and fix in CHANGELOG.md

## Permissions and Requirements

### GitHub Repository Settings

1. GitHub Pages:
   - Source: Deploy from branch
   - Branch: gh-pages
   - Folder: / (root)

2. Branch Protection:
   - Require pull request reviews
   - Require status checks to pass
   - Require linear history

3. Workflow Permissions:
   - Actions have contents:write permission
   - GITHUB_TOKEN has necessary permissions

## Version Support

- Latest version: Full support
- Previous minor version: Security updates
- Older versions: No support

## Questions

For questions about the release process:
1. Open a discussion
2. Contact maintainers
3. Join community meetings
