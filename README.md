# cpa-plugins-store

[English](README.md) | [简体中文](README.zh-CN.md)

A custom CLIProxyAPI plugin store maintained by [dillonzq](https://github.com/dillonzq).
This repository maintains `registry.json`. Plugin source code, shared libraries, and checksums are hosted in each plugin repository's GitHub Releases.

## Usage

Use CLIProxyAPI v8.0.0 or later with dynamic plugin support. Merge the following settings into the `plugins` section of your existing `config.yaml`:

```yaml
plugins:
  enabled: true
  store-sources:
    - https://raw.githubusercontent.com/dillonzq/cpa-plugins-store/main/registry.json
```

Keep your existing `plugins.configs`, `plugins.dir`, and other store sources.
Once the configuration takes effect, refresh the plugin list in a management interface that supports the plugin store, find the plugin, and install it.
CPA selects the release archive for the host's operating system and architecture, verifies its SHA256 checksum, and installs the library automatically.
Restart CPA if the installation result indicates that a restart is required. Follow the plugin's README to configure credentials and other settings.

## Plugins

| ID | Features | Repository and configuration |
|---|---|---|
| `cpa-opencode-go` | Shared OpenCode Go key pool, protocol conversion, and quota queries | [Project and configuration](https://github.com/dillonzq/cpa-opencode-go) |

Before migrating from `opencode-go-cliproxyapi`, read the plugin repository's migration instructions. Avoid enabling two plugins that register the same provider.

## Maintenance

The registry uses the official `schema_version: 1` format. GitHub Release entries resolve the latest public stable release from each plugin repository, so publishing a new plugin version does not require changing a version number in this registry.
When adding a plugin, provide `id`, `name`, `description`, `author`, and `repository`. The plugin ID must match the library's metadata.
Each plugin release must include `<id>_<version>_<goos>_<goarch>.zip` archives and `checksums.txt`.

See the [official plugin store](https://github.com/router-for-me/CLIProxyAPI-Plugins-Store) for the registry and release formats.

## License

This repository is licensed under [MIT](LICENSE). Each plugin is governed by the license in its own repository.
