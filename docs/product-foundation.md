# agent-trace Product Foundation

## Intake

- Priority: P3
- Status: deferred decision repository
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

## Architecture Brief

### Boundaries

- Keep shared workflow knowledge in OPT; keep project-specific decisions in this repository.
- Keep the main entrypoint small and explicit.
- Prefer file-based artifacts over hidden services for the first production surface.

### Data Flow

```text
input evidence -> normalize -> redact -> evaluate -> render reviewable artifact
```

### Risks

- Overclaiming safety guarantees.
- Creating generic tooling that weakens the Agentic DevSecOps signal.
- Accepting real secrets or private user data into fixtures.

## QA Plan

- Unit-test redaction and normalization before rule or report expansion.
- Add positive and negative fixtures for every behavior boundary.
- Verify generated artifacts do not include raw secrets.
- Keep bilingual README guidance aligned.

## Implementation Plan

1. Keep this foundation branch small and reviewable.
2. Add the first executable surface only after the missing inputs are resolved or explicitly skipped.
3. Use feature branches named `feat/<scope>` or `docs/<scope>`.
4. Use Conventional/Angular commits such as `feat: add packet schema` or `docs: clarify deferred scope`.
5. Never push directly to `main`; open a pull request from the feature branch.

## Skipped Inputs

- clear evidence that generic tracing is strategically necessary
