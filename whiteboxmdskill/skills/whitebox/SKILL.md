---
name: whitebox
description: "Trigger: whitebox, WHITEBOX.md, AI disclosure, session summaries. Create or maintain evidence-grounded living accounts of AI-assisted work and optional session histories."
license: Apache-2.0
metadata:
  author: gentleman-programming
  version: "1.0"
---

## Activation Contract
Use when asked to create or update an AI-use account or session history. `WHITEBOX.md` is a living engineering/AI-work account, not a generic declaration. Default to the overview only. Always name the overview exactly `WHITEBOX.md` (uppercase); never create a lowercase variant. When migrating an existing case variant, preserve content and links; if multiple variants exist, stop for conflict resolution rather than overwrite. Keep this skill/templates in English; write generated content in the requested or target project's language.

## Evidence and attribution gates
- Review the existing account and only relevant, authorized, non-sensitive repository evidence. Keep sources, dates, coverage, and limitations distinct. Never expose secrets, private chats, or raw memory contents/internal IDs by default.
- Inventory what was actually used: harnesses, agents/subagents, models, skills, and MCP servers/tools; describe their use and evidence. Availability is not use. Separate distinct items from invocation counts; memory that mentions use is not complete telemetry. Mark partial scope and unknown counts explicitly—unknown is not zero.
- File-read counts are optional. Include them only with trustworthy read logs, stating unique files versus read events and the logs' scope/coverage. Never infer counts from edits, search hits, memory summaries, or the current tree.
- Before reconstructing history, check the host's existing runtime/tool contracts for callable memory. If available and authorized, consult it for this project and relevant time window; use only relevant records. If unavailable, denied, or no relevant records, report that and continue with repository/log evidence. Never install, configure, or write to memory. Protect privacy: no unrelated records, raw chats, graph dumps, or internal IDs. Distinguish memory-only claims from corroborated facts; retain dates and conflicts. Memory is not complete telemetry.
- The actual participating agent writes each initial or later note as a nontechnical reflection in its own first-person voice. It may explore meaning, questions, images, or conversation themes; it is not another work report and must not list tools, tests, or process. Do not invent events, human feelings or experiences, identities, or models, or speak for another agent. Keep actual-author attribution honest; put factual contributions, evidence, verification, and limitations in their dedicated sections. Add later notes only when materially useful.

## Execution
1. Check existing `WHITEBOX.md` and relevant evidence. If supported, request read-only delegated reconstruction bounded by evidence sources and time/window. Ask delegates for claims, sources, coverage, conflicts, and proposed minimal section changes—not edits. If unavailable, do bounded direct analysis.
2. One writer updates only necessary sections using supported new facts or corrections. Preserve prior content and attribution. If evidence and content are unchanged, make no change: no new dates/notes or reformatting churn.
3. Use `assets/whitebox-template.md`. Keep observed checks separate from reported claims and unknown/not-run items. Verify links and every claim's source/coverage.
4. Create `sessions/` only on explicit opt-in. It complements, never replaces, the overview. Summarize genuine user-agent sessions, not delegated tasks. Use known dates, unique filenames, update matching summaries, and link each one from the overview.
5. Do not create target `WHITEBOX.md` or `sessions/` in this skill package.

## Output Contract
Report mode, changed files or no-op, evidence and coverage, observed versus reported checks, unknowns, limitations, and whether history was explicitly requested. See [overview](assets/whitebox-template.md) and [session](assets/session-template.md) templates.
