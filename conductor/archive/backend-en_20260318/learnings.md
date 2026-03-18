# Track Learnings: backend-en_20260318

Patterns, gotchas, and context discovered during implementation.

## Codebase Patterns (Inherited)

### From `conductor/patterns.md`
- Sort string replacements by length (longest first) to prevent partial-match issues
- Code comments and variables should always be in English
- Frontend regex patterns use bilingual `(?:Chinese|English)` alternations to parse backend output
- For localization tasks, always trace data flow end-to-end
- CSS comment blocks in `.vue` files contain Chinese text that is easily missed
- LLM prompt translation in backend directly controls generated report language
- Many files may already be in English — check before translating to reduce scope
- After translation, verify with Python scanning for `[\u4e00-\u9fff]` ranges rather than `grep` for non-ASCII

### From archived `frontend-en_20260317` track
- File-by-file translation with immediate verification is more reliable than bulk scripts
- Bulk script translation caused issues with special characters (fancy quotes, fullwidth punctuation)
- Chinese text categories: comments, logs, LLM prompts, API messages, docstrings — prioritize API messages first
- `zep_tools.py` and `report_agent.py` required multiple batches of `str.replace()` due to volume
- LLM prompt translation = output language change — verify generated content language
- Step4Report.vue contains ~55 bilingual regex patterns that must continue to match after backend translation

---

<!-- Learnings from implementation will be appended below -->
