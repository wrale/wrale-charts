# Chart Submission Guidelines

## Overview
This guide outlines the process and requirements for submitting new charts to the wrale-charts repository.

## Prerequisites
- Familiarity with Helm chart development
- Understanding of Kubernetes concepts
- GitHub account

## Chart Requirements

### Structure
- Must follow the standard Helm chart structure
- Include a comprehensive README.md
- Provide detailed values.yaml with comments
- Include NOTES.txt for post-installation instructions

### Documentation
1. Chart.yaml must include:
   - name
   - version
   - description
   - maintainers
   - keywords
   - home URL
   - sources

2. README.md must contain:
   - Brief description
   - Prerequisites
   - Installation instructions
   - Configuration options
   - Upgrade notes
   - Troubleshooting guide

### Testing
- Must include basic test cases
- Should pass helm lint without warnings
- Must work with latest 3 minor versions of Kubernetes
- Include upgrade tests from previous versions

### Security
- No hardcoded credentials
- Follow security best practices
- Document security considerations
- Use RBAC where appropriate

## Submission Process

1. Fork the Repository
   ```bash
   git clone https://github.com/yourusername/wrale-charts.git
   cd wrale-charts
   ```

2. Create a New Branch
   ```bash
   git checkout -b add-chart-name
   ```

3. Add Your Chart
   - Place chart in charts/ directory
   - Ensure all required files are present
   - Update global documentation if needed

4. Test Locally
   ```bash
   helm lint charts/your-chart
   helm template charts/your-chart
   helm test charts/your-chart  # if applicable
   ```

5. Submit Pull Request
   - Use clear, descriptive title
   - Fill out pull request template
   - Reference any related issues

## Review Process

1. Initial Check
   - Automated tests must pass
   - Documentation must be complete
   - Chart structure must be valid

2. Manual Review
   - Code quality assessment
   - Security review
   - Documentation review

3. Testing
   - Deployment testing
   - Upgrade testing
   - Integration testing

4. Final Approval
   - Address reviewer feedback
   - Update documentation if needed
   - Merge approval from maintainer

## After Submission

1. Maintenance
   - Monitor issues and pull requests
   - Keep chart updated
   - Respond to user questions

2. Updates
   - Version updates
   - Bug fixes
   - Feature additions

## Best Practices

1. Chart Design
   - Use subchart pattern for complex applications
   - Implement reasonable defaults
   - Make charts configurable
   - Follow the principle of least privilege

2. Values
   - Use descriptive names
   - Group related values
   - Document all values
   - Provide sensible defaults

3. Templates
   - Use helpers for repeated code
   - Implement proper indentation
   - Use consistent naming
   - Add appropriate annotations

4. Testing
   - Test different configurations
   - Verify upgrade paths
   - Test resource creation
   - Validate outputs

## Additional Resources

- [Helm Best Practices](https://helm.sh/docs/chart_best_practices/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [Chart Testing Guide](../TESTING.md)
- [Maintainer Guide](./MAINTAINER.md)

## Questions and Support

- Open an issue for questions
- Join our community discussions
- Review existing charts for examples
- Contact maintainers for guidance

---

Note: These guidelines are subject to change. Always check for the latest version before submitting a chart.