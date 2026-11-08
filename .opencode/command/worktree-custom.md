---
description: Crea un git worktree en .worktrees/ usando el argumento como nombre.
agent: build
---

El usuario quiere crear un git worktree. Argumento recibido:

$ARGUMENTS

Deriva el nombre del worktree a partir de ese argumento: minúsculas, sin acentos,
palabras separadas por guiones (ej. "Mi nueva feature" -> "mi-nueva-feature").
Si el argumento viene vacío, detente y pide un nombre; no ejecutes nada.

Ejecuta únicamente este comando con la herramienta bash, en el directorio actual
(no cambies de directorio):

git worktree add .worktrees/<nombre>

No hagas nada más: no leas archivos, no modifiques archivos, no hagas commits,
no cambies de directorio. Solo ejecuta ese único comando y reporta su salida.
