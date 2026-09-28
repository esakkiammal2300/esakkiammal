# FitBuddy – AI Fitness Plan Generator

Complete implementation based on the supplied FitBuddy documentation: FastAPI backend, Jinja2 frontend, Gemini AI integration, SQLite/SQLAlchemy persistence, feedback-based plan updates, and an admin-style user view.

## Setup in VS Code (Windows)
1. Install Python 3.11+ and open this folder in VS Code.
2. Terminal: `python -m venv .venv`
3. Activate: `.venv\Scripts\activate`
4. Install: `pip install -r requirements.txt`
5. Copy `.env.example` to `.env` and set `GEMINI_API_KEY`.
6. Run: `uvicorn app.main:app --reload`
7. Open http://127.0.0.1:8000 and http://127.0.0.1:8000/docs
8. Test: `pytest -q`

## Structure
app/main.py, routes.py, database.py, schemas.py, config.py, gemini_client.py, gemini_generator.py, gemini_flash_generator.py, updated_plan.py; templates/base.html, index.html, result.html, all_users.html, error.html; static/style.css; tests/test_app.py.

## Model configuration
The source document specifies Gemini 1.5 Pro and Gemini Flash. Model availability changes, so this implementation uses the current `google-genai` SDK and configurable model IDs in `.env`. Change `GEMINI_WORKOUT_MODEL` and `GEMINI_FLASH_MODEL` if your API project exposes different models.

## Scope
Generated content is general wellness information, not medical diagnosis or treatment. The prompts explicitly avoid unsafe exercise, extreme dieting, and unsupported medical claims.
