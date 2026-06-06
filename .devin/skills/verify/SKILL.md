---
name: verify
description: Corre lint + build (requerido por CONTRIBUTING.md antes de cualquier commit)
allowed-tools:
  - read
  - exec
permissions:
  allow:
    - Exec(npm run lint)
    - Exec(npm run build)
---

Corre la verificación obligatoria del proyecto antes de commit:

1. `npm run lint` — no silencies errores con reglas salvo que esté justificado y comentado.
2. `npm run build` — corrige errores de tipo o build.

Ambos deben pasar. Si alguno falla:

- Reporta el paso que falló y el error específico (archivo:línea).
- NO marques la tarea como completada hasta que ambos pasen.
- Sugiere la corrección mínima, no rediseñes a menos que el usuario lo pida.

Si todo pasa, reporta `lint OK` y `build OK` con el tiempo aproximado.
