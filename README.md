# Wrale Helm Charts

This repository hosts official Helm charts for Wrale projects. Our charts follow best practices for Kubernetes deployments and aim to be secure, maintainable, and user-friendly.

## Getting Started

### Prerequisites
- Kubernetes 1.19+
- Helm 3.13.0+
- kubectl configured with access to your cluster

### Installation

1. Add the Wrale Helm repository:
```bash
helm repo add wrale https://wrale.github.io/wrale-charts
helm repo update
```

2. View available charts:
```bash
helm search repo wrale
```

3. Install a chart:
```bash
helm install my-release wrale/<chart-name>
```

## Development Setup

### Local Environment Setup
1. Clone the repository:
```bash
git clone https://github.com/wrale/wrale-charts.git
cd wrale-charts
```

2. Install development dependencies:
- [helm](https://helm.sh/docs/intro/install/) (v3.13.0+)
- [helm-docs](https://github.com/norwoodj/helm-docs)
- [yamllint](https://github.com/adrienverge/yamllint)
- [ct (chart-testing)](https://github.com/helm/chart-testing)

3. Set up pre-commit hooks:
```bash
pre-commit install
```

### Creating a New Chart

1. Create a new chart using our template:
```bash
cp -r charts/app-template charts/my-chart
```

2. Update chart files following our [Chart Guidelines](docs/GUIDELINES.md)

3. Update documentation:
```bash
helm-docs -c charts/my-chart
```

4. Test your chart:
```bash
ct lint --config .github/ct.yaml --charts charts/my-chart
ct install --config .github/ct.yaml --charts charts/my-chart
```

## Testing

### Automated Testing
Our CI pipeline automatically runs:
- YAML linting
- Helm chart linting
- Chart installation tests
- Template validation
- Schema validation

### Local Testing
1. Lint your chart:
```bash
ct lint --config .github/ct.yaml --charts charts/my-chart
```

2. Install and test chart:
```bash
ct install --config .github/ct.yaml --charts charts/my-chart
```

3. Validate templates:
```bash
helm template --debug charts/my-chart
```

## Release Process

1. Update Chart.yaml with new version

2. Update CHANGELOG.md following our [guidelines](docs/RELEASE.md)

3. Submit a pull request with your changes

4. Upon merge to main:
   - GitHub Actions will package the chart
   - Chart will be published to GitHub Pages
   - GitHub Release will be created automatically
   - Helm repository index will be updated

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Available Charts
See individual chart documentation in the [charts/](charts/) directory.

## Support
- Create an [issue](https://github.com/wrale/wrale-charts/issues/new/choose) for bug reports
- Start a [discussion](https://github.com/wrale/wrale-charts/discussions) for questions

## License
Apache License 2.0