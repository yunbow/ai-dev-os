# Elegir Tus Reglas

## Conjuntos de Reglas Disponibles

| Repositorio | Lenguaje | Frameworks |
|---|---|---|
| [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | TypeScript | Next.js (App Router), Node.js CLI |
| [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Python | FastAPI, Flask, Typer CLI |

## Qué Contiene un Conjunto de Reglas

Cada conjunto de reglas contiene la estructura completa de 4 capas:

```
ai-dev-os-rules-{language}/
├── 01_philosophy/               # L1: Filosofía de Diseño (ejemplo, reescribir en tu lenguaje)
├── 02_decision-criteria/        # L2: Criterios de Decisión (ejemplo, reescribir en tu lenguaje)
├── 03_guidelines/               # L3: Directrices
│   ├── common/                  #   Reglas independientes del lenguaje (13 archivos)
│   └── frameworks/              #   Reglas específicas del framework
├── 04_ai-prompts/               # L4: Prompts y Skills de IA
└── templates/                   # Plantillas de scaffolding del proyecto
```

## Si Tu Lenguaje No Está Disponible

1. Bifurca [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) como punto de partida
2. Mantén `01_philosophy/`, `02_decision-criteria/` y `03_guidelines/common/` (estos son independientes del lenguaje)
3. Reemplaza `03_guidelines/frameworks/` con las directrices de tu framework
4. Actualiza `04_ai-prompts/` y `templates/` para tu stack

---

Languages: [English](../../../../getting-started/choose-rules.md) | [日本語](../../ja/getting-started/choose-rules.md) | [简体中文](../../zh-CN/getting-started/choose-rules.md) | [한국어](../../ko/getting-started/choose-rules.md) | Español
