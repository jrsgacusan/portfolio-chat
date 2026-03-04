# Me Chat App

A small Gradio chat UI that answers as you, using your summary and Resume. Records leads and unknown questions via Pushover (optional).

## Quick start

1. **Copy your profile data** into `me/`:
   - `me/summary.txt`
   - `me/resume.pdf`
2. **Create `.env`** from `.env.example` and set at least `OPENAI_API_KEY`.
3. **Install and run** (uses [uv](https://docs.astral.sh/uv/) and `.python-version`):
   ```bash
   uv sync
   uv run app.py
   ```

See **STEPS.md** for moving this into its own Git repository.
