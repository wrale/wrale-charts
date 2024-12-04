# Chart Validation Guide

## Overview
This document describes the validation rules and requirements for Wrale Helm charts.

## Chart Schema
All charts must conform to the schema defined in `charts/.schema.json`. This schema enforces:

- Required metadata fields
- Version formatting
- Maintainer information
- Proper Kubernetes version constraints

## Chart Testing
Charts are automatically tested using the following tools:

### chart-testing (ct)
Runs on pull requests and pushes to main, performing:
- Helm lint
- YAML validation
- Version increment checks
- Installation tests

### Schema Validation
Validates Chart.yaml against our JSON schema, ensuring:
- Proper versioning
- Complete metadata
- Valid maintainer information

## Best Practices

### Version Numbers
- Use semantic versioning (MAJOR.MINOR.PATCH)
- Increment version on every change
- Major version changes must include migration documentation

### Dependencies
- Pin dependency versions
- Document version compatibility
- Test with minimum supported versions

### Documentation
- Keep README.md up to date
- Document all configuration options
- Include example values
- Provide upgrade notes

### Testing
- Include comprehensive test values
- Test both minimal and full configurations
- Validate generated resources
- Test upgrades from previous versions

## Chart Requirements

### Metadata
- Clear description
- Accurate kubeVersion constraint
- Complete maintainer information
- Relevant keywords

### Values
- Use descriptive names
- Include descriptions for all values
- Provide sensible defaults
- Document required values

### Templates
- Follow Kubernetes best practices
- Use helper functions consistently
- Include necessary RBAC resources
- Implement proper health checks

### Security
- Follow security best practices
- Use secure defaults
- Document security considerations
- Include NetworkPolicies where appropriate

## Review Process
Charts are reviewed for:

1. Schema compliance
2. Best practices adherence
3. Documentation completeness
4. Test coverage
5. Security considerations

## Continuous Integration
Our CI pipeline ensures:

1. All tests pass
2. Schema validation succeeds
3. Version numbers are incremented
4. Documentation is updated
5. Release notes are included