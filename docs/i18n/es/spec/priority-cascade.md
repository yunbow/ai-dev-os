# Specificity Cascade — AI Coding Rules

## Analogía con la Especificidad CSS

AI Dev OS resuelve conflictos de reglas usando una cascada de prioridad inspirada en la especificidad CSS:

```
1. [Más alta]  frameworks/[stack]/*   ← Más específica
2. [Alta]      common/*               ← Común pero concreta
3. [Media]     project-specific/*     ← Contexto del proyecto
4. [Baja]      02_decision-criteria/* ← Criterios abstractos
5. [Más baja]  01_philosophy/*        ← Más abstracta
```

> **Nota**: `project-specific/*` se refiere a directrices en el proyecto del usuario (ej., `docs/guidelines/billing.md`), NO en el repositorio de reglas. El repositorio de reglas contiene solo `frameworks/` y `common/`. Las directrices específicas del proyecto son creadas por el usuario para lógica de dominio, integraciones externas, requisitos legales, etc.

## Cómo Funciona

1. Al codificar, la IA primero busca reglas **específicas del framework** (más específicas)
2. Si no existe una regla de framework, recurre a las reglas **comunes**
3. Si no existe una regla común, recurre a las convenciones **específicas del proyecto**
4. Si no existe nada explícito, aplica **criterios de decisión** para razonar sobre el mejor enfoque
5. Como último recurso, recurre a la **filosofía** para un juicio basado en valores

## Ejemplo: Manejo de Errores

Supongamos que la IA se encuentra con una decisión de manejo de errores en un Server Action de Next.js:

1. **frameworks/nextjs/server-actions.md** dice "Usar patrón ActionResult<T>" → **Aplicar esto**
2. **common/error-handling.md** dice "Clasificar errores en usuario/sistema/validación" → También aplicar
3. **02_decision-criteria/error-strategy.md** dice "Preferir tipos de error explícitos sobre excepciones" → Informa el enfoque
4. **01_philosophy/principles.md** dice "Corrección sobre conveniencia" → Valor subyacente

Todas las capas contribuyen, pero la regla más específica gana cuando hay un conflicto.

---

Languages: [English](../../../../spec/priority-cascade.md) | [日本語](../../ja/spec/priority-cascade.md) | [简体中文](../../zh-CN/spec/priority-cascade.md) | [한국어](../../ko/spec/priority-cascade.md) | Español
