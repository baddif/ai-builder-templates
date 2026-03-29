# ai-builder-templates
A repo for documents of vibe coding standard


# AI Skill & MCP Generation Standard / AI 技能与 MCP 服务端生成规范

## 📄 File Information / 文件信息
- **File Name / 文件路径**: `SKILL_GENERATION_RULES.md`
- **Current Version / 当前版本**: v4.1.1
- **Purpose / 用途**: 
  - **EN**: Definitive, executable instructions for generating AI-native skills with Model Context Protocol (MCP) and CLI support. It ensures standard output schemas, strict error handling, and dual-mode execution.
  - **ZH**: 权威且可执行的 AI 原生技能生成规范。用于指导大模型自动生成同时支持 MCP (Model Context Protocol) 和本地 CLI 调用的工具代码，确保标准化的输入输出契约和严格的错误处理。

## 🚀 Prompt Template / 提示词模板

When using AI agents (like Cursor, Claude, or ChatGPT) to generate a new skill, use the following prompt template:
使用 AI 助手生成新技能时，请使用以下提示词模板：

**English Prompt:**
> "Please read the skill generation rules at [Insert RAW URL to SKILL_GENERATION_RULES.md]. Strictly following version 4.1.1 of this specification, generate a new skill that [describe your skill's functionality, e.g., fetches weather data]. Ensure all files, contracts, and naming conventions comply with the rules."

**中文提示词:**
> "请读取并严格遵循此规范文件 [插入 SKILL_GENERATION_RULES.md 的 Raw 链接]。根据 v4.1.1 版本的规则，为我生成一个新的技能，功能是：[描述你的需求，例如：抓取指定网页正文]。请确保所有的文件结构、输入输出契约和命名规范都符合文档要求。"

## 📋 Field Explanations / 字段与契约说明

The specification heavily relies on strict naming conventions and core contracts.
本规范严格依赖以下命名约定和核心契约：

### Naming Conventions / 命名约定
- `{name}`: lowercase, underscore-separated (e.g., `pdf_merger`). Used for filenames and module names. / 小写加下划线，用于文件名。
- `{tool_name}`: MUST equal `{name}`. / 必须与 `{name}` 保持一致。
- `{Name}`: Title Case (e.g., `PDF Merger`). Used for display names. / 首字母大写，用于展示名称。
- `{class_name}`: PascalCase (e.g., `PdfMerger`). Used for Python classes. / 帕斯卡命名法，用于 Python 类名。

### Core Contracts (Output Schema) / 核心输出契约
All tool executions MUST return the following JSON structure:
所有工具执行都必须返回以下 JSON 结构：
```json
{
  "success": true, // Boolean indicating execution status / 布尔值，标识执行是否成功
  "data": {},      // The actual payload if successful / 成功时的返回数据
  "error": null    // Error message if failed, otherwise null / 失败时的错误信息，成功时为 null
}