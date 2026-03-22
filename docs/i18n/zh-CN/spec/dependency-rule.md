# AI 编程规则的依赖规则

## 原则

> 上层绝不能引用下层。

这直接借鉴了 Robert C. Martin 的 Clean Architecture 依赖规则和 Christopher Alexander 的模式语言层级。

## 各层规则

### L1: Philosophy

- 不得包含：工具名称、框架名称、库名称、API 名称
- 不得包含：任何特定语言的代码示例
- 可以包含：抽象概念、价值观、思维框架

### L2: Decision Criteria

- 不得包含：框架特定的实现细节
- 不得包含：特定的库 API 引用
- 可以包含：语言范式（OOP、FP）、通用模式（MVC、CQRS）

### L3: Guidelines

- 不得包含：工具特定的配置（CLAUDE.md 格式、.cursorrules 语法）
- 可以包含：框架名称、库名称、代码示例

### L4: AI Frames

- 可以包含：任何工具特定的内容
- 应当引用：L3 指南作为信息来源

## 违规检测

`/ai-dev-os-audit` 命令通过扫描以下内容检查依赖违规：

- L1 文件中的工具/框架术语
- L2 文件中的实现细节

插件 hooks 还在编辑 L1-L2 文件时提供实时警告。

---

Languages: [English](../../../../spec/dependency-rule.md) | [日本語](../../ja/spec/dependency-rule.md) | 简体中文 | [한국어](../../ko/spec/dependency-rule.md) | [Español](../../es/spec/dependency-rule.md)
