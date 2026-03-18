# Spec: Backend Full English Localization

## Overview
Translate ALL remaining Chinese text across the entire backend Python codebase to English.
This is the direct continuation of the archived `frontend-en` track (conductor/archive/frontend-en_20260317/),
which completed frontend localization and critical backend files (zep_tools.py, report_agent.py) but skipped
Phase 6 (secondary backend files). The goal is zero Chinese characters across the backend, enabling future
simplification of the frontend's 55 bilingual regex patterns in Step4Report.vue.

## Functional Requirements
1. All Python comments must be in English
2. All log messages (`logger.info/warning/error`, `print()`) must be in English
3. All docstrings and function documentation must be in English
4. All LLM prompts (system prompts, user prompts) must produce English output
5. All API response messages (status, error, progress) sent to the frontend must be in English
6. All SSE event data strings must be in English
7. All exception/error messages must be in English
8. The 2 regex-only Chinese lines in `zep_tools.py` (lines 1430, 1439) must be updated to match bilingual patterns (English primary, Chinese fallback)

## Non-Functional Requirements
- No new Python dependencies
- Existing API contracts must not break (endpoint URLs, response structure, status codes)
- Frontend bilingual regex patterns in Step4Report.vue must continue to work (match English alternatives)
- LLM prompt translations must preserve the original intent and produce domain-accurate English output
- Build and runtime behavior must remain identical
- File-by-file translation with immediate verification (per inherited learnings)

## Scope — File Inventory (33 files, ~3,150 Chinese lines)

| Priority | File | Chinese Lines | Category |
|----------|------|--------------|----------|
| P1 | `app/api/simulation.py` | 421 | API — SSE events, status/error messages |
| P1 | `app/api/report.py` | 149 | API — report status messages |
| P1 | `app/api/graph.py` | 114 | API — graph build messages |
| P2 | `app/services/oasis_profile_generator.py` | 315 | LLM profile generation prompts |
| P2 | `app/services/simulation_config_generator.py` | 255 | LLM config prompts |
| P2 | `app/services/ontology_generator.py` | 149 | LLM ontology prompts |
| P3 | `app/services/simulation_runner.py` | 348 | Internal logs, LLM prompts |
| P3 | `app/services/simulation_manager.py` | 91 | Simulation lifecycle |
| P3 | `app/services/graph_builder.py` | 79 | Graph construction |
| P3 | `app/services/zep_graph_memory_updater.py` | 159 | Graph memory operations |
| P3 | `app/services/zep_entity_reader.py` | 77 | Entity extraction |
| P3 | `app/services/simulation_ipc.py` | 72 | Inter-process communication |
| P3 | `app/services/zep_tools.py` | 2 | Regex-only (update to bilingual) |
| P3 | `app/services/text_processor.py` | 17 | Text processing |
| P4 | `app/models/project.py` | 50 | Data models |
| P4 | `app/models/task.py` | 37 | Task models |
| P4 | `app/utils/file_parser.py` | 38 | File parsing |
| P4 | `app/utils/retry.py` | 35 | Retry logic |
| P4 | `app/utils/logger.py` | 24 | Logging config |
| P4 | `app/utils/llm_client.py` | 18 | LLM client wrapper |
| P4 | `app/utils/zep_paging.py` | 6 | Zep pagination |
| P4 | `app/config.py` | 20 | App configuration |
| P4 | `app/__init__.py` | 19 | Flask app factory |
| P4 | `run.py` | 12 | App entry point |
| P4 | 4 × `__init__.py` | 4 total | Init files |
| P5 | `scripts/run_parallel_simulation.py` | 306 | Standalone simulation |
| P5 | `scripts/run_twitter_simulation.py` | 152 | Twitter simulation |
| P5 | `scripts/run_reddit_simulation.py` | 130 | Reddit simulation |
| P5 | `scripts/test_profile_format.py` | 35 | Test fixture |
| P5 | `scripts/action_logger.py` | 34 | Action logging |

## Acceptance Criteria
- [ ] Zero Chinese characters in any `.py` file under `backend/` (verified by `grep -rPc '[\x{4e00}-\x{9fff}]'`)
- [ ] `uv run python run.py` starts without errors
- [ ] Frontend-to-backend workflows (graph build → simulation → report → interaction) remain functional
- [ ] Frontend Step4Report.vue regex patterns successfully match backend output
- [ ] All LLM prompts produce English-language output
- [ ] zep_tools.py regex patterns updated to bilingual (Question/问题) for backward compatibility

## Out of Scope
- Frontend regex simplification (remove Chinese alternatives) — future track
- Frontend UI changes
- New features or API changes
- Test writing (translation-only scope)
