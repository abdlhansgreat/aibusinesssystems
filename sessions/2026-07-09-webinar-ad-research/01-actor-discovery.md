# 01 — Tool / Actor Discovery

**Date:** 2026-07-09
**Session:** webinar-ad-research

## What we tried

| Tool | Status | Notes |
|---|---|---|
| `mcp__Meta__ads_library_search` (native Meta MCP) | ❌ Blocked this session | Server returned `MCP tool call requires approval` on every call, even after owner approved mid-session. Approval likely applies to *new* sessions only. |
| `mcp__Apify__search-actors` / `call-actor` | ❌ Blocked this session | Same `requires approval` error. Could not search the Apify Store or run any actor. |
| `WebSearch` / `WebFetch` (built-in) | ✅ Working | Used as this session's research engine. |

## Decision for this session

Proceed with **web-research fallback**: mine documented swipe files, ad breakdowns, verbatim ad copy quoted in marketing publications, and public Ad Library viewers via WebSearch/WebFetch. Retry the MCP connectors during the session; if they unlock, layer live Ad Library data on top.

**Trade-off:** we get proven, documented winners (often with full transcripts and performance context), but not fresh "days running" data straight from the Ad Library. Next session should start with live Apify/Meta data.

## Fix for next session (IMPORTANT — do this before starting)

1. On claude.ai → Settings → Connectors: set **Apify** and **Meta** to allow tool calls without per-call approval (or approve when prompted at session start).
2. Verify at session start with one cheap call each: `mcp__Apify__search-actors` (keywords: "Facebook ads library") and `mcp__Meta__ads_library_search` (any keyword, country IN, limit 5).
3. Apify actor candidates to evaluate first (check input schema + pricing with `fetch-actor-details` before running):
   - `curious_coder/facebook-ads-library-scraper` — rich fields incl. video URLs, days running
   - `apify/facebook-ads-scraper`
   - A speech-to-text actor for video ad transcription (search "video transcription" / "whisper")
4. `mcp__Meta__ads_library_search` params that matter: `search_terms`, `countries: ["IN"]` / `["US"]`, `ad_active_status: "ACTIVE"`, `limit` (max 50).
