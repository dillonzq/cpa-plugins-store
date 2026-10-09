# cpa-plugins-store

[English](README.md) | [简体中文](README.zh-CN.md)

由 [dillonzq](https://github.com/dillonzq) 维护的 CLIProxyAPI 自定义插件源。
本仓库维护 `registry.json`；插件源码、动态库和校验文件由各插件仓库的 GitHub Releases 提供。

## 使用

使用支持动态插件的 CLIProxyAPI v8.0.0 或更高版本，并在现有 `config.yaml` 的 `plugins` 节中合并以下设置：

```yaml
plugins:
  enabled: true
  store-sources:
    - https://raw.githubusercontent.com/dillonzq/cpa-plugins-store/main/registry.json
```

保留已有的 `plugins.configs`、`plugins.dir` 和其他插件源设置。
配置生效后，在支持插件商店的管理界面刷新列表，找到插件并执行安装。
CPA 会选择当前系统和架构的发布包、校验 SHA256 并安装，无需手动下载动态库。
如安装结果提示需要重启，请重启 CPA。插件密钥及其他配置按对应插件的 README 设置。

## 插件

| ID | 功能 | 仓库与配置 |
|---|---|---|
| `cpa-opencode-go` | OpenCode Go 共享密钥池、多协议转换及额度查询 | [项目与配置说明](https://github.com/dillonzq/cpa-opencode-go) |

从旧的 `opencode-go-cliproxyapi` 迁移前，请阅读插件仓库的迁移说明，避免同时启用两个注册相同服务商的插件。

## 维护

注册表采用官方 `schema_version: 1` 格式。GitHub Release 类型的条目从插件仓库读取最新公开稳定版本，因此日常发布新版无需修改注册表版本号。
新增插件时填写 `id`、`name`、`description`、`author` 和 `repository`；插件 ID 应与动态库的元数据一致。
插件发布需包含 `<id>_<version>_<goos>_<goarch>.zip` 和 `checksums.txt`。

格式参考：[官方插件商店](https://github.com/router-for-me/CLIProxyAPI-Plugins-Store)。

## License

本仓库使用 [MIT](LICENSE) 许可证。每个插件的许可证以对应仓库为准。
