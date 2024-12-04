# Chart Guidelines

## Chart Structure

A chart MUST have the following structure:

```
chart-name/
  ├── .helmignore        # Patterns to ignore when packaging
  ├── Chart.yaml         # Chart metadata
  ├── values.yaml        # Default configuration values
  ├── values.schema.json # JSON Schema for validating values.yaml
  ├── templates/         # Template files
  │   ├── NOTES.txt     # Post-installation notes
  │   ├── _helpers.tpl  # Common template helpers
  │   └── tests/        # Test files
  └── README.md         # Chart documentation
```

## Chart.yaml Requirements

- `name`: Must be lowercase and hyphen-separated
- `version`: Must follow [SemVer 2](https://semver.org/)
- `description`: Must be clear and concise
- `type`: Must be either `application` or `library`
- `home`: URL of the project homepage
- `sources`: List of URLs to source code
- `maintainers`: List with name and email

## Values Guidelines

1. Structure:
   - Use camelCase for keys
   - Group related values logically
   - Document all values in `values.yaml`

2. Defaults:
   - Must be production-ready
   - Must be secure by default
   - Should work out-of-the-box

3. Schema:
   - Provide JSON Schema in `values.schema.json`
   - Define types for all values
   - Add descriptions and examples

## Template Best Practices

1. Metadata:
   ```yaml
   metadata:
     name: {{ include "chart.fullname" . }}
     labels: {{- include "chart.labels" . | nindent 4 }}
   ```

2. Helper Functions:
   - Use `_helpers.tpl` for common functions
   - Document each helper function
   - Test helper functions

3. Resources:
   - Use resource requests and limits
   - Make resources configurable
   - Set reasonable defaults

4. Security:
   - Enable security contexts
   - Use non-root users
   - Set read-only root filesystem

5. Configuration:
   - Use ConfigMaps for configuration
   - Use Secrets for sensitive data
   - Support external secrets

## Testing Requirements

1. Template Tests:
   ```yaml
   templates/tests/test-connection.yaml:
   apiVersion: v1
   kind: Pod
   metadata:
     name: "{{ include "chart.fullname" . }}-test"
     annotations:
       "helm.sh/hook": test
   ```

2. CI Tests:
   - Must pass `helm lint`
   - Must pass `helm test`
   - Must pass template validation

## Documentation Requirements

1. README.md:
   - Description of the chart
   - Prerequisites
   - Installation instructions
   - Configuration options
   - Examples

2. NOTES.txt:
   - Post-installation instructions
   - Access information
   - Next steps

## Versioning Guidelines

1. Chart Version:
   - MAJOR: Incompatible API changes
   - MINOR: Functionality in backward compatible manner
   - PATCH: Bug fixes

2. App Version:
   - Track the version of the contained application
   - Document version compatibility

## Contributing Guidelines

1. Pull Requests:
   - Update documentation
   - Add/update tests
   - Update CHANGELOG.md

2. Review Process:
   - Code review required
   - Test results required
   - Documentation review required
