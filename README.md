# AI Business Systems — Indian Wedding Club

This repo is the operating system for **Indian Wedding Club's** AI-powered marketing research. It holds repeatable processes (SOPs), reusable agents, evolving memory, and every session's outputs — so each session builds on the last instead of starting from zero.

## What lives where

| Path | Purpose |
|---|---|
| [`SOP.md`](SOP.md) | The master process doc. How to run an ad-research session end to end. Updated after every session. |
| [`memory/MEMORY.md`](memory/MEMORY.md) | Evolving memory: what worked, what didn't, costs, learnings. Read this first in every new session. |
| [`memory/preferences.md`](memory/preferences.md) | Durable user preferences (language, formats, style). |
| [`.claude/agents/`](.claude/agents/) | Reusable Claude Code subagents: ad-hunter, transcript-analyst, hook-writer, memory-keeper. |
| [`library/hooks-bank.md`](library/hooks-bank.md) | Cross-session swipe file of proven hooks, categorized by type. |
| [`library/frameworks.md`](library/frameworks.md) | Ad frameworks and webinar-ad anatomy observed in research. |
| [`sessions/`](sessions/) | One folder per research session, all outputs as numbered md files. |

## How to run a new session

1. Open a Claude Code session on this repo.
2. Say: **"Read SOP.md and memory/MEMORY.md, then run the SOP for [goal]."**
3. Claude creates a new `sessions/YYYY-MM-DD-<topic>/` folder and works through the SOP steps, saving every step's output as a numbered md file.
4. At the end, the memory-keeper agent updates `MEMORY.md`, `SOP.md`, and the `library/` files.

## Sessions

| Date | Session | Deliverable |
|---|---|---|
| 2026-07-09 | [webinar-ad-research](sessions/2026-07-09-webinar-ad-research/) | Ad research library + 10 Hinglish webinar-invite ad scripts |
