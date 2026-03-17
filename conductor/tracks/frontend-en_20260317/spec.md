# Spec: Frontend English Localization

## Overview
Replace all hardcoded Chinese text in the frontend with English equivalents. This includes both user-visible UI strings (labels, buttons, messages, placeholders) and code comments. No i18n framework is needed; English becomes the sole UI language.

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
- [ ] Zero Chinese characters remain in any `.vue`, `.js` file under `frontend/src/`
- [ ] Zero Chinese characters remain in `frontend/index.html`
- [ ] The app builds successfully (`npm run build`)
- [ ] All UI workflows render correctly with English text
- [ ] Brand terms (MiroFish, GraphRAG, OASIS, etc.) are preserved as-is

## Out of Scope
- Backend Python code localization
- Adding i18n framework or language switching
- Translating dynamic content returned from APIs
