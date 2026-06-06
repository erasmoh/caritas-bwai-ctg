---
name: commit
description: Crea un commit siguiendo el estilo del repo (chico, descriptivo, lint + build pasando)
argument-hint: "[mensaje opcional]"
allowed-tools:
  - read
  - grep
  - exec
permissions:
  allow:
    - Exec(git status)
    - Exec(git diff)
    - Exec(git log)
    - Exec(git add)
    - Exec(git commit)
    - Exec(npm run lint)
    - Exec(npm run build)
---

Crea un commit siguiendo las convenciones del repo (ver CONTRIBUTING.md).

1. **Inspecciona los cambios en paralelo**:
   - `git status`
   - `git diff` y `git diff --staged`
   - `git log --oneline -10` para matchear el estilo de mensaje del repo

2. **Verifica ANTES de commitear**:
   - `npm run lint`
   - `npm run build`

   Si alguno falla, **NO commitees**. Reporta los errores y detente — el usuario decide si arreglarlos.

3. **Redacta el mensaje** (chico, enfocado en el "por qué", no el "qué"):
   - Español o inglés, ambos sirven.
   - Si el usuario pasó argumentos (`$ARGUMENTS`), úsalos como base del mensaje.
   - Si los cambios cubren múltiples temas independientes, **sugiere commits separados** en vez de uno gigante.
   - Revisa que no haya secretos en el diff antes de commitear.

4. **Stage y commit**:

   ```bash
   git add <archivos relevantes>
   git commit -m "$(cat <<'EOF'
   <mensaje aquí>

   Generated with [Devin](https://cli.devin.ai/docs)

   Co-Authored-By: Devin <158243242+devin-ai-integration[bot]@users.noreply.github.com>
   EOF
   )"
   ```

5. **Si un pre-commit hook modifica archivos** y el commit falla, stage los modificados y reintenta una vez. Si falla otra vez, reporta y detente.

6. **NO pushees** salvo que el usuario lo pida explícitamente.

Al terminar, reporta el SHA y el mensaje del commit creado.
