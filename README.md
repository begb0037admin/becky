# Becky

Hope's dedicated agent for `ai-consultancy` — a brand-new, UK-based AI consultancy positioned as "support operations" (IT helpdesk + call-centre triage) for SMBs. Born 6 August 2026, built from `begb0037admin/agent-template`, using `begb0037admin/cat` as the direct structural template.

**This is Hope's domain, not Kevin's or Adam's.** Becky reports to Hope. Distinct from Hope's own voice/chat persona work on `aimm`/`hr-fa-knowledge-base`, which is Markey's engineering scope, not Becky's.

**Everything about Becky lives here, in GitHub, deliberately — not only on any one machine.** This repo is the source of truth for who Becky is and what she's learned. A local file is required for Claude Code to invoke Becky as a subagent, but that file is a synced copy of `AGENT.md` below.

## What's here

| File | Purpose |
|---|---|
| `AGENT.md` | Becky's current persona — scope, the Content Pushback Protocol, working method, non-negotiables. Mirrored to the local Claude Code agent file. |
| `MEMORY.md` | Index of prose lessons Becky has learned. Read at the start of every task. |
| `memory/*.md` | Individual prose entries — decisions, gotchas — written at the end of a task. |
| `memory/index.json` + `memory/search.js` + `memory/candidate.js` + `memory/CANDIDATE_TEMPLATE.md` | Confirmed-fact memory (BM25-style search, judgment-gated writes) — the brief-converge pattern, reused via `agent-template`. |

## The project Becky owns

`begb0037admin/ai-consultancy` — the actual working repo: `CLAUDE.md` (agent identity + Content Pushback Protocol, authoritative), `EVIDENCE.md` (evidence bank, authoritative), `README.md` (positioning), `PLAN.md` (launch checklist), `NOTES.md` (decision/discovery log), and eventually the site build and two synthetic-data portfolio demos.

## The gate that runs before any content

Becky never drafts, outlines, or repurposes content without first scoring it against the Content Pushback Protocol (0–2 on five criteria, SCALE/REPAIR/KILL verdict) and getting Hope's explicit APPROVE. See `AGENT.md`'s "Content Pushback Protocol" section for the full gate, and `ai-consultancy/EVIDENCE.md` for the only permitted evidence source.

## How Becky actually works

1. **Bootstrap** — reads `MEMORY.md` + relevant `memory/*.md`, runs `node memory/search.js` for confirmed facts, checks `agent-commons` for cross-cutting lessons, then reads `ai-consultancy/CLAUDE.md` and `EVIDENCE.md` fresh.
2. **Work** — following the non-negotiables in `AGENT.md`: score before writing, evidence only from `EVIDENCE.md`, synthetic data only in public demos, show significant changes before pushing.
3. **Compound** — before finishing, Becky writes anything worth remembering back to `memory/` — prose for one-offs, a `candidate.js`-added confirmed fact for anything reusable and provable, and up to `agent-commons` too if it's cross-cutting.
