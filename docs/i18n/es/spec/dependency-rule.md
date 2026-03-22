# Regla de Dependencia para Reglas de Codificación IA

## Principio

> Las capas superiores nunca deben referenciar a las capas inferiores.

Esto está tomado directamente de la regla de dependencia de Clean Architecture de Robert C. Martin y de la jerarquía de lenguajes de patrones de Christopher Alexander.

## Reglas por Capa

### L1: Filosofía

- NO DEBE contener: nombres de herramientas, nombres de frameworks, nombres de librerías, nombres de APIs
- NO DEBE contener: ejemplos de código en ningún lenguaje específico
- PUEDE contener: conceptos abstractos, valores, marcos de pensamiento

### L2: Criterios de Decisión

- NO DEBE contener: detalles de implementación específicos de frameworks
- NO DEBE contener: referencias específicas a APIs de librerías
- PUEDE contener: paradigmas de lenguaje (OOP, FP), patrones generales (MVC, CQRS)

### L3: Directrices

- NO DEBE contener: configuraciones específicas de herramientas (formato de CLAUDE.md, sintaxis de .cursorrules)
- PUEDE contener: nombres de frameworks, nombres de librerías, ejemplos de código

### L4: Marcos de IA

- PUEDE contener: cualquier cosa específica de herramientas
- DEBERÍA referenciar: directrices L3 como la fuente de verdad

## Detección de Violaciones

El comando `/ai-dev-os-audit` verifica violaciones de dependencia escaneando:

- Archivos L1 en busca de términos de herramientas/frameworks
- Archivos L2 en busca de detalles de implementación

Los hooks del plugin también proporcionan advertencias en tiempo real al editar archivos L1-L2.

---

Languages: [English](../../../../spec/dependency-rule.md) | [日本語](../../ja/spec/dependency-rule.md) | [简体中文](../../zh-CN/spec/dependency-rule.md) | [한국어](../../ko/spec/dependency-rule.md) | Español
