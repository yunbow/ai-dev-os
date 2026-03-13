# Guía de Inicio Rápido

## Forma Más Rápida: CLI

```bash
# Interactivo — solicita idioma y herramienta
npx ai-dev-os init

# O especificar directamente:
npx ai-dev-os init --rules typescript --plugin claude-code
npx ai-dev-os init --rules python --plugin kiro
npx ai-dev-os init --rules typescript --plugin cursor
```

> Agrega submódulos, copia plantillas y fusiona hooks en un solo comando.
> Consulta [AI Dev OS CLI](https://github.com/yunbow/ai-dev-os-cli) para todas las opciones.

---

## Configuración Manual

### Elige Tus Reglas de Lenguaje

| Lenguaje | Repositorio | Comando |
|---|---|---|
| TypeScript / Next.js | [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os` |
| Python / FastAPI | [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os` |

## Elige Tu Plugin de Herramienta

| Herramienta | Repositorio | Configuración |
|---|---|---|
| Claude Code | [ai-dev-os-plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | `git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os` |
| Kiro | [ai-dev-os-plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Copiar reglas de dirección a `.kiro/steering/` |
| Cursor | [ai-dev-os-plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Copiar reglas a `.cursor/rules/` |

## Ejemplo: TypeScript + Claude Code

```bash
cd /path/to/your-project

# 1. Agregar reglas
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. Agregar plugin
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. Configurar CLAUDE.md
cp docs/ai-dev-os/templates/nextjs/CLAUDE.md.template ./CLAUDE.md

# 4. Ejecutar asistente de configuración (escribir en el chat de Claude Code, no en la terminal)
# /ai-dev-os-init
```

## Ejemplo: Python + Claude Code

```bash
cd /path/to/your-project

# 1. Agregar reglas
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. Agregar plugin
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. Configurar CLAUDE.md
cp docs/ai-dev-os/templates/python-cli/CLAUDE.md.template ./CLAUDE.md

# 4. Ejecutar asistente de configuración (escribir en el chat de Claude Code, no en la terminal)
# /ai-dev-os-init
```

## Ejemplo: Python + Kiro

```bash
cd /path/to/your-project

# 1. Agregar reglas
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. Agregar plugin
git clone https://github.com/yunbow/ai-dev-os-plugin-kiro.git
cp -r ai-dev-os-plugin-kiro/steering/ .kiro/steering/
cp -r ai-dev-os-plugin-kiro/hooks/ .kiro/hooks/
rm -rf ai-dev-os-plugin-kiro  # Limpiar directorio clonado

# 3. Ejecutar asistente de configuración (escribir en el chat de Kiro, no en la terminal)
# #ai-dev-os-init
```

## Ejemplo: TypeScript + Cursor

```bash
cd /path/to/your-project

# 1. Agregar reglas
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. Agregar plugin
git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/

# 3. Ejecutar asistente de configuración (escribir en el chat de Cursor, no en la terminal)
# @ai-dev-os-init
```

## Actualizar Reglas

```bash
git submodule update --remote docs/ai-dev-os
```

## Fijar a una Versión Específica

```bash
cd docs/ai-dev-os
git checkout v1.2.0
cd ../..
git add docs/ai-dev-os
git commit -m "chore: pin ai-dev-os to v1.2.0"
```

## Solución de Problemas con Submódulos

| Problema | Solución |
|----------|----------|
| Directorio `docs/ai-dev-os/` vacío después de `git clone` | Ejecutar `git submodule update --init --recursive` |
| El submódulo muestra `(not initialized)` | Ejecutar `git submodule init && git submodule update` |
| El pipeline de CI falla con archivos faltantes | Agregar `git submodule update --init --recursive` al paso de configuración de CI |
| Quieres siempre clonar con submódulos | Usar `git clone --recurse-submodules <url>` |
| El submódulo apunta a un commit antiguo | Ejecutar `git submodule update --remote docs/ai-dev-os` para obtener lo último |

---

Languages: [English](../../../../getting-started/quick-start.md) | [日本語](../../ja/getting-started/quick-start.md) | [简体中文](../../zh-CN/getting-started/quick-start.md) | [한국어](../../ko/getting-started/quick-start.md) | Español
