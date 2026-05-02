---
title: "Bridle · AI Coding Governance Methodology"
description: "Hold the reins, not the whip — engineering governance methodology that lets AI code autonomously within framework and harness constraints. Three layers, three leaps, six reversibility tiers (R0-R5)."
lang: en
permalink: /
keywords: AI coding governance, Harness engineering, autonomy gradient, declarative manifest, MDM, reconciliation, DORA, agent, Claude, Anthropic, GitHub Copilot, Cursor
---

<!-- Language: 中文 | [English](#english) -->

# Bridle · 驭码

> **持缰而非持鞭** —— 在框架与 Harness 约束下，让 AI 自由奔驰而不脱缰。
>
> *Hold the reins, not the whip — let AI run free within the framework and harness.*

Bridle 是一套面向 **AI 编码时代**的工程化治理方法论。它不试图限制 AI 的产能，而是为 AI 装上**可控的缰绳**：用框架锚定边界、用声明式 manifest 管理生命周期、用 Harness 工程让渡可逆的自主权。

当前版本：**v7 · 三跃迁**（Three Leaps）。

---

## 一句话总纲

在每一个交付时刻，让 AI 生成的制品同时处于「**被需要 / 被信任 / 被理解**」三重状态。

---

## 为什么需要 Bridle

AI 编码已经把生产端边际成本压到接近零，但人类审查能力是线性的。Sonar 调研显示 **AI 代码故障率约 3× 高于人工**，价值/架构/知识三重衰减全面加速。

| 衰减 | 表现 | 失守的代价 |
|---|---|---|
| 价值衰减 | 业务变化、需求过期 | 资产腐烂为僵尸代码 |
| 架构衰减 | 依赖腐烂、熵增 | 架构腐烂为大泥球 |
| 知识衰减 | 人员流动、上下文丢失 | 质量腐烂为技术债 |

不能让 AI 单纯加速 —— 必须把 AI 装进可信的工程系统。

---

## 核心架构：三层 × 三跃迁

```
            L3 · AUTONOMOUS LOOP                  ← 跃迁③ 系统自收敛
            Harness · Agent · Reconciliation
                       ▲
            L2 · INTENT EXPRESSIBLE               ← 跃迁② 意图可表达
            INTENT → CONTRACT → VERIFIER
                       ▲
            L1 · STATE VISIBLE                    ← 跃迁① 状态可见
            身份 · 5态机 · 三维健康度
                       ▲
       ╔═══════════════════════════════════════╗
       ║ L0 · GRAVITY FIELD                    ║ ← 工程引力场（地基 · 不是阶段）
       ║  框架 · 模块身份 · CI/CD              ║   precondition
       ║  · 运行时 · DevOps · 沙箱             ║   跳过 L0 = 把 AI 放进沼泽
       ╚═══════════════════════════════════════╝
```

| 层级 | 主题 | 范式跃迁 |
|---|---|---|
| **L0** | 工程引力场 | – （地基，不是阶段） |
| **L1** | 状态可见 | 从代码 → 状态 |
| **L2** | 意图可表达 | 从命令 → 意图 |
| **L3** | 系统自收敛 | 从一次推理 → 持续自治 |

---

## 推导链（封闭体系）

```
4 条不可再分事实 → 3 公理 → 3 支柱 → 3 跃迁 + L0 地基
```

**三公理**：意图保真 · 动作可逆 · 质量涌现
**三支柱**：价值锚定 · 边界封控 · 制程内建
**三状态**：被需要 · 被信任 · 被理解

详见 [`three-leaps.md`](./three-leaps.md) §3 第一性原理推导。

---

## 自主权梯度（按可逆性 R0-R5 让渡）

| 梯度 | 范围 | AI 能否自主 |
|---|---|---|
| R0 只读 | 查代码 · 提建议 | AI 全自动 |
| R1 本地修改 | 改本仓库 · 单测护栏 | AI 自动（git 回滚） |
| R2 受控外部 | 沙箱 API · 测试环境 | AI 自动放行（audit log） |
| R3 跨域写入 | 改其他服务 · 迁移 | AI 提议 + 人审（staged rollout） |
| R4 影响用户 | 删数据 · 改账单 | 人审 · 永不放开 |
| R5 资金 / 物理 | 转账 · 设备控制 | 人决策 · 红线 |

> **R5 永不放开** —— 这是整个体系的边界条件。

---

## 文档地图

| 文档 | 适合读者 | 内容 |
|---|---|---|
| [`three-leaps.md`](./three-leaps.md) | 主方法论读者 | 16 章 / 三层 × 三跃迁 / 4 篇附录 |
| [`three-leaps-bootstrap.md`](./three-leaps-bootstrap.md) | greenfield 起步项目 | 35 项能力 → L0/L1/L2/L3 跃迁映射 |
| [`deck/index.html`](./deck/index.html) | 想要可视化总览 | 15 页配套幻灯片 · 订单团购案例贯穿 |
| [`three-leaps.pdf`](./three-leaps.pdf) | 离线 / 打印 / 分享 | 配套幻灯片的 PDF 导出（3.5 MB · 15 页） |
| [`archive/v3.md`](./archive/v3.md) | 想看推理细节 | 旧版本 · 七视角×四阶段 · 已归档 |
| [`archive/v3-bootstrap.md`](./archive/v3-bootstrap.md) | 想看原始 P0-P7 表述 | 旧版本 bootstrap · 已归档 |

**阅读顺序**：

- 已有 L0 基础 → 直接读 [`three-leaps.md`](./three-leaps.md)
- greenfield 起步 → [`three-leaps-bootstrap.md`](./three-leaps-bootstrap.md) 走通 35 能力 → 进入主方法论 §11 全景闭环
- 想要 30 分钟读完 → 在浏览器打开 [`deck/index.html`](./deck/index.html)

---

## 适用边界

**Bridle 解决**

- AI 产能与人类审查的错配
- 模块腐烂、僵尸代码堆积
- AI 决策无追溯、无回滚
- 治理"靠人记、靠会议、靠文档"的规模不经济

**Bridle 不解决**

- 业务方向错误（再好的治理救不了"用正确的方式做错的事"）
- 组织协作问题（治理的是制品，不是会议、流程、人际）
- 创意 / 研究 / 探索性代码（无法重武装）
- 小团队（< 10 人 / < 30 模块，治理 ROI 倒挂）

---

## 关键命题

> **AI 是劳动力倍增器，不是新的价值源泉。**
>
> 让 AI 能加速产出而不让组织失去对资产的把握，是这个时代软件工程的根本命题。

Bridle 给出的答案：**人在期望状态定义环路里，AI 在持续收敛执行环路里。**

---

<a id="english"></a>
<!-- Language: [中文](#bridle--驭码) | English -->

# Bridle

> **Hold the reins, not the whip** — let AI run free within the framework and harness.

Bridle is an engineering governance methodology for the **AI-coding era**. Rather than throttling AI throughput, it puts **controllable reins** on AI: anchoring boundaries with frameworks, managing lifecycles via declarative manifests, and granting reversible autonomy through harness engineering.

Current version: **v7 · Three Leaps**.

---

## One-Line Thesis

At every delivery moment, every AI-generated artifact is simultaneously **Needed, Trusted, and Understood**.

---

## Why Bridle

AI coding has driven marginal production cost toward zero, while human review capacity remains linear. Sonar reports that **AI-generated code has roughly 3× the defect rate of human-written code**, and value / architecture / knowledge decay accelerates across the board.

| Decay | Symptom | Cost of Failure |
|---|---|---|
| Value decay | Business shifts, stale requirements | Assets rot into zombie code |
| Architecture decay | Dependency rot, entropy | Codebase rots into a big ball of mud |
| Knowledge decay | Staff churn, lost context | Quality rots into technical debt |

You can't just let AI accelerate — you must place AI inside a trustworthy engineering system.

---

## Core Architecture: Three Layers × Three Leaps

```
            L3 · AUTONOMOUS LOOP                  ← Leap ③ system self-converges
            Harness · Agent · Reconciliation
                       ▲
            L2 · INTENT EXPRESSIBLE               ← Leap ② intent expressible
            INTENT → CONTRACT → VERIFIER
                       ▲
            L1 · STATE VISIBLE                    ← Leap ① state visible
            Identity · 5-state FSM · 3-D health
                       ▲
       ╔═══════════════════════════════════════╗
       ║ L0 · GRAVITY FIELD                    ║ ← Engineering gravity field
       ║  framework · module identity · CI/CD  ║   (precondition · NOT a phase)
       ║  · runtime · DevOps · sandbox         ║   skipping L0 = AI in a swamp
       ╚═══════════════════════════════════════╝
```

| Layer | Theme | Paradigm leap |
|---|---|---|
| **L0** | Gravity field | — (foundation, not a phase) |
| **L1** | State visible | From code → state |
| **L2** | Intent expressible | From command → intent |
| **L3** | Autonomous loop | From one-shot inference → continuous self-governance |

---

## Closed Derivation

```
4 irreducible facts → 3 axioms → 3 pillars → 3 leaps + L0 foundation
```

**Three Axioms**: Intent Fidelity · Action Reversibility · Quality Emergence
**Three Pillars**: Value Anchoring · Boundary Control · Built-in Process
**Three States**: Needed · Trusted · Understood

See [`three-leaps.md`](./three-leaps.md) §3 for the first-principles derivation.

---

## Autonomy Gradient (Reversibility R0–R5)

| Level | Scope | AI autonomy |
|---|---|---|
| R0 read-only | Inspect code, propose | Fully automated |
| R1 local edits | Modify own repo, unit-test guarded | Automated (git rollback) |
| R2 controlled external | Sandbox APIs, test env | Auto-released (audit log) |
| R3 cross-domain write | Modify other services, migrations | AI proposes + human review (staged rollout) |
| R4 user impact | Delete data, modify billing | Human review · never granted |
| R5 financial / physical | Money transfer, device control | Human decision · red line |

> **R5 is never granted** — this is the system's hard boundary.

---

## Document Map

| Document | Audience | Content |
|---|---|---|
| [`three-leaps.en.md`](./three-leaps.en.md) | Main methodology readers | 16 chapters · 3 layers × 3 leaps · 4 appendices |
| [`three-leaps-bootstrap.en.md`](./three-leaps-bootstrap.en.md) | Greenfield projects | 35 capabilities mapped to L0/L1/L2/L3 |
| [`deck/en/index.html`](./deck/en/index.html) | Want a visual overview | 15-page slide deck with order-service group-buy case |
| [`three-leaps.pdf`](./three-leaps.pdf) | Offline / print / share | PDF export of the slide deck (3.5 MB · 15 pages) |
| [`archive/v3.md`](./archive/v3.md) | Want derivation details | Older version · seven-lens × four-phase · archived |
| [`archive/v3-bootstrap.md`](./archive/v3-bootstrap.md) | Want original P0–P7 framing | Older bootstrap · archived |

**Reading order**:

- Already have L0 in place → go straight to [`three-leaps.md`](./three-leaps.md)
- Starting from zero → walk through [`three-leaps-bootstrap.md`](./three-leaps-bootstrap.md), then enter §11 of the main methodology
- Want a 30-minute overview → open [`deck/index.html`](./deck/index.html) in a browser

---

## Scope

**Bridle addresses**: throughput mismatch between AI output and human review / module rot / untraceable & irreversible AI decisions / governance that doesn't scale.

**Bridle does not address**: wrong business direction / organizational collaboration issues / exploratory research code / small teams (< 10 people / < 30 modules — governance ROI inverts).

---

## Core Proposition

> **AI is a labor multiplier, not a new source of value.**
>
> Letting AI accelerate output without losing the organization's grip on its assets is the fundamental software-engineering question of our era.

Bridle's answer: **humans live in the desired-state definition loop; AI lives in the continuous-convergence execution loop.**

---

## Status

🚧 Exploratory methodology (v7). This handbook is itself subject to governance — issues and PRs are welcome for:

- Real adoption cases (refuting or validating specific mechanisms)
- Anti-pattern additions
- Tool alternatives
- Measurement data

**Practical evidence outweighs methodological recommendation.**

---

## License

TBD (suggested: CC BY-SA 4.0 for methodology text; MIT for any future code implementation).
