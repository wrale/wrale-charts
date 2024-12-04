# Changelog

All notable changes to the app-template chart will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2024-04-03

### Added
- Initial release of the app-template chart
- Basic Kubernetes resource templates:
  - Deployment with security context and probes
  - Service with flexible configuration
  - ServiceAccount with optional image pull secrets
  - Ingress with networking.k8s.io/v1 support
  - HorizontalPodAutoscaler v2 with custom metrics support
  - PodDisruptionBudget for availability control
  - NetworkPolicy for pod network security
  - ServiceMonitor for Prometheus integration
- Comprehensive values.yaml with detailed documentation
- Support for container security best practices
- Prometheus ServiceMonitor integration
- Network Policy controls
- Support for custom annotations and labels on all resources
- FlexVolume and ConfigMap/Secret mounting support
