# 指令解析 (`cmd_parse.go`)

`cmd_parse.go` 文件负责解析用户输入的原始消息，并将其转换为 `CmdArgs` 结构体，以便后续的指令处理器可以方便地使用。

## `CmdArgs` 结构体

`CmdArgs` 结构体包含了指令解析后的所有信息，例如：

- **`Command`**: 解析出的指令名称。
- **`Args`**: 指令的参数列表。
- **`Raw`**: 原始消息内容。
- **`IsAt`**: 消息是否包含 at 信息。
- **`SpecialExecuteTimes`**: 特殊执行次数，例如 `.r 4d6 3` 中的 `3`。

## 主要功能

- **`commandParse` / `commandParseNew`**: 这两个函数是指令解析的核心，它们接收原始消息字符串，并返回一个填充好的 `CmdArgs` 结构体。
- **`SpecialExecuteTimesParse`**: 解析指令末尾的特殊执行次数。
- **`CQParse`**: 解析消息中的 CQ 码。