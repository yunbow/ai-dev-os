# Tacit-to-Explicit Engineering（Ingeniería de Tácito a Explícito）

## El Problema Central

> El código generado por IA es "casi correcto pero sutilmente erróneo" — el 66% de los desarrolladores lo citan como su mayor frustración.

La causa raíz no es una ingeniería de prompts insuficiente ni modelos de IA deficientes. Es que **el conocimiento tácito de los desarrolladores senior no se ha convertido en reglas explícitas y aplicables**.

## ¿Qué es el Conocimiento Tácito?

El conocimiento tácito (暗黙知) es conocimiento difícil de articular:

- "Este código no se siente bien" → ¿Qué regla específica se está violando?
- "Aquí no hacemos las cosas así" → ¿Dónde está documentada "esa forma"?
- "Cualquier ingeniero senior sabría esto" → Pero la IA no es un ingeniero senior

## La Conexión con el Modelo SECI

AI Dev OS se mapea directamente al modelo SECI de creación de conocimiento de Ikujiro Nonaka (1995):

| Fase SECI | Capa de AI Dev OS | Flujo de Conocimiento |
|-----------|-------------------|----------------------|
| Socialización (共同化) | L1: Filosofía | Tácito → Tácito: Compartido a través de la experiencia |
| Externalización (表出化) | L2: Criterios de Decisión | Tácito → Explícito: Articulado como principios |
| Combinación (連結化) | L3: Directrices | Explícito → Explícito: Organizado en reglas |
| Internalización (内面化) | L4: Marcos de IA | Explícito → Tácito: Incorporado a través de la práctica |

La idea clave: **AI Dev OS es un sistema de creación de conocimiento, no solo una jerarquía de documentación.**

## La Espiral

El modelo SECI es una espiral, no un proceso unidireccional:

```
L4 práctica → descubre nuevo conocimiento tácito → L1 evoluciona
     ↑                                              ↓
     └──── L3 reglas ← L2 principios ← L1 valores ──┘
```

El comando `/ai-dev-os-evolve` implementa esta espiral analizando las prácticas de codificación recientes y proponiendo actualizaciones a L1-L2.

## Por Qué Esto Importa

Sin reglas explícitas:
- La IA genera código que **parece correcto pero viola las normas del equipo**
- La revisión de código se convierte en una **sesión de enseñanza repetida** para los mismos problemas
- El conocimiento **se va cuando las personas se van** — la IA nunca lo aprendió

Con AI Dev OS:
- El conocimiento tácito se captura como reglas explícitas, versionadas y aplicables
- La IA **mejora con cada revisión de código** (mediante Rule Harvesting)
- El conocimiento **sobrevive a los cambios de equipo** y las migraciones de herramientas

## Referencias

- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Nonaka, I. & Konno, N. (1998). "The Concept of 'Ba'." *California Management Review*, 40(3).

---

Languages: [English](../../../../theory/tacit-to-explicit.md) | [日本語](../../ja/theory/tacit-to-explicit.md) | [简体中文](../../zh-CN/theory/tacit-to-explicit.md) | [한국어](../../ko/theory/tacit-to-explicit.md) | Español
