# Revisions: Frontend English Localization

## Revision #1 — 2026-03-18

- **Type:** Both (Spec + Plan)
- **Triggered at:** Phase 4 (Verification) — after discovering backend generates Chinese text parsed by frontend
- **Trigger:** During frontend translation, `Step4Report.vue` retained 42 bilingual regex patterns because backend `zep_tools.py` outputs Chinese headers (`【关键事实】`, `分析问题:`, etc.) and `report_agent.py` sends Chinese LLM prompts. The user decided to extend scope to include critical backend files.

### Changes Made

**Spec changes:**
- Removed "Backend Python code localization" from Out of Scope
- Added new scope: Critical backend files that generate frontend-facing content
- Added acceptance criteria for backend output format

**Plan changes:**
- Added Phase 5: Critical Backend Translation (2 tasks — `zep_tools.py`, `report_agent.py`)
- Added Phase 6: Secondary Backend Translation (API routes, runner, other services) — optional
- Both Phase 5 tasks already completed during this session

### Rationale
The frontend localization is incomplete without translating the backend output formats that the frontend directly parses and displays. Without backend translation, generated reports would still contain Chinese headers and the frontend would need to maintain bilingual regex patterns indefinitely.

### Impact
- +2 phases, +8 tasks added to plan
- Phase 5 (critical) already 100% complete
- Phase 6 (secondary) is optional/lower priority
- Frontend regex patterns in Step4Report.vue can now be simplified (future cleanup task)
