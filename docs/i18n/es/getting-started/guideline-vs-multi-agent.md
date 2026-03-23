# Revisión de Código con IA: Directrices vs Revisión Multi-Agente — Cuándo Usar Cada Una

## La Pregunta

> "¿Debería usar las directrices de AI Dev OS, o hacer que múltiples LLMs debatan mi código?"

**Respuesta: Ambas — pero en diferentes capas.**

Las directrices de AI Dev OS y la revisión multi-LLM no son alternativas. Cubren diferentes dimensiones de calidad y funcionan mejor cuando se combinan según el nivel de riesgo.

## La Idea Central

```text
Calidad
 ↑
 |          ┌─── Debate multi-LLM (efecto techo)
 |         ╱     Descubre problemas desconocidos: casos límite, zero-days, compromisos de diseño
 |        ╱
 |       ╱
 |  ════╪══════ Directrices (efecto piso)
 |      |       Garantiza línea base: nomenclatura, patrones, checklist de seguridad, consistencia
 |      |
 └──────┴──────→ Costo
```

- **Las directrices elevan el piso** — reproducibles, costo casi nulo, el conocimiento se acumula con el tiempo
- **El debate multi-LLM eleva el techo** — explora problemas desconocidos, pero costoso y no reproducible

## Dimensiones de Calidad

| Dimensión de Calidad | Directrices (AI Dev OS) | Debate Multi-LLM | Responsable Principal |
|---|---|---|---|
| Conformidad (estándares de código) | ★★★★★ | ★★ | Directrices |
| Mantenibilidad (nomenclatura, estructura) | ★★★★★ | ★★ | Directrices |
| Corrección (bugs lógicos) | ★★★ | ★★★★ | Multi-LLM |
| Robustez (casos límite) | ★★ | ★★★★ | Multi-LLM |
| Seguridad (vulnerabilidades) | ★★★ | ★★★★★ | Multi-LLM (+ Directrices) |
| Retención de conocimiento | ★★★★★ | ★ | Directrices |
| Eficiencia de costos | ★★★★★ | ★★ | Directrices |

## Guía Basada en Tareas

| Tarea | Riesgo | Enfoque Recomendado | Costo Est. |
|---|---|---|---|
| Implementación CRUD | Bajo | Solo directrices (`/ai-dev-os-check`) | ~$0 |
| Componentes de UI | Bajo | Solo directrices | ~$0 |
| Lógica de negocio | Medio | Directrices + revisión de un solo LLM (sesión separada) | ~$0.04 |
| Refactorización | Medio | Directrices + suite de tests | ~$0 |
| Diseño de API | Medio-Alto | Directrices + revisión de 2 modelos | ~$0.40 |
| Código relacionado con seguridad | Alto | Directrices + debate de 3 modelos | ~$0.80 |
| Pagos / autenticación | Crítico | Directrices + debate de 3 modelos + revisión humana | ~$0.80+ |
| Decisiones de arquitectura | Alto | Debate de 3 modelos (no hay una única respuesta correcta) | ~$0.80 |

## El Modelo Recomendado: Directrices Primero, Debate Según Riesgo

```text
Fase 1: Generación de Código
  La IA escribe código con las directrices de AI Dev OS cargadas en contexto (CLAUDE.md)
  → Calidad base mediante reglas estáticas (3-5 reglas de alto impacto)
  → Costo: incluido en la codificación normal con IA

Fase 2: Verificación Pre-Commit (/ai-dev-os-check)
  Verificación exhaustiva contra 30+ reglas
  → Detecta conformidad y violaciones de patrones conocidos
  → Costo: casi nulo

Fase 3: Revisión de PR (basada en riesgo)
  Auto-detección: cambios en archivos de seguridad/pagos/autenticación
  → Solo PRs de alto riesgo: activar revisión cruzada entre modelos
  → Costo: solo para el 10-20% de los PRs

Fase 4: Retroalimentación de Conocimiento
  Nuevos patrones descubiertos por debate multi-LLM → agregar a directrices L3
  → La próxima vez, el mismo problema se detecta a costo casi nulo
  → Este es el Rule Harvesting en acción
```

## ¿Por Qué No Solo Debate Multi-LLM para Todo?

| Preocupación | Datos |
|---|---|
| **Costo** | Los sistemas multi-agente consumen 4-220x más tokens que un solo agente (ICLR 2025). Para un equipo de 10 desarrolladores, debate en todos los PR = ~$16,000/mes vs directrices a ~$0 |
| **Reproducibilidad** | Mismo código + mismos modelos = resultados diferentes cada vez. Las directrices producen verificaciones determinísticas |
| **Pérdida de conocimiento** | Los resultados del debate son volátiles — las ideas de la semana pasada no se trasladan a la siguiente revisión. Las directrices se acumulan |
| **Barrera de adopción** | Menos del 10% de las empresas escalan exitosamente sistemas multi-agente. `npx ai-dev-os init` funciona desde el primer día |
| **Falsos positivos** | Los LLMs sobre-corrigen sistemáticamente código correcto y atribuyen erróneamente las causas de defectos (investigación 2026) |

## ¿Por Qué No Solo Directrices?

| Preocupación | Datos |
|---|---|
| **Complacencia** | Los LLMs están de acuerdo con las expectativas del usuario el 56-62% del tiempo (SycEval, AAAI 2025). Incluso al verificar directrices, el LLM revisor puede aplicar reglas con indulgencia — ~40% de riesgo residual de complacencia |
| **Puntos ciegos estáticos** | Las directrices solo detectan lo que se ha documentado. Vulnerabilidades nuevas, casos límite inesperados y problemas específicos del dominio requieren exploración |
| **Sesgo del mismo modelo** | Un solo modelo tiene un conjunto de sesgos. Omite sistemáticamente los mismos tipos de bugs cada vez |

## El Ciclo de Retroalimentación

La idea más poderosa: **el debate multi-LLM es un motor de descubrimiento de directrices**.

```text
El debate multi-LLM encuentra un nuevo patrón
  → Extraer como directriz L3 (Rule Harvesting)
  → Agregar a las reglas de ai-dev-os
  → La próxima vez: detectado por /ai-dev-os-check a costo cero
  → Presupuesto de debate liberado para la próxima incógnita
```

Con el tiempo, el conjunto de directrices crece para cubrir más patrones, y el presupuesto de debate se concentra en problemas genuinamente nuevos. Esto crea un ciclo virtuoso.

## Relacionado

- [Comparación de Frameworks](./comparison.md) — AI Dev OS vs Spec Kit, GSD, BMAD, ContextKit
- [Inicio Rápido](./quick-start.md) — Comenzar con AI Dev OS
- [AI Dev OS CLI](https://github.com/yunbow/ai-dev-os-cli) — Configuración en un solo comando

---

Languages: [English](../../../../getting-started/guideline-vs-multi-agent.md) | [日本語](../../ja/getting-started/guideline-vs-multi-agent.md) | [简体中文](../../zh-CN/getting-started/guideline-vs-multi-agent.md) | [한국어](../../ko/getting-started/guideline-vs-multi-agent.md) | Español
