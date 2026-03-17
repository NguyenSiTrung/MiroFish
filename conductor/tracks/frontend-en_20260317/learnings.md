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
