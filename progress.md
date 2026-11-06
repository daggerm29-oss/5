# HELIX — Development Progress

> **Read this first.** This file is the single source of truth for what is actually implemented. `plan.md` is the product spec, and `architecture.md` is the technical blueprint. A status of **Verified** means an automated or manual check proved the acceptance criteria. Written code alone is at most **Implemented**.

## Project Status

- Project: Helix
- Current Phase: M0 — Engineering Foundations
- Overall Completion: ~2% (M0 just started; M1–M6 not started)
- Current Status: In Progress
- Last Updated: 2026-11-06
- Current Development Branch: `helix/m0-foundations`

## Phase Overview

| Phase | Name | Status | Completion |
|---|---|---|---|
| M0 | Engineering Foundations | In Progress | 5% |
| M1 | Core MVP | Not Started | 0% |
| M2 | Advanced Intelligence | Not Started | 0% |
| M3 | Multi-Agent Intelligence | Not Started | 0% |
| M4 | Team and Ecosystem | Not Started | 0% |
| M5 | Platform Expansion | Not Started | 0% |
| M6 | Collaboration | Not Started | 0% |

## Current Phase Details

**Objectives (plan §12 M0):** monorepo + build, Helix Engine process (JSON-RPC over WebSocket/stdio), event bus, SQLite storage, Gemini and OpenAI API-key adapters + conformance suite, local sandbox v0 (no masking), tool framework (fs, shell, search-exact), CLI `helix -p`, ledger v0, OpenTelemetry spans.

**Exit criteria:** (1) the CLI agent fixes a seeded failing test in 3 fixture repos inside the sandbox; (2) ledger totals reconcile with provider-reported usage; (3) an Engine restart resumes a task.

- Completed tasks: progress.md initialized; architecture/plan reviewed.
- In progress: monorepo scaffolding.
- Remaining: everything else in M0 (see Next Actions).
- Known issues: none yet.
- Dependencies: Node 24 (built-in `node:sqlite`, TypeScript type stripping), pnpm 12.
- Blockers: none yet. Environment notes: no Docker/Podman preinstalled in the dev VM; unprivileged user namespaces available; no provider API keys configured yet.

## Feature Implementation Tracker

Statuses: Not Started / In Progress / Implemented / Tested / Verified / Blocked / Deferred.

| Feature ID | Feature | Status | Tests | Notes |
|---|---|---|---|---|
| F-MDL-1 | Provider adapter framework | In Progress | — | M0 scope. Arch §7.1, §7.2, §31.3 |
| F-MDL-2 | Gemini integration | In Progress | — | M0 scope. Arch §7.3 |
| F-MDL-3 | OpenAI integration (API key + Sign in with ChatGPT) | In Progress | — | M0 scope. Arch §7.4, §8.2 |
| F-MDL-4 | Role-based model configuration | Not Started | — | Arch §7.5 |
| F-MDL-5 | Automatic model router + fallback | Not Started | — | Arch §7.6, §29.5 |
| F-AUTH-1 | Secure credential vault | In Progress | — | M0 scope. Arch §8.1, §8.3, §25.9 |
| F-AUTH-2 | OAuth broker | Not Started | — | Arch §8.2 |
| F-AUTH-3 | Helix account and org SSO | Not Started | — | Arch §8.5 |
| F-IDX-1 | Incremental parser and symbol index | Not Started | — | Arch §11.1–11.3, §12.1, §12.4 |
| F-IDX-2 | Precise references (SCIP/LSP) | Not Started | — | Arch §11.4 |
| F-IDX-3 | Code graph | Not Started | — | Arch §11.5 |
| F-IDX-4 | Hybrid retrieval engine | Not Started | — | Arch §11.6 |
| F-IDX-5 | Domain extractors | Not Started | — | Arch §11.7 |
| F-IDX-6 | Semantic embeddings (local-first) | Not Started | — | Arch §12.3 |
| F-CTX-1 | Budgeted context assembler | Not Started | — | Arch §13.1–13.3 |
| F-CTX-2 | Compaction | Not Started | — | Arch §13.4 |
| F-CTX-3 | Project instructions | Not Started | — | Arch §13.5 |
| F-CTX-4 | Typed project memory | Not Started | — | Arch §13.6 |
| F-AGT-1 | Primary agent loop | In Progress | — | M0 scope. Arch §9.1–9.3, §30.1 |
| F-AGT-2 | Plan Mode | Not Started | — | Arch §9.4 |
| F-AGT-3 | Self-correction loop | In Progress | — | M0 subset: retry with diagnostics. Arch §9.5 |
| F-AGT-4 | Verification gates | In Progress | — | M0 subset: single verify command gate (full gates M1). Arch §9.6 |
| F-AGT-5 | Skills and hooks | Not Started | — | Arch §9.7 |
| F-ORC-1 | Subagents | Not Started | — | Arch §10.1–10.2 |
| F-ORC-2 | Task DAG scheduler | Not Started | — | Arch §10.3 |
| F-ORC-3 | Write leases and worktrees | Not Started | — | Arch §10.4 |
| F-ORC-4 | Human-in-the-loop approvals | In Progress | — | M0 subset: allow/ask/deny policy; headless ask→deny. Arch §10.5, §25.4 |
| F-ORC-5 | Background and scheduled agents | Not Started | — | Arch §10.6, §30.4 |
| F-SBX-1 | Sandbox provider abstraction | In Progress | — | M0 scope. Arch §16.1–16.2 |
| F-SBX-2 | Whole-toolchain containment | Not Started | — | Arch §16.3 |
| F-SBX-3 | Network egress control | Not Started | — | Arch §16.5 |
| F-SBX-4 | Credential masking | Not Started | — | Arch §16.6, §8.3, §30.5 |
| F-SBX-5 | Lifecycle and resources | In Progress | — | M0 subset: create/destroy + reaper. Arch §16.4 |
| F-PRV-1 | Dev server detection and startup | Not Started | — | Arch §17.2 |
| F-PRV-2 | Live preview panel | Not Started | — | Arch §17.1, §17.3–17.5 |
| F-PRV-3 | Runtime telemetry | Not Started | — | Arch §18.3 |
| F-PRV-4 | Environment Snapshot (X1) | Not Started | — | Arch §18.4, §29.3 |
| F-PRV-5 | Browser automation tools | Not Started | — | Arch §18.5, §30.2 |
| F-TRM-1 | Integrated terminal | In Progress | — | M0 scope. Arch §19.1–19.3 |
| F-TRM-2 | Diagnostic parsers | Not Started | — | Arch §19.4 |
| F-GIT-1 | Source control panel | Not Started | — | Arch §20.1–20.2, §5.2 |
| F-GIT-2 | Shadow checkpoints | Not Started | — | Arch §20.3 |
| F-GIT-3 | Worktree manager | Not Started | — | Arch §20.4 |
| F-GIT-4 | PR integration | Not Started | — | Arch §20.5 |
| F-GIT-5 | Git safeguards | Not Started | — | Arch §20.6 |
| F-MCP-1 | MCP client manager | Not Started | — | Arch §14.1–14.3 |
| F-MCP-2 | Tool registry and tool search (X7) | Not Started | — | Arch §14.4, §15.2 |
| F-MCP-3 | Permissions and trust tiers | Not Started | — | Arch §14.6 |
| F-MCP-4 | Result normalization, compression, caching | Not Started | — | Arch §15.4 |
| F-MCP-5 | Injection defense | Not Started | — | Arch §25.6 |
| F-TOK-1 | Token ledger | In Progress | — | M0 scope. Arch §29.1, §29.6 |
| F-TOK-2 | Budgets | In Progress | — | M0 subset: hard budget pre-call check. Arch §29.6 |
| F-TOK-3 | Deterministic-first policy | Not Started | — | Arch §29.2, §15.5 |
| F-TOK-4 | Prompt-cache optimizer | Not Started | — | Arch §29.4 |
| F-VIS-1 | Element→source mapping (X2) | Not Started | — | Arch §18.6 |
| F-VIS-2 | Select-and-instruct | Not Started | — | Arch §18.6 |
| F-VIS-3 | Visual regression (X10) | Not Started | — | Arch §18.7 |
| F-VIS-4 | UI consistency analysis | Not Started | — | Arch §18.7 |
| F-TST-1 | Change-based test selection | Not Started | — | Arch §11.5, §9.6 |
| F-TST-2 | Test generation | Not Started | — | Arch §9.6 |
| F-TST-3 | Browser E2E from recordings (X16) | Not Started | — | Arch §18.5 |
| F-TST-4 | Bug auto-reproduction (X11) | Not Started | — | Arch §9.5 |
| F-REV-1 | Review agent | Not Started | — | Arch §10.2 |
| F-REV-2 | Security analysis | Not Started | — | Arch §25.10 |
| F-REV-3 | Dependency risk gate (X17) | Not Started | — | Arch §16.7 |
| F-UI-1 | Workbench | Not Started | — | Arch §5.1–5.3 |
| F-UI-2 | Agent activity monitor | Not Started | — | Arch §5.4 |
| F-UI-3 | Intelligence Explorer | Not Started | — | Arch §5.5 |
| F-UI-4 | Artifacts | Not Started | — | Arch §5.6 |
| F-OBS-1 | Traces and logs | In Progress | — | M0 scope. Arch §26.1–26.3 |
| F-OBS-2 | Session replay (X14) | Not Started | — | Arch §26.4 |
| F-OBS-3 | Audit log | In Progress | — | M0 subset: hash-chained audit_log. Arch §26.5 |
| F-DEP-1 | Deploy adapters | Not Started | — | Arch §22.6 |
| F-TEAM-1 | Org policies | Not Started | — | Arch §25.8 |
| F-TEAM-2 | Shared memory and skills (X18) | Not Started | — | Arch §13.6 |
| F-TEAM-3 | Cloud workspaces | Not Started | — | Arch §28.4, §6.3 |

## Completed Work Log

- **2026-11-06 — Docs phase (pre-M0).** `plan.md` and `architecture.md` completed and cross-checked. The docs-phase log moved to `docs/progress-docs-phase.md`.

## Bugs and Known Issues

| Issue ID | Description | Severity | Affected components | Root cause | Status | Resolution |
|---|---|---|---|---|---|---|
| — | none yet | — | — | — | — | — |

## Architecture Decision Log

(Deviations from or additions to `architecture.md`. Numbered `IMPL-ADR-n` to avoid clashing with architecture ADR-001…023.)

## Test and Verification Results

| Suite | Scope | Result | Evidence |
|---|---|---|---|
| — | — | Not tested | — |

## Next Actions

1. Scaffold the pnpm monorepo: `packages/protocol`, `packages/engine`, `apps/cli`, `fixtures/`.
