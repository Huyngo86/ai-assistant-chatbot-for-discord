# AIO Assistant for Discord

A Python Discord assistant for course meetings and learning. It supports meeting and lecture summaries, context-aware questions, and references to slides and transcripts.

## Features

- Summarizes meeting transcripts from Fireflies.ai, with AssemblyAI transcription support.
- Summarizes lecture videos from supported URLs and Google Drive sources.
- Combines transcripts, PDF slides, and uploaded chat history to answer questions in context.
- Adds slide references, extracts links from learning materials, and renders LaTeX formulas.
- Uses Gemini as the primary model with GLM support, plus caching for video, transcript, slide, and summary stages.

## Structure

- `src/cogs/` contains the meeting, lecture, ask, and system command modules.
- `src/services/` contains the model integrations, transcription, video handling, storage, scheduling, and caches.
- `src/utils/` contains shared document and Discord helpers.

## Setup

The archive includes a pinned `requirements.txt` and uses Playwright for browser-based transcript handling:

```bash
python -m pip install -r requirements.txt
playwright install chromium
```

Create a local `.env` from `.env.example`, then set the Discord bot token and any required provider credentials. Provider keys can also be configured through the bot's configuration commands. Keep `.env` out of version control and never commit API keys.

Start the bot with:

```bash
python src/main.py
```

## Security and reuse

The original archive included a development script, `test_fireflies.py`, containing a credential-like value, and a course slide PDF. Neither file is included in this public repository. If the credential was real, rotate it. No license file was present in the archive; add one if you want others to reuse the project.

