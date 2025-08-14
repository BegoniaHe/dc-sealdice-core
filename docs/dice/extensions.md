# 扩展系统

`sealdice-core` 的扩展系统允许开发者使用 JavaScript 来编写新的功能，从而极大地增强了其灵活性和可扩展性。该系统主要由 `ext.go` 和 `dice_jsvm.go` 两个文件实现。

## `ExtInfo` 结构体 (`ext.go`)

`ExtInfo` 结构体定义了一个扩展的基本信息，包括：

- **`Name`**: 扩展的名称。
- **`Version`**: 扩展的版本。
- **`Author`**: 扩展的作者。
- **`Cmds`**: 扩展注册的指令列表。
- **`OnLoad`**: 扩展加载时执行的函数。
- **`OnEnable`**: 扩展启用时执行的函数。
- **`OnDisable`**: 扩展禁用时执行的函数。

## JavaScript 虚拟机 (`dice_jsvm.go`)

`dice_jsvm.go` 文件实现了一个 JavaScript 虚拟机（VM），用于加载和执行扩展脚本。

### 主要功能

- **`JsLoadScripts`**: 加载 `scripts` 目录下的所有 JavaScript 扩展脚本。
- **`JsParseMeta`**: 解析 JavaScript 脚本头部的元数据（meta），例如 `@name`, `@version`, `@author` 等，用于创建一个 `JsScriptInfo` 对象。
- **`JsLoadScriptRaw`**: 将解析后的脚本加载到 JavaScript 虚拟机中，并使其可执行。
- **API 注入**: `sealdice-core` 向 JavaScript 虚拟机中注入了一系列 API，允许脚本与核心功能进行交互，例如发送消息、修改数据、注册指令等。