# AI Dev OS — Guía de Operación

English | [日本語](../ja/operation-guide.md) | [简体中文](../zh-CN/operation-guide.md) | [한국어](../ko/operation-guide.md) | Español

Este documento cubre la operación del **repositorio principal de ai-dev-os** (especificación, teoría, guía de inicio).

Para guías de operación de componentes específicos, consulta:
- **Reglas**: Cada repositorio de reglas tiene su propio `docs/operation-guide.md`
- **Plugins**: Cada repositorio de plugins tiene su propio `docs/operation-guide.md`

---

## 1. Estructura del Repositorio

```
ai-dev-os/
├── spec/                        # Especificación del framework
├── theory/                      # Trasfondo teórico
├── getting-started/             # Guías de inicio
└── docs/                        # Esta guía + i18n
```

Este repositorio contiene **solo la especificación y la teoría** del framework AI Dev OS. Los archivos de directrices reales están en los repositorios de reglas:
- [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript)
- [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python)

---

## 2. Política de Actualización

### 2.1 Cuándo Actualizar

| Sección | Disparador de Actualización | Frecuencia |
|---------|----------------------------|-----------|
| `spec/` | Cambios en el diseño del modelo de 4 capas, nuevos principios de diseño | Muy rara |
| `theory/` | Nuevas conexiones teóricas, referencias de investigación actualizadas | Rara |
| `getting-started/` | Nuevas reglas/plugins agregados, cambios en el ecosistema | Media |
| `docs/` | Mejoras en la guía, nuevas traducciones i18n | Media |

### 2.2 Reglas para Actualizaciones

- **spec/**: Los cambios aquí afectan a todo el ecosistema. Tratar como cambios de versión MAJOR.
- **theory/**: Referencias académicas y análisis teórico. Mantener factual y bien citado.
- **getting-started/**: Debe mantenerse sincronizado con los últimos repositorios de reglas/plugins.
- Al agregar un nuevo repositorio de reglas o plugin, actualizar:
  - `README.md` (tabla del Ecosistema, sección de Inicio Rápido)
  - `getting-started/choose-rules.md` o `getting-started/choose-plugin.md`

---

## 3. Versionado

Gestionado con versionado semántico (etiquetas git).

| Tipo de Cambio | Versión | Ejemplo |
|----------------|---------|--------|
| Cambios fundamentales en la especificación (rediseño del modelo de 4 capas) | MAJOR | v2.0.0 |
| Nuevos documentos teóricos, actualizaciones de getting-started | MINOR | v1.1.0 |
| Correcciones de errores tipográficos, mejoras de redacción | PATCH | v1.0.1 |

---

## 4. Política de Idiomas

- Todo el contenido en este repositorio está escrito en **inglés**
- Las guías de operación multilingües se mantienen en `docs/i18n/` (JA, ZH-CN, KO, ES)
- Las traducciones i18n del README.md están en `docs/i18n/{lang}/README.md`

---

Languages: [English](../../operation-guide.md) | [日本語](../ja/operation-guide.md) | [简体中文](../zh-CN/operation-guide.md) | [한국어](../ko/operation-guide.md) | Español
