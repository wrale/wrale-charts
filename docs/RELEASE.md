# Release Process

## Overview

This document outlines the process for releasing new versions of Helm charts in this repository.

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
   helm lint charts/my-chart
   helm template charts/my-chart
   helm test my-chart
   ```

2. CI/CD Checks:
   - Wait for all checks to pass
   - Address any issues

### 3. Release Process

1. Create Pull Request:
   - Title: `Release: Chart-Name vX.Y.Z`
   - Description: Include changelog

2. Review:
   - Get required approvals
   - Address feedback

3. Merge:
   - Squash and merge to main
   - GitHub Actions will:
     - Package the chart
     - Push to GitHub Pages
     - Create GitHub Release

### 4. Post-Release

1. Verify:
   - Chart is published
   - Release is created
   - Documentation is updated

2. Announce:
   - Update release notes
   - Notify users if needed

## Rollback Process

If issues are found after release:

1. Create hotfix branch
2. Fix the issue
3. Follow release process for patch version
4. Document the issue and fix

## Version Support

- Latest version: Full support
- Previous minor version: Security updates
- Older versions: No support

## Questions

For questions about the release process:
1. Open a discussion
2. Contact maintainers
3. Join community meetings
