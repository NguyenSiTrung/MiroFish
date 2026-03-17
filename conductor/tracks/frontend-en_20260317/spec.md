# Spec: Frontend English Localization

> **Last Revised:** 2026-03-18 — Revision #1 (scope expanded to include critical backend files)

## Overview
Replace all hardcoded Chinese text in the frontend with English equivalents. This includes both user-visible UI strings (labels, buttons, messages, placeholders) and code comments. No i18n framework is needed; English becomes the sole UI language.

Additionally, translate critical backend files whose output is directly parsed/displayed by the frontend (tool output format headers, LLM prompts for report generation, etc.).

## Functional Requirements
1. All user-facing UI text (labels, buttons, tooltips, placeholders, status messages, error messages) must be in English
2. All JavaScript/Vue code comments must be translated to English
3. All CSS comments must be translated to English
4. Log messages visible in the UI (addLog calls) must be in English
5. Console-facing messages (console.log/error) must be in English

## Non-Functional Requirements
- No new dependencies (no vue-i18n or locale files)
- Existing functionality must not be affected
- Translations must be contextually accurate for the MiroFish domain (swarm intelligence, simulation, agents, graphs)

## Acceptance Criteria
- [x] Zero Chinese characters remain in any `.vue`, `.js` file under `frontend/src/` (excluding backend-parsing regex patterns)
- [x] Zero Chinese characters remain in `frontend/index.html`
- [x] The app builds successfully (`npm run build`)
- [x] All UI workflows render correctly with English text
- [x] Brand terms (MiroFish, GraphRAG, OASIS, etc.) are preserved as-is
- [x] Backend tool output formats use English headers (`zep_tools.py`)
- [x] Backend LLM prompts generate English-format reports (`report_agent.py`)

## Out of Scope
- Full backend Python code localization (only critical frontend-facing files are in scope)
- Adding i18n framework or language switching
- Translating dynamic content returned from APIs (beyond format headers)
- Secondary backend files (API routes, simulation runner, utilities) — lower priority, separate track
