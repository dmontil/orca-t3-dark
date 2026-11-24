---
name: orca-t3-dark
description: Configura automáticamente la apariencia de Orca en macOS con la estética oscura minimalista de T3 Code (#0a0a0a y sidebar unificado).
---

# Configurar Orca con estética T3 Code Dark

Cuando el usuario pida aplicar el tema oscuro estilo T3 Code a Orca:

1. Localiza el directorio de configuración de Orca en macOS revisando `~/Library/Application Support/` (carpetas que contengan `orca`) y `~/.config/` (por ejemplo `~/.config/orca`).
2. Haz una copia de seguridad (`settings.json.bak` o similar) del archivo de configuración principal antes de modificarlo.
3. Inspecciona las claves existentes en el archivo JSON de configuración (buscando claves relacionadas con `appearance`, `theme`, `colorOverrides`, `leftSidebarAppearance`, `background`, `foreground`, etc.).
4. Actualiza o fusiona (sin borrar proyectos, workspaces ni automations existentes) estos valores:
   - **Sidebar:** `Match Terminal` (o el equivalente booleano/enum en el JSON de `leftSidebarAppearance`).
   - **Base Colors:**
     - `background`: `#0a0a0a`
     - `foreground`: `#ededed`
     - `cursor`: `#ededed`
     - `cursorText`: `#0a0a0a`
     - `selectionBackground`: `#27272a`
     - `selectionForeground`: `#ffffff`
     - `boldText`: `#ffffff`
   - **ANSI Normal:**
     - `black`: `#18181b`, `red`: `#f87171`, `green`: `#4ade80`, `yellow`: `#facc15`
     - `blue`: `#60a5fa`, `magenta`: `#c084fc`, `cyan`: `#22d3ee`, `white`: `#e4e4e7`
   - **ANSI Bright:**
     - `brightBlack`: `#52525b`, `brightRed`: `#fca5a5`, `brightGreen`: `#86efac`, `brightYellow`: `#fde047`
   - **ANSI Bright (cont.):**
     - `brightBlue`: `#93c5fd`, `brightMagenta`: `#d8b4fe`, `brightCyan`: `#67e8f9`, `brightWhite`: `#ffffff`
5. Verifica que el JSON siga siendo válido (`python3 -m json.tool` o `jq`) y avisa al usuario si necesita reiniciar Orca (`Cmd + Q` y volver a abrir) para que recargue la interfaz.
