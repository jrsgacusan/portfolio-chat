# Step-by-step: Move this app to its own repository

Do these in order. Run all commands from your terminal.

---

## 1. Copy your profile data into the scaffold

From the `agents` repo (this workspace), copy your existing `me/` content into the new app folder:

```bash
cp /home/jrsgacusan/coding/agents/1_foundations/me/summary.txt /home/jrsgacusan/coding/agents/me-chat-app/me/
cp /home/jrsgacusan/coding/agents/1_foundations/me/resume.pdf /home/jrsgacusan/coding/agents/me-chat-app/me/
```

(Or copy `me/summary.txt` and `me/resume.pdf` into `me-chat-app/me/` however you prefer.)

---

## 2. Create your `.env` in the new app folder

```bash
cd /home/jrsgacusan/coding/agents/me-chat-app
cp .env.example .env
```

Edit `.env` and set at least:

- `OPENAI_API_KEY` (required)
- Optionally: `PUSHOVER_TOKEN`, `PUSHOVER_USER`, `MY_NAME`

---

## 3. Move the folder out of the `agents` repo (optional but recommended)

So the new app is not inside the agents repo:

```bash
mv /home/jrsgacusan/coding/agents/me-chat-app /home/jrsgacusan/coding/me-chat-app
cd /home/jrsgacusan/coding/me-chat-app
```

If you prefer to keep it inside `agents`, skip this and use `agents/me-chat-app` as the project root in the next steps.

---

## 4. Create a new repository on GitHub (or GitLab, etc.)

- Go to https://github.com/new (or your host).
- Create a new repo, e.g. `me-chat-app`.
- Do **not** add a README, .gitignore, or license (we already have them).

---

## 5. Initialize Git in the app folder and connect the remote

From the app folder (e.g. `/home/jrsgacusan/coding/me-chat-app`):

```bash
git init
git add .
git commit -m "Initial commit: me chat app scaffold"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/me-chat-app.git
git push -u origin main
```

Replace `YOUR_USERNAME` and `me-chat-app` with your actual GitHub username and repo name. Use the SSH URL if you use SSH keys:

```bash
git remote add origin git@github.com:YOUR_USERNAME/me-chat-app.git
```

---

## 6. Verify the app runs

Uses [uv](https://docs.astral.sh/uv/) and the repo’s `.python-version` (3.12):

```bash
uv venv
uv pip install -r requirements.txt
uv run python app.py
```

Open the URL Gradio prints (usually http://127.0.0.1:7860) and chat to confirm it works.

---

## Summary checklist

- [ ] Copy `me/summary.txt` and `me/resume.pdf` into `me-chat-app/me/`
- [ ] Create `.env` from `.env.example` and set `OPENAI_API_KEY`
- [ ] (Optional) Move `me-chat-app` out of the agents repo
- [ ] Create a new empty repo on GitHub/GitLab
- [ ] `git init`, `git add .`, `git commit`, `git remote add origin`, `git push`
- [ ] Run `uv venv`, `uv pip install -r requirements.txt`, `uv run python app.py` and test

Done. The app now lives in its own repository.
