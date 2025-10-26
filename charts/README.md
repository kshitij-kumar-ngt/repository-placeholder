# Helm Charts

This directory contains all the Helm charts available in this repository.

## Adding a New Chart

To add a new chart to this repository:

1. Create a new directory with your chart name:
   ```bash
   mkdir charts/my-chart
   cd charts/my-chart
   ```

2. Initialize the chart structure:
   ```bash
   helm create my-chart
   ```
   
   Or manually create the following files:
   - `Chart.yaml` - Chart metadata
   - `values.yaml` - Default configuration values
   - `templates/` - Kubernetes manifest templates
   - `README.md` - Chart documentation

3. Ensure your `Chart.yaml` includes:
   ```yaml
   apiVersion: v2
   name: my-chart
   description: A brief description of your chart
   type: application
   version: 0.1.0
   appVersion: "1.0"
   ```

4. Test your chart:
   ```bash
   helm lint charts/my-chart
   helm template charts/my-chart
   ```

5. Document your chart in its `README.md` with:
   - Description of what the chart deploys
   - Prerequisites
   - Installation instructions
   - Configuration options
   - Examples

## Chart Guidelines

- Follow [Helm chart best practices](https://helm.sh/docs/chart_best_practices/)
- Use semantic versioning for chart versions
- Provide sensible defaults in `values.yaml`
- Document all configurable parameters
- Include resource limits and requests
- Use labels and annotations consistently
- Test charts before submitting

## Chart Structure Example

```
my-chart/
├── Chart.yaml          # Chart metadata
├── values.yaml         # Default values
├── templates/          # Kubernetes templates
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── ingress.yaml
│   ├── _helpers.tpl   # Template helpers
│   └── NOTES.txt      # Post-install notes
├── .helmignore        # Files to ignore
└── README.md          # Chart documentation
```

## Testing Your Chart

Before submitting, test your chart:

```bash
# Lint the chart
helm lint charts/my-chart

# Template the chart to check output
helm template my-release charts/my-chart

# Dry run install
helm install my-release charts/my-chart --dry-run --debug

# Install in a test cluster
helm install my-release charts/my-chart
```
