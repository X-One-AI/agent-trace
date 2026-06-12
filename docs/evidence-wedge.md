# Evidence Wedge

This document defines the small slice of tracing that remains useful to X-One.

## Packet-Shaped Trace Fields

| Field | Purpose | Destination |
|---|---|---|
| `step_id` | Stable ordering inside a failed run | `agent-failure-packet` |
| `actor` | Agent, tool, model, or human reviewer | `agent-failure-packet` |
| `action` | Short action label | `agent-failure-packet` |
| `redacted_input_summary` | Safe summary of tool/model input | `agent-failure-packet` |
| `redacted_output_summary` | Safe summary of output or error | `agent-failure-packet` |
| `failure_boundary` | Where the run became unrecoverable | incident review |
| `review_note` | Maintainer-facing next check | incident review |

## Excluded Fields

- raw prompts
- full tool payloads
- secrets
- browser/session cookies
- private repository data
- long-running storage identifiers

## Merge Rule

If a trace idea fits this table, move it to `agent-failure-packet`. If it does not fit, reject it unless reopen criteria in `docs/defer-decision.md` are met.
