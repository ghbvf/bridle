---
title: "Three Leaps Bootstrap · Bridle"
description: "35-capability checklist from zero repo to L3 autonomy — eight-stage P0-P7 path for greenfield projects, each capability laid out in five fields (why / what / system weaving / exit / tools)."
lang: en
permalink: /en/three-leaps-bootstrap/
keywords: AI coding bootstrap, greenfield, manifest, static guard, OpenTelemetry, DORA, Harness, IaC, GitOps, Reconciliation, Bridle
---

# Three Leaps · Bootstrap Handbook

> The capability ladder from zero to L3 autonomy. The main methodology [`three-leaps.en.md`](./three-leaps.en.md) assumes the L0 gravity field is already in place. This handbook covers the step before that: **zero repo / zero CI / zero manifest / zero Harness** — a greenfield bootstrap path.
>
> *中文版：[`three-leaps-bootstrap.md`](./three-leaps-bootstrap.md)*

After completing the 35 capabilities in this handbook, your team has more than satisfied the entry conditions for the L3 leap.

---

## 0 · Scope

### What this is

- A bootstrap-path handbook + 35-capability checklist + leap-mapping diagram
- A "pre-foundation" for the main methodology, with concrete actionable steps
- **Capability is the subject; tools are details**

### What this is not

- Not a specification (no mandatory requirements)
- Not a "best practice" manifesto
- Not a replacement for [`three-leaps.en.md`](./three-leaps.en.md)

### Prerequisites

- Project at the 0 → 0.5 stage (no framework, no CI, no manifest, no static guard)
- Determined to adopt three-leaps governance, but lacking foundation
- Solo or team (10-person teams fit best, 10–30 adaptable, 30+ orgs usually have internal platforms)

### Out of scope

- One-off scripts / research code (governance ROI inverts)
- Already complete framework + CI + kanban (read [`three-leaps.en.md`](./three-leaps.en.md) directly)
- Heavily regulated core trading systems (regulatory constraints > this handbook)

### Key acknowledgements (preserving v3's reflective spirit)

- This handbook remains **exploratory** — based on the main methodology + a recommended combination of existing tools
- **Real adopters' practical evidence > this handbook's recommendations**
- Each tool comes with "why this + alternatives," no "best" claims
- This handbook itself must be governed (see §10)

---

## 1 · Design Principles + Phases vs Time

### Four design principles

1. **Capabilities replace time** — time commitments lie, capability achievement is real
2. **Entry/exit signals must be objectively observable** — no subjective judgment
3. **Capability is the subject, tools are details** — 5-field standard template
4. **Preserve reflective spirit** — this handbook can still be refuted by practice

### Why time lies

| Dimension | Real variance | How time commitment fails |
|---|---|---|
| Team size | Solo vs 5 vs 30 | Same phase varies 5–10× in duration |
| Tool familiarity | First contact vs expert | Learning curve 1–4 weeks |
| Parallelism | Full-time vs part-time vs hobby | Real input differs 3–5× |
| Requirement variance | Stable vs volatile | Mid-course rework 50–200% |
| Historical debt | Greenfield vs partial-legacy | Cleanup unpredictable |

**Conclusion**: writing "complete P1 in 4 weeks" goes bankrupt by week 5, triggering governance distrust. Rewrite as "P1 exit = all 5 capabilities achieved" to make it executable and verifiable.

### Why capabilities are real

Each capability has three things, all objectively observable events:

- **Entry signal**: previous capability's exit achieved (machine-verifiable)
- **Mandatory action**: 5-field template (why / what / system weaving / exit / tools)
- **Exit signal**: verifiable event (e.g., "deliberately-out-of-bounds PR is blocked by CI")

**No skipping capabilities** — running the next capability before exiting the previous one creates compounding fragility.

---

## 2 · 35 Capabilities → Three Leaps Mapping

The main methodology's hierarchy is **L0 → L1 → L2 → L3**. This handbook's 35 capabilities map as follows:

```
                     ┌────────────────────────────────────────┐
                     │  L3 Leap ③ · Autonomous Loop            │
                     │  P6.3 Runtime agent + R0–R5             │
                     │  P6.4 Reconciliation loop               │
                     │  P6.5 Decision audit store upgrade      │
                     │  P6.6 Chaos engineering (optional)      │
                     └────────────────────────────────────────┘
                                       ▲
                     ┌────────────────────────────────────────┐
                     │  L2 Leap ② · Intent Expressible         │
                     │  P5.1 Harness Five Pack                 │
                     │  P5.4 AI decision audit (starter)       │
                     │  P6.1 Feature flag systematization      │
                     │  P6.2 IaC + GitOps                      │
                     └────────────────────────────────────────┘
                                       ▲
                     ┌────────────────────────────────────────┐
                     │  L1 Leap ① · State Visible              │
                     │  P1.2 Module manifest + lifecycle       │
                     │  P1.3 Static boundary guard             │
                     │  P3 full set (3.1-3.5) observability    │
                     │  P4 full set (4.1-4.5) flow             │
                     │  P5.2 AI acceptance / P5.3 3-D health   │
                     └────────────────────────────────────────┘
                                       ▲
       ╔════════════════════════════════════════════════════════╗
       ║  L0 · Engineering Gravity Field                         ║
       ║  P0 full set (0.1-0.5) repo/CI/ADR/collab/review        ║
       ║  P1.1 domain layering / P1.4 API ver / P1.5 DB migration║
       ║  P2 full set (2.1-2.6) vuln/coverage/deps/secrets/flag/compliance║
       ╚════════════════════════════════════════════════════════╝
```

### Inter-stage parallelism rules

- **L0 strict gating** (foundation, must be sequential) — P0 / P1.1, 1.4, 1.5 / P2 full set
- **Inside L1, P3 + P4 may parallelize** (metrics vs process, mutually independent)
- **L2 P5.1 Harness may begin during mid-L1** (DORA data feeds AI)
- **L3 must start after L2 exit** (runtime agent needs Harness config in place)

---

## 3 · L0 · Engineering Gravity Field (Foundation)

### 3.1 Repo + first CI (P0.1)

- **Why**: without version control + auto verification, all subsequent governance has no anchor
- **What**: git repo + push/PR triggered CI workflow (lint + test + build)
- **System weaving**: foundation for all subsequent CI (P1 guards / P2 scans / P4 DORA); CI green is the earliest event signal for L3 evaluation
- **Exit**: CI green for 4 consecutive PRs; any push/PR runs < 5 min
- **Tools**: GitHub Actions / Azure Pipelines / GitLab CI

### 3.2 Hello-world main path (P0.2)

- **Why**: project being runnable is the basis for everything; no hello-world means you don't even know the stack choice failed
- **What**: shortest path from entry to outward interface (HTTP endpoint / CLI command)
- **System weaving**: earliest sample for L1 OTel instrumentation; starting point for L3 Agent eval loop
- **Exit**: main branch one-click runs; new member from clone to running < 5 min
- **Tools**: stack-native + optional Docker

### 3.3 Decision records · ADR (P0.3)

- **Why**: early decisions (stack choice / arch direction / tooling) forgotten in 6 months; retrospectives lose grounding
- **What**: `docs/adr/` directory + first ADR + template
- **System weaving**: → L2 Harness "project memory" layer; → L3 quarterly review historical input
- **Exit**: first ADR exists; subsequent major decisions go through ADR flow
- **Tools**: adr-tools / Log4brains / hand-written markdown

### 3.4 Collaboration conventions (P0.4)

- **Why**: without "how to contribute" conventions, PR review relies on verbal consensus; team ≥ 2 collapses
- **What**: README + CONTRIBUTING + branch protection
- **System weaving**: → Code review's basis; → Harness collaboration context (CLAUDE.md / cursor rules can reference)
- **Exit**: new member from repo to first PR < 1 hour; branch protection enforced on main
- **Tools**: GitHub Branch Protection / Azure DevOps Branch Policies / Conventional Commits

### 3.5 Code review system (P0.5)

- **Why**: lint alone cannot catch design errors; review is the human-side action for knowledge transfer and boundary guarding
- **What**: CODEOWNERS + required reviewer count + stale PR auto-close
- **System weaving**: → AI acceptance rate baseline; → DORA Lead Time bottleneck
- **Exit**: every PR has at least 1 reviewer approve; CODEOWNERS covers all directories
- **Tools**: CODEOWNERS (GitHub/GitLab/Azure) + stale-bot / Probot

### 3.6 Domain layering (P1.1)

- **Why**: a single src/ directory becomes a big ball of mud; subsequent static guards have no target
- **What**: at least three tiers (domain / shared / adapters), each with clear responsibility
- **System weaving**: → module manifest organized by domain; → target of static guards
- **Exit**: every file belongs to exactly one tier; cross-references go through clear interfaces
- **Tools**: stack-native directory conventions (no special tool)

### 3.7 API version strategy (P1.4)

- **Why**: first version of an API without a version number cannot evolve smoothly; clients have no deprecation path
- **What**: all outward APIs use `/api/v1/` prefix; deprecation policy (≥ 2 release dual-run)
- **System weaving**: → Feature flag version routing; → performance baseline by version
- **Exit**: all routes have a version segment; at least 1 deprecation flow doc
- **Tools**: OpenAPI 3 + Swagger UI / Redoc / Stoplight

### 3.8 DB migration (P1.5)

- **Why**: directly editing schema becomes production incidents; version mismatch breaks cross-service integration
- **What**: all schema changes go through migration tooling; CI verifies order and rollback-ability
- **System weaving**: → Secrets (migration uses db creds); → incident management (schema changes are incident-prone)
- **Exit**: `migrations/` exists; at least 1 successful forward + rollback drill
- **Tools**: Flyway / Liquibase / Alembic / golang-migrate / EF Core / Prisma Migrate

### 3.9 Multi-layer vulnerability scanning (P2.1)

- **Why**: dependency / pattern / data-flow / SBOM each have blind spots; one layer is insufficient for supply-chain attack surface
- **What**: 4 independent scan layers — dependency + pattern SAST + data-flow SAST + SBOM
- **System weaving**: → L1 health structure score; incidents traceable backward
- **Exit**: 4 layers green for 4 consecutive weeks; any layer failure has named owner
- **Tools**: Dependabot + CodeQL + Semgrep + Syft

### 3.10 Coverage gate (P2.2)

- **Why**: coverage is not quality, but low coverage definitely has quality issues
- **What**: coverage gate **only on new code** (avoid fake-test backfill traps)
- **System weaving**: → L1 engineering signal source; with DORA Lead Time jointly measures "fast and stable"
- **Exit**: coverage has ≥ 4 weeks of trend data; new code coverage ≥ 80%
- **Tools**: Codecov / Coveralls / SonarCloud

### 3.11 Auto dependency upgrade (P2.3)

- **Why**: dependencies expire, vulnerabilize, deprecate; manual tracking is toil and inevitably slips
- **What**: enable Dependabot/Renovate auto PRs; set merge cadence (e.g., weekly batch)
- **System weaving**: → vuln scan remediation path; avoid noise pile-up
- **Exit**: Dependabot PR avg lifespan < 7 days; no ≥ 30-day backlog
- **Tools**: Dependabot / Mend Renovate / Snyk

### 3.12 Secrets + credential rotation (P2.4)

- **Why**: plain-text secrets in git is a routine incident; non-rotated credentials, once leaked, are permanently exposed
- **What**: centralized secrets + apps read via SDK + pre-commit + push-time double scan + periodic rotation
- **System weaving**: → DB migration creds; → IaC cloud creds
- **Exit**: 0 plain-text secrets in git ≥ 4 weeks; at least 1 successful rotation drill
- **Tools**: HashiCorp Vault / Azure Key Vault / Doppler / AWS Secrets Manager + gitleaks

### 3.13 Config + feature flag starter (P2.5)

- **Why**: config hardcoded = every config change requires a release; feature flag is the foundation of progressive delivery
- **What**: env / config separation + feature flag SDK starter + flag cleanup policy
- **System weaving**: → L2 flag systematization + canary delivery; → L3 reconciler uses flags for experimental traffic
- **Exit**: first feature flag working; config changes don't require rebuild
- **Tools**: Flipt / Unleash (OSS) / LaunchDarkly / ConfigCat

### 3.14 Data compliance annotation (P2.6)

- **Why**: GDPR/HIPAA/PCI-DSS require field-level tracking; retroactive work means re-auditing all code
- **What**: annotate sensitive fields (PII / PHI / PCI) in manifest or schema; CI verifies "sensitive fields not in logs / not crossing domains"
- **System weaving**: → OTel (filter sensitive fields in logs); → L2 decision audit (annotate sensitive ops)
- **Exit**: sensitive field annotation coverage ≥ target ratio; CI blocks "sensitive field in log" PRs
- **Tools**: custom annotation + Semgrep custom rules / OpenPolicyAgent / Bridgecrew

### L0 exit signals

- CI green + main runs hello-world + first ADR + README/CONTRIBUTING/CODEOWNERS in place
- Deliberately-out-of-bounds PR blocked by CI (based on domain layering + later guards)
- Migration drill passed
- 4-layer scan green ≥ 4 weeks; coverage trend; 0 secrets in git; feature flag starter; data compliance annotation coverage

→ **Enter L1 leap**

---

## 4 · L1 Leap ① · State Visible

### 4.1 Module manifest + lifecycle (P1.2) ★

> **L1 entry capability · most important artifact in the entire diagram**

- **Why**: cornerstone of the declarative governance system. No manifest = cannot mechanically judge module state
- **What**: per-module `manifest.yaml` (module/domain/lifecycle/contracts) + JSON Schema validation + lifecycle field (experimental → candidate → asset → maintenance → retired)
- **System weaving**: consumed by vuln scans (per-module) / health (indexed by manifest) / reconciler (pulls manifest, computes drift)
- **Exit**: 100% modules have manifests; CI enforces schema validation; manifest errors fail
- **Tools**: JSON Schema + ajv / gojsonschema / jsonschema / NJsonSchema

### 4.2 Static boundary guard (P1.3)

- **Why**: relying on review alone to prevent boundary violations breaks within 6 months. Need machine-enforced interception
- **What**: at least one rule blocking critical out-of-bounds ("cross-domain import" / "experimental referenced from production journey" / "adapter directly called by domain")
- **System weaving**: → health structure score sub-item; violation count = score deduction input
- **Exit**: deliberately-out-of-bounds PR fails CI; rule count ≥ 3
- **Tools**: dependency-cruiser / hand-written archtest / ArchUnit / NetArchTest / import-linter

### 4.3 OpenTelemetry triple (P3.1)

- **Why**: missing logs/metrics/traces = blind spots in incident analysis; vendor lock-in blocks tool migration later
- **What**: OTel SDK unified instrumentation + structured logs (JSON) + metrics (counter/gauge/histogram) + tracing (trace_id stitched across services)
- **System weaving**: → SLO / incident tracing / perf baseline / health signal
- **Exit**: trace_id stitches from entry to DB; all 3 components have data
- **Tools**: OpenTelemetry SDK + Grafana Cloud / DataDog / Application Insights / Honeycomb

### 4.4 SLI/SLO + Error budget (P3.2)

- **Why**: without SLO, "availability" is a subjective word; error budget is the objective anchor constraining release speed
- **What**: define ≥ 1 SLI (P99 latency / success rate) + 1 SLO + error budget tracking
- **System weaving**: → incident management trigger; → DORA Change Failure Rate linked with budget
- **Exit**: SLO has begun burning; budget calculation visible
- **Tools**: Sloth (OSS) / Pyrra (OSS) / Nobl9 (commercial)

### 4.5 Incident management (P3.3)

- **Why**: zero response on production issues = users discover before the team; on-call concentrated on 1 person = burnout
- **What**: on-call schedule + alert channels + incident flow + runbook library
- **System weaving**: ← SLO burn trigger; → blameless post-mortem input
- **Exit**: on-call has owner; at least 1 real incident walked through full flow; runbooks ≥ 3
- **Tools**: PagerDuty free / Opsgenie / FireHydrant / homemade + Slack notifications

### 4.6 Performance baseline + budget (P3.4)

- **Why**: without baseline, perf regression is invisible; frontend especially loses control of bundle size / LCP
- **What**: CI integrated perf tests + baseline snapshots + perf budget + regression fails
- **System weaving**: → engineering score sub-item; → API version comparison baseline
- **Exit**: perf baseline runs in CI; at least 1 regression caught
- **Tools**: k6 / Lighthouse CI / JMeter / Gatling / NBomber

### 4.7 a11y / i18n baseline (P3.5 · user-facing projects)

- **Why**: a11y retrofitted means re-auditing all UI; hardcoded i18n strings have high batch-extraction cost
- **What**: a11y auto-detection (CI integrated) + i18n string externalization + at least 1 non-default language verified
- **System weaving**: → perf budget (i18n bundle growth)
- **Exit**: a11y detection has no critical violations; i18n framework in place
- **Tools**: axe-core + Pa11y CI / Lighthouse a11y / WAVE; i18next / FormatJS / .NET ResX

### 4.8 DORA five-metric collection (P4.1)

- **Why**: without objective metrics, "we're efficient" is subjective; DORA is the industry-comparable baseline
- **What**: collect deployment frequency / lead time / change failure rate / recovery time / rework rate; daily snapshot
- **System weaving**: ← WIP directly affects lead time; → health engineering score; → quarterly review input
- **Exit**: 5 metrics daily snapshot ≥ 4 weeks
- **Tools**: homemade (gh CLI + jq + cron) → Apache DevLake → Sleuth / DX / DataDog DORA

### 4.9 Kanban + WIP limit (P4.2)

- **Why**: no WIP = unlimited parallel tasks = no task actually completes; kanban + WIP is the physical constraint on flow
- **What**: kanban columns (Backlog/Doing/Review/Done) + Doing column WIP cap
- **System weaving**: → DORA Lead Time (larger WIP, longer lead time)
- **Exit**: WIP cap quantified; exceeding triggers auto alert or column refusal
- **Tools**: GitHub Projects / Azure DevOps Boards / Linear / Jira

### 4.10 Retrospective rhythm (P4.3)

- **Why**: no periodic retro = same mistakes repeat; no improvement accumulation
- **What**: retro at end of every milestone; output owner-tagged action items; follow up next time
- **System weaving**: ← post-mortem input; ← DORA data input; → ADR
- **Exit**: at least 1 retro outputs action and follows up
- **Tools**: Miro / FunRetro / Metro Retro / Notion templates

### 4.11 Blameless post-mortem (P4.4)

- **Why**: post-incident blame = team hides next incident; blameless is the precondition of organizational learning
- **What**: every incident goes through blameless template (timeline + root cause + actions) + public archive
- **System weaving**: ← incident management trigger; → retro input
- **Exit**: at least 1 real post-mortem publicly archived; tone is blameless
- **Tools**: Google SRE template / PagerDuty Postmortems / homemade

### 4.12 Value stream mapping (P4.5)

- **Why**: bottlenecks guessed by hunch are usually wrong; VSM makes "idea to production" wait time visible
- **What**: at least one full VSM (idea → backlog → dev → review → deploy → user), mark wait time per segment
- **System weaving**: → DORA Lead Time optimization input; → retro improvement target
- **Exit**: first VSM doc archived
- **Tools**: Miro / draw.io / Lucidchart / Figjam

### 4.13 AI acceptance rate (P5.2)

- **Why**: not knowing AI suggestion accept/reject rate = cannot judge whether Harness is effective
- **What**: tag AI source in PRs (commit trailer / label) + count merge rate
- **System weaving**: ← Code review system; → R1 autonomy threshold calibration
- **Exit**: acceptance rate has ≥ 4 weeks real data; neither at 100% nor persistently < 30%
- **Tools**: homemade git log parsing + GitHub label statistics

### 4.14 3-D health score (P5.3) ★

> **L1 core capability · most important convergence point in the entire diagram**

- **Why**: "is this module still needed / healthy / in-bounds" must be computable; otherwise everything is subjective
- **What**: business / structure / engineering 3-D score + mechanical collection + daily snapshot + any dimension < 30 alerts
- **System weaving**: convergence point of manifest / static guard / vuln scan / coverage / OTel / perf / DORA (7 inflows); → reconciler input
- **Exit**: at least 3 modules have non-placeholder 3-D scores; scores have ≥ 4 weeks trend
- **Tools**: homemade shell/python scripts + upstream tool APIs (Codecov / archtest / sonar)

### L1 exit signals

- 100% modules have manifest+lifecycle
- Deliberately-out-of-bounds PR blocked by CI
- trace_id reverse-traceable to PR
- SLO has burned; on-call owner; perf regression caught
- DORA daily ≥ 4 weeks
- AI acceptance rate ≥ 4 weeks real data
- Health scores trending

→ **Enter L2 leap**

---

## 5 · L2 Leap ② · Intent Expressible

### 5.1 Harness Five Pack (P5.1) ★

> **L2 entry capability**

- **Why**: ad-hoc prompts cannot persist across sessions; Harness is "AI's engineering shell within the project"
- **What**: build Anthropic's Five Pack
  - System context (CLAUDE.md / cursor rules / copilot instructions)
  - Tool constraints (permissions / command blocklists)
  - Context injection (rules/skills files)
  - Memory & progress (git log + ADR + memory files)
  - Evaluation loop (CI green + eval suite)
- **System weaving**: → runtime agent reuses Harness config; ← ADR + collaboration conventions are context input
- **Exit**: all five components have concrete files; AI can reference project history in PRs
- **Tools**: Claude Code / Cursor / GitHub Copilot — pick one

### 5.2 AI decision audit starter (P5.4)

- **Why**: AI autonomous decisions must be traceable; otherwise R1–R3 delegation cannot be retroactively reviewed
- **What**: every AI-triggered state change (lifecycle migration suggestion / auto PR) writes to `docs/agent-decisions/<date>.md` with trigger / action / reversibility level / rollback method
- **System weaving**: → decision audit store upgrade (structured); ← Harness eval loop trigger
- **Exit**: decision audit ≥ 30 entries accumulated
- **Tools**: append-only markdown + git log

### 5.3 Feature flag systematization (P6.1)

- **Why**: starter flag needs upgrade: targeting rules / segments / progressive rollout / auto cleanup
- **What**: flag service + canary (1% → 10% → 50% → 100%) + shadow + flag lifecycle
- **System weaving**: ← API version (route by version); ← starter config; → reconciler (experimental traffic via flag)
- **Exit**: at least 1 real canary rollback verification; flag cleanup automated
- **Tools**: Flipt (OSS) / Unleash (OSS) / LaunchDarkly / ConfigCat

### 5.4 IaC + GitOps (P6.2)

- **Why**: manual env operations cause state drift; can't one-click create/destroy = can't test + can't recover quickly
- **What**: infra goes via Terraform/Pulumi/Bicep + state centrally managed + GitOps (git is source of truth)
- **System weaving**: → reconciler borrows K8s controller pattern; ← Secrets (IaC uses cloud creds)
- **Exit**: env one-click create + one-click destroy; state drift detectable
- **Tools**: Terraform / Pulumi / OpenTofu / Bicep + ArgoCD / Flux / Azure Deployment Environments

### L2 exit signals

- Harness Five Pack in place
- Decision audit ≥ 30 entries
- Feature flag at least 1 real canary rollback
- Env one-click create/destroy

→ **Enter L3 leap**

> **Critical L2 → L3 signal**: ability to write the first 4-block intent file (business / contract / quality / lifecycle) where every field has a corresponding verifier (see main methodology §7.3).

---

## 6 · L3 Leap ③ · Autonomous Loop

### 6.1 Runtime agent + R0–R5 reversibility gradient (P6.3)

- **Why**: real "runtime governance" promise. No agent = governance only at compile time
- **What**: build `runtime/agent/` abstraction (AgentTask interface) + executor routes by reversibility R0–R5
  - R0–R1: autonomous
  - R2: auto-released + audit log
  - R3: proposed + human review + staged rollout
  - R4: blocked + forced human decision
  - R5: never granted (red line)
- **System weaving**: ← Harness config; → invoked by reconciler
- **Exit**: R1 experimental lifecycle auto-migration runs in dry-run
- **Tools**: stack-native (Go time.Tick / Node node-cron / Python APScheduler / .NET IHostedService+Quartz / JVM @Scheduled) → Temporal / Dapr (if scaling)

### 6.2 Reconciliation loop (P6.4) ★

> **L3 core capability**

- **Why**: periodic check desired vs current = proactively find drift; passively waiting for users = too late
- **What**: scheduled cron (e.g., 30 min) pulls manifest + intent + computes drift + routes by R0–R5 + reports status
- **System weaving**: convergence of manifest / health / runtime agent (3 inflows); → decision audit store
- **Exit**: dry-run multiple times zero false positives; R1 autonomy in dry-run works
- **Tools**: homemade + GitHub Actions cron / stack-native scheduler / K8s Controller-runtime / Crossplane

### 6.3 Decision audit store upgrade (P6.5)

- **Why**: markdown storage doesn't support structured queries; must upgrade after scaling
- **What**: append-only markdown → SQLite (medium) / EventStoreDB (large); provide query CLI
- **System weaving**: ← starter store / ← reconciler writes; → quarterly review input
- **Exit**: decisions structurally queryable (filter by time / trigger / reversibility level)
- **Tools**: SQLite / EventStoreDB / Postgres append-only table

### 6.4 Chaos engineering (P6.6 · optional)

- **Why**: without fault-injection drills, you don't know the system's real fault tolerance; when it really happens you panic
- **What**: periodic fault injection (dependency latency / node down / network partition) + verify SLO still meets
- **System weaving**: → SLO verification; → post-mortem drill
- **Exit**: at least 1 successful chaos experiment + report
- **Tools**: Litmus / Chaos Mesh (K8s) / Gremlin / homemade fault injection

### L3 exit signals

- Reconciler dry-run zero false positives
- R1 experimental autonomy works
- Decision audit structurally queryable
- (Optional) at least 1 successful chaos experiment

→ **This handbook concludes its mission**. Continue per [`three-leaps.en.md`](./three-leaps.en.md) §11 full loop + §14 measurement framework.

---

## 7 · Cross-capability anti-patterns

| Anti-pattern | Symptom | Correction |
|---|---|---|
| Capability skipping | L0 not exited but doing L1 | Strict gating: previous capability not exited, no entry |
| One-step-to-everything | L0 immediately on K8s+Temporal+DataDog | Per mapping order, each capability does only the minimum |
| Tool stack collision | Using GitHub Projects+Linear+Jira simultaneously | Each capability picks 1 tool only |
| Signal fill-in | Humans manually filling manifest / health signals | Must be mechanically collected |
| AI worship | Acceptance 100% rejection 0 | Force ≥ 10% rejection rate as health floor |
| Governance ROI inversion | Governance time > coding 30% for two milestones | Pause, re-scope this capability |
| Fake coverage | Whole-repo 80% gate forces fake tests | Only new-code gate |
| Framework over-engineering | L0 immediately 12-layer Clean Architecture | L0 only 3 layers (domain / shared / adapters) |
| Bridge skipping | L1 exit directly to reconciliation autonomy | Must go through L2 Harness Five Pack |
| Premature K8s | Services < 5 on K8s | Cloud Run / Container Apps starter |

---

## 8 · Regression signals (not failure, honesty)

If any of the following occurs, **regress to the previous capability and redo** rather than continuing:

- **Regress to L0 redo**: repo structure too messy for new member to onboard in 1 day
- **Regress to L0 guard**: deliberately-out-of-bounds PR actually passed CI (guard failed)
- **Regress to L0 vuln scan**: 2 consecutive weeks of production incidents from known CVEs Dependabot didn't catch
- **Regress to L1 OTel**: production incident untraceable (no trace / SLO never burns)
- **Regress to L1 DORA**: DORA Lead Time persistently rising for 3 milestones
- **Regress to L1 acceptance**: AI acceptance persistently < 30% or > 95%
- **Regress to L3 reconciler**: reconciler falsely retired active modules ≥ 1 time

Regression is not failure — it is honesty. **Pushing forward** would compound the unstable foundation.

---

## 9 · Verification checklists (per leap exit)

| Leap | Objectively verifiable checklist |
|---|---|
| L0 | [ ] CI green; [ ] main runs; [ ] ADR; [ ] README+CONTRIBUTING+CODEOWNERS; [ ] OOB PR blocked; [ ] migration drill; [ ] 4-layer scan green ≥ 4w; [ ] 0 secrets in git; [ ] feature flag starter |
| L1 | [ ] 100% modules manifest+lifecycle; [ ] trace_id reverse-traceable; [ ] SLO burned; [ ] on-call owner; [ ] DORA daily ≥ 4w; [ ] retro+action; [ ] post-mortem; [ ] VSM; [ ] health score trending |
| L2 | [ ] Harness Five Pack in place; [ ] AI acceptance has data; [ ] decision audit ≥ 30; [ ] flag canary rollback; [ ] IaC one-click env |
| L3 | [ ] Reconciler dry-run zero FP; [ ] R1 autonomy works; [ ] decision audit queryable; [ ] R5 never granted |

---

## 10 · Continuous revision (governing this handbook)

This handbook remains **exploratory** and must accept practical critique:

- Every real project applying this handbook opens a `bootstrap-feedback` issue (in that project's repo)
- At least 3 different projects walking through L0–L3 before considering "v1" release (until then it is v0.x exploratory)
- Every tool recommendation comes with practical evidence (which project used it + feedback); no evidence, no preference
- At least 1 review per year: which tools are sunset, which new tools onboard

**Self-governance red lines**:

- ❌ This handbook claims to be "best practice" → delete that wording, revert to "exploratory"
- ❌ Tool menu unchanged ≥ 6 months → trigger review
- ❌ Project completes L0–L3 but main methodology §11 full loop fails → reverse-revise this handbook

---

## Appendix A · Tool menu matrix (5 stacks × key capabilities)

**Starter = solo / small team**, **Upgrade = team ≥ 5 or services ≥ 5**.

| Capability | TS/Node | Go | Python | Java/Kotlin | .NET |
|---|---|---|---|---|---|
| Package/build | npm/pnpm + tsx / esbuild | go modules | poetry / uv | maven / gradle | dotnet sdk |
| Lint | ESLint | golangci-lint | ruff | Checkstyle / ktlint | Roslyn analyzers |
| Type | tsc strict | go vet+staticcheck | mypy | compiler builtin | compiler builtin |
| Static guard | dependency-cruiser | hand-written archtest | import-linter | ArchUnit | NetArchTest |
| Test | Jest / Vitest | testing+testify | pytest | JUnit 5 | xUnit |
| Coverage | c8 / Istanbul → Codecov | -cover → Codecov | pytest-cov → Codecov | JaCoCo → Codecov | coverlet → Codecov |
| Dep vuln | npm audit + Dependabot | govulncheck + Dependabot | pip-audit + Dependabot | OWASP DC + Dependabot | dotnet vulnerable + Dependabot |
| DB migration | Prisma Migrate / Knex | golang-migrate | Alembic | Flyway / Liquibase | EF Core Migrations |
| Perf baseline | k6 / Artillery / Lighthouse CI | k6 | Locust / k6 | JMeter / Gatling | NBomber / k6 |
| BDD | Cucumber.js | godog | behave | Cucumber-JVM | SpecFlow |
| Runtime agent | node-cron / BullMQ | time.Tick / robfig/cron | APScheduler / Celery | @Scheduled / Quartz | IHostedService + Quartz.NET |

**Universal layer** (stack-agnostic):

| Capability | Starter | Upgrade |
|---|---|---|
| Repo + CI/CD + kanban | GitHub (one-stop) | Azure DevOps (Boards/Pipelines/Repos/Artifacts/Test Plans 5-pack) |
| Vuln SAST | CodeQL (GitHub) / Semgrep | SonarCloud / Snyk |
| Container | Docker | Buildah / nerdctl |
| Orchestration | Cloud Run / Container Apps / ECS Fargate / direct systemd | Kubernetes (EKS / AKS / GKE) |
| IaC | Terraform | Pulumi / OpenTofu / Bicep (Azure) |
| GitOps | ArgoCD | Flux / Azure Deployment Environments |
| Telemetry | OpenTelemetry SDK + Grafana Cloud free | Application Insights / DataDog / New Relic / Honeycomb |
| Feature flag | Flipt / Unleash (OSS) | LaunchDarkly |
| Secrets | HashiCorp Vault / Azure Key Vault | Doppler / AWS Secrets Manager |
| AI Harness | Claude Code / Cursor / Copilot — pick one | Multi-role agent separation |
| DORA | Homemade scripts | Apache DevLake / Sleuth / DX |
| Incident management | PagerDuty free | Opsgenie / FireHydrant |

**Kubernetes adoption timing**:

- Solo / small team / services < 5: **don't go K8s**, use Cloud Run / Azure Container Apps / ECS Fargate / VM systemd
- Medium team / services 5-30: consider managed K8s (EKS / AKS / GKE)
- Large team / services 30+: managed or self-managed K8s, service mesh on demand

---

## Appendix B · Solo / small team / medium team tool differentiation

| Capability | Solo | Small team (2-5) | Medium team (5-30) |
|---|---|---|---|
| Repo+CI | GitHub Free | GitHub Team / Azure DevOps Basic | GitHub Enterprise / Azure DevOps Server |
| Issue+kanban | GitHub Issues+Projects | + Linear / Azure Boards | Linear / Jira / Azure Boards Pro |
| Comms | – | Slack free / Teams | Slack paid + PagerDuty |
| Vuln | Dependabot+CodeQL | + Snyk free / Semgrep | + Snyk team / SonarCloud |
| Coverage | Codecov free | Codecov team | SonarCloud |
| Telemetry | Grafana Cloud free | + Sentry free | DataDog / Application Insights / New Relic |
| Secrets | Vault OSS / 1Password | Doppler / Vault Cloud | Vault Enterprise / AWS SM / Azure Key Vault |
| Feature flag | Flipt OSS / env switch | Unleash OSS | LaunchDarkly |
| AI Harness | Claude Code personal | Cursor Team / Claude for Teams | Cursor Enterprise / homemade eval |
| Runtime | Cloud Run / Container Apps | Managed K8s (if needed) | Full K8s + service mesh |
| DORA | Homemade scripts | Apache DevLake | DevLake / Sleuth / DX |
| Decision audit | Append-only markdown | + SQLite | EventStoreDB / Postgres |
| Incident management | PagerDuty free (self on-call) | PagerDuty 5-user free | Opsgenie / FireHydrant |

**Upgrade principle**: each tier-up, **only swap the most painful 1-2 tools**. Swapping 5 tools at once collapses team workflow for 4-6 weeks.

---

## Related documents

- [Main methodology · three-leaps.en.md](./three-leaps.en.md)
- [Companion deck · deck/index.html](./deck/index.html)
- [v3 original (archived) · archive/v3.md](./archive/v3.md)
- [v3-bootstrap original (archived) · archive/v3-bootstrap.md](./archive/v3-bootstrap.md)
- [Anthropic · Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [DORA · State of DevOps Report](https://dora.dev/)
- [Apache DevLake](https://devlake.apache.org/)
