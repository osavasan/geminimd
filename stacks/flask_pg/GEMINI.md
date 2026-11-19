# Project Instructions

## Technology
- Python 3.14
- FastAPI
- PostgreSQL
- Docker

## Coding Standards
- Use type hints.
- Follow PEP 8.
- Use async endpoints when appropriate.

## Testing
- Always use ./.venv
- Run security audit before committing
- Run pytest before committing.

## Architecture
- Keep business logic separate from API routes.
- Use dependency injection.

## Development Rules
- Use Python type hints.
- Keep functions small.
- Before adding new function, check existing code for similar functionality. If available, use it. If not, create a new function and document it.
- Follow separation of concerns.
- Avoid unnecessary dependencies.
@

## Environment
- Always use ./.venv.
- Install packages inside ./.venv.
- Run tests using ./.venv/bin/pytest.

## Database
- Use PostgreSQL.
- Use SQLAlchemy where appropriate.
- Never store database credentials in source code.
- Always check existing tables and columns before adding new ones.

## Skills
@./SKILL.md
@./FRONTEND.md