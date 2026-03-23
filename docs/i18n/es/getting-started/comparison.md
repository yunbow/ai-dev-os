# AI Dev OS en 5 Minutos — Comparación de Frameworks

## ¿Qué es AI Dev OS? — Framework de Reglas de Codificación IA

Un framework para convertir el conocimiento tácito del desarrollador en reglas explícitas y aplicables para la codificación asistida por IA. A diferencia de las herramientas de orquestación de flujos de trabajo, AI Dev OS trata el problema como **gestión del conocimiento**.

## Comparación Rápida

| | AI Dev OS | ContextKit (Anthropic) | Spec Kit (GitHub) | GSD | BMAD | bkit |
|---|---|---|---|---|---|---|
| **Idea central** | Capas de conocimiento con vidas útiles | Documentos de contexto estructurados | Especificación como fuente de verdad | Orquestación de ejecución | Roles multi-agente | Ciclos PDCA |
| **Organización de reglas** | 4 capas (Filosofía → Criterios de Decisión → Directrices → Marcos de IA) | Documentos de Producto/Arquitectura/Estilo | Especificación/plan/tarea plana | 3 documentos | 19 agentes, 50+ flujos de trabajo | Basado en fases |
| **Soporte de herramientas** | Claude Code + Kiro + Cursor | Claude Code (principal) | Multi-herramienta (shell) | Solo Claude Code | Multi-herramienta | Gemini + Claude |
| **Evolución de reglas** | Integrada (`ai-dev-os-evolve`) | Manual | Manual | Manual | Manual | Manual |
| **Resolución de conflictos** | Specificity Cascade | No definida | No definida | No definida | No definida | No definida |
| **Sobrecarga de contexto** | Dos niveles (estáticas 3-5 reglas + verificación dinámica completa) | Alcance a nivel de documento | No abordada | Sub-agente nuevo | Especialización de agentes | Basado en hooks |
| **Migración de herramientas** | 75% preservado (L1-L3 portables) | Parcialmente portable | La especificación sobrevive | Los documentos de estado sobreviven | Los documentos sobreviven | Basado en sesiones |
| **Base teórica** | 16 teorías clásicas de IS | Ingeniería de contexto | Metodología SDD | Ingeniería de contexto | Ágil + agentes | PDCA |
| **Configuración** | `npx ai-dev-os init` (CLI) | Creación manual de Markdown | Scripts de shell | Basado en prompts | Asistente de múltiples pasos | Archivos de configuración |

## Cuándo Elegir AI Dev OS

**Elige AI Dev OS si:**

- Quieres reglas que sobrevivan cambios de herramientas (Claude Code → Kiro → Cursor)
- Necesitas un sistema que mejore con el tiempo (Rule Harvesting + espiral SECI)
- Valoras el "por qué" sobre el "qué" — entender principios, no solo seguir plantillas
- Trabajas en múltiples proyectos y quieres directrices reutilizables

**Elige otra opción si:**

- Quieres documentos de contexto ligeros sin un modelo por capas (→ ContextKit)
- Quieres un optimizador de flujo de trabajo de una sola sesión (→ GSD)
- Necesitas orquestación multi-agente para equipos grandes (→ BMAD)
- Quieres gestión de especificaciones nativa de GitHub (→ Spec Kit)

## Compromisos

AI Dev OS no es la opción correcta para todas las situaciones:

- **Inversión inicial**: No verás valor en los primeros 30 minutos. Las reglas necesitan ser escritas y refinadas con el tiempo.
- **Complejidad de configuración**: Incluso con el CLI, el modelo de submódulos requiere conocimiento de git. Los flujos de trabajo sin git no están soportados.
- **Mantenimiento de reglas**: Las reglas necesitan revisión periódica. Sin disciplina, se vuelven obsoletas.

## Diferenciadores Clave

### 1. Reglas con Fechas de Expiración

Cada regla tiene una vida útil. L1 (filosofía) dura 2-5 años. L4 (configuración de herramientas) dura 2-4 meses. Esto previene la obsolescencia de reglas.

### 2. Descubrimiento de Reglas de Abajo hacia Arriba

No escribas reglas de arriba hacia abajo. Deja que la IA genere código, encuentra brechas, extrae reglas de fallos reales. Reglas fundamentadas en experiencia, no en teoría.

### 3. "Menos es Más" para el Contexto

La investigación muestra que demasiadas reglas degradan la salida de la IA. AI Dev OS cura 3-5 reglas de alto impacto para contexto estático, y verifica todas las 30+ dinámicamente bajo demanda.

### 4. La Regla Centinela

Las reglas de seguridad con cero violaciones están *funcionando* — nunca las elimines por ser "no utilizadas."

## Filosofía de Diseño: Diseño basado en Markdown

AI Dev OS está compuesto intencionalmente en su totalidad por archivos Markdown. Esta es una decisión de diseño deliberada, no una limitación:

- **Transparencia**: Cada regla es legible por humanos. Sin compilación, sin formatos binarios, sin configuraciones opacas.
- **Bifurcabilidad**: Cualquiera puede bifurcar, modificar y redistribuir reglas sin aprender una herramienta propietaria o DSL.
- **Independencia de herramientas**: Markdown funciona con cualquier editor, cualquier herramienta de IA, cualquier sistema de CI. Sin dependencia de proveedores.

La [herramienta CLI](https://github.com/yunbow/ai-dev-os-cli) (`npx ai-dev-os init`) automatiza la configuración, pero el modelo subyacente sigue siendo git submodules — las reglas viven en tu repositorio como archivos de texto auditables y comparables. El CLI es opcional; la configuración manual siempre está soportada.

---

Languages: [English](../../../../getting-started/comparison.md) | [日本語](../../ja/getting-started/comparison.md) | [简体中文](../../zh-CN/getting-started/comparison.md) | [한국어](../../ko/getting-started/comparison.md) | Español
