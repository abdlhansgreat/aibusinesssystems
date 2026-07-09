# MEMORY — Evolving Knowledge Base

> Read this file at the start of EVERY session. The memory-keeper agent appends learnings at the end of every session. Never delete past learnings — mark them superseded instead.

## Business context

- **Business:** Indian Wedding Club — a masterclass/webinar teaching Indian wedding businesses (photographers, planners, decorators, makeup artists, caterers, venue owners) how to grow.
- **Funnel:** Meta ads → webinar registration → masterclass → (backend offer).
- **Audience:** Indian wedding vendors/business owners. They think in ₹, wedding seasons (Nov–Feb, Apr–May peaks), referral-driven business, Instagram-led marketing.
- **Owner email:** connect@wpbmastery.in

## Tooling knowledge

_(Updated per session — actor names, what they cost, what worked.)_

- **Apify MCP** (`mcp__Apify__*`) — 2026-07-09: BLOCKED all session with `MCP tool call requires approval`, even after the user approved mid-session. **Must be pre-approved in claude.ai → Settings → Connectors before the session starts.** Never got to run an actor. Cost so far: ₹0.
- **Meta MCP** (`mcp__Meta__ads_library_search`) — 2026-07-09: BLOCKED, same `requires approval` error. This is the FREE first-choice tool when it works (direct Ad Library API; params: `search_terms`, `countries:["IN"]`, `ad_active_status:"ACTIVE"`, `limit` max 50). Requires the caller to have ≥1 active ad account.
- **WebSearch** (built-in) — 2026-07-09: WORKED, was the whole session's engine. Snippet-mining `site:facebook.com "<name>" webinar/masterclass` recovered verbatim ad opening lines + duplicate-creative winner signals.
- **WebFetch** (built-in) — 2026-07-09: BLOCKED (gateway 403 on nearly every domain incl. archive.org, swiped.co, facebook.com). Do not rely on it in this environment; use WebSearch snippets instead.
- **Apify actor candidates to try once unblocked:** `curious_coder/facebook-ads-library-scraper` (video URLs + days running), `apify/facebook-ads-scraper`, plus an STT/whisper actor for video transcription. Always `fetch-actor-details` for schema+pricing before running; cap items ~40/run.

## Keyword performance

_(Which ad-library search keywords surfaced the best ads.)_

- 2026-07-09 (via WebSearch, not Ad Library): highest-yield pattern = `site:facebook.com "<advertiser name>" webinar` / `masterclass videos` — exposes verbatim title + first ~140 chars of creative. Exact-phrase searches of a known hook (e.g. "Join our paid workshop FREE", "eLearning is HOT") surface duplicate creatives = winner signal.
- Advertisers with rich documented copy: Siddharth Rajsekar, Rajiv Talreja, Dev Gadhvi, GrowthSchool/Vaibhav Sisinty, Saurabh Bhatnagar, Digital Azadi (India); Sam Ovens, Russell Brunson, Frank Kern, Billy Gene, Mindvalley, Hormozi, Tai Lopez (global); Katelyn James, Book More Weddings Summit, Steven de Cuba, WedMeGood (wedding B2B).
- Dead ends: Sandeep Maheshwari (no paid webinar ads — free model), Hindi-only "फ्री मास्टरक्लास" ads (poorly indexed), Iman Gadzhi / Foundr (no quoted copy in snippets).

## Reusable insight (research → scripts)

- **Winning webinar-ad skeleton:** HOOK(0-3s) → ONE sharp pain → story OR proof-number → free/₹99 offer w/ numbered curriculum → CTA + scarcity. See `library/frameworks.md`.
- **Hinglish trigger-stack:** English punch words (FREE/LIVE/WEBINAR) + Hindi promise (और हिंदी में/क्या सीखोगे) + English CTA verb + करें. THE key India pattern.
- **India credibility currency:** lakhs of people + cities/states, and ₹99 tripwires with no-questions refund. Not $.
- **Video > static** for webinar ads (Jasmine Star case study). Caption for mute; first 3 sec = 80% of the battle.

## Learnings log

_(Newest first. Format: date — learning.)_

- 2026-07-09 — Delivered 10 Hinglish ad scripts from 45 researched ads (25 transcribed). Repo is its own default branch (started empty) so no PR target exists — work ships directly to the branch. See `sessions/2026-07-09-webinar-ad-research/99-session-summary.md`.
- 2026-07-09 — Biggest blocker: Apify + Meta MCP connectors require pre-session approval or they hard-block. Fix before next session.
- 2026-07-09 — System initialized. First session: webinar ad research across 3 categories (Indian coaching, global webinar legends, wedding B2B).
