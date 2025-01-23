本文是对 Juan Stoppa 的博文 *Code Smarter, Not Harder: Developing with Cursor and Claude Sonnet* 的改译。虽然文章框架参考了原文，但大部分内容基于我的实际使用体验撰写。本教程将详细介绍 Cursor 的基本功能及使用方法。

---

## 什么是 Cursor？

Cursor 是由 Anysphere 实验室开发的一款代码编辑器，基于 VSCode 修改和派生而来。因此，VSCode 的配置可以无缝导入到 Cursor 中。如果你习惯使用 VSCode 开发，迁移到 Cursor 会非常便捷。

Cursor 的最大亮点在于其内置的 AI 协作功能。相比 VSCode 上的插件（如 Github Copilot），Cursor 的体验更加流畅和高效。以下是两者的对比：

- **代码补全**：Cursor 的代码补全功能更加精准，几乎不会出现代码块不完整的情况（如括号未闭合）。
- **对话窗口**：Cursor 的对话窗口支持直接将生成的代码应用到项目中，而 Copilot 仅提供建议。
- **多文件支持**：Cursor 可以在一次对话中处理多个文件，甚至扫描整个项目代码仓，提供更全面的上下文支持。

总之，Cursor 在功能和体验上全面超越了 Copilot。

---

## Cursor 的基本使用

### 安装

1. 前往 [Cursor 官网](https://www.cursor.com/) 下载并安装。
2. 注册账号（支持 Google 和 Github 登录）。
3. 安装完成后，首次启动时会提示是否导入 VSCode 配置。导入后，你将拥有一个 AI 增强版的 VSCode。

> **订阅信息**：Cursor 采用订阅制，新用户可免费试用两周 Pro 订阅。正式订阅每月 20 美元（约 140 元）。

---

### 快捷键及功能

Cursor 提供了多种快捷键，方便用户快速调用 AI 功能：

#### 1. `CTRL/CMD + L` 打开对话框

按下 `CTRL/CMD + L` 键可在编辑器右侧打开对话框，用于与 AI 进行交互。

#### 2. `CTRL/CMD + K` 打开生成窗口

按下 `CTRL/CMD + K` 键可在光标上方打开生成窗口。选中代码后使用此快捷键，生成内容会基于选中的上下文。

#### 3. `CTRL/CMD + I` 打开 Composer

Composer 是 Cursor 的特色功能，支持在一个对话窗口中同时对多个文件进行修改。启用方法：

- 依次进入 `File > Preferences > Cursor Settings > Features > Enable Composer`。
- 按下 `CTRL/CMD + I` 打开 Composer 面板。

Composer 的完整界面支持列出所有修改内容，并直接应用到代码中。

---

### 提供上下文信息的 `@` 注记

Cursor 提供多种 `@` 注记，便于向 AI 提供上下文信息：

1. **`@Files`**：传递指定代码文件的上下文。
2. **`@Code`**：传递指定代码块的上下文。
3. **`@Docs`**：从函数或库的官方文档中获取上下文。
4. **`@Web`**：从搜索引擎的搜索结果中提取上下文。
5. **`@Folders`**：传递文件目录信息的上下文。
6. **`@Chat`**：将对话窗口内容作为上下文传递。
7. **`@Definitions`**：传递变量或类型的定义信息。
8. **`@Git`**：传递 Git 仓库的 commit 历史。
9. **`@Codebase`**：扫描代码仓库并传递相关上下文。

---

## 为什么选择 Cursor？

Cursor 的使用体验远超 Copilot，尤其是在以下方面：

- **高效的代码补全**：生成代码更加精准，减少手动修改的时间。
- **便捷的对话窗口**：支持直接应用生成的代码。
- **多文件支持**：一次对话即可处理多个文件，提升开发效率。
- **强大的上下文注记**：通过 `@` 注记快速传递上下文信息，生成结果更符合预期。

如果你有经济条件，强烈推荐尝试 Cursor。它的开发体验真的非常出色。

---

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)