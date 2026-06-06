---
name: nextjs-docs
description: Busca docs locales de Next.js 16 en node_modules/next/dist/docs/ antes de escribir código Next.js
argument-hint: "<tema>"
allowed-tools:
  - read
  - grep
  - glob
---

Esta versión (Next.js 16.2.4) tiene **breaking changes** respecto a versiones anteriores. APIs, convenciones y estructura pueden diferir de lo que viste en entrenamiento. **Nunca asumas** — consulta los docs locales antes de codear.

Tema a buscar: **$ARGUMENTS**

Pasos:

1. **Descubre archivos relevantes**:
   - `glob` en `node_modules/next/dist/docs/**/*$ARGUMENTS*` (y variantes razonables del nombre).
   - Si no aparece por nombre, `grep` el término en `node_modules/next/dist/docs/**/*.{md,mdx}`.

2. **Lee los archivos más relevantes** (máx. 3-5).

3. **Reporta**:
   - **API actual en Next 16** — firma, parámetros, tipos.
   - **Breaking changes / deprecations** marcados explícitamente.
   - **Ejemplo mínimo** de uso (copia del doc oficial si existe).
   - **Archivos consultados** con su ruta para que el usuario pueda profundizar.

4. **Si no hay doc sobre el tema**: dilo claramente. **No inventes APIs.** Sugiere buscar en el código fuente (`node_modules/next/dist/`) o en la web oficial como fallback.
