---
title: "Bridle · AI Coding Governance Methodology"
description: "Hold the reins, not the whip — engineering governance methodology that lets AI code autonomously within framework and harness constraints. Three layers, three leaps, six reversibility tiers (R0-R5)."
lang: en
permalink: /
keywords: AI coding governance, Harness engineering, autonomy gradient, declarative manifest, MDM, reconciliation, DORA, agent, Claude, Anthropic, GitHub Copilot, Cursor
---

<!-- Language: 中文 | [English](#english) -->

# Bridle · 驭码

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Docs](https://img.shields.io/badge/📚_docs-ghbvf.github.io%2Fbridle-blue)](https://ghbvf.github.io/bridle/)
[![Stars](https://img.shields.io/github/stars/ghbvf/bridle?style=social)](https://github.com/ghbvf/bridle/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/ghbvf/bridle?color=informational)](https://github.com/ghbvf/bridle/commits/main)
[![AI-generated](https://img.shields.io/badge/AI--generated-Claude-7b3fe4)](#%EF%B8%8F-ai-生成免责声明)
[![Bilingual](https://img.shields.io/badge/lang-中文_·_English-green)](#english)

> **持缰而非持鞭** —— 在框架与 Harness 约束下，让 AI 自由奔驰而不脱缰。
>
> *Hold the reins, not the whip — let AI run free within the framework and harness.*

**Bridle** is an **AI coding governance methodology** for the era of **AI agents** (Claude, Claude Code, Cursor, GitHub Copilot, autonomous coding agents) — engineered around the **Harness Five-Pack**, **declarative manifests**, **reconciliation loops**, and an **R0–R5 reversibility gradient** that lets AI take over reversible actions while keeping humans in charge of irreversible ones. Three layers (L0 gravity field · L1 state visible · L2 intent expressible · L3 autonomous loop), three leaps, six tiers, one running case (order service supports group-buy).

Bridle 是一套面向 **AI 编码时代**的工程化治理方法论。它不试图限制 AI 的产能，而是为 AI 装上**可控的缰绳**：用框架锚定边界、用声明式 manifest 管理生命周期、用 Harness 工程让渡可逆的自主权。

当前版本：**v7 · 三跃迁**（Three Leaps · MIT License · Bilingual zh/en）。

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

## 📚 文档地图

### 📖 主方法论 · Main Methodology

> 16 章 · 三层 × 三跃迁 · 4 篇附录 · 第一性原理推导

➡️ **[阅读中文版 → `three-leaps.md`](./three-leaps.md)**　|　**[Read English → `three-leaps.en.md`](./three-leaps.en.md)**

---

### 🚀 起步手册 · Bootstrap Handbook

> 35 项能力 · 从零仓库到 L3 自治 · 映射到 L0/L1/L2/L3 跃迁

➡️ **[阅读中文版 → `three-leaps-bootstrap.md`](./three-leaps-bootstrap.md)**　|　**[Read English → `three-leaps-bootstrap.en.md`](./three-leaps-bootstrap.en.md)**

---

### 🎬 配套幻灯片 · Slide Deck

> 15 页 · 订单团购案例贯穿全程 · 1920×1080 keynote

➡️ **[打开中文版 → `deck/index.html`](./deck/index.html)**　|　**[Open English → `deck/en/index.html`](./deck/en/index.html)**　|　**[📄 PDF (3.5 MB)](./three-leaps.pdf)**

---

### 🛠️ 立即可用的范例 · Drop-in Examples

> 直接拷到你项目里改名即可的 4 个核心 artifact

| 文件 | 层级 | 说明 |
|---|---|---|
| [`examples/module.yaml`](./examples/module.yaml) | L1 入口 | 模块身份 / 契约 / lifecycle / 信号 |
| [`examples/intent.yaml`](./examples/intent.yaml) | L2 跃迁② | 意图声明 4 块结构 |
| [`examples/reconciler.py`](./examples/reconciler.py) | L3 跃迁③ | reconciliation loop + R0-R5 路由参考实现 |
| [`examples/CLAUDE.md`](./examples/CLAUDE.md) | L3 Harness | AI agent 系统上下文 / Harness 五件套之一 |

➡️ **[查看 examples/ 目录](./examples/)**

---

### 🧭 阅读顺序

| 你的情况 | 推荐路径 |
|---|---|
| 已有 L0 基础 | 直接读 **主方法论** |
| 想要 30 分钟速览 | 浏览器打开 **配套幻灯片** |
| greenfield 起步项目 | **起步手册** 走通 35 能力 → 进入主方法论 §11 全景闭环 |
| 离线 / 打印 / 分享 | 下载 **PDF** |

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

## ⚠️ AI 生成免责声明

> 本仓库的**全部内容**——方法论文档、起步手册、配套幻灯片、源代码、配置文件、本 README——**均由 AI（Claude）协作生成**，未经过任何团队的真实工程实践完整验证。

具体含义：

- **探索性 ≠ 最佳实践**：本方法论是一个尚未被多组织验证的**理论框架**，不是经过实战检验的工业标准
- **真实证据 > AI 推荐**：当本仓库的建议与你团队的实际经验冲突时，请相信你的经验
- **不构成专业建议**：不应作为关键工程决策、合规判断、商业战略的唯一依据
- **引用前请核实**：所有数据点（如"AI 代码故障率 3×"、"DORA 高性能水位"等）都应回到原始来源核实

请把本仓库当作**讨论起点**，而非**最终答案**。欢迎以 Issue / PR 形式提供：真实采用案例（推翻或验证某条机制）、反模式补充、工具替代方案、度量数据。

---

## License

[MIT License](./LICENSE) · Copyright © 2026 ghbvf · Bridle Project

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

## 📚 Document Map

### 📖 Main Methodology

> 16 chapters · 3 layers × 3 leaps · 4 appendices · derived from first principles

➡️ **[Read English → `three-leaps.en.md`](./three-leaps.en.md)**　|　**[阅读中文版 → `three-leaps.md`](./three-leaps.md)**

---

### 🚀 Bootstrap Handbook

> 35 capabilities · from zero repo to L3 autonomy · mapped to L0/L1/L2/L3 leaps

➡️ **[Read English → `three-leaps-bootstrap.en.md`](./three-leaps-bootstrap.en.md)**　|　**[阅读中文版 → `three-leaps-bootstrap.md`](./three-leaps-bootstrap.md)**

---

### 🎬 Slide Deck

> 15 pages · order-service group-buy case throughout · 1920×1080 keynote

➡️ **[Open English → `deck/en/index.html`](./deck/en/index.html)**　|　**[打开中文版 → `deck/index.html`](./deck/index.html)**　|　**[📄 PDF (3.5 MB)](./three-leaps.pdf)**

---

### 🛠️ Drop-in Examples

> 4 ready-to-copy artifacts — paste into your repo, rename, ship

| File | Layer | Purpose |
|---|---|---|
| [`examples/module.yaml`](./examples/module.yaml) | L1 entry | Module identity / contracts / lifecycle / signals |
| [`examples/intent.yaml`](./examples/intent.yaml) | L2 leap ② | Intent declaration · 4-block structure |
| [`examples/reconciler.py`](./examples/reconciler.py) | L3 leap ③ | Reference reconciliation loop with R0–R5 routing |
| [`examples/CLAUDE.md`](./examples/CLAUDE.md) | L3 Harness | AI agent system context · 1 of the Harness Five-Pack |

➡️ **[Browse examples/ →](./examples/)**

---

### 🧭 Reading order

| Your situation | Recommended path |
|---|---|
| Already have L0 in place | Read the **main methodology** directly |
| Want a 30-minute overview | Open the **slide deck** in a browser |
| Greenfield project starting from zero | Walk through the **bootstrap handbook**'s 35 capabilities, then §11 of the main methodology |
| Offline / print / share | Download the **PDF** |

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

## ⚠️ AI-Generated Content Disclaimer

> **All content in this repository** — methodology docs, bootstrap handbook, companion deck, source code, configuration, this README — was **generated collaboratively with AI (Claude)** and has not been fully validated by any team's real engineering practice.

What this means concretely:

- **Exploratory ≠ best practice**: this methodology is a **theoretical framework** not yet validated across multiple organizations, not a battle-tested industry standard
- **Real evidence > AI recommendation**: when this repo's advice conflicts with your team's lived experience, trust your experience
- **Not professional advice**: do not use as the sole basis for critical engineering decisions, compliance judgments, or business strategy
- **Verify before citing**: all data points (e.g. "AI code defect rate 3×", "DORA high-performance thresholds") should be re-verified against original sources

Treat this repo as a **starting point for discussion**, not the **final answer**. Issues and PRs welcome with: real adoption cases (refuting or validating mechanisms), anti-pattern additions, tool alternatives, measurement data.

---

## License

[MIT License](./LICENSE) · Copyright © 2026 ghbvf · Bridle Project
