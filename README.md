# Publish an atopile Package

A Github action to publish atopile packages 📦 🛳️

Check our [docs](https://docs.atopile.io/publish-package) for a guide to setup publishing

## Configuration

In the example below, the option selected is the default, so it's not necessary to specify the options.

```yaml
- uses: atopile/publish-package@v1
  with:
    # Either: derive the version from a config file (e.g., pyproject.toml or ato.yaml)
    # [Recommended and default if neither are provided]
    ato-config: "ato.yaml"
    # Or: Specify the atopile version directly
    atopile-version: "0.3.23"

    # Version of the package to publish. If empty, the version is expected in the ato.yaml file.
    package-version: "from-tag"

    # Include artifacts in the package.
    include-artifacts: "true"

    # Skip publishing if the version already exists. If "false", the action will fail if the version already exists.
    # This is useful if you want to publish from the `main` branch or whenever the `package.version` is bumped.
    skip-duplicate-versions: "true"

    # A path (`path/to/package`) to the package to publish.
    # Useful for monorepos where you have more than one package, or the atopile project isn't the root of the repo.
    package-entrypoint: "./"
```

See more options in [action.yml](action.yml)
