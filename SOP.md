# SOP — Meta Ad Research → Hook Extraction → Ad Script Writing

**Version:** 1.0 (2026-07-09)
**Owner:** Indian Wedding Club
**Purpose:** Repeatable process to research the world's best webinar/masterclass ads, extract their hooks and structures, and produce ready-to-shoot ad scripts that fill our webinar with Indian wedding business owners.

> This is a living document. The **memory-keeper** agent updates it at the end of every session with anything that changed (better actors, better keywords, better formats).

---

## Step 0 — Session setup

1. Read `memory/MEMORY.md` and `memory/preferences.md` before doing anything.
2. Create a new session folder: `sessions/YYYY-MM-DD-<topic>/`.
3. Write `00-session-plan.md`: goal, ad-source categories, target ad counts, deliverable.
4. Commit early, commit often — every step's output is a separate md file and commit.

## Step 1 — Tool / actor discovery → `01-actor-discovery.md`

1. Try the **native Meta MCP tool first**: `ads_library_search` (free, direct Ad Library API).
2. Search Apify Store (`search-actors`) for:
   - "Facebook ads library" (ad scrapers with richer fields: video URLs, run duration)
   - "video transcription" / "video transcript" (for video ad transcripts)
3. For each candidate actor, run `fetch-actor-details` to check **input schema, pricing, rating, success rate** BEFORE running it.
4. Document which tools were chosen, why, and their cost model.

**Known-good tools (see MEMORY.md for updates):** listed in memory after each session.

## Step 2 — Ad hunting → one `02-ads-<category>.md` per category

Agent: **ad-hunter**

Source categories (default three, adjust per session goal):
1. **Indian webinar/coaching ads** — coaches and course-sellers inviting Indian business owners to webinars/masterclasses. Keywords: "free masterclass", "webinar", "business owners", "मास्टरक्लास"; country = IN.
2. **Global webinar-funnel legends** — long-running webinar invite ads worldwide. Keywords: "free training", "webinar", "masterclass", "challenge"; country = US/global.
3. **Wedding-industry B2B** — ads targeting wedding vendors. Keywords: "wedding photographers", "wedding planners", "grow your wedding business".

Rules:
- **Longest-running ads and ads with many versions = proven winners.** Prioritize them.
- Target 20–40 raw ads per category; keep the best 10–15.
- Record for each ad: page name, ad library ID/link, start date (days running), platforms, media type, full primary text, headline, CTA, link.
- Cap Apify item limits (~40/category) to control cost. Record actual spend.

## Step 3 — Transcripts → `03-transcripts.md`

Agent: **transcript-analyst**

For every kept ad, produce an entry in the **hook-breakdown format**:

```
### [N]. <Page name> — "<short label>"
- **Source category:** Indian coaching / Global legend / Wedding B2B
- **Ad Library link:** ...
- **Running since:** ... (X days — winner signal)
- **Media:** video / image / carousel
- **Verbatim transcript / ad copy:**
  > full text here
- **Breakdown:**
  - **HOOK (first 3 sec):** ...
  - **PROBLEM / AGITATION:** ...
  - **STORY / PROOF:** ...
  - **OFFER:** ...
  - **CTA:** ...
- **Why it works:** 2–3 lines.
```

Video ads: transcribe via transcription actor if video URL is available; otherwise use primary text + captions and mark the entry `(copy-only)`.

## Step 4 — Hook analysis → `04-hook-analysis.md`

Agent: **transcript-analyst**

- Build a hook taxonomy from the collected ads (question, callout, contrarian, curiosity-gap, proof-led, pain-led, aspiration, urgency…).
- Identify the anatomy of a winning webinar ad (structure, length, CTA patterns).
- Note India-specific patterns (language mixing, price anchoring in ₹, festival/season references).
- Append the best hooks to `library/hooks-bank.md` and new frameworks to `library/frameworks.md`.

## Step 5 — Script writing → `05-ad-scripts.md`

Agent: **hook-writer**

- Default deliverable: **10 ready-to-shoot video ad scripts** in **Hinglish**.
- Each script: hook type + source inspiration, spoken lines (~45–75 sec), on-screen text suggestions, register-CTA.
- Vary the angles: pain (seasonal income, low-paying clients), aspiration (premium weddings), curiosity, authority, social proof, contrarian.

## Step 6 — Memory + wrap-up

Agent: **memory-keeper**

1. Update `memory/MEMORY.md`: what worked, actor performance, keyword performance, costs, learnings.
2. Update this `SOP.md` if the process changed. Bump version.
3. Write `99-session-summary.md` in the session folder.
4. Update the sessions table in `README.md`.

## Step 7 — Ship

1. Commit all outputs with clear messages.
2. `git push -u origin <session branch>`.
3. Open a **draft PR**, subscribe to PR activity.

---

## Change log

| Version | Date | Change |
|---|---|---|
| 1.0 | 2026-07-09 | Initial SOP created during first webinar-ad-research session. |
