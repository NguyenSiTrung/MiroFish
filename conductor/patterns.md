# Codebase Patterns

Reusable patterns discovered during development. Read this before starting new work.

## Code Conventions
- Sort string replacements by length (longest first) to prevent partial-match issues (from: frontend-en_20260317, 2026-03-18)
- Code comments and variables should always be in English (from: frontend-en_20260317, 2026-03-18)

## Architecture
- Frontend regex patterns use bilingual `(?:Chinese|English)` alternations to parse backend output that may be in either language (from: frontend-en_20260317, 2026-03-18)
- For localization tasks, always trace data flow end-to-end — if frontend parses backend-generated content, backend output formats must be in the localization scope (from: frontend-en_20260317, 2026-03-18)

## Gotchas
- CSS comment blocks in `.vue` files contain Chinese text that is easily missed during translation (from: frontend-en_20260317, 2026-03-18)
- LLM prompt translation in backend directly controls generated report language (from: frontend-en_20260317, 2026-03-18)
- Many files may already be in English — check before translating to reduce scope (from: frontend-en_20260317, 2026-03-18)

## Testing
- After translation, verify with: `python3 -c "import re; ..."` scanning for `[\u4e00-\u9fff]` ranges rather than `grep` for non-ASCII (grep misses some CJK ranges) (from: frontend-en_20260317, 2026-03-18)

---
Last refreshed: 2026-03-18
