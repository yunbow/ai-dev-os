# Guía de Migración de Herramientas

## Descripción General

El modelo de 4 capas de AI Dev OS garantiza que **el 75% de tu inversión (L1-L3)** sobreviva a las migraciones de herramientas. Solo **L4 (25%)** — el plugin — necesita cambiar.

## Pasos de Migración

### De Claude Code a Kiro

1. **Mantener**: submódulo `docs/ai-dev-os/` (reglas L1-L3) — no se necesitan cambios
2. **Eliminar**: submódulo `.claude/plugins/ai-dev-os/`
3. **Agregar**: plugin de Kiro
   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-kiro.git .kiro/plugins/ai-dev-os
   cp -r .kiro/plugins/ai-dev-os/steering/ .kiro/steering/
   cp -r .kiro/plugins/ai-dev-os/hooks/ .kiro/hooks/
   ```
4. **Convertir**: CLAUDE.md → AGENTS.md (mismo contenido, Kiro lee AGENTS.md)
   ```bash
   cp CLAUDE.md AGENTS.md
   ```
5. **Verificar**: Ejecutar `#ai-dev-os-init` en Kiro para confirmar la configuración

### De Claude Code a Cursor

1. **Mantener**: submódulo `docs/ai-dev-os/` — no se necesitan cambios
2. **Eliminar**: submódulo `.claude/plugins/ai-dev-os/`
3. **Agregar**: plugin de Cursor
   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
   cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/
   ```
4. **Convertir**: CLAUDE.md → .cursorrules
   ```bash
   cp CLAUDE.md .cursorrules
   ```
5. **Verificar**: Ejecutar `@ai-dev-os-init` en Cursor para confirmar la configuración

### De Kiro a Claude Code

1. **Mantener**: submódulo `docs/ai-dev-os/` — no se necesitan cambios
2. **Eliminar**: archivos `.kiro/steering/ai-dev-os-*` y hooks
3. **Agregar**: plugin de Claude Code
   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```
4. **Convertir**: AGENTS.md → CLAUDE.md
   ```bash
   cp AGENTS.md CLAUDE.md
   ```
5. **Verificar**: Ejecutar `/ai-dev-os-init`

### De Cursor a Claude Code

1. **Mantener**: submódulo `docs/ai-dev-os/` — no se necesitan cambios
2. **Eliminar**: archivos `.cursor/rules/ai-dev-os-*`
3. **Agregar**: plugin de Claude Code
   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```
4. **Convertir**: .cursorrules → CLAUDE.md
   ```bash
   cp .cursorrules CLAUDE.md
   ```
5. **Verificar**: Ejecutar `/ai-dev-os-init`

## Qué Se Transfiere (75%)

| Capa | Contenido | ¿Se transfiere? |
|------|-----------|-----------------|
| L1: Filosofía | `01_philosophy/` | ✅ 100% — sin cambios |
| L2: Criterios de Decisión | `02_decision-criteria/` | ✅ 100% — sin cambios |
| L3: Directrices | `03_guidelines/` | ✅ 100% — sin cambios |
| L4: Marcos de IA | Específico del plugin | ❌ Reemplazar con nuevo plugin |
| Archivo de contexto | CLAUDE.md / AGENTS.md / .cursorrules | ⚠️ Copiar y renombrar |

## Qué NO Se Transfiere

- Configuración de hooks específica del plugin
- Sintaxis de invocación de skills específica de la herramienta (`/` vs `#` vs `@`)
- Integraciones de CI/CD que referencian comandos de herramientas específicas

---

Languages: [English](../../../../getting-started/migration.md) | [日本語](../../ja/getting-started/migration.md) | [简体中文](../../zh-CN/getting-started/migration.md) | [한국어](../../ko/getting-started/migration.md) | Español
