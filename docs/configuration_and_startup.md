# 配置和启动

本文档将指导您如何配置和启动 `sealdice-core` 应用。

## 配置

`sealdice-core` 的主要配置存储在 `data/configs/` 目录下的 `config.yaml` 文件中。当您第一次启动应用时，如果该文件不存在，系统会自动创建一个默认的配置文件。

### 主要配置项

- **`HttpPort`**: Web UI 和 API 服务监听的端口。
- **`AutoBackupEnable`**: 是否启用自动备份。
- **`BackupCron`**: 自动备份的 Cron 表达式。
- **`DiceMasters`**: Master 用户的 ID 列表。
- **`IMConnections`**: 各个 IM 平台的连接配置。

### IM 平台连接配置

您需要在 `IMConnections` 部分为每个希望连接的 IM 平台提供相应的认证信息。例如，对于 Discord，您需要提供 Bot Token。

```yaml
IMConnections:
  - Platform: "Discord"
    Enable: true
    Token: "YOUR_DISCORD_BOT_TOKEN"
```

## 启动

### 从源码启动

如果您希望从源码编译和启动 `sealdice-core`，请按照以下步骤操作：

1.  **安装 Go**: 确保您已经安装了 Go 1.18 或更高版本。
2.  **克隆仓库**: `git clone https://github.com/sealdice/sealdice-core.git`
3.  **进入目录**: `cd sealdice-core`
4.  **下载依赖**: `go mod tidy`
5.  **运行**: `go run main.go`

### 使用预编译版本

您可以从 [GitHub Releases](https://github.com/sealdice/sealdice-core/releases) 页面下载适用于您操作系统的预编译版本。下载后，解压并直接运行可执行文件即可。

## 访问 Web UI

启动成功后，您可以通过浏览器访问 `http://localhost:3211` (或您在配置中指定的端口) 来打开 `sealdice-ui` 的管理界面。