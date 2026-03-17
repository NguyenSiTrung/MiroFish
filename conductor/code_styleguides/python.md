# Python Style Guide (Backend)

## Conventions (inferred from codebase)

- Follow PEP 8 naming: `snake_case` for functions/variables, `PascalCase` for classes
- Use docstrings (triple-quoted) for modules and public functions
- Comments in Chinese are acceptable for inline code comments (existing pattern)
- Use type hints where practical (Pydantic models enforce this)
- Flask app factory pattern (`create_app()`) is the standard entry point
- Blueprint-based API organization under `app/api/`
- Service layer pattern: business logic in `app/services/`, utilities in `app/utils/`
- Configuration via `app/config.py` using environment variables (python-dotenv)
- Use `uv` for dependency management, not pip directly
- Logging via custom `setup_logger`/`get_logger` utilities
