# Wrale Helm Charts

## Setup

1. Enable GitHub Pages in repository settings
2. Create `.github/workflows/release.yaml` for chart releases
3. Create `.github/workflows/lint-test.yaml` for PR validation
4. Set `GITHUB_TOKEN` secret for chart-releaser

## Usage

```bash
helm repo add wrale https://wrale.github.io/wrale-charts
helm repo update
helm search repo wrale
```

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Charts
See individual chart documentation in the [charts/](charts/) directory.

## License
Apache License 2.0