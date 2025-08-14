# SealDice-UI 前端项目概述

`sealdice-ui` 是 `sealdice-core` 的官方前端界面，为用户提供了一个美观、易用的图形化界面来管理和使用 `sealdice-core` 的各项功能。

## 技术栈

- **框架**: [Vue.js 3](https://vuejs.org/)
- **构建工具**: [Vite](https://vitejs.dev/)
- **语言**: [TypeScript](https://www.typescriptlang.org/)
- **UI 库**: [Element Plus](https://element-plus.org/)
- **CSS 框架**: [Tailwind CSS](https://tailwindcss.com/)
- **状态管理**: [Pinia](https://pinia.vuejs.org/)
- **路由**: [Vue Router](https://router.vuejs.org/)

## 项目结构

- **`src/`**: 项目的源代码目录。
  - **`main.ts`**: 项目的入口文件，负责创建和挂载 Vue 应用实例。
  - **`App.vue`**: 根组件。
  - **`api/`**: 存放所有与后端 API 交互的代码。每个子目录对应后端 `api` 模块的一个功能分组。
  - **`assets/`**: 存放静态资源，例如图片、图标等。
  - **`components/`**: 存放可复用的 Vue 组件。
    - **`pages/`**: 页面级组件。
    - **`utils/`**: 通用工具组件。
  - **`router/`**: 存放 Vue Router 的配置，负责定义应用的页面路由。
  - **`store/`**: 存放 Pinia 的状态管理模块。
  - **`styles/`**: 存放全局样式文件。
- **`public/`**: 存放不会被 Vite 处理的静态资源。
- **`index.html`**: 应用的 HTML 入口文件。
- **`vite.config.ts`**: Vite 的配置文件。
- **`package.json`**: 项目的依赖和脚本配置文件。

## 主要功能模块

`sealdice-ui` 的功能模块与后端的 `api` 模块一一对应，通过调用相应的 API 来实现。主要功能页面包括：

- **主页**: 显示 `sealdice-core` 的基本信息和状态。
- **连接管理**: 管理与各个 IM 平台的连接。
- **日志查看**: 查看和搜索日志。
- **配置中心**: 修改 `sealdice-core` 的各项配置。
- **扩展管理**: 管理 JavaScript 扩展。
- **以及更多...**