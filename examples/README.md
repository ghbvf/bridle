# Bridle Examples

Reference implementations of the four key Bridle artifacts. Drop them into your project as a starting point.

| File | Layer | Purpose |
|---|---|---|
| [`module.yaml`](./module.yaml) | L0 module identity → L1 entry | Per-module manifest with identity, contracts, lifecycle, signals |
| [`intent.yaml`](./intent.yaml) | L2 intent expressible | Desired-state declaration with 4 blocks: business / contract / quality / lifecycle |
| [`reconciler.py`](./reconciler.py) | L3 autonomous loop | Reference reconciliation loop with R0–R5 gradient routing |
| [`CLAUDE.md`](./CLAUDE.md) | L3 Harness · system context | Drop-in `CLAUDE.md` / cursor-rules / copilot-instructions for AI agents |

## Reading order

1. Read [`module.yaml`](./module.yaml) — understand what L1 state visibility looks like in YAML
2. Read [`intent.yaml`](./intent.yaml) — see how a business goal becomes a verifiable contract
3. Read [`CLAUDE.md`](./CLAUDE.md) — the AI agent's bounded operating instructions
4. Read [`reconciler.py`](./reconciler.py) — how all of the above flow into one continuous loop

## Adapting to your project

These are **illustrations**, not production-ready code. Adapt to your stack:

- **Reconciler runtime**: Temporal / Dapr / GitHub Actions cron / K8s Controller-runtime — see `three-leaps-bootstrap.md` §6.1 (P6.3) for stack-specific options
- **Manifest schema validation**: ajv / gojsonschema / jsonschema / NJsonSchema (CI must enforce)
- **Audit store**: append-only markdown (starter) → SQLite → EventStoreDB / Postgres (scale)
- **Signal collection**: each upstream tool has its own API (Codecov / archtest / sonar / OTel collector / GitHub API)

See [`../three-leaps.md`](../three-leaps.md) for the full methodology and [`../three-leaps-bootstrap.md`](../three-leaps-bootstrap.md) for the 35-capability bootstrap path that builds the infrastructure these examples assume.
