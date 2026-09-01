# TaskMesh roadmap tracker

Source of truth for scope and acceptance criteria: the product plan (`pm-product-plan.md` in the founder's planning repo). This file tracks execution status only. Update it in the same PR as the ticket it lands.

Legend: ☐ todo · ◐ in progress · ☑ done · ⏸ founder action pending

## Phase 0 — Evaluation & fork decision (Weeks 1–2)

| Ticket | Summary | Status |
| --- | --- | --- |
| PM-001 | Dogfood vanilla baseline with 10 real tasks across 2 projects | ⏸ founder |
| PM-002 | Code & license audit of the fork surface | ☑ (audited 2026-09-01: MIT deps; Better Auth maps cleanly to agent identities via user-row + profile pattern; MCP loopback tools delegate authz to REST; warts noted — duplicated `mcp.all("/mcp")` handler, no audit table) |
| PM-003 | Fork repo setup (pin baseline, upstream remote, CI green) | ☑ |
| PM-004 | Security baseline (strip upstream automation, document defaults) | ☑ |

## Phase 1 — Fork stabilization + data model (Weeks 3–6)

| Ticket | Summary | Status |
| --- | --- | --- |
| PM-010 | Rebrand user-facing surfaces | ☐ |
| PM-011 | Agent actor model (profiles, scoped keys, settings UI) | ☐ |
| PM-012 | Task brief fields (outcome, non-goals, acceptance criteria, context refs) | ☐ |
| PM-013 | Agent assignee + presence | ☐ |
| PM-014 | Activity attribution (human / agent / automation) | ☐ |
| PM-015 | Test floor + rebase runbook | ☐ |

## Phase 2 — MCP v2: chat + agent modes (Weeks 7–10)

| Ticket | Summary | Status |
| --- | --- | --- |
| PM-020 | Agent-mode auth on MCP (API-key bearer on `/api/mcp`) | ☐ |
| PM-021 | Discovery & brief tools (`tasks.list_my`, `tasks.get_brief`, `tasks.get_context`) | ☐ |
| PM-022 | Working tools (`report_progress`, `ask_question`, `comments.create_as_agent`) | ☐ |
| PM-023 | DoneProposal + Review queue | ☐ |
| PM-024 | MCP resources & prompts | ☐ |
| PM-025 | Workflow rules on agent events | ☐ |
| PM-026 | E2E with two real clients | ⏸ founder |
| PM-027 | `@taskmesh/mcp` stdio package | ☐ |

## Phase 3 — File & context management (Weeks 11–13)

PM-030 generalized attachments · PM-031 context buckets · PM-032 extraction + excerpts · PM-033 versioning + revocation · PM-034 prompt-injection hygiene — all ☐

## Phase 4 — GitHub depth (Weeks 14–16)

PM-040 evidence links · PM-041 agent→evidence flow · PM-042 PR-event automation · PM-043 proposal-first writeback — all ☐

## Phase 5 — Orca desktop fork (Weeks 17–22)

PM-050 upstream TaskProvider proposal · PM-051 fork infrastructure · PM-052 read-only drawer · PM-053 worktree from task · PM-054 context injection · PM-055 status surface · PM-056 fork hygiene — all ☐

## Phase 6 — Private beta & hardening (Weeks 23–26)

PM-060 onboarding pack · PM-061 observability · PM-062 safety audit · PM-063 beta cohort · PM-064 1.0 cut — all ☐
