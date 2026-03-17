# Plan: Frontend English Localization

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

- [ ] Task 1: Run grep to verify zero Chinese characters remain in frontend/src/ (excluding backend regex patterns)
- [ ] Task 2: Run `npm run build` to verify successful build
- [ ] Task 3: Conductor - User Manual Verification 'Frontend English Localization' (Protocol in workflow.md)
