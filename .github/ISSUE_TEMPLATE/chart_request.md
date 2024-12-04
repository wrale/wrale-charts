---
name: Chart Request
about: Request a new Helm chart to be added to the repository
title: '[CHART REQUEST] '
labels: ['new-chart']
assignees: ''

---

## Application Details
**Application Name:** <!-- e.g., nginx, prometheus, custom-app -->
**Application Type:** <!-- e.g., Web Server, Database, Monitoring Tool -->
**Source Repository:** <!-- Link to the application's source code -->

## Chart Requirements

### Dependencies
<!-- List any required dependencies or related charts -->
- <!-- e.g., Requires PostgreSQL chart -->
- <!-- e.g., Depends on Redis -->

### Target Platforms
<!-- Which Kubernetes distributions should this chart support? -->
- [ ] Generic Kubernetes
- [ ] OpenShift
- [ ] GKE
- [ ] EKS
- [ ] AKS
- [ ] Other: <!-- specify -->

### Resource Requirements
<!-- Estimated resource requirements -->
- CPU: <!-- e.g., 100m-500m -->
- Memory: <!-- e.g., 256Mi-1Gi -->
- Storage: <!-- e.g., 1Gi persistent volume -->

## Use Case
<!-- Describe your use case and why this chart would be valuable -->

## Existing Solutions
<!-- Are there existing Helm charts for this application? If yes, why do we need a new one? -->

## Feature Requirements
<!-- List key features the chart should support -->
1. <!-- e.g., High Availability configuration -->
2. <!-- e.g., Monitoring integration -->
3. <!-- e.g., Backup capabilities -->

## Configuration Options
<!-- List important configuration options that should be exposed -->
```yaml
# Example desired values.yaml structure
```

## Additional Context
<!-- Any additional information that might be helpful -->

## Contribution
- [ ] I am willing to help create this chart
- [ ] I can help test this chart
- [ ] I have production experience with this application

## Checklist
- [ ] I have searched for existing chart requests
- [ ] The application is actively maintained
- [ ] This chart would benefit multiple users
- [ ] I have reviewed the chart requirements in GUIDELINES.md