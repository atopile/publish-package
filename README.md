# Publish an atopile Package

A Github action to publish atopile packages 📦 🛳️

Check our [docs](https://docs.atopile.io/publish-package) for a guide to setup publishing

## Configuration

In the example below, the option selected is the default, so it's not necessary to specify the options.

```yaml
- uses: atopile/publish-package@v1
  with:
    atopile-version: "latest"  # The version of atopile to use for publishing.

    # Version of the package to publish. If empty, the version is expected in the ato.yaml file.
    package-version: "from-tag"

    # Skip publishing if the version already exists. If "false", the action will fail if the version already exists.
    # This is useful if you want to publish from the `main` branch or whenever the `package.version` is bumped.
    skip-duplicate-versions: "true"

    # A path (`path/to/package`) to the package to publish.
    # Useful for monorepos where you have more than one package, or the atopile project isn't the root of the repo.
    package-entrypoint: "./"
```

See more options in [action.yml](action.yml)
