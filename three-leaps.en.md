---
title: "Three Leaps · Bridle Main Methodology"
description: "AI coding governance methodology v7 — Three Layers × Three Leaps + R0-R5 autonomy gradient. Derived from first principles, integrating Capital theory, V-model, DORA, and MDM declarative paradigm."
lang: en
permalink: /en/three-leaps/
keywords: AI coding governance, Harness engineering, autonomy gradient, declarative manifest, MDM, reconciliation, DORA, Three Leaps, Bridle, agent
---

# Three Leaps

> **From Acceleration to Liberation** — AI's path to autonomous coding under framework and harness constraints.
>
> *中文版：[`three-leaps.md`](./three-leaps.md)*

This methodology takes the v7 deck's "**Three Layers × Three Leaps**" as its main thread, weaving in v3's first-principles derivation, measurement formulas, and Capital-theoretic analysis. Companion slide deck: [`deck/index.html`](./deck/index.html). Zero-to-L3 bootstrap: [`three-leaps-bootstrap.en.md`](./three-leaps-bootstrap.en.md).

---

## 0 · Reading Map

| # | Chapter | Question it answers | Source |
|---|---|---|---|
| 1 | The Current Tension | Why governance is mandatory | v7 §02 + v3 three decays |
| 2 | The Map: Three Layers × Three Leaps | One picture for the whole system | v7 §03 |
| 3 | First-Principles Derivation | Why these three layers, not others | v3 §1 |
| 4 | L0 · Engineering Gravity Field | The foundation before AI enters | v7 §04 |
| 5 | Leap ① · State Visible | From code → state | v7 §05 + v3 §8 |
| 6 | Bridge · Signal → Intent | L1 to L2 | v7 §06 |
| 7 | Leap ② · Intent Expressible | From command → intent | v7 §07 + v3 §6.4 |
| 8 | Bridge · Intent → Execution | L2 to L3 | v7 §08 |
| 9 | Leap ③ · Autonomous Loop | From inference → continuous self-governance | v7 §09 + v3 §6 |
| 10 | Autonomy Gradient R0–R5 | Delegate reversible actions to AI | v7 §10 |
| 11 | Full Loop · Order Group-Buy Case | End-to-end walkthrough | v7 §11 |
| 12 | Anti-Patterns and Boundaries | When to stop | v7 §12 + v3 §11 |
| 13 | Role Evolution | Where humans go | v7 §13 + v3 §10 |
| 14 | Measurement Framework | How we know it's improving | v3 §12 |
| 15 | Future Shape | The 2030 engineer | v7 §14 |
| 16 | Value Finale | Enterprise / Individual / AI | v7 §15 |
| Appendix A | Capital · C/V/M Mapping | Value-flow analysis | v3 §3 |
| Appendix B | V-Model in the AI Era | Verification re-armament | v3 §4 |
| Appendix C | CALMS · DORA · Kanban | Flow execution rhythm | v3 §5 |
| Appendix D | MDM Declarative Paradigm Leap | Philosophical foundation | v3 §6 |

### One-Line Thesis

At every delivery moment, every AI-generated artifact is simultaneously **Needed, Trusted, and Understood**.

### SCQA

- **Situation**: AI coding has driven marginal production cost toward zero
- **Complication**: Human review capacity is linear; AI code defect rate is ~3× higher than human-written code
- **Question**: How do we keep the organization Needing, Trusting, Understanding its artifacts without throttling AI throughput?
- **Answer**: First build the engineering gravity field (L0), then make module state visible (L1), then make business intent declarable (L2), then let the system self-converge (L3) — three leaps stacked layer by layer, placing AI inside a trustworthy engineering system.

---

## 1 · The Current Tension

### 1.1 Code generation has outpaced human verification

```
capability
   ↑
   │           AI coding output
   │         /  exponential growth
   │        / ┌───────────────┐
   │       /  │ capability gap │
   │      /   └───────────────┘
   │     /  ─ ─ ─ ─ ─ ─  human review
   │    /   ─ ─ ─ ─ ─ ─  linear growth
   │   /
   │  /
   └─────────────────────────→ time
```

Sonar research: **AI code defect rate is ~3× higher than human-written code**. When AI output grows exponentially while human review grows linearly, the capability gap is not a temporary staffing shortage — it is structural.

### 1.2 Three Decays

Software assets are simultaneously eroded by three forces:

| Decay | Source | Symptom | Cost of failure |
|---|---|---|---|
| **Value decay** | Business shifts, stale requirements | Features no longer used | Assets rot into zombie code |
| **Architecture decay** | Dependency rot, entropy | Modules entangle each other | Codebase rots into a big ball of mud |
| **Knowledge decay** | Staff churn, lost context | "Legacy code no one dares to touch" | Quality rots into technical debt |

AI acceleration **amplifies all three decays simultaneously** — it writes fast, but it also writes things that aren't needed, that violate boundaries, that no one understands.

### 1.3 The purpose of governance: Needed / Trusted / Understood

| Three states | Decay it counters |
|---|---|
| Needed | Value decay |
| Trusted | Architecture decay |
| Understood | Knowledge decay |

**Conclusion**: We can't just let AI accelerate — we must place AI inside a trustworthy engineering system.

---

## 2 · The Map: Three Layers × Three Leaps

```
            L3 · AUTONOMOUS LOOP                  ← Leap ③ system self-converges
            Harness · Agent · Reconciliation         (Apple DDM paradigm reborn)
                       ▲
                       │
            L2 · INTENT EXPRESSIBLE               ← Leap ② intent expressible
            INTENT → CONTRACT → VERIFIER             (business intent → declaration)
                       ▲
                       │
            L1 · STATE VISIBLE                    ← Leap ① state visible
            identity · 5-state FSM · 3-D health      (systems engineering · DDD)
                       ▲
                       │
       ╔═══════════════════════════════════════╗
       ║ L0 · GRAVITY FIELD                    ║ ← Engineering gravity field
       ║  framework · module identity · CI/CD  ║   (foundation · NOT a phase)
       ║  · runtime · DevOps · sandbox         ║   precondition
       ╚═══════════════════════════════════════╝   skip L0 = AI in a swamp
```

### 2.1 Reading conventions

- **L0 is foundation, not phase**: it precedes everything; without it, leaps are impossible
- **L1 → L2 → L3 are leaps**: each one is a paradigm change, not incremental upgrade
  - Leap ① from code → state
  - Leap ② from command → intent
  - Leap ③ from one-shot inference → continuous self-governance
- **L0–L3 are not sequential phases, they are collaborative layers**: after going live, every layer is working at the same time (see §11)

### 2.2 What's inside each leap

```
Leap ③ internals: HARNESS → AGENT → RECONCILE → GRADIENT → SIGNAL
Leap ② internals: INTENT FILE → CONTRACT → VERIFIER
Leap ① internals: IDENTITY → 5-STATE FSM → 3-D HEALTH
```

### 2.3 Running case throughout

Every chapter below uses the same case to anchor the abstraction: **the order service supports a group-buy feature**.

---

## 3 · First-Principles Derivation

> This system is not an empirical checklist — it is a closed system derived from 4 irreducible facts. If any later mechanism feels "plausible but I don't know why," return to this chapter.

### 3.1 Four irreducible facts

| Fact | Statement | Supporting evidence |
|---|---|---|
| F1 | The marginal cost of AI coding approaches zero | LLM compute scaling is industry reality |
| F2 | Human review capacity grows linearly, cannot follow AI throughput | Sonar: AI code defect rate ~3× human |
| F3 | Software assets undergo value/architecture/knowledge triple decay | Business change / dependency rot / staff churn |
| F4 | Organizational survival depends on accumulating trustworthy assets; untrustworthy assets are liabilities | Marx's "congealed labor" + engineering practice |

These four facts cannot be decomposed into more basic propositions — they are the "physical constraints" of the AI-coding era.

### 3.2 From facts to three axioms

| Derivation | Axiom |
|---|---|
| F2 + F4 → AI output must align with intent | **Axiom 1: Intent Fidelity** |
| F2 + F3 → AI decisions must be rollback-able | **Axiom 2: Action Reversibility** |
| F1 + F3 + F4 → Quality must be encoded into the system, not patched in afterward | **Axiom 3: Quality Emergence** |

### 3.3 From axioms to three pillars

| Axiom | Pillar | Engineering axis | Cost of failure |
|---|---|---|---|
| Intent Fidelity | **Value Anchoring** | Time | Zombie code |
| Action Reversibility | **Boundary Control** | Space | Big ball of mud |
| Quality Emergence | **Built-in Process** | Causality | Technical debt |

The three pillars work on three independent axes — time/space/causality — and they are **two-by-two orthogonal and jointly exhaustive**. A single pillar's collapse produces a distinct failure mode.

### 3.4 Mapping axioms onto the three leaps

| Axiom | Where it directly lands |
|---|---|
| Axiom 1 Intent Fidelity | **Leap ② Intent Expressible** (turn intent into a verifiable contract) |
| Axiom 2 Action Reversibility | **Leap ③ Autonomous Loop + R0–R5 gradient** (delegate by reversibility) |
| Axiom 3 Quality Emergence | **L0 + Leap ① State Visible** (encode quality into substrate and state machine) |

### 3.5 Why L0 is not a leap

A "leap" implies a paradigm change. L0's six items (framework / module identity / CI / runtime / DevOps / sandbox) are all **explicit, automated versions of classical software engineering** — they are physical constraints, not paradigm leaps.

Calling them "foundation" rather than "phase 1" prevents organizations from treating L0 as an entry-level checkpoint to rush past. **Without L0, the leaps are just slideware.**

> **What this section answers**: This is the reasoning engine — proof that the three leaps are not a choice, they are a necessity.

---

## 4 · L0 · Engineering Gravity Field (Precondition · NOT a Phase)

> Before placing AI inside a system, you must first build the "system" — this is a physical-law constraint.

L0 has six pillars. The first three continue classical engineering governance; the latter three are re-emphasized in the AI era:

| # | Pillar | Content | Why it matters in the AI era |
|---|---|---|---|
| 01 | **Framework** | Domain abstraction · contract skeleton · quality substrate | Better framework · greater AI value |
| 02 | **Module identity** | `module.yaml`: identity · intent · state · signals | The entry point to Leap ① |
| 03 | **CI/CD gates** | lint · type · test · contract · sec scan | Left side accelerated 100× · right side re-armed 3× |
| 04 | **Runtime** *(NEW)* | Containers · K8s · service mesh · registry | AI-written code must actually run |
| 05 | **DevOps stack** *(NEW)* | deploy · log · trace · metric · secret · alert | When AI errs · rollback must be seconds |
| 06 | **Sandbox** | Isolation · observability · DDD bounded contexts | AI experiments only inside the sandbox |

### 4.1 Framework: the machine tool

Borrowing v3's Capital-theoretic view: **the framework is the most highly congealed constant capital (C)**.

| Framework function | Cost of failure |
|---|---|
| Domain isolation (physical boundaries of bounded contexts) | Modules entangle; refactor cost grows quadratically over time |
| Base abstractions (storage / messaging / auth / observability) | Adapter sprawl; dependency chaos |
| Contract skeleton (API / event / error code standards) | Modules cannot interoperate |
| Quality substrate (test base classes / mocks / sandbox / archtest) | Every module reinvents the wheel |

> Excellent framework × 100 modules = 100 high-quality outputs
> Missing framework × 100 modules = 100 messes (chaos replicated at the same speed)

#### Framework is not a single capability — it is the cumulative output of the entire L0 layer

The four functions cannot all be in place at one time:

```
Blueprint (pre-ADR + 3-tier skeleton + SDK signatures + contract location + test-base placeholder)
   ↓
CI lets lint/test/build run on the skeleton (constraints start being enforced)
   ↓
hello-world routes through the skeleton, not naked code (blueprint validated runnable)
   ↓
Domain layering fills the skeleton (skeleton becomes content-bearing)
   ↓
archtest turns README boundaries into machine rules (constraints truly bind)
                            ↓
        Complete framework = blueprint + 6 enforced capabilities
```

**Important**: the framework's "constraints" need CI and archtest to enforce them. Without enforcement, the framework is just README text — **any AI autonomy promise built on top stands on loose constraints**. This is the shared root of anti-patterns A1 (over-governance) and A3 (gradient breach).

See [`three-leaps-bootstrap.en.md` §3](./three-leaps-bootstrap.en.md#3--l0--engineering-gravity-field-foundation) for the staged construction path and the P0.0 blueprint capability.

### 4.2 Module identity: `module.yaml`

Every module must carry a machine-readable identity card. This is the entry point to Leap ① — without manifests, you can't even say "which module is failing."

```yaml
module:
  name: order-service.group-buy
  domain: order

intent:
  goal: group-buy ordering
  metric: GMV ↑ 15%

contracts:
  exposed: [GroupOrder]
  consumed: [payment.coupon]

lifecycle:
  state: experimental   # → candidate → asset → maintenance → retired

signals:
  collected_by: [ci, otel, sonar]
```

### 4.3 CI/CD gates: left-accelerated × right-rearmed

The V-model in the AI era (see Appendix B):

```
   Left side accelerated 100×             Right side re-armed 3×
   AI coding in seconds  ───────────►    static analysis + fuzzing + contract + formal verification
```

CI/CD is not "lint runs once" — it is **5–7 layers of independent gates in series**: lint → type → test → contract → sec scan → SBOM → coverage gate.

### 4.4 Runtime (NEW · v7 emphasis)

AI-written code must actually run — not merely look correct. This requires:

- Containerization (Docker / OCI image)
- Orchestration (Cloud Run / Container Apps / K8s, scaled to size)
- Service mesh (mTLS / traffic mirroring / canary routing)
- Image registry + provenance

**Anti-pattern**: AI writes code, PR merges, but no runtime verification — equivalent to letting AI write code on a whiteboard.

### 4.5 DevOps stack (NEW · v7 emphasis)

When AI errs, rollback must take seconds. This requires:

| Capability | Purpose |
|---|---|
| Deploy (progressive delivery) | canary 1% → 10% → 50% → 100% |
| Logs (structured JSON) | Trace AI decision paths after the fact |
| Tracing (OTel) | Cross-service fault localization |
| Metrics (SLI/SLO + budget) | Objectively judge "is it good" |
| Secrets management | AI should never see plain-text credentials |
| Alert + on-call | Drift detected early |

**Rollback is the physical foundation of the R-gradient**: R1–R3 can be delegated to AI precisely because seconds-level rollback exists. Without the DevOps stack, the entire §10 autonomy gradient is hollow.

### 4.6 Sandbox: controlled trial-and-error

AI must experiment in a sandbox first, then unlock permission level by level:

- Isolation (namespace / network policy / resource quota)
- Observability (every action inside the sandbox is auditable)
- DDD bounded contexts (the sandbox is itself a bounded experimental site)

### 4.7 Capital view: L0 = the most highly congealed C

All six L0 pillars are "congealed past labor." Every additional ounce of effort organizations invest in L0 raises AI's output precision in L1–L3 by a tier.

> **What this section answers**: L0 is a physical-law constraint. Skipping L0 = placing AI in a swamp.

---

## 5 · Leap ① · State Visible (L1)

> From code → state. Every module has identity, a state machine, and health-signal scores.

### 5.1 Two dimensions

L1 is not just "tag a state on a single module" — it establishes two dimensions simultaneously:

| Dimension | Content | Cost of failure |
|---|---|---|
| **Single-module lifecycle** | 5-state FSM + 3-D health | Cannot judge "should this module still be alive" |
| **Inter-module composition** | System composition view + contract graph | Modules without system assembly = systems engineering failure |

### 5.2 Five-state machine

```
intent → experimental → candidate → asset → maintenance → retired
                                                          ↓
                                                  tombstone (24h soft-delete)
       │              │           │              │
       value review   biz signal  human + gates  biz decay
```

| State | Entry condition | Rollback path |
|---|---|---|
| experimental | Intent passes value review | Delete skeleton + close intent |
| candidate | Business signals ≥ threshold + smoke pass | Back to experimental |
| asset | Full gates passed + human approval | Back to candidate |
| maintenance | Business signals decay but dependencies remain | Reactivate to asset |
| retired | No dependencies + business signals zero | Recoverable within 24h |

**Tombstone**: module name / final version / outward contract snapshot / dependency snapshot / retirement reason / retirement date / 24h soft-delete window. A tombstone is an "auditable death certificate," not a one-line log.

### 5.3 Three-dimensional health score

```
value score    = w1·active demands + w2·contract subscribers + w3·traffic     (0-100)
structure score= w1·framework compliance + w2·boundary consistency + w3·contracts  (0-100)
engineering    = w1·coverage + w2·build pass rate + w3·activity decay-weighted  (0-100)
```

**Derived signals**:
- Health warning: any dimension < 30
- Forced retirement suggestion: any dimension < 10
- Mandatory human review: all three < 50 for two weeks

### 5.4 Signal collection (mechanized checklist)

| Dimension | Signal | Collection method |
|---|---|---|
| Business | Active demand count / contract subscribers / traffic reach | Demand system API + traffic instrumentation |
| Architecture | Framework usage compliance / cross-domain dependencies / contract registry consistency | Static analysis + archtest |
| Engineering | Test coverage / build pass rate / defect density / activity decay-weighted | CI + git + defect tracking |

**Strictly forbidden**: humans filling in signals by hand. All signals must be mechanically collected derived quantities.

### 5.5 System composition view

A single module's health does not equal system health. L1 must simultaneously maintain the **module composition graph**:

```
user-svc ──► [order.group-buy] ──► payment.coupon
                  │                       │
                  ├──► notify-svc         │
                  └──► inventory          │
                  contract: GroupOrder ◄──┘

SYSTEM · 5 hops assembly · weakest node 65 ──► system score ≠ module mean
```

System score = min(weakest dimension across all modules in the chain), not the mean. **A 65-point critical dependency drags down the entire chain.**

### 5.6 Case: current state of the group-buy module

```
case · order-service.group-buy
state · candidate (collecting business signals)
3-D health · value 80 · structure 65 · engineering 90
```

L1's output is **state visibility** — the next step is to declare intent on top of it (→ §6 bridge).

> **What this section answers**: Leap ① turns every module from code into an observable object.

---

## 6 · Bridge · Signal → Intent (L1 → L2)

> Seeing state → enables describing intent. L1 turns each module into an "observable object" · L2 turns each change into a "declarable event."

### 6.1 Raw signals are a data deluge

```
L1 OUTPUT · signals
─────────────────────────────────────
order-service.discount · call rate ↓ 73% / 30d
order-service.group-buy · error rate 2.1%
payment.coupon · health 91 / 90 / 88
…live portraits of hundreds of modules

→ no direction · cannot act
```

Live portraits of hundreds of modules, without "what they should be" as a comparison baseline, are just noise.

### 6.2 Intent turns signals into judgments

```
L2 INPUT · intent
─────────────────────────────────────
"Let the order service support group-buy,
 with coupon-code payment, p99 < 200ms"
                    │
                    ▼ AI translation
contract: POST /orders/group
sla.p99: 200ms · sla.error: 0.5%
depends_on: payment.coupon (≥85)
success: signals.usage ≥ 1k/d
```

Now every signal can be compared:
- error rate 2.1% vs sla.error 0.5% → divergent
- payment.coupon health 88 ≥ 85 → satisfied

### 6.3 The bridge thesis

> **Without L1's state visibility, L2's intent is just a blank check.**

Intent cannot be declared in a vacuum — it must be grounded in "what is real now." The L1→L2 bridge guarantees intent is always rooted in reality.

---

## 7 · Leap ② · Intent Expressible (L2)

> From command → intent. Not by directly applying MDM — by re-embedding the "declare + converge" paradigm at the code layer.

### 7.1 Intent file: four-block structure

The intent file is not an abstract concept — it is these four blocks:

```
┌─────────────────────────┬─────────────────────────┐
│ 01 · BUSINESS           │ 02 · CONTRACT           │
│ business intent         │ technical contract      │
│ goal: group-buy ordering│ api: POST /orders/group │
│ metric: GMV ↑ 15%       │ schema: GroupOrder      │
│ deadline: 2026-Q2       │ events: [GroupCreated]  │
├─────────────────────────┼─────────────────────────┤
│ 03 · QUALITY            │ 04 · LIFECYCLE          │
│ quality thresholds      │ lifecycle               │
│ p99: 200ms              │ state: candidate        │
│ error: < 0.5%           │ sunset_if: usage<100/d  │
│ coverage: ≥ 95%         │ review_at: 30d          │
└─────────────────────────┴─────────────────────────┘
```

Every field maps directly to a verifier (see §7.3).

### 7.2 Creative application of MDM

Not directly applying Apple DDM — **borrowing the paradigm by isomorphism**:

| Apple DDM (device management) | Software module governance |
|---|---|
| Declaration | Intent file |
| Reconciliation | Drift detect + AI agent loop |
| Convergence | Continuous convergence toward intent |
| Predicates | Signal-threshold conditions |
| Status channels | Three-dimensional health write-back |

**Isomorphic, not identical**: devices pull declarations · modules pull intents; devices auto-configure · modules self-evolve.

### 7.3 Direct field-to-verifier binding

Not documentation · executable:

| Intent field | Auto-bound verifier |
|---|---|
| `sla.p99: 200ms` | k6 performance test, regression fails |
| `contract: GroupOrder` | Contract test (pact / openapi diff) |
| `coverage: ≥ 95%` | New-code coverage gate |
| `sunset_if: usage<100/d` | Reconciler scheduled check + auto alert |
| `depends_on: payment.coupon (≥85)` | Composition view health linkage |

### 7.4 What business need does this solve

> **The group-buy requirement** is no longer a PRD doc + scheduling meeting + Jira ticket — it is an intent file that simultaneously declares, delivers, and monitors.

This is the real grounding of v3 §6 "paradigm leap": from "humans inside the decision loop" to "humans inside the desired-state-definition loop."

> **What this section answers**: Leap ② turns intent into a verifiable, convergent, auditable engineering object.

---

## 8 · Bridge · Intent → Execution (L2 → L3)

> Once you declare → you need an "executor." L1's state machine says "where we are now" · L2's intent says "where we want to go" · L3's Harness is "how to automatically get there."

### 8.1 Drift detect: gap between declaration and reality

```
┌────────── DESIRED STATE ──────────┐    ┌─── CURRENT STATE (L1) ───┐
│ group-buy ordering                 │    │ api: not implemented      │
│ p99 200ms · 95% cov                │    │ delta: missing            │
│ contract: GroupOrder               │    └───────────────────────────┘
└────────────────────────────────────┘                │
                    │                                  │
                    └─────► drift detected ◄──────────┘
                          desired ≠ current
```

Only when desired ≠ current is an "executor" needed. The essence of reconciliation is **closing the drift**.

### 8.2 AI Agent · autonomous task loop

```
01 · read intent + current signals
02 · plan tasks · decompose steps
03 · invoke tools inside Harness
04 · write code · run tests · self-verify
05 · open PR · wait for gates · collect signals
06 · failed → back to 01
```

Until desired = current (CONVERGED), the loop continues.

### 8.3 The bridge thesis

> **L2 without L3 is just a promise written on paper.**

Declaration alone won't make the group-buy feature live. You need an executor that translates intent into PRs, runs tests, and retries on failure. That executor is the next chapter's **Harness + Agent**.

---

## 9 · Leap ③ · Autonomous Loop (L3)

> From one-shot inference → continuous self-governance. The Agent's context and progress can be **progressively disclosed** from L1 system state — they don't have to be conjured from nothing.

### 9.1 Harness is the engineering shell, not a prompt

> **The key** is not a smarter AI · it is a more stable "shell + heartbeat."

Harness Five-Pack (based on Anthropic's official guidance):

| Component | Purpose |
|---|---|
| **System context** | Inject project knowledge, constraints, conventions (CLAUDE.md / cursor rules) |
| **Tool constraints** | Fail-closed permissions + command blocklists |
| **Context injection** | Agent Skills + Progressive Disclosure |
| **Memory & progress** | Cross-session state preservation (git log + ADR + memory) |
| **Evaluation loop** | Continuous convergence, not one-shot inference (CI green + eval suite) |

### 9.2 Progressive disclosure: context comes from L1 system state

The Agent's context need not be conjured from nothing — **most of it comes from L1's already-recorded system state**:

```
L1 STATE · source                          HARNESS · engineering shell
┌──────────────────────┐                   ┌─────────────────────────┐
│ system design (DDD)  │                   │      AGENT · brain       │
│ API · contract       │   progressive     │      AI agent            │
│ UI design (tokens)   │   ─────────────►  │      plan · act · obs   │
│ progress (tasks/PRs) │                   │                         │
│ health (3-D scores)  │                   │   TOOLS·constrained EVAL·heartbeat │
│ ALL RECORDED         │                   │   whitelisted actions   self-verify│
└──────────────────────┘                   └─────────────────────────┘
                                                     │
        ┌────────────── write back ◄───────────────┘
        │
        ▼
   RECONCILE · system state converges to intent · ∞ loop
```

This is why §5 and §6 must come first — L1's state visibility is the source of L3 Harness context.

### 9.3 Isomorphic to K8s controllers / Apple DDM

L3 is not a new paradigm — it borrows mature ones:

| Dimension | Apple DDM | Kubernetes | L3 software governance |
|---|---|---|---|
| Desired state | Declarations | CRDs | Intent file |
| Pull mechanism | Device pulls | Controller watches | Reconciliation agent |
| Conditional application | Predicates | Label selectors | Signal thresholds |
| Status reporting | Status channels | Status subresources | 3-D health |
| Offline behavior | Offline self-maintains | Controller restart idempotent | Soft-delete window + tombstone |

### 9.4 Reconciliation Loop pseudocode

```
loop:
    1. pull module manifests + intent files
    2. collect signals (CI / git / dependency / traffic)
    3. compute current health score (3-D)
    4. detect drift (current vs desired)
    5. choose remediation strategy: PATCH or REPLACE
         PATCH (apply patch) ── fits: localized drift / sound module structure / low fix cost
         REPLACE (rewrite)   ── fits: systemic drift / framework has evolved / rewrite cost ≤ patch cost
                              ↳ Module-as-commodity (see §10.6): under strong framework
                                constraints, regenerating from scaffolding + letting intent
                                drive AI to write a fresh one is often more controllable
                                than patching years of accumulated patches
    6. apply remediation, delegated by reversibility R0–R5:
         R0–R1 (read-only / experimental): AI executes directly
         R2 (controlled external): AI auto-released + audit log
         R3 (cross-domain write): AI proposes + review (see §10.5 for reviewer evolution)
         R4 (user impact): blocked + mandatory human decision
         R5 (financial / physical): never granted
    7. report status to dashboard + decision audit store
    8. state changes feed back to L1 · input for next cycle
```

> **What this section answers**: Leap ③ turns "one-off prompts" into "continuously running environment-level feedback control systems."

---

### 9.5 Multi-agent multi-model · ensemble play

> Single agent / single model is v7's initial stance. With a strong-enough framework and quality substrate, **every step of intent → state → module → launch can be run in parallel by multiple agents and multiple models, racing → winning combination chosen.**

#### 9.5.1 Why ensemble

Different models have different strengths (long context / reasoning depth / coding precision / tool use / vision); a single model is suboptimal at every stage. Letting multiple models specialize: **combined strengths > strongest single model.**

#### 9.5.2 Stage-by-stage ensemble examples

| Stage | How to use multiple agents | Selection rule |
|---|---|---|
| Intent comprehension | Long-context model (Gemini 2M) parses PRD + reasoning model (Claude) extracts intent.yaml + verifier model cross-checks | All three agree → pass; disagree → escalate to human |
| Module implementation | 3 agents implement in parallel → run same test suite | PR with highest coverage + perf wins |
| Code review | Security agent + perf agent + arch agent + style agent in parallel | Composite score; any critical issue blocks |
| Launch decision | Reconciler combines multiple independent health-score evaluations | Majority rules; minority dissent enters audit |

#### 9.5.3 Selection strategy encoded in intent

```yaml
intent:
  execution:
    strategy: race | majority | ensemble | tournament
    # race       = multiple agents race; first to pass wins
    # majority   = multi-model vote, majority rules
    # ensemble   = weighted combination of multiple outputs
    # tournament = multiple elimination rounds, best wins
    judges:
      - model: claude-opus-4-7
        role: architecture compliance
      - model: claude-sonnet-4-6
        role: performance optimization
      - model: gpt-5
        role: security risk
    quorum: 2/3      # threshold for release
```

#### 9.5.4 Capital-theoretic view: V multiplied

Single agent = 1× V; ensemble = N× V, but **you only pay for the highest-quality output**. The other N–1 drafts become "scrap," but at the system level the cost is often far lower than human rework. **The key is: token cost < human cost × reworks saved.**

#### 9.5.5 Anti-patterns

- **Blind voting** — if different models share highly homogeneous training data, majority rule degenerates to single rule; pick judges with model heterogeneity
- **Judge = player** — same model both writes and reviews code, drifts toward self-rationalization; the judge must be an independent model
- **Infinite rounds** — tournament must have a max-round cap, otherwise it loops forever

> **What this section answers**: Ensemble play evolves v7's "AI soldier" into "AI cluster" — this is §10's R-gradient in parallel form: **the same reversible action, multiple agents racing → best wins.**
>
> **§9.5 is the engineering implementation of §10.5**: when the independent AI reviewer agent is played by "another model," §9.5's "the judge must be an independent model" principle provides the credibility §10.5's "independent AI review" needs.

---

## 10 · Autonomy Gradient R0–R5

> Not "AI in full control" · but "AI taking over reversible actions." Give reversible actions to AI · keep irreversible actions for humans — that is true liberation.

### 10.1 Six levels

```
REVERSIBILITY
reversible ←─────────────────────────────────────────────────► irreversible

┌─────────┬─────────┬─────────┬─────────┬─────────┬─────────┐
│ R0 READ │ R1 LOCAL│ R2 CTRL │ R3 CROSS│ R4 USER │ R5 IRREV│
├─────────┼─────────┼─────────┼─────────┼─────────┼─────────┤
│ read-   │ local   │ sandbox │ modify  │ delete  │ funds   │
│ only    │ edits   │ APIs    │ other   │ data    │ physical│
│ inspect │ own     │ test    │ services│ change  │ device  │
│ propose │ repo    │ env     │ migrate │ billing │ control │
├─────────┼─────────┼─────────┼─────────┼─────────┼─────────┤
│ AI auto │ AI auto │ AI auto │ AI prop │ human · │ human · │
│         │         │ release │ + human │ never   │ red     │
│         │         │         │ review  │ granted │ line    │
│ no human│ git roll│audit log│ staged  │human    │never    │
│         │         │         │rollout  │ gate    │  auto   │
└─────────┴─────────┴─────────┴─────────┴─────────┴─────────┘
```

### 10.2 Mapping gradient to Harness configuration

| Level | Harness configuration | Safety net |
|---|---|---|
| R0 read-only | Context + evaluation only | Writes nothing |
| R1 local edits | + Restricted file editing tool | git rollback |
| R2 controlled external | + Sandbox API + test env write | Audit log + sandbox isolation |
| R3 cross-domain write | + Cross-service / migration permissions | Staged rollout + human review |
| R4 user impact | – | Human gate · never granted |
| R5 financial / physical | – | Never auto · red line |

### 10.3 Permanent boundary

**R5 is never granted** — this is the system's hard boundary regardless of organizational trust or AI capability.

R4 in even the long-term vision phase remains "block + force human decision," not within automation.

### 10.4 Gradient breach = catastrophe

Handing R4/R5 to the Agent is the core symptom of anti-pattern A3 "Gradient Breach" (see §12). **Anti-pattern cost rises with layer** — L0 breach is waste, L3 breach is incident.

> **What this section answers**: The R-gradient turns "AI autonomy" from a slogan into an executable, auditable engineering parameter with a red line.

---

### 10.5 Reviewer evolution (v7+ direction)

> R3 = "AI proposes + human review" in §10.1's table is **v7's initial stance**. With a strong-enough framework and DevOps stack, **the "human review" itself can evolve** — not by abandoning review, but by freeing the reviewer from being the bottleneck.

#### Three reviewer kinds

| Reviewer | Fits | Cadence | Trust source |
|---|---|---|---|
| **Human review** | Framework / contract / spec changes (meta layer) | Slow but authoritative | Seniority + accountability |
| **Independent AI review** | Instance code changes (within the framework) | 24×7 | Model heterogeneity + strong framework + health-score safety net |
| **Multi-agent cross-review** | High-disagreement / high-risk scenarios | Parallel | Multi-model majority vote (see §9.5) |

#### Boundaries between the three

> **Key**: upgrading the reviewer ≠ removing review. The three reviewer kinds coexist across different scenarios.

```
┌────────────────────────────────┬────────────────────────────────┐
│  Human review preserved (never │  AI review can take over       │
│  goes away)                    │                                │
├────────────────────────────────┼────────────────────────────────┤
│ · L0 framework changes         │ · Instance code (within the    │
│   (affects all modules)        │   framework boundary)          │
│ · New boundary rules between   │ · Verification scenarios bound │
│   R3 → R4                      │   to intent.yaml fields        │
│ · Changes to the R-gradient    │ · Routine changes covered by   │
│   itself                       │   health thresholds            │
│ · ADR-level decisions          │ · OOB attempts already caught  │
│ · Anything touching R4/R5      │   by archtest                  │
│                                │ · Changes safe under staged    │
│                                │   rollout                      │
└────────────────────────────────┴────────────────────────────────┘
```

#### R3 upgrade prerequisites (all four must hold)

1. **Complete L0 framework in place** — archtest / contract / quality substrate all enforced
2. **DevOps stack in place** — seconds-level rollback + canary + 3-D health + on-call
3. **Independent reviewer agent** — uses **heterogeneous models** vs the coding agent, avoiding judge = player (echoes §9.5.5 anti-pattern)
4. **Complete decision audit** — every AI autonomous decision is structurally queryable, post-hoc replayable

When met, R3 evolves:

```
v7 initial R3:  AI proposes + human review
   ↓ once prerequisites met
v7+ R3:        AI proposes + independent AI review (multi-agent cross-review)
               + health-score safety net + reversible
   ↓
R4/R5:         Never change — human review / never granted
```

> **What this section answers**: Turn "human review" from a fixed role into an **engineerable bottleneck that can be upgraded** — provided strong framework + heterogeneous models + health-score safety net are all in place.

---

### 10.6 Module-as-commodity — economics of patch vs replace

> A module is a commodity stamped out on the framework machine tool. Under quality-substrate constraints, **"fix" is no longer the default option — "rewrite the whole module" is often the more economical fix.**

#### Why "fix-first" used to be the rule

Traditional software engineering defaulted to patch over replace because:

- Average module dev cost = several person-weeks
- Rewrite = re-paying the entire dev cost
- Rewrite-failure risk ≥ patch-failure risk

#### Why v7+ enables "replace-first"

Three preconditions changed the economics:

| Precondition | Cost impact |
|---|---|
| **L0 strong framework constraints** | Modules start from scaffolding, reuse framework SDKs / contracts / test substrate → rewrite cost ↓ 70%+ |
| **L2 intent fully executable** | intent.yaml is the module's "DNA" — rewrite is essentially "regenerate from intent via AI" |
| **L3 multi-agent ensemble** | Same intent rewritten by N agents in parallel → best wins (§9.5) → rewrite time drops from days to hours |

#### Reconciler decision point: patch or replace

```
when drift detected:
    if drift_localized AND patch_cost < replace_cost:
        propose PATCH                    # traditional path
    elif framework_drifted_significantly OR
         module_age > 6mo AND patch_count > 10 OR
         intent_has_changed_substantially:
        propose REPLACE                  # new path
                                         # NB: REPLACE still flows through
                                         # the R-gradient and §10.5 reviewers
```

#### Anti-patterns

- **Replace addiction** — every bug becomes a rewrite: surrenders patch's cost advantage on small changes
- **Replace without touching intent** — rewrite but don't update intent.yaml: same requirement produces the same bug
- **Replace bypassing review** — treating replace as R0 auto-execute: replace cost ≥ patch, must traverse the same R-gradient

> **What this section answers**: Module replaceability is the new engineering economics enabled by v7+. **Framework is the machine, modules are the commodities** — a broken commodity gets replaced, the machine doesn't move. This is the natural corollary of §4.1's Capital-theoretic C/V view.

---

## 11 · Full Loop · Order Group-Buy Case

> L0 → L1 → L2 → L3 are not phases, they are collaboration — at the same time, every layer is working.

### 11.1 One requirement from declaration to live

```
┌────────────┬────────────┬────────────┬────────────┬────────────┐
│ STEP 1·L2  │ STEP 2·L3  │ STEP 3·L0  │ STEP 4·L3  │ STEP 5·L1  │
│            │            │            │   GATE     │            │
├────────────┼────────────┼────────────┼────────────┼────────────┤
│ human      │ Agent      │ gates+test │ human PR   │ go live    │
│ writes     │ takes over │ CI/CD      │ R3·cross   │ enter FSM  │
│ intent     │ reads intent│ contract   │ 5 evidence │ candidate  │
│ "group-buy"│ decompose  │ check      │ 1-click    │ → asset    │
│ + p99 200ms│ write code │ 3 fail→fix │ release    │ observe 30d│
├────────────┼────────────┼────────────┼────────────┼────────────┤
│ 3 min      │ 22 min     │ 9 min      │ 5 min      │ continuous │
│ human · L2 │ AI auto    │ system·auto│ human·gate │ system·evolve│
└────────────┴────────────┴────────────┴────────────┴────────────┘

TOTAL · 39 MIN HUMAN-BLOCKING + ∞ SYSTEM-AUTO
For comparison · same requirement, traditional flow: 3 weeks scheduling + 4 meetings + 2 reworks
```

### 11.2 Which layer each step works in

| Step | Primarily in | Also in |
|---|---|---|
| 1 Write intent | L2 | L0 (intent file passes schema check) |
| 2 Agent takes over | L3 | L1 (reads current signals) + L0 (sandbox execution) |
| 3 Gates + tests | L0 | L1 (health updated) + L3 (drift loop monitoring) |
| 4 Human PR review | L3 gate | L0 (CI data as approval evidence) |
| 5 Go live | L1 FSM | L3 (continuous reconciliation) |

### 11.3 Key insight: collaboration ≠ phases

The waterfall mental model treats L0–L3 as sequential dependencies — first build L0, then L1. **The v7 view is collaboration**:

- L0 is 24×7 running foundation, used in every PR
- L1 is 24×7 updating state machine, every module produces new signals every second
- L2 is the declaration layer used every time a developer writes an intent
- L3 is the 24×7 reconciliation agent loop

**At the same time, every layer is working** — that is the real form of "system self-convergence."

### 11.4 Case outcomes

| Dimension | Traditional flow | Three-leaps full loop |
|---|---|---|
| Human-blocking time | 3 weeks + 4 meetings + 2 reworks | 39 minutes |
| Decision record | Scattered in Jira / Slack / email | Intent file + decision audit store |
| Post-launch traceability | From memory | trace_id + 3-D health + state machine |
| Retirement judgment | No one dares to touch | sunset_if auto-triggers |

> **What this section answers**: The full loop is the only test of whether the entire system actually works — completing one real requirement in 39 minutes.

---

## 12 · Anti-Patterns and Boundaries

> Every leap has its failure modes · knowing the boundaries matters more than knowing the methods.

### 12.1 Anti-patterns by "stage × consequence"

```
consequence ↑                        ANTI-PATTERNS
CATASTROPHIC                                       ┌─────────────┐
                                                    │ A3 Gradient │
                                                    │ Breach      │
                                                    │ R4/R5 to AI │
                                                    │ → disaster  │
                                                    └─────────────┘
SYSTEMIC               ┌─────────────┐
                       │ A2 Intent ≠ │
                       │ Execution   │
                       │ declared but│
                       │ unverified  │
                       └─────────────┘
REVERSIBLE  ┌─────────────┐
            │ A1 Over-    │
            │ governance  │
            │ gates > code│
            └─────────────┘
              L0          L1          L2          L3 →
              Gravity     State       Intent      Autonomous
              field       visible     expressible loop

                     ↗ higher layer · greater cost of breach
```

### 12.2 Seven anti-patterns (v3 + v7 merged)

| # | Anti-pattern | Symptom | Correction |
|---|---|---|---|
| A1 | **Over-governance** | Experimental modules also run full gates; governance time > coding 30% | Strict tiering, prefer leniency over uniformity |
| A2 | **Intent ≠ Execution** (declared but unverified) | intent.yaml goes unchecked; declaration becomes decoration | Field-bound verifiers (§7.3) |
| A3 | **Gradient breach** | R4/R5 also delegated to Agent; irreversible disaster | R5 never granted; R4 forced human decision |
| A4 | **Signal fill-in** | Humans manually fill business signals | Must be mechanically collected |
| A5 | **AI suggestion worship** | Acceptance rate 100%, rejection 0% | Healthy rejection rate ≥ 10% as floor |
| A6 | **State machine rigidity** | Modules stuck in one state for half a year | Add "overdue migration" alerts |
| A7 | **Approval ritualism** | Click approve without checking evidence | Mandate "evidence checked" toggle |

### 12.3 Out of scope

Do not try to use this methodology to solve:

- **Wrong business direction** — no governance saves "the right way to do the wrong thing"
- **Organizational collaboration issues** — this method governs artifacts, not meetings, processes, or interpersonal dynamics
- **Exploratory / research code** — exploration / prototyping / innovation cannot be re-armed

These are human territory.

### 12.4 When to stop advancing

If any of the following appear, stop at the current layer rather than advancing to the next leap:

- Governance activities > 30% of engineer time for two consecutive quarters
- False alarm / false retirement rate persistently exceeds target
- Team < 10 people and modules < 30 (governance ROI inverts)

> **What this section answers**: Boundary awareness is the precondition for this system's survival — governance itself must be governed (§14.4).

---

## 13 · Role Evolution

> Labor flows toward higher value. AI is not here to replace engineers · it is here to liberate them.

### 13.1 Migration of engineer time allocation

```
TODAY · alienated labor                TOMORROW · creative labor
75% in low-value activities            100% in high-value activities

┌─────┬───────────────┬─────┐       ┌─────────────┬─────┬─────┐
│design│ CRUD·typo    │mtg  │       │system design│gate│research│
│25%  │ deps 50%      │25%  │  ─►  │intent 50%   │audit│explore│
│     │               │     │       │              │25% │25%   │
└─────┴───────────────┴─────┘       └─────────────┴─────┴─────┘
high V · low M (alienation)             high V · high M (creation)
```

### 13.2 Four new roles

Every team needs:

| # | Role | Responsibility | From which pillar |
|---|---|---|---|
| 01 | **Architect** | Design L0 gravity field; rules as capital | L0 congealed capital |
| 02 | **Intent Designer** | Write intent files; translate business into declarations | L2 Leap ② |
| 03 | **Harness Engineer** | Build Agent engineering shells; manage heartbeat rhythm | L3 Leap ③ |
| 04 | **AI Decision Auditor** | Independent of tuning engineer; guard R3-R5 red lines | R-gradient boundary |

### 13.3 Independence of the AI Decision Auditor

**Key principle**: the AI Decision Auditor must be independent of the AI Agent tuning engineer — to avoid referee = player. This role is mandatory only when AI autonomy enters the R3 cross-domain-write level.

### 13.4 Capital view of labor reallocation

Rising AI autonomy = V being replaced by C. Released V must flow to higher-value areas, otherwise it is "replacement" rather than "liberation":

| Leap | Released V | Destination high-value V |
|---|---|---|
| L0 → L1 | Manual module tagging | Framework architecture / rule design |
| L1 → L2 | Health inspection, triage | Health-model design / intent design |
| L2 → L3 | Experimental module ops | Lifecycle rule design / rollback design |
| Vision | Approval labor | Strategy / safety / ethics gating |

> **What this section answers**: Role evolution is the engineering answer to the "AI replaces engineers" fear — not replacement, but migration to higher value.

---

## 14 · Measurement Framework

> How do we know it's improving.

### 14.1 North Star metric

> **Asset Health Rate** = (asset modules with all 3 dimensions ≥ 60) / (total asset modules)

This is the single most worth-tracking metric — it simultaneously reflects all three pillars (value / structure / engineering).

### 14.2 Per-leap secondary metrics

| Leap | Secondary metrics |
|---|---|
| L0 | Governance coverage / gate effectiveness / CI green rate |
| L1 | Module manifest coverage / 3-D health trend / state migration rate |
| L2 | Intent file coverage / field-verifier binding rate / drift detection rate |
| L3 | AI suggestion acceptance / false alarm rate / R-gradient violations / auto-retirement rollback rate |

### 14.3 DORA five metrics

| DORA metric | Governance meaning | High-performance threshold |
|---|---|---|
| Deployment Frequency | Module migration velocity | Multiple per day |
| Lead Time for Changes | Single-module end-to-end engineering efficiency | < 1 day |
| Change Failure Rate | Governance quality | < 5% |
| Failed Deployment Recovery Time | Rollback effectiveness | < 1 hour |
| Rework Rate (added 2024) | Manifest / intent quality | Trending down |

### 14.4 Quarterly review (governing the governance)

Review the methodology itself every quarter:

- Which signals turned out to be useless?
- Which gates only intercept false positives?
- Which state-migration rules feel rigid to the team?
- Which anti-patterns never appeared and can be removed from the list?

**The methodology itself must enter governance** — it cannot become an untouchable sacred text.

### 14.5 Governance is necessary supervisory labor (boundary condition)

By Marx's criterion: supervisory labor is a "gray zone" — productive only when it directly creates value for capital accumulation.

```
Governance is productive if and only if:
    M_preserved = surplus value preserved by avoiding decay ≥ V_governance = labor consumed by governance
```

Violating this boundary → trigger §12.4 "when to stop advancing."

> **What this section answers**: The measurement framework gives the entire scheme a measurable, criticizable, refutable interface to the world.

---

## 15 · Future Shape (2030+)

> Software is no longer "maintained" · it **continuously evolves**.
> Engineers no longer "write code" · they **steward a system that grows itself**.

### 15.1 Four orbits of an autonomous system

```
                       SELF-EVOLVING
                       autonomous system
                  Code as Living Infrastructure
                        ●
                       ╱│╲
              ┌─HUMAN ╱ │ ╲ AI ─────┐
              │paint   │   self-   │
              │intent   │   converge│
              └────────  │  ────────┘
                         │
              ┌─SYSTEM   │   VALUE──┐
              │evolve    │  compound│
              └──────────●──────────┘
```

### 15.2 No timeline commitment

Entry conditions for the vision phase (full autonomy) are strict:

- Continuously running ≥ 6 months without major incident
- Industry has mature AI-decision explainability / auditability technology
- Organization has established the independent AI Decision Auditor role

If any condition is unmet, do not enter. This is not a roadmap clause — it is a defense against premature closure.

### 15.3 Permanent red line

No matter how high autonomy reaches, R5 (financial / physical / irreversible user impact) **never enters automation**. This is a system boundary, not a phase issue.

> **What this section answers**: The future shape paints a direction, not a commitment — direction matters more than a timeline.

---

## 16 · Value Finale · Enterprise / Individual / AI

> What this is all for.

Three subjects · three "work" philosophies:

### 16.1 Enterprise · COMPOUND · ACCELERATE

**Asset compound interest · anti-entropy**

- **Asset health rate** replaces lines-of-code as the new North Star
- **Constant delivery speed** · doesn't decay with codebase age
- **Failure rate ↓ 50% · onboarding ↓ 60%**
- Self-feedback · domain experts directly optimize the system

### 16.2 Individual · LIBERATE · CREATE

**work everywhere · every status**

- **work everywhere** · workspace travels with you
- **work every status** · productive in any state
- **time to dive into business** · truly understand users
- **workers in every industry** can optimize their own systems · feeding back to enterprise and country

### 16.3 AI · AMPLIFY · NEVER REPLACE

**work everytime**

- **7×24** without rest
- **inside the sandbox** for reversible experiments
- **gate and execute** rather than decide
- **amplify humans** rather than replace them

### 16.4 Final proposition

> **AI is not here to replace engineers · AI is here to liberate engineers.**
>
> Letting AI accelerate output without losing the organization's grip on its assets is the fundamental software-engineering question of our era.

This methodology's answer: **humans live in the desired-state-definition loop; AI lives in the continuous-convergence execution loop**.

---

## Appendix A · Capital · C/V/M Mapping

> An independent "value-flow" lens to judge whether governance actions are productive.

### A.1 Precise mapping in AI software engineering

| Marx concept | Traditional software engineering | AI-era evolution | Governance meaning |
|---|---|---|---|
| **C constant capital** (congealed labor) | Framework / infrastructure / contract skeleton / codebase | + Pre-trained models / vector stores / eval sets | The more refined C, the higher module output precision |
| **V variable capital** (labor power) | Engineer hours | Engineer + AI tool labor combination | AI is the V multiplier (same V → N× output) |
| **M surplus value** (asset deposit) | Paying users + trustworthy code asset | + Eval feedback data | M eroded by three decays |
| **W total value** | C + V + M | C + V + M | The equation unchanged, the structure shifts |

### A.2 Key proposition: AI is not a new source of value

The core proposition of the labor theory of value: **only living labor (V) creates new value**. AI is congealed past labor (belongs to C); it **transfers** its own value into the product but does not create surplus value.

Two symmetric corollaries:
- Treating AI as "a new programmer" is wrong — AI is a machine tool, not a worker
- Overestimating AI autonomy = mistaking C for V → the organization loses its conscious source of value creation
- Underestimating AI as multiplier = under-using means of production → the organization is outpaced in throughput

### A.3 L0 = the most highly congealed C

See §4.1 / §4.7. The framework is the congealed crystallization of an organization's highest architectural wisdom, infinitely amplified by replication across modules.

### A.4 Three decays = M devoured by entropy

| Decay | Capital interpretation |
|---|---|
| Value decay | Already-deposited M loses market recognition due to business shifts |
| Architecture decay | Already-deposited M needs rewriting due to architectural rot |
| Knowledge decay | Already-deposited M needs re-understanding due to staff churn |

Governance is the engineered mechanism against entropy — turning M from "perishable" to "long-term."

---

## Appendix B · V-Model in the AI Era

> Land the abstract "quality emergence" onto concrete V-model form.

### B.1 The transformed shape

```
       Left side (AI accelerated)         Right side (re-armed verification)

           Intent definition  ───────────►  End-to-end acceptance
              ↓                              ↑
           Architecture design  ─────────►  Integration test + contract
              ↓                              ↑
           Detailed design  ───────────►  Unit test + formal verification
              ↓                              ↑
       ┌──────────────┐                       │
       │ AI coding    │ ─────────────►  Static analysis + fuzzing
       │ (seconds)    │                       │
       └──────────────┘                       │
              ▲                                │
       【accelerated 100×】              【verification re-armed 3×】
```

### B.2 Transformation logic

The traditional V-model assumed left-right manpower symmetry — one developer, one test. In the AI era the left side is accelerated 100×; if the right side is not re-armed, **the failure rate inevitably rises 3×** (Sonar data).

The V-model's essence rewrite in the AI era: **left-side coding value → right-side verification value**. Verification is not after-the-fact patching — it is the core channel of V flowing into M.

### B.3 SWEBOK v4 newly added KAs in the three leaps

| New KA | Position in three leaps |
|---|---|
| Software Architecture | Carrier of L0 framework, ceiling of AI output precision |
| Software Operations (DevOps) | L0 fifth pillar (DevOps stack) |
| Software Security | L0 third pillar (sec scan in CI gates) + R-gradient safety constraints |

---

## Appendix C · CALMS · DORA · Kanban (Flow Execution Rhythm)

### C.1 CALMS redefined in the AI era

| Pillar | Traditional DevOps | AI era |
|---|---|---|
| Culture | Dev/ops collaboration | + Human/AI collaboration (trust calibration) |
| Automation | Deployment automation | + AI decision automation (constrained by Harness) |
| Lean | Eliminate waste | Focus on culling "AI-produced low-value code" |
| Measurement | DORA | DORA + 3-D health |
| Sharing | Knowledge accumulation | + AI decision audit log |

### C.2 Little's Law breaks the AI throughput bottleneck

**Core problem**: AI produces 50 functions per day, team reviews 10 → backlog → escape rate skyrockets.

**Little's Law formula**:

```
Average cycle time = WIP / throughput
```

**Application**: to keep < 1 day review cycle with team daily review capacity = 5, then WIP ≤ 5.

### C.3 Tiered fast lanes (pull system)

Schedule review WIP by R-gradient:

| Tier | Risk | WIP | Decision mode |
|---|---|---|---|
| L1 low risk (90% auto-test pass) | R0–R1 | 20 | AI-driven, human spot-check 10% |
| L2 medium risk (new features) | R2 | 10 | AI drafts + human review |
| L3 high risk (security/concurrency/external) | R3 | 3 | Expert + formal verification |

Weighted WIP: high-risk cards consume review time ×2, auto-throttled.

### C.4 Six Kanban practices (David J. Anderson)

1. **Visualize**: dual-loop kanban (intent loop + module loop)
2. **Limit WIP**: WIP cap (C.2 core)
3. **Manage Flow**: flow rate monitoring (linked to DORA Lead Time)
4. **Make Policies Explicit**: differentiated gate policies in writing
5. **Implement Feedback Loops**: reconciliation loop (§9)
6. **Improve Collaboratively**: quarterly review (§14.4)

---

## Appendix D · MDM Declarative Paradigm Leap

### D.1 Imperative → Declarative

| Paradigm | Form | Cost |
|---|---|---|
| Imperative | Humans decide when to migrate | Humans become the bottleneck |
| Declarative | Manifests declare desired state, system continuously reconciles | Designed once, runs forever |

This is the deepest paradigm leap from v3 to v7 — governance shifts from "humans inside the decision loop" to "humans inside the desired-state-definition loop."

### D.2 Apple DDM 2024+ three elements

| Element | Definition | Implementation in three leaps |
|---|---|---|
| Declaration | Desired state manifest defined by manager | L2 intent file (§7.1 four-block structure) |
| Reconciliation | Devices pull manifests and auto-converge | L3 reconciliation loop (§9.4) |
| Convergence | Continuously enforced: maintain desired state even offline | Three-dimensional health continuous write-back + soft-delete window |

### D.3 Harness + DDM unified

```
        ┌──────── Desired state (intent file) ────────┐
        │  Defined by humans: intent, contracts,       │
        │  constraints, health thresholds              │
        └────────────────────┬─────────────────────────┘
                             ▼
        ┌──────────────────────────────────────────────┐
        │       Reconciliation Loop (continuous)        │
        │                                              │
        │   ┌──────────┐         ┌──────────────┐    │
        │   │ Signal   │ ◄─────►│ Harness Five  │    │
        │   │ collect  │         │ Pack          │    │
        │   │ (auto)   │         │              │    │
        │   └──────────┘         └──────────────┘    │
        │         │                       │            │
        │         ▼                       ▼            │
        │   ┌─────────────────────────────────┐        │
        │   │  Apply remediation              │        │
        │   │  (delegated by R0–R5)           │        │
        │   └─────────────────────────────────┘        │
        └──────────────────────────────────────────────┘
                             │
                             ▼
                  Reality converges to desired state
```

**Core proposition**: Harness + DDM = **environment-level feedback control system**. The two are isomorphic; both shift from "imperative one-shot intervention" to "declarative continuous convergence."

---

## Related documents

- Companion deck: [`deck/en/index.html`](./deck/en/index.html)
- Bootstrap handbook: [`three-leaps-bootstrap.en.md`](./three-leaps-bootstrap.en.md)
- 中文版: [`three-leaps.md`](./three-leaps.md)

---

## Related resources

- [Anthropic · Effective Harnesses for Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [Apple · Declarative Device Management](https://developer.apple.com/documentation/devicemanagement)
- [DORA · State of DevOps Report](https://dora.dev/)
- [SWEBOK v4](https://www.computer.org/education/bodies-of-knowledge/software-engineering)




