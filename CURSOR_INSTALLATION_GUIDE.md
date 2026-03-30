# LuaHelper 在 Cursor 中的安装指南

## 概述

本指南将帮助您在 Cursor 编辑器中安装和使用 LuaHelper 插件。LuaHelper 是一个由腾讯开发的高性能 Lua 语言插件，提供智能感知、代码检查、调试、代码格式化等功能。

## 修改内容

为了使其在 Cursor 中可用，我们对原始代码进行了以下修改：

1. **更新 package.json**：
   - 添加了对 Cursor 编辑器的支持 (`"cursor": "^0.1.0"`)
   - 更新了 Node.js 类型定义到最新版本
   - 升级了 vscode-languageclient 到兼容版本

2. **修复 TypeScript 编译错误**：
   - 修复了 Timer 类型定义问题
   - 更新了 LanguageClient API 调用方式
   - 修复了类型检查问题

## 安装步骤

### 方法一：从构建的 .vsix 文件安装

1. **确保您已经安装了 Cursor 编辑器**

2. **打开 Cursor 编辑器**

3. **安装扩展**：
   - 按 `Cmd+Shift+P` (macOS) 或 `Ctrl+Shift+P` (Windows/Linux) 打开命令面板
   - 输入 "Extensions: Install from VSIX..."
   - 选择构建好的 `luahelper-0.2.29.vsix` 文件
   - 文件位置：`/Users/xsm/Documents/workspace/LuaHelper/luahelper-vscode/luahelper-0.2.29.vsix`

4. **重启 Cursor** 以确保扩展正确加载

### 方法二：从源码构建安装

如果您想从源码构建，请按照以下步骤：

1. **安装依赖**：
   ```bash
   cd /Users/xsm/Documents/workspace/LuaHelper/luahelper-vscode
   npm install
   ```

2. **编译 TypeScript**：
   ```bash
   npm run compile
   ```

3. **构建扩展包**：
   ```bash
   npm run package
   ```

4. **安装构建的扩展**：
   - 在 Cursor 中按 `Cmd+Shift+P` (macOS) 或 `Ctrl+Shift+P` (Windows/Linux)
   - 输入 "Extensions: Install from VSIX..."
   - 选择生成的 `.vsix` 文件

## 功能特性

安装成功后，LuaHelper 将提供以下功能：

### 代码编辑功能
- **定义跳转**：支持局部、全局文件定义查询跳转
- **引用查找**：支持基于作用域的各类型引用查找
- **文档符号**：支持文件域符号表查询
- **工作区符号**：支持工程域符号表查询
- **自动代码补全**：支持变量、函数的自动输入提示
- **代码格式化**：支持 Lua 代码格式化
- **代码悬停**：支持代码悬停提示
- **全局变量着色**：支持全局变量高亮着色

### 代码检测功能
- **语法检测**：提供丰富的语法错误检测类型
- **语义检测**：支持多种类型的语义检测
- **快速增量分析**：支持增量变化分析

### 调试功能
- **调试连接**：支持连接其他进程进行调试
- **单文件调试**：支持调试单个 Lua 文件
- **单文件运行**：支持运行单个 Lua 文件

## 配置说明

安装后，您可以在 Cursor 的设置中配置 LuaHelper：

1. 打开 Cursor 设置 (`Cmd+,` 或 `Ctrl+,`)
2. 搜索 "luahelper" 查看所有可用配置选项
3. 主要配置项包括：
   - **基础设置**：LSP 模式、根目录、报告设置等
   - **颜色设置**：全局变量颜色、函数颜色等
   - **警告设置**：各种代码检查开关
   - **格式化设置**：代码格式化相关配置

## 使用说明

1. **打开 Lua 文件**：在 Cursor 中打开任何 `.lua` 文件
2. **等待初始化**：首次打开时，LuaHelper 会进行项目分析
3. **享受功能**：现在您可以享受智能感知、代码检查等功能

## 故障排除

如果遇到问题，请检查：

1. **确保 Cursor 版本兼容**：建议使用最新版本的 Cursor
2. **检查扩展状态**：在扩展面板中确认 LuaHelper 已启用
3. **查看输出日志**：在 Cursor 的输出面板中查看 LuaHelper 的日志
4. **重启编辑器**：如果问题持续，尝试重启 Cursor

## 技术细节

- **语言服务器**：使用 Go 语言开发的 LSP 服务器
- **客户端**：TypeScript 编写的 VSCode/Cursor 扩展
- **调试器**：集成了 LuaPanda 调试组件
- **格式化**：使用 C++ 编写的 LuaFormatter 库

## 支持

如果您在使用过程中遇到问题，可以：

1. 查看 [FAQ 文档](./docs/manual/FAQ.md)
2. 在 [GitHub Issues](https://github.com/Tencent/LuaHelper/issues) 中报告问题
3. 联系开发团队：yvanfyin@tencent.com

## 许可证

本项目采用 BSD-3-Clause 许可证，详见 [LICENSE](./LICENSE) 文件。

---

**注意**：本修改版本专门针对 Cursor 编辑器进行了优化，确保与 Cursor 的兼容性。如果您在使用过程中发现任何问题，请及时反馈。


