# Teorías Clásicas de Ingeniería de Software

## Descripción General

El modelo de 4 capas de AI Dev OS no es una invención nueva — se mapea a patrones observados en 15 teorías establecidas de ingeniería de software que abarcan 50 años.

## Nivel 1: Similitud Estructural Directa

### Clean Architecture (Robert C. Martin, 2012/2017)

| AI Dev OS | Clean Architecture | Estabilidad |
|-----------|-------------------|-------------|
| L1: Filosofía | Entidades (Reglas de Negocio) | Más alta |
| L2: Criterios de Decisión | Casos de Uso (Reglas de Aplicación) | Alta |
| L3: Directrices | Adaptadores de Interfaz | Media |
| L4: Marcos de IA | Frameworks y Drivers | Más baja |

**Idea clave**: La regla de dependencia — las dependencias del código fuente deben apuntar hacia adentro.

### Lenguajes de Patrones (Christopher Alexander, 1977)

| AI Dev OS | Lenguaje de Patrones | Escala |
|-----------|---------------------|--------|
| L1: Filosofía | "Calidad Sin Nombre" | Ciudad |
| L2: Criterios de Decisión | Patrones a gran escala | Distrito |
| L3: Directrices | Patrones a mediana escala | Edificio |
| L4: Marcos de IA | Patrones a pequeña escala | Materiales |

**Idea clave**: Los patrones más grandes tienen mayor duración. Los patrones abstractos generan los concretos.

### Modelo SECI (Nonaka & Takeuchi, 1995)

| AI Dev OS | SECI | Flujo de Conocimiento |
|-----------|------|----------------------|
| L1: Filosofía | Socialización | Tácito → Tácito |
| L2: Criterios de Decisión | Externalización | Tácito → Explícito |
| L3: Directrices | Combinación | Explícito → Explícito |
| L4: Marcos de IA | Internalización | Explícito → Tácito |

**Idea clave**: La creación de conocimiento es una espiral, no lineal. La práctica retroalimenta la filosofía.

### Manifiesto Ágil (2001)

| AI Dev OS | Ágil | Tasa de Cambio |
|-----------|------|----------------|
| L1: Filosofía | 4 Valores Fundamentales | Casi inmutable |
| L2: Criterios de Decisión | 12 Principios | Baja |
| L3: Directrices | Prácticas Scrum/XP/Kanban | Media |
| L4: Marcos de IA | Flujos de Jira, Configuración CI/CD | Alta |

**Idea clave**: Advertencia de culto cargo — copiar L3-L4 sin entender L1-L2 lleva al fracaso.

## Nivel 2: Similitud Estructural Parcial

| Teoría | Contribución Clave a AI Dev OS |
|--------|-------------------------------|
| **Diseño Guiado por el Dominio** (Evans, 2003) | Bounded Context → Directrices con alcance por dominio |
| **Framework de Zachman** (1987) | Cada capa es cualitativamente diferente, no solo más detallada |
| **Líneas de Producto de Software** (CMU SEI, 2001) | Activos centrales vs. activos específicos del producto; puntos de variación |
| **TOGAF** (The Open Group, 1995) | Gobernanza: quién puede cambiar qué capa |
| **Architecture Decision Records** (Nygard, 2011) | Registrar la justificación, no solo las decisiones; seguimiento de sustituciones |
| **Patrones de Diseño GoF** (1994) | 30 años de evidencia: los patrones abstractos sobreviven a los concretos |

## Las 6 Leyes Transversales

El análisis de las 15 teorías revela 6 leyes universales:

| # | Ley | Teorías Fuente |
|---|-----|----------------|
| 1 | **Regla de Dependencia** — Las capas superiores no deben referenciar a las inferiores | Clean Architecture, Lenguajes de Patrones |
| 2 | **Vida útil = Abstracción** — Las cosas abstractas viven más tiempo | Clean Architecture, GoF, Alexander, Zachman |
| 3 | **No Saltar Capas** — La madurez es secuencial | CMMI, Ágil (culto cargo), Craftsmanship |
| 4 | **Diferencia Cualitativa** — Las capas difieren en tipo, no en grado | Zachman, ISO 42010, Kruchten |
| 5 | **Retroalimentación en Espiral** — La práctica debe retroalimentar la filosofía | SECI, Alexander |
| 6 | **Trazabilidad = Generatividad** — Los vínculos explícitos entre capas permiten la inferencia en situaciones nuevas | Lenguajes de Patrones, ADR, GoF |

## Referencias

- Alexander, C. (1977). *A Pattern Language*. Oxford University Press.
- Beck, K. et al. (2001). "Manifesto for Agile Software Development."
- Evans, E. (2003). *Domain-Driven Design*. Addison-Wesley.
- Gamma, E. et al. (1994). *Design Patterns*. Addison-Wesley.
- Martin, R.C. (2017). *Clean Architecture*. Prentice Hall.
- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Zachman, J. (1987). "A Framework for Information Systems Architecture." *IBM Systems Journal*, 26(3).

---

Languages: [English](../../../../theory/classical-theories.md) | [日本語](../../ja/theory/classical-theories.md) | [简体中文](../../zh-CN/theory/classical-theories.md) | [한국어](../../ko/theory/classical-theories.md) | Español
