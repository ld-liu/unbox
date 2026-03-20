---
name: Project Alpha — Current State
description: Primary project — where things stand, what's next, what's blocked
type: project
---

## Core Goal
Build a research tool that goes beyond surface-level data. Everything else — framework, modules, architecture — serves this goal and is subject to change.

## Current Focus
Building data source modules. Retrieval layer (semantic search over notes) is ready. What's missing are data source tools that don't exist yet.

**Build order:**
1. Options data module — options chain, delta tracking, key metrics (free API)
2. Short interest module — short interest % float, days to cover (free, public data)
3. SEC filings — institutional holdings, key financial sections
4. Earnings transcripts — management guidance, tone shifts

## Open Questions
- Signal rankings are drafts — need user review before driving automation
- Some data sources have no confirmed free API yet
- Some trigger conditions are qualitative — need specific thresholds

## What's in the Files
- Strategy docs: `~/projects/alpha/` (thesis.md / playbook.md / signals.md / TODO.md)
- Build backlog: `~/projects/alpha/TODO.md`
