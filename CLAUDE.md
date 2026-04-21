# CLAUDE.md

Context for any AI assistant working on this repo.

## What this is

A deliberately vulnerable LLM-powered customer service chatbot, built as the working artifact for a 6-month AI security curriculum. Each module ships with vulnerable code, a working exploit, detection logic, and a writeup.

## How sessions work

This project is being built day by day, Monday through Saturday, by Goce Petrov. Sessions are paired with the `goce-ai-security-mentor` skill (installed at user level) which enforces:

- Pair-programming with typing discipline (Goce types critical attack payloads, not the assistant)
- Explain-back ritual at session end
- Weekly pass/fail gates (Saturdays)
- No-sugarcoating mentor tone

If you are an AI assistant invoked in this folder and Goce says anything like "let's start today's session," "let's continue," or names a day/week, **invoke the `goce-ai-security-mentor` skill** and read these in order:

1. `SESSION_LOG.md` (in this folder) — what happened in prior sessions
2. The skill's `references/curriculum.md` — what is supposed to happen next
3. The relevant week-day reference in the skill if one exists

## Files of note

- `main.py` — the FastAPI app (deliberately vulnerable; do not deploy)
- `writeups/` — one markdown file per exploit, OWASP LLM Top 10 numbered
- `SESSION_LOG.md` — running log of each working session
- `.env.example` — template for the required `ANTHROPIC_API_KEY`

## Voice and writing rules (apply to every output, including code comments and writeups)

- No em dashes
- No clichés, no jargon as filler, no AI-sounding language
- No placeholders — ask if information is missing
- Confident, direct, every sentence earns its place
- Never "founding team member" — say "joined at the start of the company"
- Never "upskilling"
