# 选择插件

## 可用插件

| 工具 | 仓库 | 特性 |
|---|---|---|
| [Claude Code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | Skills（斜杠命令）、Hooks、子智能体 | 具有生命周期 hooks 的完全自动化 |
| [Kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Steering Rules、Hooks | auto/manual/fileMatch 激活模式 |
| [Cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Rules (.mdc) | 文件范围和智能体请求的规则 |

## 功能比较

| 功能 | Claude Code | Kiro | Cursor |
|---------|------------|------|--------|
| 设置向导 | `/ai-dev-os-init` | `#ai-dev-os-init` | `@ai-dev-os-init` |
| 差异检查 | `/ai-dev-os-check` | `#ai-dev-os-check` | `@ai-dev-os-check` |
| 全量扫描 | `/ai-dev-os-scan` | `#ai-dev-os-scan` | `@ai-dev-os-scan` |
| 规则提取 | `/ai-dev-os-extract` | `#ai-dev-os-extract` | `@ai-dev-os-extract` |
| 实施计划 | `/ai-dev-os-plan` | `#ai-dev-os-plan` | `@ai-dev-os-plan` |
| 规则说明 | `/ai-dev-os-why` | `#ai-dev-os-why` | `@ai-dev-os-why` |
| 健康审计 | `/ai-dev-os-audit` | `#ai-dev-os-audit` | `@ai-dev-os-audit` |
| SECI 演进 | `/ai-dev-os-evolve` | `#ai-dev-os-evolve` | `@ai-dev-os-evolve` |
| 合规报告 | `/ai-dev-os-report` | `#ai-dev-os-report` | `@ai-dev-os-report` |
| 工单生成 | `/ai-dev-os-ticket` | `#ai-dev-os-ticket` | `@ai-dev-os-ticket` |
| 预提交 hook | ✅ | ✅ | — |
| 文件保存 hook | — | ✅ | — |
| 自动代码检查 | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| L1-L2 依赖警告 | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| 子智能体 | ✅ (3 个智能体) | — | — |

## 如果您的工具不在列表中

4 层指南（L1-L3）适用于任何 AI 编程工具。仅 L4（AI 框架）是工具特定的。您可以：

1. 直接使用规则仓库，从工具的配置文件中引用指南
2. 参考插件仓库作为示例，创建自己的集成

---

Languages: [English](../../../../getting-started/choose-plugin.md) | [日本語](../../ja/getting-started/choose-plugin.md) | 简体中文 | [한국어](../../ko/getting-started/choose-plugin.md) | [Español](../../es/getting-started/choose-plugin.md)
