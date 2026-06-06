# Caritas BUILD WITH AI Medellin

Webapp Next.js 16 + React 19 + Tailwind 4 + Supabase (opcional) + IA (opcional). Ver `README.md` para detalles.

## Reglas siempre activas

- **Next.js 16 NO es el Next.js que conoces.** Hay breaking changes respecto a versiones anteriores: APIs, convenciones y estructura de archivos pueden diferir de tu entrenamiento. **Antes de escribir código Next.js**, consulta `node_modules/next/dist/docs/` o usa la skill `/nextjs-docs <tema>`. Respeta deprecation notices.
- **TypeScript estricto**: nada de `any` salvo justificación explícita en comentario.
- **React 19**: preferir Server Components; usa Client Components solo si necesitas estado, efectos o APIs de browser.
- **Tailwind 4**: estilos en clases; evita CSS suelto fuera de `app/globals.css`.
- **Sin nuevas dependencias** sin discutirlo primero (ver `CONTRIBUTING.md`).
- **Secretos**: nunca prefijes service keys con `NEXT_PUBLIC_` (en especial `SUPABASE_SERVICE_ROLE_KEY`).

## Verificación obligatoria antes de commit

`npm run lint` y `npm run build` deben pasar (ver `CONTRIBUTING.md`). Usa la skill `/verify`.

## Skills disponibles

Prefiere invocar estas skills en vez de re-derivar el flujo cada vez:

- `/verify` — corre `npm run lint` + `npm run build`.
- `/review` — revisa el diff actual contra las convenciones del proyecto.
- `/commit [mensaje]` — crea un commit siguiendo el estilo del repo (incluye verify previo).
- `/nextjs-docs <tema>` — busca docs locales de Next.js 16 antes de codear.

## Idioma

Código, comentarios y mensajes de commit: español o inglés, ambos sirven. Docs y READMEs del proyecto en español.
