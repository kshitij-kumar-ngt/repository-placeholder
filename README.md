# Helm Charts Repository

This repository serves as a public Helm chart repository, hosting various Helm charts that can be used with Kubernetes deployments.

## 🚀 Quick Start

### Adding the Helm Repository

To add this repository to your Helm installation:

```bash
helm repo add repository-placeholder https://kshitij-kumar-ngt.github.io/repository-placeholder/
helm repo update
```

### Searching for Charts

To search for available charts in this repository:

```bash
helm search repo repository-placeholder
```

### Installing a Chart

To install a chart from this repository:

```bash
helm install my-release repository-placeholder/<chart-name>
```

Replace `<chart-name>` with the name of the chart you want to install.

## 📦 Available Charts

Charts are stored in the `charts/` directory. Each chart has its own subdirectory with a `README.md` file containing specific installation and configuration instructions.

To see all available charts, browse the [charts/](./charts/) directory.

## 🛠️ Usage Examples

### Installing with Custom Values

```bash
# Install with custom values file
helm install my-release repository-placeholder/<chart-name> -f values.yaml

# Install with inline value overrides
helm install my-release repository-placeholder/<chart-name> --set key=value
```

### Upgrading a Release

```bash
helm upgrade my-release repository-placeholder/<chart-name>
```

### Uninstalling a Release

```bash
helm uninstall my-release
```

## 📋 Repository Structure

```
.
├── charts/                 # Helm charts directory
│   ├── chart-name-1/      # Individual chart
│   │   ├── Chart.yaml
│   │   ├── values.yaml
│   │   ├── templates/
│   │   └── README.md
│   └── chart-name-2/      # Another chart
│       └── ...
├── .github/
│   └── workflows/         # GitHub Actions for automation
└── README.md
```

## 🤝 Contributing

We welcome contributions! If you'd like to add a new chart or improve an existing one:

1. **Fork the repository**
2. **Create a new branch** for your chart or changes
3. **Add your chart** to the `charts/` directory following Helm best practices
4. **Test your chart** thoroughly
5. **Submit a pull request** with a clear description of your changes

### Chart Requirements

- Charts must follow [Helm chart best practices](https://helm.sh/docs/chart_best_practices/)
- Each chart must include:
  - `Chart.yaml` with proper metadata
  - `values.yaml` with sensible defaults
  - `README.md` with usage instructions
  - Templates in the `templates/` directory
- Charts should be well-documented and tested

## 🔄 Automatic Publishing

This repository uses GitHub Actions to automatically package and publish charts to GitHub Pages when changes are merged to the main branch. The chart repository index is automatically updated.

## 📚 Resources

- [Helm Documentation](https://helm.sh/docs/)
- [Chart Best Practices](https://helm.sh/docs/chart_best_practices/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

## 📄 License

See [LICENSE](./LICENSE) file for details.

## 📞 Support

For issues, questions, or contributions, please open an issue in this repository.
