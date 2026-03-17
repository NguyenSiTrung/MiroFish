# Plan: Frontend English Localization

> **Last Revised:** 2026-03-18 — Revision #1 (added Phase 5 & 6 for backend)

## Phase 1: Core Pages & Components Translation

- [x] Task 1: Translate `frontend/index.html` (meta description, title)
- [x] Task 2: Translate `frontend/src/App.vue` (CSS comments)
- [x] Task 3: Translate `frontend/src/views/Home.vue` (hero text, status labels, step descriptions, navigation)
- [x] Task 4: Translate `frontend/src/views/Process.vue` (graph panel, build flow, status messages, project info, comments)
- [x] Task 5: Translate `frontend/src/views/MainView.vue` (step names, mode labels, log messages, comments)
- [x] Task 6: Translate `frontend/src/views/SimulationView.vue` (mode labels, step name, log messages, comments)
- [x] Task 7: Translate `frontend/src/views/SimulationRunView.vue` (mode labels, step name, log messages, comments)
- [x] Task 8: Translate `frontend/src/views/ReportView.vue` (mode labels, step name, log messages, comments)
- [x] Task 9: Translate `frontend/src/views/InteractionView.vue` (mode labels, step name, log messages, comments)

## Phase 2: Step Components Translation

- [x] Task 1: Translate `frontend/src/components/Step1GraphBuild.vue` (phase labels, badges, descriptions, button text, comments)
- [x] Task 2: Translate `frontend/src/components/Step2EnvSetup.vue` (step titles, badges, descriptions, stat labels, profile text, comments)
- [x] Task 3: Translate `frontend/src/components/Step3Simulation.vue` (action labels, button text, status messages, comments)
- [x] Task 4: Translate `frontend/src/components/Step4Report.vue` (tab labels, panel titles, status text, tool descriptions, markdown processing comments, render functions) — *NOTE: retains Chinese regex patterns for parsing backend responses (bilingual CN|EN alternatives)*
- [x] Task 5: Translate `frontend/src/components/Step5Interaction.vue` (chat UI, survey UI, tool descriptions, profile cards, comments)
- [x] Task 6: Translate `frontend/src/components/GraphPanel.vue` (toolbar, legend, status messages, comments)
- [x] Task 7: Translate `frontend/src/components/HistoryDatabase.vue` (card labels, modal content, status text, comments)

## Phase 3: Utility & Support Files Translation

- [x] Task 1: Translate `frontend/src/store/pendingUpload.js` (comments) — already in English
- [x] Task 2: Translate `frontend/src/api/graph.js` (JSDoc comments) — already in English
- [x] Task 3: Translate `frontend/src/api/report.js` (JSDoc comments) — already in English
- [x] Task 4: Translate `frontend/src/api/simulation.js` (comments if any) — already in English
- [x] Task 5: Translate `frontend/src/api/index.js` (comments)
- [x] Task 6: Translate `frontend/src/router/index.js` (comments if any) — already in English

## Phase 4: Verification

- [x] Task 1: Run grep to verify zero Chinese characters remain in frontend/src/ (excluding backend regex patterns) — ✅ 42 regex-only lines in Step4Report.vue, 0 UI text lines
- [x] Task 2: Run `npm run build` to verify successful build — ✅ 676 modules, 0 errors
- [ ] Task 3: Conductor - User Manual Verification 'Frontend English Localization' (Protocol in workflow.md)

## Phase 5: Critical Backend Translation *(Added in Revision #1)*

- [x] Task 1: Translate `backend/app/services/zep_tools.py` — Tool output format headers (`【関键事実】` → `[Key Facts]`, etc.), docstrings, log messages (461 → 2 regex-only lines remaining)
- [x] Task 2: Translate `backend/app/services/report_agent.py` — LLM prompts, tool descriptions, ReACT loop messages, ReportManager docstrings (670 → 0 lines remaining)

## Phase 6: Secondary Backend Translation *(Optional — Added in Revision #1)*

- [ ] Task 1: Translate `backend/app/api/simulation.py` (~487 lines — status/error messages to frontend)
- [ ] Task 2: Translate `backend/app/api/report.py` (~149 lines — report status messages)
- [ ] Task 3: Translate `backend/app/services/simulation_runner.py` (~348 lines — internal log messages)
- [ ] Task 4: Translate `backend/app/services/oasis_profile_generator.py` (~315 lines — LLM prompts)
- [ ] Task 5: Translate `backend/app/services/simulation_config_generator.py` (~255 lines — config prompts)
- [ ] Task 6: Translate remaining backend files (~1,500+ lines — comments, utilities, configs)
