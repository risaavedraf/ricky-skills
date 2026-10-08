# Whitebox

**Make AI-assisted work transparent—with evidence, not just a disclosure.**

Whitebox is an agent skill for creating and maintaining a living `WHITEBOX.md`: an account of how humans and AI worked on a project, which tools contributed, what was verified, and what remains uncertain.

[Skill instructions](skills/whitebox/SKILL.md) · [Overview template](skills/whitebox/assets/whitebox-template.md) · [Session template](skills/whitebox/assets/session-template.md)

> **Not white-box testing.** Here, Whitebox means transparency about AI-assisted work. A chronology or a high tool count does not, by itself, prove engineering quality.

## What it records

- **Contributions and decisions:** human, AI, shared, or unknown responsibilities; decisions and their rationale.
- **Actual tool use:** harnesses, agents/subagents, identified models, skills, and MCP servers/tools—plus how they contributed.
- **Evidence and verification:** observed checks versus reported results, sources, coverage, limitations, and unresolved conflicts.
- **Agent notes:** an initial reflection by the actual participating agent; later notes only when useful. Keep notes nontechnical reflections on meaning, questions, images, or conversation themes—not another work report—and separate them from factual evidence. Preserve authorship without impersonation or invented human feelings/experiences.
- **Optional session history:** concise summaries of genuine sessions, linked from the overview.

## Quick start

1. Make the complete [`skills/whitebox/`](skills/whitebox/) folder available to your agent runtime, including its `assets/` directory.
2. Load or reference [`SKILL.md`](skills/whitebox/SKILL.md) through your runtime's supported mechanism.
3. Request an initial account, a targeted update, or explicitly opt into session history using the examples below.

**Copying files does not automatically install or register the skill.** Discovery and loading depend on your runtime.

The skill and templates are written in English. Generated accounts follow the requested language or the target project's convention.

## Choose the output

| Mode | Result in the target project |
| --- | --- |
| **Create an overview** | Create `WHITEBOX.md` with evidence, contributions, and an actual-author agent note. No `sessions/` directory. |
| **Update an existing account** | Revise only sections supported by relevant new facts or corrections; preserve existing content, history, and attribution. |
| **Add session history** | On explicit request, add useful summaries under `sessions/` and link them from `WHITEBOX.md`. |

> **No new information, no edit.** An update must not change dates, add notes, or reformat the account merely because another session occurred.

### Example target-project layout

```text
project/
├── WHITEBOX.md
└── sessions/                      # Only when explicitly requested
    ├── YYYY-MM-DD-architecture.md
    └── YYYY-MM-DD-verification.md
```

Session filenames use known dates. Existing matching summaries are updated rather than duplicated; distinct sessions with the same date and topic receive a unique suffix. Delegated tasks are not automatically treated as separate human sessions.

## Example requests

### Create the initial account

```text
Use the Whitebox skill to create this project's WHITEBOX.md.
Consult the available, authorized memory and relevant repository evidence.
Explain human and AI contributions, decisions, actually used harnesses,
agents, models, skills, and MCP tools. State evidence coverage and unknowns.
Write a nontechnical reflection in your own voice about meaning, questions, images, or themes in the conversation. Keep role, attribution, evidence, and verification in their sections; do not report tools, tests, or process, impersonate another agent, or invent human feelings/experiences.
Do not create session history.
```

### Update only what matters

```text
Use the Whitebox skill to review the existing WHITEBOX.md against new evidence.
Consult available, authorized memory for this project and period.
Preserve existing content and agent attribution; change only sections supported
by material new facts or corrections. If nothing relevant changed, make no edit.
```

### Include session summaries

```text
Use the Whitebox skill to update WHITEBOX.md and include session history
for [specified period]. Create useful summaries of genuine sessions only,
use known dates, avoid duplicates, and link the summaries from the overview.
Keep private conversations and sensitive data out of the documents.
```

## Memory and reconstruction

Before reconstructing work, the agent checks which memory tools are callable and authorized in its runtime. It must consult relevant records when accessible, bounded to the project and time window—not search unrelated histories or dump an entire memory store.

Examples of memory systems include:

- **Engram** — use its available runtime tools and access rules.
- **[MCP Knowledge Graph Memory Server](https://github.com/modelcontextprotocol/servers/tree/main/src/memory)** (`@modelcontextprotocol/server-memory`) — persistent memory backed by a local knowledge graph.

These are examples, **not prerequisites or claims of installation or use**. Whitebox does not require a particular provider or authorize installing, configuring, or writing to memory.

If memory is unavailable, access is denied, or no relevant records exist, report that limitation and continue with accessible repository/log evidence. Separate historical, memory-only claims from facts corroborated in the current repository; retain meaningful dates, conflicts, and coverage limits.

When subagents are available, reconstruction can be delegated as a **bounded, read-only analysis**. The delegate returns claims, sources, coverage, conflicts, and proposed section changes; one writer applies only supported updates.

## Evidence and privacy safeguards

| Safeguard | Rule |
| --- | --- |
| **Used ≠ available** | Report observed tool use, not every capability listed in the runtime. |
| **Counts need context** | Separate distinct items from invocations: two recorded calls to one tool are one distinct tool and two invocations. State the scope and completeness. |
| **Unknown ≠ zero** | Missing records must not become invented counts, model identities, dates, or results. |
| **File-read metrics are optional** | Require trustworthy read logs; distinguish unique files from read events and state coverage. Do not infer reads from edits, search hits, memory summaries, or the current tree. |
| **Memory is not telemetry** | Historical summaries can inform the account but do not establish complete usage totals. |
| **Notes have authors** | Keep notes nontechnical reflections, not work reports. Preserve actual attribution; do not impersonate another agent or invent human feelings/experiences. Keep factual evidence in its own sections. |
| **Private data stays private** | Exclude secrets, raw chats, graph dumps, internal memory IDs, and unnecessary personal data. |

## Skill contents

```text
skills/whitebox/
├── SKILL.md
└── assets/
    ├── whitebox-template.md
    └── session-template.md
```

Copy the complete folder when adding this skill to your own collection. The templates support the runtime instructions; they are not fabricated examples of completed work.

**This repository contains the skill, not a target project's generated account or session history.**
