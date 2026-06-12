# agent-trace

Languages: English | [中文](./README.zh-CN.md)

Generic AI agent tracing is deferred; only failure-packet-shaped evidence remains in scope.

## Status

`v0.1.0` - deferred tracing decision and failure-packet evidence wedge.

## Purpose

Avoid competing head-on with established tracing and observability platforms.

## First Production Surface

Decision log that prevents scope creep and captures failure-packet-relevant ideas.

This repository intentionally does not ship a tracing backend, dashboard, or CLI in v0.1.0.

## Required Evidence

- deferred rationale
- competition notes
- allowed evidence wedge
- delete-or-merge review cadence

## Decision

Generic agent tracing is deferred. Only packet-shaped trace evidence that improves `agent-failure-packet` remains in scope.

## Non-Goals

- not a dashboard
- not a tracing backend
- not a Langfuse/Phoenix/LangSmith clone

## OPT Operating Model

This project references the shared One Person Team workflow through [ops/opt-overlay.md](./ops/opt-overlay.md). Project-specific constraints live under [ops/constraints](./ops/constraints), and evolvable local skills live under [ops/skills](./ops/skills).

## Blocked Inputs

Inputs that require user or real-world data are recorded in `../x-one-skipped-inputs.md` and should not block foundation work.

## Docs

- [Product Foundation](./docs/product-foundation.md)
- [Defer Decision](./docs/defer-decision.md)
- [Evidence Wedge](./docs/evidence-wedge.md)
- [Review Cadence](./docs/review-cadence.md)
- [OPT Overlay](./ops/opt-overlay.md)
- [Production Constraints](./ops/constraints/production.md)
- [Main Entry Constraints](./ops/constraints/main-entry.md)
- [Skill Evolution](./ops/skills/evolution.md)
