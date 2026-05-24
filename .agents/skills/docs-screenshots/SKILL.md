---
name: docs-screenshots
description: Refresh and verify generated EspControl documentation screenshots. Use when the user asks to update, regenerate, automate, refresh, or check docs images for the webserver cards, card examples, settings panel, settings tab, or docs site screenshots.
---

# Docs Screenshots

## Workflow

1. Confirm the workspace is the EspControl repository.
2. Check `git status --short --branch` before starting so unrelated user changes are not mixed into the work.
3. Run:

```bash
node scripts/generate_doc_screenshots.js
```

4. If Playwright reports that Chromium is missing, install only the needed browser, then rerun the generator:

```bash
npx playwright install chromium
```

5. Review the generated image list under `docs/public/images/`. Use `view_image` for important screenshots or changed images where visual quality matters.
6. Run:

```bash
npm run docs:build
```

7. Inspect the diff. The expected outputs are PNG changes in `docs/public/images/` and, when adding new examples, Markdown references in `docs/`.
8. Commit and push only the files belonging to the screenshot refresh, following the repository instruction to work on `main` when possible.

## Notes

- The generator loads the real bundled webserver UI, seeds example card/settings data, and writes PNG files for the docs site.
- Do not run the generator as part of every docs build; it intentionally changes image files and should be an explicit refresh step.
- Do not overwrite or revert unrelated local changes. If unrelated staged files exist, commit with an explicit file list.
