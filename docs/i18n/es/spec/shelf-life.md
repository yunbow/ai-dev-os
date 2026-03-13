# Modelo de Vida Útil para Reglas de Codificación IA

## Concepto

Cada capa tiene una "vida útil" — el período esperado antes de que el contenido necesite una revisión significativa.

| Capa | Vida Útil | Analogía |
|------|-----------|----------|
| L1: Filosofía | 2-5 años | Trazado de calles de la ciudad |
| L2: Criterios de Decisión | 1-3 años | Arquitectura del edificio |
| L3: Directrices | 6-12 meses | Diseño de interiores |
| L4: Marcos de IA | 2-4 meses | Disposición de muebles |

## Estrategia de Inversión

Invierte más fuertemente en las capas superiores, porque los errores se propagan hacia abajo:

- **Error en L1** (filosofía equivocada) → catastrófico, casi invisible, afecta todo
- **Error en L2** (principio equivocado) → costoso, difícil de detectar, afecta todo el código
- **Error en L3** (directriz equivocada) → moderado, detectable por revisión, afecta patrones específicos
- **Error en L4** (configuración de herramienta equivocada) → barato, inmediatamente visible, fácil de arreglar

## Detección de Expiración

Usa `git log` para detectar obsolescencia:

```bash
# Verificar la fecha de última actualización para cada capa
git log -1 --format="%ci" -- 01_philosophy/
git log -1 --format="%ci" -- 02_decision-criteria/
git log -1 --format="%ci" -- 03_guidelines/
git log -1 --format="%ci" -- 04_ai-frames/
```

El comando `/ai-dev-os-audit` automatiza esta verificación.

---

Languages: [English](../../../../spec/shelf-life.md) | [日本語](../../ja/spec/shelf-life.md) | [简体中文](../../zh-CN/spec/shelf-life.md) | [한국어](../../ko/spec/shelf-life.md) | Español
