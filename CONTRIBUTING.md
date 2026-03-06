<div align="center">
  <img width="100%" src="https://cdn.marmot-cloud.com/storage/zenmux/2025/09/16/lAK3vlZ/banner.png" alt="ZenMux Banner" />

  <p>
    <a href="#contributing-to-zenmux-documentation">English</a> | <a href="#贡献指南">简体中文</a>
  </p>
</div>

# Contributing to ZenMux Documentation

Thank you for your interest in contributing to the ZenMux documentation! This guide explains how to submit a Markdown file via a Pull Request.

## Before You Start

- This repository uses **Chinese as the source language**. All documentation is written in Chinese first, then translated to English.
- The documentation site is built with [VitePress](https://vitepress.dev/).
- We use `pnpm` as the package manager.

## How to Submit a Markdown File

### 1. Fork and Clone

1. Fork this repository on GitHub.
2. Clone your fork locally:
   ```sh
   git clone https://github.com/<your-username>/zenmux-doc.git
   cd zenmux-doc
   ```

### 2. Install Dependencies

```sh
pnpm install
```

### 3. Create Your Markdown File

All new documentation files must be created in **Chinese first** under `docs_source/zh/`:

```
docs_source/zh/
├── guide/          # User guides and tutorials
├── about/          # About ZenMux
├── best-practices/ # Integration and usage best practices
├── api/            # API reference documentation
└── help/           # Help center (privacy, terms, contact)
```

**File requirements:**

- The file **must** be placed in the appropriate folder under `docs_source/zh/`.
- The file **must** include a `title` field in the YAML front matter:
  ```yaml
  ---
  title: Your Page Title
  ---
  ```
- Use standard VitePress Markdown syntax. See the [VitePress documentation](https://vitepress.dev/guide/markdown) for reference.
- Follow the existing file structure and formatting conventions.

### 4. Generate the English Translation

After creating the Chinese documentation, generate the English version:

```sh
# Translate a single file
pnpm run translate docs_source/zh/your-file.md

# Or translate an entire folder
pnpm run translate docs_source/zh/your-folder/
```

> **Note:** The `ZENMUX_API_KEY` environment variable is required for the translation script.

### 5. Update Sidebar Navigation

Add your new page to the sidebar in both language config files:

- **Chinese sidebar:** `docs_source/zh/config.ts`
- **English sidebar:** `docs_source/en/config.ts`

Add an entry following this pattern:

```ts
{ text: "Your Page Title", link: "/zh/guide/your-file" }
```

### 6. Preview Locally

```sh
pnpm run dev
```

Open `http://localhost:5173` in your browser to preview your changes.

### 7. Open a Pull Request

1. Create a new branch: `git checkout -b feat/add-your-doc-name`
2. Commit your changes: `git commit -m "docs: add <your-doc-title>"`
3. Push and open a PR against the `main` branch.

## PR Requirements

When submitting a Pull Request, please ensure:

- [ ] The Chinese source file is included under `docs_source/zh/`
- [ ] The corresponding English translation is included under `docs_source/en/`
- [ ] Both language sidebar configs (`docs_source/zh/config.ts` and `docs_source/en/config.ts`) are updated
- [ ] The Markdown file includes a valid `title` in the front matter
- [ ] The content is accurate, well-structured, and follows existing formatting conventions
- [ ] The PR title clearly describes the change (e.g., `docs: add Cursor integration guide`)
- [ ] The PR description explains what was added and why

## Code of Conduct

Please be respectful and constructive in all interactions. We welcome contributions from everyone.

## Questions?

If you have questions or need help, feel free to reach out:

- **Email:** [support@zenmux.ai](mailto:support@zenmux.ai)
- **Discord:** [discord.gg/vHZZzj84Bm](http://discord.gg/vHZZzj84Bm)

---

# 贡献指南

感谢你有兴趣为 ZenMux 文档做出贡献！本指南将说明如何通过 Pull Request 提交一个 Markdown 文件。

## 开始之前

- 本仓库以**中文为源语言**，所有文档均先用中文编写，再翻译为英文。
- 文档站点基于 [VitePress](https://vitepress.dev/) 构建。
- 我们使用 `pnpm` 作为包管理器。

## 如何提交 Markdown 文件

### 1. Fork 并克隆仓库

1. 在 GitHub 上 Fork 本仓库。
2. 在本地克隆你的 Fork：
   ```sh
   git clone https://github.com/<你的用户名>/zenmux-doc.git
   cd zenmux-doc
   ```

### 2. 安装依赖

```sh
pnpm install
```

### 3. 创建你的 Markdown 文件

所有新文档文件必须**首先以中文编写**，放在 `docs_source/zh/` 目录下：

```
docs_source/zh/
├── guide/          # 用户指南和教程
├── about/          # 关于 ZenMux
├── best-practices/ # 集成和使用最佳实践
├── api/            # API 参考文档
└── help/           # 帮助中心（隐私、协议、联系方式）
```

**文件要求：**

- 文件**必须**放置在 `docs_source/zh/` 下的对应目录中。
- 文件**必须**在 YAML 头部信息中包含 `title` 字段：
  ```yaml
  ---
  title: 你的页面标题
  ---
  ```
- 使用标准的 VitePress Markdown 语法，参考 [VitePress 文档](https://vitepress.dev/guide/markdown)。
- 遵循现有的文件结构和格式规范。

### 4. 生成英文翻译

创建中文文档后，生成对应的英文版本：

```sh
# 翻译单个文件
pnpm run translate docs_source/zh/your-file.md

# 或翻译整个文件夹
pnpm run translate docs_source/zh/your-folder/
```

> **注意：** 翻译脚本需要设置 `ZENMUX_API_KEY` 环境变量。

### 5. 更新侧边栏导航

在两个语言配置文件中添加新页面的侧边栏条目：

- **中文侧边栏：** `docs_source/zh/config.ts`
- **英文侧边栏：** `docs_source/en/config.ts`

按照以下格式添加条目：

```ts
{ text: "你的页面标题", link: "/zh/guide/your-file" }
```

### 6. 本地预览

```sh
pnpm run dev
```

在浏览器中打开 `http://localhost:5173` 预览你的修改。

### 7. 发起 Pull Request

1. 创建新分支：`git checkout -b feat/add-your-doc-name`
2. 提交更改：`git commit -m "docs: 添加 <你的文档标题>"`
3. 推送并针对 `main` 分支发起 PR。

## PR 要求

提交 Pull Request 时，请确保：

- [ ] `docs_source/zh/` 目录下包含中文源文件
- [ ] `docs_source/en/` 目录下包含对应的英文翻译
- [ ] 已更新两个语言的侧边栏配置（`docs_source/zh/config.ts` 和 `docs_source/en/config.ts`）
- [ ] Markdown 文件的头部信息中包含有效的 `title` 字段
- [ ] 内容准确、结构清晰，并遵循现有格式规范
- [ ] PR 标题清晰描述了变更内容（例如：`docs: 新增 Cursor 接入指南`）
- [ ] PR 描述说明了新增内容及原因

## 行为准则

请在所有交流中保持尊重和建设性态度，我们欢迎所有人的贡献。

## 有疑问？

如有问题或需要帮助，欢迎随时联系我们：

- **邮箱：** [support@zenmux.ai](mailto:support@zenmux.ai)
- **Discord：** [discord.gg/vHZZzj84Bm](http://discord.gg/vHZZzj84Bm)
