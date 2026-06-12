# Defer Decision

## Status

Accepted for v0.1.0.

## Decision

Do not build `agent-trace` as a generic tracing dashboard, tracing backend, or observability platform.

Keep only the evidence wedge that strengthens `agent-failure-packet`:

- compact failure timelines
- redacted tool-call summaries
- replay-safe step metadata
- handoff notes for maintainers
- incident review attachments

## Why

The generic agent tracing space already has strong incumbents and broad observability products. A new dashboard would dilute the X-One signal and pull effort away from Safe Agent Operations.

The useful wedge is not tracing for its own sake. It is:

> enough structured trace evidence to make a failed agent run safe to share, debug, and review.

## Allowed Scope

Keep an idea only when it can become part of `agent-failure-packet` or an incident review artifact.

Allowed:

- local timeline export
- redacted tool call table
- failure step summary
- prompt/context contamination note
- evidence bundle attachment

Not allowed:

- hosted tracing backend
- dashboard-first product
- distributed tracing storage
- performance observability platform
- Langfuse, Phoenix, LangSmith, or OpenTelemetry clone

## Reopen Criteria

Reconsider standalone tracing only if all are true:

- 5 or more target users explicitly need trace evidence not covered by failure packets.
- The needed data contract is narrow and local-first.
- The output supports audit/review rather than generic monitoring.
- Existing tools cannot reasonably cover the workflow.

## Decision Outcome

`agent-trace` remains a decision repository. Useful concepts should be moved into `agent-failure-packet` issues, fixtures, or docs.
