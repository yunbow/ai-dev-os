# Elegir Tu Plugin

## Plugins Disponibles

| Herramienta | Repositorio | Características |
|---|---|---|
| [Claude Code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | Skills (comandos slash), Hooks, Sub-agentes | Automatización completa con hooks de ciclo de vida |
| [Kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Reglas de Dirección, Hooks | Modos de activación auto/manual/fileMatch |
| [Cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Reglas (.mdc) | Reglas con alcance de archivo y solicitadas por agente |

## Comparación de Características

| Característica | Claude Code | Kiro | Cursor |
|----------------|------------|------|--------|
| Asistente de configuración | `/ai-dev-os-init` | `#ai-dev-os-init` | `@ai-dev-os-init` |
| Verificación de diff | `/ai-dev-os-check` | `#ai-dev-os-check` | `@ai-dev-os-check` |
| Escaneo completo | `/ai-dev-os-scan` | `#ai-dev-os-scan` | `@ai-dev-os-scan` |
| Extracción de reglas | `/ai-dev-os-extract` | `#ai-dev-os-extract` | `@ai-dev-os-extract` |
| Plan de implementación | `/ai-dev-os-plan` | `#ai-dev-os-plan` | `@ai-dev-os-plan` |
| Explicador de reglas | `/ai-dev-os-why` | `#ai-dev-os-why` | `@ai-dev-os-why` |
| Auditoría de salud | `/ai-dev-os-audit` | `#ai-dev-os-audit` | `@ai-dev-os-audit` |
| Evolución SECI | `/ai-dev-os-evolve` | `#ai-dev-os-evolve` | `@ai-dev-os-evolve` |
| Informe de cumplimiento | `/ai-dev-os-report` | `#ai-dev-os-report` | `@ai-dev-os-report` |
| Generación de tickets | `/ai-dev-os-ticket` | `#ai-dev-os-ticket` | `@ai-dev-os-ticket` |
| Hook pre-commit | ✅ | ✅ | — |
| Hook al guardar archivo | — | ✅ | — |
| Verificación automática de código | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| Advertencia de dependencia L1-L2 | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| Sub-agentes | ✅ (3 agentes) | — | — |

## Si Tu Herramienta No Está en la Lista

Las directrices de 4 capas (L1-L3) funcionan con cualquier herramienta de codificación con IA. Solo L4 (Marcos de IA) es específico de la herramienta. Puedes:

1. Usar el repositorio de reglas directamente y referenciar las directrices desde el archivo de configuración de tu herramienta
2. Consultar los repositorios de plugins como ejemplos para crear tu propia integración

---

Languages: [English](../../../../getting-started/choose-plugin.md) | [日本語](../../ja/getting-started/choose-plugin.md) | [简体中文](../../zh-CN/getting-started/choose-plugin.md) | [한국어](../../ko/getting-started/choose-plugin.md) | Español
