# Plan: Backend Full English Localization

## Phase 1: Frontend-Facing API Files
<!-- execution: parallel -->

Highest user impact — these files send status/error/progress messages directly to the frontend via SSE and HTTP responses.

- [x] Task 1: Translate `app/api/simulation.py` (421 Chinese lines)
  <!-- files: app/api/simulation.py -->
  - [x] Translate all SSE event data strings
  - [x] Translate all status/error/progress messages
  - [x] Translate all log messages
  - [x] Translate all comments and docstrings
  - [x] Verify: `grep -Pc '[\x{4e00}-\x{9fff}]' app/api/simulation.py` returns 0

- [x] Task 2: Translate `app/api/report.py` (149 Chinese lines)
  <!-- files: app/api/report.py -->
  - [x] Translate all report status messages
  - [x] Translate all log messages
  - [x] Translate all comments and docstrings
  - [x] Verify: `grep -Pc '[\x{4e00}-\x{9fff}]' app/api/report.py` returns 0

- [x] Task 3: Translate `app/api/graph.py` (114 Chinese lines)
  <!-- files: app/api/graph.py -->
  - [x] Translate all graph build messages
  - [x] Translate all log messages
  - [x] Translate all comments and docstrings
  - [x] Verify: `grep -Pc '[\x{4e00}-\x{9fff}]' app/api/graph.py` returns 0

- [x] Task 4: Conductor - User Manual Verification 'Phase 1' (Protocol in workflow.md)

## Phase 2: LLM Prompt Files
<!-- execution: parallel -->
<!-- depends: -->

Affects generated content quality — all prompts must produce English output.

- [x] Task 1: Translate `app/services/oasis_profile_generator.py` (315 Chinese lines)
  <!-- files: app/services/oasis_profile_generator.py -->
  - [x] Translate all LLM system prompts to English
  - [x] Translate all LLM user prompts to English
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: `grep -Pc '[\x{4e00}-\x{9fff}]' app/services/oasis_profile_generator.py` returns 0

- [x] Task 2: Translate `app/services/simulation_config_generator.py` (255 Chinese lines)
  <!-- files: app/services/simulation_config_generator.py -->
  - [x] Translate all LLM prompts to English
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: `grep -Pc '[\x{4e00}-\x{9fff}]' app/services/simulation_config_generator.py` returns 0

- [x] Task 3: Translate `app/services/ontology_generator.py` (149 Chinese lines)
  <!-- files: app/services/ontology_generator.py -->
  - [x] Translate all LLM prompts to English
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: `grep -Pc '[\x{4e00}-\x{9fff}]' app/services/ontology_generator.py` returns 0

- [x] Task 4: Conductor - User Manual Verification 'Phase 2' (Protocol in workflow.md)

## Phase 3: Core Services
<!-- execution: parallel -->
<!-- depends: -->

Internal services — logs, lifecycle management, graph operations.

- [x] Task 1: Translate `app/services/simulation_runner.py` (348 Chinese lines)
  <!-- files: app/services/simulation_runner.py -->
  - [x] Translate all internal log messages
  - [x] Translate any LLM prompts within this file
  - [x] Translate all comments and docstrings
  - [x] Verify: zero Chinese characters

- [x] Task 2: Translate `app/services/simulation_manager.py` (91 Chinese lines)
  <!-- files: app/services/simulation_manager.py -->
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: zero Chinese characters

- [x] Task 3: Translate `app/services/graph_builder.py` (79 Chinese lines)
  <!-- files: app/services/graph_builder.py -->
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: zero Chinese characters

- [x] Task 4: Translate `app/services/zep_graph_memory_updater.py` (159 Chinese lines)
  <!-- files: app/services/zep_graph_memory_updater.py -->
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: zero Chinese characters

- [x] Task 5: Translate `app/services/zep_entity_reader.py` (77 Chinese lines)
  <!-- files: app/services/zep_entity_reader.py -->
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: zero Chinese characters

- [x] Task 6: Translate `app/services/simulation_ipc.py` (72 Chinese lines)
  <!-- files: app/services/simulation_ipc.py -->
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: zero Chinese characters

- [x] Task 7: Update `app/services/zep_tools.py` regex patterns (2 Chinese lines)
  <!-- files: app/services/zep_tools.py -->
  - [x] Line 1430: Update regex to bilingual `(?:Question|问题)\d+[：:]\s*`
  - [x] Line 1439: Update `.startswith` to `('{', '问题', 'Question')`
  - [x] Verify: regex patterns match both English and Chinese Agent responses

- [x] Task 8: Translate `app/services/text_processor.py` (17 Chinese lines)
  <!-- files: app/services/text_processor.py -->
  - [x] Translate all log messages, comments, docstrings
  - [x] Verify: zero Chinese characters

- [x] Task 9: Conductor - User Manual Verification 'Phase 3' (Protocol in workflow.md)

## Phase 4: Utilities, Models & Config
<!-- execution: parallel -->
<!-- depends: -->

Lower-level infrastructure files.

- [x] Task 1: Translate `app/models/project.py` (50 Chinese lines)
  <!-- files: app/models/project.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 2: Translate `app/models/task.py` (37 Chinese lines)
  <!-- files: app/models/task.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 3: Translate `app/utils/file_parser.py` (38 Chinese lines)
  <!-- files: app/utils/file_parser.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 4: Translate `app/utils/retry.py` (35 Chinese lines)
  <!-- files: app/utils/retry.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 5: Translate `app/utils/logger.py` (24 Chinese lines)
  <!-- files: app/utils/logger.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 6: Translate `app/utils/llm_client.py` (18 Chinese lines)
  <!-- files: app/utils/llm_client.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 7: Translate `app/utils/zep_paging.py` (6 Chinese lines)
  <!-- files: app/utils/zep_paging.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 8: Translate `app/config.py` (20 Chinese lines)
  <!-- files: app/config.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 9: Translate `app/__init__.py` (19 Chinese lines)
  <!-- files: app/__init__.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 10: Translate `run.py` (12 Chinese lines)
  <!-- files: run.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 11: Translate remaining `__init__.py` files (4 total Chinese lines)
  <!-- files: app/api/__init__.py, app/services/__init__.py, app/models/__init__.py, app/utils/__init__.py -->
  - [x] Translate all comments
  - [x] Verify: zero Chinese characters

- [x] Task 12: Conductor - User Manual Verification 'Phase 4' (Protocol in workflow.md)

## Phase 5: Scripts
<!-- execution: parallel -->
<!-- depends: -->

Standalone scripts — lowest priority, no runtime impact.

- [x] Task 1: Translate `scripts/run_parallel_simulation.py` (306 Chinese lines)
  <!-- files: scripts/run_parallel_simulation.py -->
  - [x] Translate all comments, docstrings, log messages, print statements
  - [x] Verify: zero Chinese characters

- [x] Task 2: Translate `scripts/run_twitter_simulation.py` (152 Chinese lines)
  <!-- files: scripts/run_twitter_simulation.py -->
  - [x] Translate all comments, docstrings, log messages, print statements
  - [x] Verify: zero Chinese characters

- [x] Task 3: Translate `scripts/run_reddit_simulation.py` (130 Chinese lines)
  <!-- files: scripts/run_reddit_simulation.py -->
  - [x] Translate all comments, docstrings, log messages, print statements
  - [x] Verify: zero Chinese characters

- [x] Task 4: Translate `scripts/test_profile_format.py` (35 Chinese lines)
  <!-- files: scripts/test_profile_format.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 5: Translate `scripts/action_logger.py` (34 Chinese lines)
  <!-- files: scripts/action_logger.py -->
  - [x] Translate all comments, docstrings, log messages
  - [x] Verify: zero Chinese characters

- [x] Task 6: Conductor - User Manual Verification 'Phase 5' (Protocol in workflow.md)

## Phase 6: Verification & Final Scan
<!-- execution: sequential -->
<!-- depends: phase1, phase2, phase3, phase4, phase5 -->

Final verification pass.

- [x] Task 1: Full Chinese character scan
  - [x] Run `grep -rPc '[\x{4e00}-\x{9fff}]' backend/` on all `.py` files
  - [x] Fix any remaining Chinese characters found

- [x] Task 2: Build verification
  - [x] Run `cd backend && uv run python run.py` — verify startup without errors

- [x] Task 3: Runtime smoke test
  - [x] Verify frontend-to-backend workflows still function
  - [x] Verify Step4Report.vue regex patterns match backend output

- [x] Task 4: Conductor - User Manual Verification 'Phase 6' (Protocol in workflow.md)
