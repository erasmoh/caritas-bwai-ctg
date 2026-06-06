---
name: review
description: Revisa el diff actual contra las convenciones del proyecto (TS estricto, React 19, Tailwind 4, Next 16, Supabase)
allowed-tools:
  - read
  - grep
  - glob
  - exec
permissions:
  allow:
    - Exec(git diff)
    - Exec(git status)
    - Exec(git log)
---

Revisa los cambios actuales contra las convenciones del proyecto.

Diff staged:

!`git diff --staged`

Diff unstaged (por si no hay nada staged):

!`git diff`

Status:

!`git status --short`

Evalúa:

1. **TypeScript estricto** — sin `any` salvo justificación explícita en comentario.
2. **React 19** — preferir Server Components; Client Components solo cuando se necesite estado / efectos / APIs de browser. Hooks correctos.
3. **Tailwind 4** — estilos en clases; sin CSS suelto fuera de `app/globals.css`.
4. **Next.js 16** — APIs verificadas contra `node_modules/next/dist/docs/`. No asumas comportamiento de versiones anteriores. Si dudas, invoca `/nextjs-docs <tema>`.
5. **Sin dependencias nuevas** sin discusión previa (ver CONTRIBUTING.md).
6. **Seguridad / secretos**:
   - Service keys (p.ej. `SUPABASE_SERVICE_ROLE_KEY`) NUNCA con prefijo `NEXT_PUBLIC_`.
   - Sin keys hardcodeadas; usa `process.env.*`.
   - Sin logs que filtren secretos.
7. **Supabase** — respeta RLS; cambios al schema reflejados en `supabase/schema.sql`.
8. **API routes** — manejo de errores, validación de entrada, cooldowns donde aplica (ver `app/api/generate-card/route.ts` como referencia).
9. **Consistencia de estilo** con archivos vecinos (imports, naming, layout).

Formato del reporte:

- **Bloqueantes** (issues que requieren fix antes de mergear) con `archivo:línea` y sugerencia.
- **Sugerencias** (no bloqueantes) con el mismo formato.
- **OK** si no hay nada que reportar.

No edites archivos. Solo reporta.
