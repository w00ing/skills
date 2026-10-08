---
name: codex-imagegen
description: Generate or edit raster images (illustrations, icons, sprites, photos, mockups) by delegating to the local Codex CLI's built-in image tool. Use whenever a task needs a bitmap asset the current agent cannot draw itself.
---

# Codex image generation

Agents without an image model can borrow the one in the Codex CLI. Run `codex exec` non-interactively and send the prompt on **stdin**:

```text
Generate one image with your built-in image generation tool. Do not write code to draw it. <prompt> Copy the PNG to <path relative to the working directory> and reply with just its path.
```

```bash
# POSIX shells
printf '%s' "$PROMPT" | codex exec --approve-for-me [-i reference.png ...]
```

```powershell
# PowerShell
$Prompt | codex exec --approve-for-me [-i reference.png ...]
```

- Before the first call, confirm `codex` is installed and signed in (`codex --version`). If it is missing, tell the user instead of improvising another image path.
- Call the real Codex binary. An alias or wrapper that adds `--remote` breaks it, because `codex exec` rejects that flag. Resolve the binary's own path if one shadows it.
- `-i` takes several files and consumes a trailing prompt argument, which is why the prompt goes on stdin. To edit an image, attach it with `-i` and say what to keep unchanged.
- Each call takes about 1–3 minutes. Run independent images in parallel.
- Outputs are opaque RGB. For a transparent asset, ask for a flat `#FF00FF` background with no magenta in the subject, then key it out with Codex's bundled script: `python <CODEX_HOME>/skills/.system/imagegen/scripts/remove_chroma_key.py --input in.png --out out.png --key-color '#ff00ff' --soft-matte --despill`.
- `CODEX_HOME` is the `CODEX_HOME` environment variable, or `.codex` in the user's home directory when it is unset. Generated files also land in `<CODEX_HOME>/generated_images/<session>/`.
- Look at every result before using it. For prompt structure, see `<CODEX_HOME>/skills/.system/imagegen/references/prompting.md`.
