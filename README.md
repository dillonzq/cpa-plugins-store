# cpa-plugins-store

[English](README.md) | [简体中文](README.zh-CN.md)

A custom [CLIProxyAPI](https://github.com/router-for-me/CLIProxyAPI) plugin registry maintained by [dillonzq](https://github.com/dillonzq). This repository hosts the registry; plugin source code and release artifacts live in each plugin's repository.

## Included plugins

| Plugin | ID | Description |
|---|---|---|
| <img src="https://raw.githubusercontent.com/dillonzq/cpa-opencode-go/main/assets/logo.png" width="20" alt=""> [OpenCode Go](https://github.com/dillonzq/cpa-opencode-go) | `cpa-opencode-go` | Shared API keys, automatic model discovery, OpenAI/Anthropic/Gemini protocol conversion, streaming, reasoning, and native quota queries. |

## Usage

Requires CLIProxyAPI v8.0.0 or later with plugin support. Merge the following settings into your existing `config.yaml`, preserving any configured plugin settings and other store sources:

```yaml
plugins:
  enabled: true
  store-sources:
    - https://raw.githubusercontent.com/dillonzq/cpa-plugins-store/main/registry.json
```

Refresh the plugin store in your management interface, install the plugin, and follow its repository's configuration guide. Restart CPA if prompted.

## Registry

[`registry.json`](registry.json) follows the [official registry format](https://github.com/router-for-me/CLIProxyAPI-Plugins-Store#registry-format). Plugins are installed from their repositories' latest stable GitHub Releases; versions are not pinned here.

## License

This repository is licensed under [MIT](LICENSE). Each plugin is governed by the license in its own repository.
