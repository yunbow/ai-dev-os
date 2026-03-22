# AI Dev OS

[![Lint & Link Check](https://github.com/yunbow/ai-dev-os/actions/workflows/lint.yml/badge.svg)](https://github.com/yunbow/ai-dev-os/actions/workflows/lint.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](../../../LICENSE)

> Convierte el conocimiento tacito del desarrollador en reglas explicitas y aplicables para la codificacion asistida por IA.

Framework de reglas de codificación para asistentes de IA — Claude Code, Cursor y Kiro

```text
> /ai-dev-os-check

## AI Dev OS Check & Fix Report
- Files checked: 12
- ✅ Passed: 45 / 🔧 Fixed: 3 / ⚠️ Manual Review: 1

| # | File              | Rule         | What was fixed              |
|---|-------------------|--------------|-----------------------------|
| 1 | route.ts:42       | security.md  | Added rate limiting         |
| 2 | user-card.tsx:7   | naming.md    | Renamed to kebab-case       |
| 3 | action.ts:15      | validation.md| Added .refine() for dueDate |
```

## ¿Por qué AI Dev OS?

Tu IA escribe codigo que parece correcto, pero viola las convenciones del equipo.
Los estandares de codificacion viven en la cabeza de los desarrolladores senior, no en el contexto de la IA.

AI Dev OS resuelve esto haciendo explicito el conocimiento tacito:

- **El 75% sobrevive a las migraciones de herramientas** — Las reglas son independientes de herramientas (L1–L3). Cambia libremente entre Claude Code → Kiro → Cursor
- **Las reglas mejoran con el tiempo** — Cosecha reglas de revisiones de codigo reales, no de ideales hipoteticos (Rule Harvesting)
- **Costo casi cero** — 3-5 reglas estáticas en contexto + verificación y corrección integral bajo demanda ([benchmark: 96.9/100](https://github.com/yunbow/ai-dev-os-benchmark))
- **Markdown puro** — Sin DSL, sin compilacion. Haz fork, modifica y audita cada regla

AI Dev OS complementa tu herramienta de IA, no la reemplaza. Claude Code, Kiro y Cursor se encargan de la generacion de codigo; AI Dev OS se encarga de las reglas que siguen.

## Inicio Rapido

```bash
npx ai-dev-os init
```

Elige un lenguaje (`typescript` / `python`) y una herramienta (`claude-code` / `kiro` / `cursor`).

```bash
# No interactivo:
npx ai-dev-os init --rules typescript --plugin claude-code
```

> [Detalles del CLI](https://github.com/yunbow/ai-dev-os-cli) | [Configuracion manual](getting-started/quick-start.md) | [Elegir Reglas](getting-started/choose-rules.md) | [Elegir Plugin](getting-started/choose-plugin.md)

## Lifespan Layers — El Modelo de 4 Capas

| Capa | Nombre | Vida Util | Proposito |
|------|--------|-----------|-----------|
| L1 | Filosofia | 2-5 anos | Valores fundamentales que trascienden herramientas y lenguajes |
| L2 | Criterios de Decision | 1-3 anos | Criterios de decision de diseno y arquitectura |
| L3 | Directrices | 6-12 meses | Reglas de codificacion concretas y verificables |
| L4 | Marcos de IA | 2-4 meses | Configuraciones y flujos de trabajo especificos de herramientas |

Las capas superiores son abstractas y estables; las inferiores son concretas y volatiles.
Al cambiar de herramienta, L1–L3 (75%) se mantienen intactas — solo cambia L4.

## Conceptos Clave

**Specificity Cascade (rule conflict resolution)** — Cuando las reglas entran en conflicto, la mas especifica gana (como la especificidad CSS). Reglas de framework > reglas comunes > convenciones de proyecto > principios > filosofia. [→ Detalles](spec/priority-cascade.md)

**Rule Harvesting (bottom-up rule discovery)** — No escribas reglas de arriba hacia abajo. Deja que la IA codifique → revisa las brechas → cosecha como reglas. De abajo hacia arriba, basado en experiencia real. [→ Detalles](spec/4-layer-model.md#rule-harvesting)

**Guideline Capital (guidelines as intellectual assets)** — Las directrices no son prompts desechables, son capital intelectual. A diferencia de la Technical Debt (pasivo), el Guideline Capital es un activo que se acumula. [→ Detalles](getting-started/comparison.md)

**Two-Tier Context Strategy** (generate + verify + fix) — Carga solo 3-5 archivos específicos del proyecto en CLAUDE.md (~8K tokens). Verifica todas las reglas post-generación vía `/ai-dev-os-check`. [Datos de benchmark](https://github.com/yunbow/ai-dev-os-benchmark) muestran que este enfoque obtiene 96.9/100, mientras que cargar 10+ archivos obtiene menos que sin directrices.

## Funciona Con

AI Dev OS proporciona un enfoque estructurado para escribir archivos de reglas de codificación de IA efectivos:

- **Claude Code** — vía `CLAUDE.md` y skills personalizados ([plugin](https://github.com/yunbow/ai-dev-os-plugin-claude-code))
- **Kiro** — vía `AGENTS.md` y steering rules ([plugin](https://github.com/yunbow/ai-dev-os-plugin-kiro))
- **Cursor** — vía `.cursorrules` y archivos `.mdc` ([plugin](https://github.com/yunbow/ai-dev-os-plugin-cursor))

## Ecosistema

| Repositorio | Descripcion |
|---|---|
| **ai-dev-os** (este repo) | Especificacion y teoria del framework |
| [rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | Directrices para TypeScript / Next.js / Node.js |
| [rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Directrices para Python / FastAPI |
| [plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | Skills, Hooks y Agents para Claude Code |
| [plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Steering Rules y Hooks para Kiro |
| [plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Cursor Rules (.mdc) |
| [cli](https://github.com/yunbow/ai-dev-os-cli) | `npx ai-dev-os init` |
| [benchmark](https://github.com/yunbow/ai-dev-os-benchmark) | Benchmark cuantitativo — datos de impacto de directrices en calidad de código |

## Mas Informacion

- [Modelo de 4 Capas](spec/4-layer-model.md) | [Regla de Dependencia](spec/dependency-rule.md) | [Specificity Cascade](spec/priority-cascade.md) | [Modelo de Vida Util](spec/shelf-life.md)
- [Tacit-to-Explicit Engineering](theory/tacit-to-explicit.md) | [Mapeo de Teorias Clasicas](theory/classical-theories.md) | [Preparación para el Futuro](theory/future-proofing.md)
- [Comparacion de Frameworks](getting-started/comparison.md) | [Directrices vs Multi-Agente](getting-started/guideline-vs-multi-agent.md) | [Migracion de Herramientas](getting-started/migration.md)
- [Zenn Book: AI DEV OS (Japanese)](https://zenn.dev/yun_bow)

<details>
<summary>Estructura de Directorios</summary>

```text
ai-dev-os/
├── spec/                        # Especificacion del Framework
│   ├── 4-layer-model.md         #   Lifespan Layers (modelo de 4 capas)
│   ├── dependency-rule.md       #   Regla de dependencia
│   ├── priority-cascade.md      #   Specificity Cascade
│   ├── shelf-life.md            #   Modelo de vida util
│   └── governance.md            #   Modelo de gobernanza
├── theory/                      # Trasfondo Teorico
├── getting-started/             # Guia de Inicio
└── docs/                        # Guia de Operacion e i18n
```

> Los archivos de directrices reales (01_philosophy/ ... 04_ai-prompts/) estan en los
> [repositorios de reglas](https://github.com/yunbow/ai-dev-os-rules-typescript), no en este repositorio principal.

</details>

## Licencia

[MIT](../../../LICENSE)

---

Languages: [English](../../../README.md) | [日本語](../ja/README.md) | [简体中文](../zh-CN/README.md) | [한국어](../ko/README.md) | Español
