# My Claude Skills
Personal AI skill library built on top of [gstack](https://github.com/garrytan/gstack) 
and Claude Code.
## What this is
A collection of custom slash commands I designed and built to automate 
repetitive workflow-specific tasks — starting with company research before meetings.
## Skills
### \/company-brief\
Produces a structured intelligence brief on any company before a meeting.
**Usage:**
/company-brief {company website} --meeting "recruiting call with co-founder"
/company-brief {company website} --quick        # Phase 1 only, 90 seconds
/company-brief {company website} --update       # re-run, show what changed
**What it produces:**
- Phase 1 — Company overview, founders, funding, runway, risks
- Phase 2 — Client persona, workflow, where the product fits
- Phase 3 — Competitive landscape
**Design decisions:**
- Source discipline: Tier 1/2 sources labeled confirmed, everything else 
  explicitly marked "Educated guess"
- URL-derived slugs for deterministic \--update\ lookups
- Controlled tag vocabulary so the index stays queryable over time
- Parallel searches within each phase (~2 min saved per brief)
- Phase-by-phase disk saves in case of failure mid-run
Briefs saved to \~/research-briefs/{slug}/{date}.md\ with a master 
\index.json\ for search.
## Stack
- [Claude Code](https://claude.ai/code) — AI that operates the terminal
- [gstack](https://github.com/garrytan/gstack) — slash command framework
- [gbrain](https://github.com/garrytan/gbrain) — personal knowledge base (in progress)
## Status
Active. WIP.