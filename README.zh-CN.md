# cpa-plugins-store

[English](README.md) | [简体中文](README.zh-CN.md)

由 [dillonzq](https://github.com/dillonzq) 维护的 [CLIProxyAPI](https://github.com/router-for-me/CLIProxyAPI) 自定义插件源。本仓库仅维护注册表，插件源码和发布产物由各插件仓库提供。

## 收录插件

| 插件 | ID | 简介 |
|---|---|---|
| <img src="https://raw.githubusercontent.com/dillonzq/cpa-opencode-go/main/assets/logo.png" width="20" alt=""> [OpenCode Go](https://github.com/dillonzq/cpa-opencode-go) | `cpa-opencode-go` | 共享 API 密钥池、自动模型发现、OpenAI/Anthropic/Gemini 协议转换、流式响应、思考与推理及原生额度查询。 |
| <img src="https://raw.githubusercontent.com/dillonzq/cpa-opencode/main/assets/logo.png" width="20" alt=""> [OpenCode](https://github.com/dillonzq/cpa-opencode) | `cpa-opencode` | 按量付费接入、共享 API 密钥池、自动模型发现、OpenAI/Anthropic/Gemini 协议支持、流式响应、思考与推理及预算和余额查询。 |
| <img src="https://raw.githubusercontent.com/dillonzq/cpa-minimax/main/assets/logo.png" width="20" alt=""> [MiniMax](https://github.com/dillonzq/cpa-minimax) | `cpa-minimax` | 订阅与按量付费密钥、国际及中国大陆凭证池、OpenAI/Anthropic/Gemini 协议支持、流式响应、思考控制及订阅额度查询。 |
| <img src="https://api-docs.deepseek.com/img/favicon.svg" width="20" alt=""> [DeepSeek](https://github.com/dillonzq/cpa-deepseek) | `cpa-deepseek` | 官方 API 接入、共享 API 密钥池、自动模型发现、OpenAI/Anthropic/Gemini 协议支持、流式响应、思考与推理及账户余额查询。 |

## 使用

需要支持插件的 CLIProxyAPI v8.0.0 或更高版本。将以下设置合并到现有 `config.yaml`，保留已有插件配置和其他插件源：

```yaml
plugins:
  enabled: true
  store-sources:
    - https://raw.githubusercontent.com/dillonzq/cpa-plugins-store/main/registry.json
```

在管理界面刷新插件商店并安装插件，随后按插件仓库的文档完成配置。如提示需要重启，请重启 CPA。

## 注册表

[`registry.json`](registry.json) 遵循[官方注册表格式](https://github.com/router-for-me/CLIProxyAPI-Plugins-Store#registry-format)。插件从各自仓库的最新稳定版 GitHub Releases 安装，本仓库不固定版本号。

## License

本仓库使用 [MIT](LICENSE) 许可证。每个插件的许可证以对应仓库为准。
