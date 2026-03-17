# Learnings: Frontend English Localization

## Inherited Patterns
- None found

## Track Learnings

### 1. Backend Regex Patterns Must Be Preserved
Step4Report.vue contains ~42 regex patterns that match Chinese text returned by the backend API (e.g., `分析问题`, `关键事实`, `采访主题`). These were updated to bilingual alternatives `(?:Chinese|English)` to support both languages, but the Chinese patterns cannot be removed without backend changes.

### 2. File-by-file Translation Is More Reliable
Bulk script translation caused issues with special characters (fancy quotes `'`/`'`, fullwidth punctuation). Processing files individually with Python string replacement and immediate verification was more reliable.

### 3. Many Files Were Already in English
Several files in the plan (index.html, App.vue, Home.vue, Step1GraphBuild.vue, all api/*.js except index.js, store/*.js, router/*.js) were already fully in English, reducing actual work scope from 22 files to ~10 files.

### 4. Chinese Text Categories
Frontend Chinese text fell into 4 categories:
- **UI text** (buttons, labels, headings) — must translate
- **Code comments** — should translate
- **Log messages** (addLog/console.warn) — should translate
- **Regex patterns** (for parsing backend responses) — keep with bilingual alternatives

### 5. CSS Comments Contain Chinese
Many `.vue` files had Chinese text in CSS comment blocks (e.g., `/* 响应式 */`). These are easily missed but should be included in the translation scope.

## [2026-03-18 00:09] - REVISION #1
- **Type:** Both (Spec + Plan)
- **Trigger:** Frontend regex patterns in Step4Report.vue needed to stay bilingual because backend generates Chinese output headers
- **Learning:**
  - Gotcha: Frontend localization is incomplete if backend-generated content displayed in the UI is not also localized
  - Pattern: For localization tasks, always trace the data flow end-to-end. If the frontend parses/displays backend-generated content, the backend output formats must be in the localization scope from the start.

### 6. Backend Translation Volume
`zep_tools.py` (1735 lines, 461 Chinese) and `report_agent.py` (2571 lines, 670 Chinese) required multiple batches of `str.replace()` due to the sheer volume. Sorting replacements by length (longest first) prevents partial-match issues.

### 7. LLM Prompt Translation = Report Language
Backend LLM prompts in `report_agent.py` directly control what language generated reports appear in. Translating these prompts means the LLM will produce English-language reports, which is the desired behavior for the English frontend.

## [2026-03-18 00:26] - Track Completion
- **Completed Phases:** 1-5 (all core tasks done)
- **Skipped:** Phase 6 (secondary backend translation — optional, lower priority)
- **Key Results:**
  - 0 Chinese UI text in frontend
  - 55 regex-only lines (bilingual patterns for backward-compat)
  - Backend critical files (`zep_tools.py`, `report_agent.py`) fully translated
  - Build passes: 676 modules, 0 errors
- **Remaining Work:** ~2,500 Chinese lines across 26 backend files (comments, logs, error messages) — can be a separate track
---
