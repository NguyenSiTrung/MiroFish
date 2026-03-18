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
- **f-string quote collision**: When translating Chinese brackets `「」` to English quotes `"..."`, use single-quoted f-strings (`f'...'`) to avoid Python `SyntaxError` (from: backend-en_20260318, archived 2026-03-18)
- LLM prompt blocks contain long, interconnected text that resists pattern-based replacement — treat them as whole-block translations, not line-by-line (from: backend-en_20260318, archived 2026-03-18)

## Translation Strategy
- For large codebases (700+ lines), use iterative multi-pass dictionary translation with progressively targeted dictionaries rather than one mega-script (from: backend-en_20260318, archived 2026-03-18)

## Testing
- After translation, verify with: `python3 -c "import re; ..."` scanning for `[\u4e00-\u9fff]` ranges rather than `grep` for non-ASCII (grep misses some CJK ranges) (from: frontend-en_20260317, 2026-03-18)
- Always run `python3 -m py_compile <file>` after bulk translation — string replacement can break Python syntax (unbalanced quotes, encoding issues) (from: backend-en_20260318, archived 2026-03-18)

---
Last refreshed: 2026-03-18
