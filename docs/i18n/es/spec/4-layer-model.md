# Lifespan Layers — El Modelo de 4 Capas para Reglas de Codificación IA

## Descripción General

AI Dev OS organiza el conocimiento del desarrollador en cuatro capas, cada una con una vida útil y un nivel de abstracción distintos.

```text
┌──────────────────────────────────────────────────────┐
│ L1: Filosofía                     Vida útil: 2-5 años │
│ "Por qué construimos de esta manera"                  │
│ Valores fundamentales que trascienden herramientas     │
│ y lenguajes                                           │
├──────────────────────────────────────────────────────┤
│ L2: Criterios de Decisión        Vida útil: 1-3 años │
│ "Cómo decidir"                                       │
│ Principios de diseño y arquitectura                    │
├──────────────────────────────────────────────────────┤
│ L3: Directrices                  Vida útil: 6-12 meses│
│ "Qué hacer"                                          │
│ Reglas de codificación concretas y verificables        │
├──────────────────────────────────────────────────────┤
│ L4: Marcos de IA                 Vida útil: 2-4 meses │
│ "Cómo comunicar"                                     │
│ Configuraciones y flujos de trabajo específicos de     │
│ herramientas                                          │
└──────────────────────────────────────────────────────┘
```

## Principios de Diseño

### Regla de Dependencia (de Clean Architecture)

Las capas superiores NO DEBEN referenciar a las capas inferiores.

- L1 no debe contener nombres de herramientas ("Claude Code", "Cursor") ni nombres de frameworks ("Next.js", "FastAPI")
- L2 no debe contener detalles de implementación específicos de frameworks
- L3 puede referenciar frameworks pero no configuraciones específicas de herramientas
- L4 es específico de herramientas por definición

### Vida Útil = Nivel de Abstracción

Cuanto más abstracta es una capa, más tiempo dura. Esto no es coincidencia — es una ley universal observada en 16 teorías clásicas de ingeniería de software (ver [classical-theories.md](../theory/classical-theories.md)).

### Cada Capa es Cualitativamente Diferente

Las capas no son niveles de detalle. Sirven diferentes propósitos para diferentes audiencias (según el Framework de Zachman):

| Capa | Propósito | Audiencia |
|------|-----------|-----------|
| L1 | Alinear valores del equipo | Todos |
| L2 | Guiar decisiones de arquitectura | Arquitectos, ingenieros senior |
| L3 | Aplicar estándares de codificación | Todos los desarrolladores |
| L4 | Configurar herramientas de IA | Usuarios de herramientas de IA |

## Specificity Cascade

Cuando las reglas entran en conflicto, se resuelve por especificidad:

```text
1. [Más alta]  frameworks/[stack]/*   ← Más específica
2. [Alta]      common/*               ← Común pero concreta
3. [Media]     project-specific/*     ← Contexto del proyecto
4. [Baja]      02_decision-criteria/* ← Criterios abstractos
5. [Más baja]  01_philosophy/*        ← Más abstracta
```

## Rule Harvesting

AI Dev OS se construye de abajo hacia arriba, no de arriba hacia abajo:

1. **Código primero** — Deja que la IA genere código
2. **Revisión** — Encuentra brechas entre el resultado y las expectativas
3. **Cosechar reglas** — Convierte las brechas en directrices explícitas (L3)
4. **Descubrir principios** — Encuentra patrones entre las reglas (L2)
5. **Articular filosofía** — Define los valores fundamentales (L1)

Este enfoque asegura que las reglas estén fundamentadas en experiencia real, no en ideales hipotéticos.

## Independencia de Herramientas

El modelo de 4 capas separa las responsabilidades por vida útil:

- **L1–L3 (75%)** — Independiente de herramientas. Sobrevive la migración entre Claude Code, Kiro, Cursor, etc.
- **L4 (25%)** — Específico de herramientas. Implementado por cada repositorio de plugins.

Este es el diferenciador clave de AI Dev OS: cuando cambias de herramienta de IA, el 75% de tu inversión se preserva.

## Two-Tier Context Strategy（Estrategia de Contexto de Dos Niveles）

No todas las directrices deben cargarse en el contexto de la IA en todo momento. La investigación muestra que demasiadas reglas pueden degradar la calidad de la salida de la IA.

**Contexto estático** (CLAUDE.md / .cursorrules / AGENTS.md):

- Cargado por la IA en cada conversación
- Debe contener solo **3-5 archivos de directrices específicas del proyecto** (seguridad, manejo de errores, nomenclatura, estructura del proyecto, descripción general del framework)
- Curar manualmente — no eliminar automáticamente basándose en la frecuencia de violaciones (las reglas de baja frecuencia como las de seguridad pueden estar funcionando precisamente porque están presentes)

**Verificaciones dinámicas** (skills/reglas del plugin):

- Invocadas bajo demanda (`/ai-dev-os-check`, `/ai-dev-os-scan`, `/ai-dev-os-review`)
- Verifican contra **todas las directrices** (30+) de forma exhaustiva
- Sin dilución de atención porque la IA las procesa en una tarea de revisión enfocada, no durante la generación de código

Este enfoque de dos niveles resuelve ambos problemas:

- "Demasiadas reglas degradan la calidad" → el contexto estático está curado y enfocado
- "Las reglas importantes no deben omitirse" → las verificaciones dinámicas cubren todo

## La Regla Centinela

> **La ausencia de violaciones demuestra la presencia de protección, no la ausencia de necesidad.**

Una regla de seguridad con cero violaciones está *funcionando*. Eliminarla porque "nunca se activa" causaría regresiones inmediatamente. Este principio aplica a todas las reglas de alto riesgo (seguridad, autenticación, integridad de datos):

- Nunca eliminar automáticamente reglas basándose en baja frecuencia de violaciones
- Nunca desprioritizar reglas que han prevenido problemas
- Al curar el contexto estático, siempre mantener las reglas de seguridad y autenticación sin importar el conteo de violaciones

---

Languages: [English](../../../../spec/4-layer-model.md) | [日本語](../../ja/spec/4-layer-model.md) | [简体中文](../../zh-CN/spec/4-layer-model.md) | [한국어](../../ko/spec/4-layer-model.md) | Español
