# Dependency Rule for AI Coding Rules

## Principle

> Upper layers must never reference lower layers.

This is borrowed directly from Robert C. Martin's Clean Architecture dependency rule and Christopher Alexander's pattern language hierarchy.

## Rules by Layer

### L1: Philosophy

- MUST NOT contain: tool names, framework names, library names, API names
- MUST NOT contain: code examples in any specific language
- MAY contain: abstract concepts, values, thinking frameworks

### L2: Decision Criteria

- MUST NOT contain: framework-specific implementation details
- MUST NOT contain: specific library API references
- MAY contain: language paradigms (OOP, FP), general patterns (MVC, CQRS)

### L3: Guidelines

- MUST NOT contain: tool-specific configurations (CLAUDE.md format, .cursorrules syntax)
- MAY contain: framework names, library names, code examples

### L4: AI Frames

- MAY contain: anything tool-specific
- SHOULD reference: L3 guidelines as the source of truth

## Violation Detection

The `/ai-dev-os-audit` command checks for dependency violations by scanning:

- L1 files for tool/framework terms
- L2 files for implementation details

The plugin hooks also provide real-time warnings when editing L1-L2 files.

---

Languages: English | [日本語](../docs/i18n/ja/spec/dependency-rule.md) | [简体中文](../docs/i18n/zh-CN/spec/dependency-rule.md) | [한국어](../docs/i18n/ko/spec/dependency-rule.md) | [Español](../docs/i18n/es/spec/dependency-rule.md)
