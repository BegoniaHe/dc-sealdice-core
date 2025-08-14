# Dice 核心模块 (`dice.go`)

`dice.go` 文件定义了 `Dice` 结构体，它是整个 `sealdice-core` 应用的核心。这个结构体封装了应用的所有状态和功能。

## `Dice` 结构体

`Dice` 结构体包含了以下主要部分：

- **`DiceManager`**: 管理多个 `Dice` 实例。
- **`ImSession`**: 管理与不同IM平台的连接。
- **`DBOperator`**: 数据库操作接口，用于数据的持久化。
- **`ExtList`**: 扩展列表，管理所有加载的扩展。
- **`CmdMap`**: 指令映射，存储所有注册的指令和它们的处理器。
- **`BanList`**: 封禁列表，管理被封禁的用户和群组。
- **`Log`**: 日志记录器。
- **`IsRunning`**: 应用是否正在运行的标志。

## 主要功能

### 初始化 (`Init`)

`Init` 函数负责初始化 `Dice` 实例。它会执行以下操作：

1.  初始化数据库连接。
2.  加载配置。
3.  加载扩展。
4.  注册核心指令。
5.  启动后台任务，例如定时备份和清理。

### 指令处理

`Dice` 实例通过 `ImSession` 接收来自不同平台的消息，然后解析消息中的指令，并调用相应的处理器来执行。

### 扩展系统

`sealdice-core` 拥有一个强大的扩展系统，允许开发者通过编写JavaScript脚本来扩展应用的功能。`Dice` 结构体中的 `ExtList` 和相关方法负责加载、管理和执行这些扩展。

### 平台适配

`sealdice-core` 支持多种IM平台，例如 Discord, KOOK, Telegram 等。`ImSession` 和 `platform_adapter_...` 文件共同实现了对不同平台的适配。