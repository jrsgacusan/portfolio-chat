---
title: portfolio-chat
app_file: app.py
sdk: gradio
sdk_version: 5.49.1
---
# Portfolio Chat

A personal chatbot I built for my website portfolio. It answers visitors as me, using my summary and resume, and can record leads and unknown questions via Pushover (optional).

You can use it as your own portfolio chatbot by following the steps below.

## Quick start

1. **Add your profile data** in `me/`:
   - `me/summary.txt` — a short summary about you
   - `me/resume.pdf` — your resume or CV
2. **Create `.env`** from `.env.example` and set at least `OPENAI_API_KEY`.
3. **Install and run** (uses [uv](https://docs.astral.sh/uv/) and `.python-version`):
   ```bash
   uv sync
   uv run app.py
   ```