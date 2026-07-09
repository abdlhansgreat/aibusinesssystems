# 99 — Session Summary

**Date:** 2026-07-09
**Session:** webinar-ad-research
**Branch:** `claude/wedding-club-ad-research-3bzjxf`
**Goal:** Research the world's best webinar-invite ads → extract hooks/transcripts → produce 10 Hinglish ad scripts for Indian Wedding Club.

## What was done (step by step)
1. **Scaffolded the whole system** — README, SOP.md v1.0, `memory/`, 4 reusable agents in `.claude/agents/`, `library/` swipe files, and this session folder.
2. **Tool discovery** (`01-actor-discovery.md`) — Apify + Meta MCP connectors both returned `MCP tool call requires approval` and stayed blocked all session. Fell back to WebSearch/WebFetch. (WebFetch was also gateway-blocked at 403; WebSearch snippet-mining did the work.)
3. **Ad hunt** — 3 parallel research agents, 15 ads each = **45 raw ads** into `02-ads-indian-coaching.md`, `02-ads-global-legends.md`, `02-ads-wedding-industry.md`. Every entry source-cited.
4. **Transcripts** (`03-transcripts.md`) — best **25 ads** in the hook-breakdown format (HOOK / PROBLEM / STORY-PROOF / OFFER / CTA + why-it-works).
5. **Hook analysis** (`04-hook-analysis.md`) — 17-type hook taxonomy, the 5-beat winning-ad skeleton, India/Hinglish patterns, and the 12 most stealable hooks adapted for wedding businesses.
6. **Library seeded** — `library/hooks-bank.md` (20 verbatim winners + 12 adapted Hinglish hooks) and `library/frameworks.md` (skeleton + taxonomy + India framework).
7. **Deliverable** (`05-ad-scripts.md`) — **10 ready-to-shoot Hinglish video scripts**, each on a different hook type, with on-screen text + first-frame visual + a testing guide.
8. **Memory + SOP** updated; README sessions table updated.

## Deliverables (links)
- 10 ad scripts → [`05-ad-scripts.md`](05-ad-scripts.md)
- Transcripts → [`03-transcripts.md`](03-transcripts.md)
- Hook analysis → [`04-hook-analysis.md`](04-hook-analysis.md)
- Raw ads → [`02-ads-indian-coaching.md`](02-ads-indian-coaching.md) · [`02-ads-global-legends.md`](02-ads-global-legends.md) · [`02-ads-wedding-industry.md`](02-ads-wedding-industry.md)

## Costs
- **₹0 / $0** — no Apify actor runs (connector blocked); WebSearch only. No paid API spend this session.

## Key learnings
- **MCP connectors need pre-approval.** Apify + Meta must be set to allow-without-approval BEFORE the session, or they block the whole run. This is the #1 fix for next time (see `01-actor-discovery.md`).
- **WebSearch snippet-mining works** as a fallback and recovered real verbatim hooks (Tai Lopez, Kern, Brunson, Ovens, Indian coaches' opening lines) even with WebFetch blocked.
- **The Hinglish trigger-stack** (English punch words + Hindi promise + English CTA verb + करें) is the single most important India pattern — anchor all scripts on it.
- **Video > static** (Jasmine Star data). Shoot talking-head/story video, caption for mute.

## Suggested next session
1. **Fix connectors, then re-run live.** With Apify unblocked, run `curious_coder/facebook-ads-library-scraper` on the exact competitor pages found here (Digital Azadi, Talreja, Dev Gadhvi, Book More Weddings) to get real "days running" data + video URLs, then transcribe the top videos with an STT actor → richer `03-transcripts.md`.
2. **Shoot + launch** 3–4 of the 10 scripts, feed real CTR/CPL back into `memory/MEMORY.md` so the system learns which hooks actually convert for this audience.
3. **Landing-page copy** session — same research → webinar registration page + WhatsApp/email follow-up sequence.
