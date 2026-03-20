---
name: Tool Sync Rules
description: After changing any tool config, sync updates to secondary AI assistant's memory
type: feedback
---

After any skill or tool change, update the secondary AI assistant's memory for consistency:
1. Assistant's index file
2. Tool reference docs
3. Lessons learned / known pitfalls

These files must not contradict each other or contain stale info.

**Why:** Secondary assistant has its own memory, completely separate from the primary AI's. Without explicit sync, it will use outdated references or repeat known mistakes.

**How to apply:** Any time a skill is added/modified/deleted, or a tool interface changes, check and update all related files before closing the session.
