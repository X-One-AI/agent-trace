# agent-trace Product Foundation

## Intake

- Priority: P3
- Status: v0.1.0 deferred tracing decision and failure-packet evidence wedge
- Positioning: Generic AI agent tracing is deferred; only failure-packet-shaped evidence remains in scope.
- Primary route: Product -> Architecture -> Expert/Security -> QA -> Implementation -> Completion readiness

## PRD

### Problem

Avoid competing head-on with established tracing and observability platforms.

### Users

- Developers adopting AI agents or MCP tools
- Platform, DevTools, Security, and AI infrastructure teams
- Maintainers who need reviewable evidence rather than vague AI automation claims

### Goals

- deferred rationale
- competition notes
- allowed evidence wedge
- delete-or-merge review cadence

### Non-Goals

- not a dashboard
- not a tracing backend
- not a Langfuse/Phoenix/LangSmith clone

### Acceptance Criteria

- The project can explain its place in Safe Agent Operations in one sentence.
- The first production surface is local-first or review-first, not a hosted dashboard by default.
- Reports, packets, indexes, or labs must be redaction-safe by design.
- Every risky claim links to evidence, rule logic, or an explicit limitation.
- The repository explicitly defers generic tracing.
- Packet-shaped trace fields are documented for possible absorption into `agent-failure-packet`.

## Architecture Brief

### Boundaries

- Keep shared workflow knowledge in OPT; keep project-specific decisions in this repository.
- Keep the main entrypoint small and explicit.
- Prefer file-based artifacts over hidden services for the first production surface.

### Data Flow

```text
trace idea -> packet-shaped evidence check -> move to agent-failure-packet / watch / reject / reopen decision
```

### Risks

- Overclaiming safety guarantees.
- Creating generic tooling that weakens the Agentic DevSecOps signal.
- Accepting real secrets or private user data into fixtures.

## QA Plan

- Verify no README or docs imply a tracing backend exists.
- Verify useful trace fields are routed to `agent-failure-packet`.
- Verify raw prompts, tool payloads, secrets, and private data remain excluded.
- Keep bilingual README guidance aligned.

## Implementation Plan

1. Keep this as a decision repository until reopen criteria are met.
2. Merge useful packet-shaped fields into `agent-failure-packet`.
3. Delete generic dashboard ideas that weaken positioning.
4. Use feature branches named `docs/<scope>`.
5. Use Conventional/Angular commits such as `docs: clarify trace wedge`.
6. Never push directly to `main`; open a pull request from the feature branch.

## Skipped Inputs

- clear evidence that generic tracing is strategically necessary
