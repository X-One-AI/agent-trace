# Governance Contract

`agent-trace` is a deferred decision repository. Its job is to prevent generic tracing scope creep while preserving the small packet-shaped evidence wedge that can improve `agent-failure-packet`.

## Portfolio Role

This repository must strengthen shareable failure evidence, not compete with tracing or observability platforms.

Allowed output:

- packet-shaped field proposals for `agent-failure-packet`
- redaction-safe timeline examples
- incident review attachment ideas
- explicit reject decisions for dashboard, backend, or monitoring concepts
- review cadence notes after `agent-failure-packet` releases

Disallowed output:

- hosted tracing backend
- tracing dashboard
- distributed storage
- OpenTelemetry, Langfuse, Phoenix, or LangSmith clone behavior
- raw prompt, tool payload, cookie, or private repository capture

## Absorption Contract

Move an idea out of this repository when it can be represented as failure-packet evidence.

| Candidate Shape | Required Evidence | Destination Artifact |
|---|---|---|
| timeline field | failed-run example with stable ordering | `agent-failure-packet` schema or docs issue |
| redacted tool-call summary | safe input/output summary that avoids raw payloads | fixture or rendering requirement |
| handoff note | maintainer-facing next check from a failed run | handoff context field or template update |
| incident attachment | packet-safe artifact useful in review | incident review or packet docs proposal |

Absorbed ideas should leave this repository as soon as a destination issue or PR exists. Keep only a link and the decision outcome.

## Rejection Contract

Reject or delete an idea when any are true:

- it requires persistent tracing storage
- it needs raw prompts, raw tool payloads, secrets, cookies, or private repository data
- it is primarily useful for performance monitoring rather than failure review
- it makes `agent-failure-packet` harder to explain
- it duplicates mature observability products without a packet-specific advantage

Watch-only ideas must name the exact missing evidence. If the missing evidence stays unchanged for two release reviews, delete the idea.

## Review Cadence

Run this governance review after every `agent-failure-packet` release and after every real-user or open-source sample feedback batch.

Review questions:

1. Did a failure-packet workflow need a missing packet-shaped trace field?
2. Can the idea be absorbed without adding a new product surface?
3. Is any watch-only idea still missing the same evidence?
4. Did any text imply that X-One ships tracing infrastructure?
5. Did any local constraint or skill need strengthening, rewrite, or deletion?

## Reopen Gate

Reopen standalone tracing only when the criteria in `docs/defer-decision.md` are met and a new PRD proves the product is local-first, review-first, and materially different from established tracing platforms.

Until then, this repository ships governance, not tracing behavior.
