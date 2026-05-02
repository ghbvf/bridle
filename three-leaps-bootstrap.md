---
title: "三跃迁 · 起步手册 · Bridle Bootstrap"
description: "从零仓库到 L3 自治的 35 项能力清单 —— greenfield 项目走完 P0-P7 八阶段进入主方法论。每项能力按 5 字段标准（为什么/做什么/系统编织/出口/工具）展开。"
lang: zh-CN
permalink: /three-leaps-bootstrap/
keywords: AI 编码起步, greenfield, manifest, 静态守卫, OpenTelemetry, DORA, Harness, IaC, GitOps, Reconciliation, Bridle
---

# 三跃迁 · 起步手册（Bootstrap）

> 从零到 L3 自治的能力台阶 —— 主方法论 [`three-leaps.md`](./three-leaps.md) 假设 L0 引力场已就位。本手册补的是更前一步：**零仓库 / 零 CI / 零 manifest / 零 Harness** 的 greenfield 起步路径。

走通本手册的 35 项能力后，团队进入 L3 跃迁的入口条件就已超额满足。

---

## 0 · 适用边界

### 是什么

- 起步路径手册 + 35 项能力清单 + 跃迁映射图
- 给主方法论提供"前置地基"的可操作步骤
- **能力为主体、工具为细节**

### 不是什么

- 不是规范（无强制要求）
- 不是最佳实践宣言
- 不是 [`three-leaps.md`](./three-leaps.md) 的替代

### 适用前提

- 项目处于 0 → 0.5 阶段（无框架、无 CI、无 manifest、无静态守卫）
- 决心引入三跃迁治理思想，但缺地基
- 单人或团队（10 人内最贴合，10-30 人可适配，30+ 人组织通常已有内部平台）

### 不适用场景

- 一次性脚本 / 研究代码（治理 ROI 倒挂）
- 已有完整框架 + CI + 看板（直接读 [`three-leaps.md`](./three-leaps.md)）
- 强监管行业核心交易系统（监管约束 > 本手册）

### 关键认知（保留 v3 反思精神）

- 本手册仍是**探索性**——基于主方法论 + 现有工具的组合推荐
- **真实采用者的实践证据 > 本手册推荐**
- 每条工具给"为什么选 + 替代方案"，不做"最佳"宣言
- 本手册自身也要被治理（详见 §8）

---

## 1 · 设计原则 + 阶段 vs 时间的辨析

### 4 条设计原则

1. **能力替代时间** —— 时间承诺假，能力达成真
2. **入口/出口信号必须客观可观察** —— 不靠主观判断
3. **能力为主体、工具为细节** —— 5 字段标准模板展开
4. **保留反思精神** —— 本手册仍可被实践推翻

### 时间假在哪

| 维度 | 真实差异 | 时间承诺如何失真 |
|---|---|---|
| 团队规模 | 单人 vs 5 人 vs 30 人 | 同阶段时长差 5-10 倍 |
| 工具熟悉度 | 第一次接触 vs 资深 | 学习曲线 1-4 周不等 |
| 并行度 | 全职 vs 兼职 vs 业余 | 实际投入差 3-5 倍 |
| 需求变化 | 稳定 vs 波动 | 中途返工拖延 50-200% |
| 历史债务 | greenfield vs 半遗留 | 清理工作量不可预估 |

**结论**：写"4 周完成 P1"在第 5 周就破产，引发治理失信。改写"P1 出口 = 5 个能力都达成"才可执行可验证。

### 能力为什么真

每能力含三件事，全是客观可观察的事件：

- **入口信号**：上一能力出口达成（机器可验证）
- **必建动作**：5 字段模板（为什么 / 做什么 / 系统编织 / 出口标准 / 实现工具）
- **出口信号**：可验证事件（如"故意越界 PR 被 CI 拦住"）

**唯一禁止跳能力**——前能力未达出口直接跑下一项，会形成基础不稳的脆弱叠加。

---

## 2 · 35 能力 → 三跃迁映射

主方法论的层级是 **L0 → L1 → L2 → L3**。本手册 35 能力按以下映射归属：

```
                     ┌────────────────────────────────────────┐
                     │  L3 跃迁③ · 系统自收敛                   │
                     │  P6.3 Runtime agent + R0-R5             │
                     │  P6.4 Reconciliation loop               │
                     │  P6.5 决策审计存储升级                    │
                     │  P6.6 Chaos engineering（可选）          │
                     └────────────────────────────────────────┘
                                       ▲
                     ┌────────────────────────────────────────┐
                     │  L2 跃迁② · 意图可表达                   │
                     │  P5.1 Harness 五件套                     │
                     │  P5.4 AI 决策审计起步                     │
                     │  P6.1 Feature flag 系统化                │
                     │  P6.2 IaC + GitOps                      │
                     └────────────────────────────────────────┘
                                       ▲
                     ┌────────────────────────────────────────┐
                     │  L1 跃迁① · 状态可见                     │
                     │  P1.2 模块 manifest + lifecycle         │
                     │  P1.3 静态边界守卫                        │
                     │  P3 全套 (3.1-3.5) 可观测                │
                     │  P4 全套 (4.1-4.5) 流                    │
                     │  P5.2 AI 接受率 / P5.3 健康度三维         │
                     └────────────────────────────────────────┘
                                       ▲
       ╔════════════════════════════════════════════════════════╗
       ║  L0 · 工程引力场                                         ║
       ║  P0 全套 (0.1-0.5) 仓库/CI/ADR/协作/review              ║
       ║  P1.1 领域分层 / P1.4 API 版本 / P1.5 DB migration      ║
       ║  P2 全套 (2.1-2.6) 漏洞/覆盖率/依赖/secrets/flag/合规     ║
       ╚════════════════════════════════════════════════════════╝
```

### 阶段间的并行规则

- **L0 严格门控**（地基层，必须串行）—— P0/P1.1-1.4-1.5/P2 全套
- **L1 内部 P3 + P4 可并行**（指标 vs 流程，互不干扰）
- **L2 P5.1 Harness 可在 L1 中段开始**（DORA 数据可作 AI 输入）
- **L3 必须在 L2 出口后启动**（runtime agent 需 Harness 配置就位）

---

## 3 · L0 · 工程引力场（地基）

### 3.1 仓库 + 第一条 CI（P0.1）

- **为什么**：没有版本控制 + 自动验证，所有后续治理无附着点
- **做什么**：建立 git 仓库 + 一条 push/PR 触发的 CI（lint + test + build）
- **系统编织**：作为后续所有 CI 流水线的扩展基底；CI 全绿是 L3 评估循环的最早事件信号
- **出口**：CI 全绿持续 4 PR；任何 push/PR 自动跑 < 5 min
- **工具**：GitHub Actions / Azure Pipelines / GitLab CI

### 3.2 hello-world 主路径（P0.2）

- **为什么**：项目可运行是后续一切的基础；无 hello-world 证明栈选错都不知道
- **做什么**：建立从入口到对外接口的最短路径（HTTP 端点 / CLI 命令）
- **系统编织**：是 L1 OTel 埋点的最早样本；是 L3 Agent 评估循环的起点
- **出口**：main 分支可一键运行；新成员从 clone 到运行 < 5 分钟
- **工具**：栈原生 + 可选 Docker

### 3.3 决策记录 ADR（P0.3）

- **为什么**：早期决策（栈选 / 架构方向）半年后无人记得，复盘失去依据
- **做什么**：`docs/adr/` 目录 + 第一份 ADR + 模板
- **系统编织**：→ L2 Harness 的"项目记忆"层；→ L3 季度评审的历史输入
- **出口**：第一份 ADR 存在；后续重大决策走 ADR 流程
- **工具**：adr-tools / Log4brains / 手写 markdown

### 3.4 协作约定（P0.4）

- **为什么**：没有"如何贡献"约定，PR 审查靠口头共识，团队 ≥ 2 人即崩
- **做什么**：README + CONTRIBUTING + branch protection
- **系统编织**：→ Code review 的依据；→ Harness 的协作上下文（CLAUDE.md/cursor 规则可引用）
- **出口**：新成员从仓库到第一份 PR < 1 小时；branch protection 对 main 强制
- **工具**：GitHub Branch Protection / Azure DevOps Branch Policies / Conventional Commits

### 3.5 Code review 制度（P0.5）

- **为什么**：单纯 lint 不能拦设计错误；review 是知识传递与边界守卫的人侧动作
- **做什么**：CODEOWNERS + 必须 reviewer 数 + stale PR 自动关闭
- **系统编织**：→ AI 接受率的对比基线；→ DORA Lead Time 的关键瓶颈点
- **出口**：所有 PR 至少 1 reviewer approve；CODEOWNERS 覆盖所有目录
- **工具**：CODEOWNERS（GitHub/GitLab/Azure 通用）+ stale-bot / Probot

### 3.6 领域分层（P1.1）

- **为什么**：单一 src/ 目录会演变为大泥球；后续静态守卫无对象
- **做什么**：建立至少三档分层（domain / shared / adapters），每档清晰职责
- **系统编织**：→ 模块 manifest 按领域组织；→ 静态守卫的目标
- **出口**：每个文件可归属唯一一档；交叉引用走明确接口
- **工具**：栈原生目录约定（无专门工具）

### 3.7 API 版本策略（P1.4）

- **为什么**：第一版 API 不带版本号，未来无法平滑演进；客户端无 deprecation 路径
- **做什么**：所有对外 API 走 `/api/v1/` 前缀；deprecation policy（≥ 2 个 release 双跑）
- **系统编织**：→ Feature flag 按版本路由；→ 性能基线按版本对比
- **出口**：所有路由有 version 段；至少 1 条 deprecation 流程文档
- **工具**：OpenAPI 3 + Swagger UI / Redoc / Stoplight

### 3.8 DB migration（P1.5）

- **为什么**：直接改 schema 必演变为生产事故；版本不一致导致跨服务联调失败
- **做什么**：所有 schema 变更走 migration 工具；CI 校验顺序与可回滚性
- **系统编织**：→ Secrets（migration 用 db 凭证）；→ 事件管理（schema 变更是 incident 高发源）
- **出口**：`migrations/` 目录存在；至少 1 次成功的 forward + rollback 演练
- **工具**：Flyway / Liquibase / Alembic / golang-migrate / EF Core / Prisma Migrate

### 3.9 多层漏洞扫描（P2.1）

- **为什么**：依赖 / 模式 / 数据流 / 物料清单各有盲区，单层不足以覆盖供应链攻击面
- **做什么**：4 层独立扫描——依赖 + SAST 模式 + SAST 数据流 + SBOM
- **系统编织**：→ L1 健康度结构得分子项；事件可反向追溯
- **出口**：4 层全绿持续 4 周；任一层中断有明确 owner
- **工具**：Dependabot + CodeQL + Semgrep + Syft

### 3.10 测试覆盖率门禁（P2.2）

- **为什么**：覆盖率不是质量本身，但低覆盖率必有质量问题
- **做什么**：仅对**新增代码**设覆盖率门禁（避免 fake test 灌存量陷阱）
- **系统编织**：→ L1 工程信号源之一；与 DORA Lead Time 共同衡量"快而稳"
- **出口**：覆盖率有 ≥ 4 周趋势数据；新增代码覆盖率 ≥ 80%
- **工具**：Codecov / Coveralls / SonarCloud

### 3.11 依赖自动升级（P2.3）

- **为什么**：依赖会过期、出漏洞、被弃用；手动跟进必漏
- **做什么**：开 Dependabot/Renovate 自动 PR；制定升级合并节奏（如 weekly batch）
- **系统编织**：→ 漏洞扫描的修复路径；避免噪声堆积
- **出口**：Dependabot PR 平均存活 < 7 天；无 ≥ 30 天积压
- **工具**：Dependabot / Mend Renovate / Snyk

### 3.12 Secrets + 凭证轮转（P2.4）

- **为什么**：明文 secret 进 git 是常态事故；不轮转的凭证一旦泄露永久暴露
- **做什么**：secrets 集中管理 + 应用读 secrets 走 SDK + pre-commit + push-time 双层扫描 + 定期轮转
- **系统编织**：→ DB migration 凭证；→ IaC 中的 cloud 凭证
- **出口**：0 次明文 secret 进 git ≥ 4 周；至少 1 次成功轮转演练
- **工具**：HashiCorp Vault / Azure Key Vault / Doppler / AWS Secrets Manager + gitleaks

### 3.13 配置 + Feature flag 起步（P2.5）

- **为什么**：配置写死 = 每次改配置都要发布；feature flag 是后续 progressive delivery 基础
- **做什么**：env / config 分离 + feature flag SDK 起步 + 制定 flag 清理策略
- **系统编织**：→ L2 Flag 系统化 + canary delivery；→ L3 reconciler 用 flag 做实验态切流
- **出口**：第一个 feature flag 跑通；config 变更不需要重新构建
- **工具**：Flipt / Unleash（OSS） / LaunchDarkly / ConfigCat

### 3.14 数据合规标注（P2.6）

- **为什么**：GDPR/HIPAA/PCI-DSS 等合规要求字段级追踪；事后补做需重审全部代码
- **做什么**：在 manifest 或 schema 标注敏感字段（PII / PHI / PCI），CI 校验"敏感字段不进日志/不出域"
- **系统编织**：→ OTel（日志中过滤敏感字段）；→ L2 决策审计（标注敏感操作）
- **出口**：敏感字段标注覆盖率 ≥ 设定比例；CI 拦住"敏感字段写日志"PR
- **工具**：自建标注 + Semgrep custom rules / OpenPolicyAgent / Bridgecrew

### L0 出口信号

- CI 全绿 + main 可运行 hello-world + 第一份 ADR + README/CONTRIBUTING/CODEOWNERS 齐全
- 故意越界 PR 被 CI 拦（基于领域分层 + 后续守卫）
- migration 演练通过
- 4 层扫描全绿 ≥ 4 周；覆盖率有趋势；0 secret 进 git；feature flag 起步；数据合规标注覆盖

→ **进入 L1 跃迁**

---

## 4 · L1 跃迁① · 状态可见

### 4.1 模块 manifest + lifecycle（P1.2）★

> **L1 入口能力 · 全图最重要的产出物**

- **为什么**：声明式治理体系的基石。无 manifest = 无法机器化判断模块状态
- **做什么**：每模块一份 `manifest.yaml`（含 module/domain/lifecycle/contracts）+ JSON Schema 校验 + lifecycle 字段（experimental → candidate → asset → maintenance → retired）
- **系统编织**：被漏洞扫描分模块 / 健康度按 manifest 索引 / reconciler 拉 manifest 算 drift 三方消费
- **出口**：100% 模块有 manifest；CI 强制 schema 校验；manifest 错误必 fail
- **工具**：JSON Schema + ajv / gojsonschema / jsonschema / NJsonSchema

### 4.2 静态边界守卫（P1.3）

- **为什么**：仅靠 review 防越界，半年必崩。需要机器化拦截
- **做什么**：至少一条规则拦致命越界（"跨域 import" / "experimental 被 production journey 引用" / "adapter 被 domain 直接调用"）
- **系统编织**：→ 健康度结构得分子项；违反数即倒扣输入
- **出口**：故意越界 PR 被 CI fail；规则数 ≥ 3 条
- **工具**：dependency-cruiser / 自写 archtest / ArchUnit / NetArchTest / import-linter

### 4.3 OpenTelemetry 三件套（P3.1）

- **为什么**：日志/度量/链路任一缺失，事件分析必有盲区；vendor lock-in 阻碍后期工具切换
- **做什么**：OTel SDK 统一埋点 + 结构化日志（JSON）+ 度量（counter/gauge/histogram）+ 链路追踪
- **系统编织**：→ SLO / 事件追踪 / 性能基线 / 健康度信号
- **出口**：trace_id 可贯通从入口到 DB；3 件套都有数据
- **工具**：OpenTelemetry SDK + Grafana Cloud / DataDog / Application Insights / Honeycomb

### 4.4 SLI/SLO + Error budget（P3.2）

- **为什么**：没有 SLO = "可用性"是主观词；error budget 是约束发布速度的客观锚
- **做什么**：定义至少 1 条 SLI（如 P99 latency / 成功率）+ 1 个 SLO + error budget 跟踪
- **系统编织**：→ 事件管理触发；→ DORA Change Failure Rate 与 budget 联动
- **出口**：SLO 已开始 burn；budget 计算可见
- **工具**：Sloth（OSS）/ Pyrra（OSS）/ Nobl9（商业）

### 4.5 事件管理（P3.3）

- **为什么**：生产问题 0 响应 = 用户先于团队发现；on-call 集中在 1 人 = burnout
- **做什么**：on-call schedule + alert 通道 + incident 流程 + runbook 库
- **系统编织**：← SLO burn 触发；→ blameless post-mortem 输入
- **出口**：on-call 有人；至少 1 次真实事件走完流程；runbook ≥ 3 份
- **工具**：PagerDuty free / Opsgenie / FireHydrant / 自建 + Slack 通知

### 4.6 性能基线 + 预算（P3.4）

- **为什么**：没有基线，性能回归不可见；前端项目尤其 bundle size / LCP 必失控
- **做什么**：CI 集成性能测试 + 基线快照 + 性能预算 + 回归 fail
- **系统编织**：→ 工程得分子项；→ API 版本对比基线
- **出口**：性能基线在 CI 持续跑；至少 1 次回归被拦
- **工具**：k6 / Lighthouse CI / JMeter / Gatling / NBomber

### 4.7 a11y / i18n 基线（P3.5 · 用户面项目）

- **为什么**：a11y 后期补做需重审全部 UI；i18n 字符串硬编码后批量提取成本高
- **做什么**：a11y 自动检测（CI 集成）+ i18n 字符串外置 + 至少 1 个非默认语言验证
- **系统编织**：→ 性能预算（i18n 包体增长）
- **出口**：a11y 检测无 critical violation；i18n 框架就位
- **工具**：axe-core + Pa11y CI / Lighthouse a11y / WAVE；i18next / FormatJS / .NET ResX

### 4.8 DORA 五指标采集（P4.1）

- **为什么**：没有客观指标 = "我们效率高"是主观判断；DORA 是行业可比基线
- **做什么**：采集 deployment frequency / lead time / change failure rate / recovery time / rework rate；daily snapshot
- **系统编织**：← WIP 直接影响 lead time；→ 健康度工程得分；→ 季度评审输入
- **出口**：5 指标 daily snapshot ≥ 4 周
- **工具**：自建（gh CLI + jq + cron）→ Apache DevLake → Sleuth / DX / DataDog DORA

### 4.9 看板 + WIP 限制（P4.2）

- **为什么**：无 WIP = 任务并行无限 = 实际无任务真正完成；看板 + WIP 是流速的物理约束
- **做什么**：看板列（Backlog/Doing/Review/Done）+ Doing 列 WIP 上限
- **系统编织**：→ DORA Lead Time（WIP 越大 lead time 越长）
- **出口**：WIP 上限有数；超出会被自动告警或拒入列
- **工具**：GitHub Projects / Azure DevOps Boards / Linear / Jira

### 4.10 Retrospective 节奏（P4.3）

- **为什么**：没有定期回顾 = 同样的错误重犯；改进无积累
- **做什么**：每个里程碑结束跑 retro；输出有 owner 的 action item；下次跟进
- **系统编织**：← post-mortem 输入；← DORA 数据输入；→ ADR
- **出口**：至少 1 次 retro 输出 action 并完成跟进
- **工具**：Miro / FunRetro / Metro Retro / Notion 模板

### 4.11 Blameless post-mortem（P4.4）

- **为什么**：incident 后追责 = 团队隐瞒下一次 incident；blameless 是组织学习的前提
- **做什么**：每次 incident 走 blameless 模板（时间线 + 根因 + 行动）+ 公开归档
- **系统编织**：← 事件管理触发；→ retro 输入
- **出口**：至少 1 次真实 post-mortem 公开存档；语气 blameless
- **工具**：Google SRE 模板 / PagerDuty Postmortems / 自建

### 4.12 Value stream mapping（P4.5）

- **为什么**：流程瓶颈靠拍脑袋找通常错；VSM 让"想法到生产"的等待时间可见
- **做什么**：至少做一次完整 VSM（idea → backlog → dev → review → deploy → 用户），标出每段等待时间
- **系统编织**：→ DORA Lead Time 优化输入；→ retro 改进对象
- **出口**：第一份 VSM 文档存档
- **工具**：Miro / draw.io / Lucidchart / Figjam

### 4.13 AI 接受率统计（P5.2）

- **为什么**：不知道 AI 建议被接受/拒绝率 = 无法判断 Harness 是否有效
- **做什么**：在 PR 中标记 AI 来源（commit trailer / label）+ 统计 merge 率
- **系统编织**：← Code review 制度；→ R1 自治阈值校准
- **出口**：接受率有 ≥ 4 周真实数据；既不在 100% 也不持续 < 30%
- **工具**：自建 git log 解析 + GitHub label 统计

### 4.14 健康度三维评分（P5.3）★

> **L1 核心能力 · 全图最重要的汇聚点**

- **为什么**：模块"还被需要 / 还健康 / 还在边界内"必须可计算；否则全靠主观
- **做什么**：业务/结构/工程三维评分 + 机械化采集 + daily 快照 + 任一维 < 30 告警
- **系统编织**：被 manifest / 静态守卫 / 漏洞扫描 / 覆盖率 / OTel / 性能基线 / DORA 七路汇入；→ reconciler 输入
- **出口**：至少 3 个模块有非占位三维分；评分有 ≥ 4 周趋势
- **工具**：自建 shell/python 脚本 + 各上游工具 API（Codecov / archtest / sonar）

### L1 出口信号

- 100% 模块 manifest+lifecycle
- 故意越界 PR 被 CI 拦
- trace_id 可反追 PR
- SLO 已 burn；on-call 有人；性能回归被拦过
- DORA daily ≥ 4 周
- AI 接受率 ≥ 4 周真实数据
- 健康度评分有趋势

→ **进入 L2 跃迁**

---

## 5 · L2 跃迁② · 意图可表达

### 5.1 Harness 五件套（P5.1）★

> **L2 入口能力**

- **为什么**：临时 prompt 无法跨 session 持久；Harness 是"AI 在项目中的工程外壳"
- **做什么**：建立 Anthropic 五件套
  - 系统上下文（CLAUDE.md / cursor rules / copilot instructions）
  - 工具约束（permissions / 命令黑名单）
  - 上下文注入（rules/skills 文件）
  - 记忆与进度（git log + ADR + memory 文件）
  - 评估循环（CI 全绿 + eval suite）
- **系统编织**：→ runtime agent 复用 Harness 配置；← ADR 与协作约定 是上下文输入
- **出口**：五件套都有具体文件；AI 在 PR 中能引用项目历史决策
- **工具**：Claude Code / Cursor / GitHub Copilot 选一

### 5.2 AI 决策审计起步（P5.4）

- **为什么**：AI 自主决策必须可追溯；否则 R1-R3 让渡时无法事后复盘
- **做什么**：每次 AI 触发的状态变更（lifecycle 迁移建议 / 自动 PR）写入 `docs/agent-decisions/<date>.md`，含触发器/动作/可逆性级别/回滚方式
- **系统编织**：→ 决策审计存储升级（结构化）；← Harness 评估循环触发
- **出口**：决策审计 ≥ 30 条积累
- **工具**：append-only markdown + git log

### 5.3 Feature flag 系统化（P6.1）

- **为什么**：起步的 flag 需要升级为系统：targeting rules / segment / 渐进 rollout / 自动清理
- **做什么**：flag 服务化 + canary（1% → 10% → 50% → 100%）+ shadow（对比新旧）+ flag 生命周期
- **系统编织**：← API 版本（按版本路由）；← 起步配置；→ reconciler（实验态切流走 flag）
- **出口**：至少 1 次真实 canary 回滚验证；flag 清理流程有自动化
- **工具**：Flipt（OSS）/ Unleash（OSS）/ LaunchDarkly / ConfigCat

### 5.4 IaC + GitOps（P6.2）

- **为什么**：手动操作环境必引发 state drift；不可一键创建/销毁 = 无法测试 + 无法快速恢复
- **做什么**：基础设施走 Terraform/Pulumi/Bicep + state 中心化管理 + GitOps（git 是真相源）
- **系统编织**：→ reconciler 借鉴 K8s controller 模式；← Secrets（IaC 用云凭证）
- **出口**：环境一键创建 + 一键销毁；state drift 可检测
- **工具**：Terraform / Pulumi / OpenTofu / Bicep + ArgoCD / Flux / Azure Deployment Environments

### L2 出口信号

- Harness 五件套就位
- 决策审计 ≥ 30 条
- Feature flag 至少 1 次真实 canary 回滚
- 环境一键创建/销毁

→ **进入 L3 跃迁**

> **关键 L2 → L3 信号**：能写出第一份带 4 块结构的 intent 文件（business / contract / quality / lifecycle），并且每个字段都能找到对应的验证器（参见主方法论 §7.3）。

---

## 6 · L3 跃迁③ · 系统自收敛

### 6.1 Runtime agent + R0-R5 可逆性梯度（P6.3）

- **为什么**：真正"运行时治理"的承诺。无 agent = 治理只在编译时
- **做什么**：建立 `runtime/agent/` 抽象（AgentTask interface）+ executor 按可逆性 R0-R5 路由
  - R0-R1：自治
  - R2：自动放行 + audit log
  - R3：提议 + 人审 + staged rollout
  - R4：阻塞 + 强制人决策
  - R5：永不放开（红线）
- **系统编织**：← Harness 配置；→ 被 reconciler 调用
- **出口**：R1 实验态 lifecycle 自动迁移在 dry-run 跑通
- **工具**：栈原生（Go time.Tick / Node node-cron / Python APScheduler / .NET IHostedService+Quartz / JVM @Scheduled）→ Temporal / Dapr（如规模大）

### 6.2 Reconciliation loop（P6.4）★

> **L3 核心能力**

- **为什么**：定期检查 desired vs current = 主动发现 drift；被动等用户报告 = 太晚
- **做什么**：定时 cron（如 30 min）拉 manifest + intent + 算 drift + 按 R0-R5 路由修正 + 报告状态
- **系统编织**：被 manifest / 健康度 / runtime agent 三方汇入；→ 决策审计存储
- **出口**：dry-run 多次零误判；R1 自治在 dry-run 跑通
- **工具**：自建 + GitHub Actions cron / 栈原生 scheduler / K8s Controller-runtime / Crossplane

### 6.3 决策审计存储升级（P6.5）

- **为什么**：markdown 存储不支持结构化查询；规模化后必须升级
- **做什么**：append-only markdown → SQLite（中量）/ EventStoreDB（大量）；提供 query CLI
- **系统编织**：← 起步存储 / ← reconciler 写入；→ 季度评审输入
- **出口**：决策可结构化查询（按时间/触发器/可逆性级别 filter）
- **工具**：SQLite / EventStoreDB / Postgres append-only table

### 6.4 Chaos engineering（P6.6 · 可选）

- **为什么**：没有故障注入演练 = 不知道系统真实容错边界；真出事时必慌
- **做什么**：定期注入故障（依赖延迟 / 节点 down / 网络分区）+ 验证 SLO 是否仍达
- **系统编织**：→ SLO 验证；→ post-mortem 演练
- **出口**：至少 1 次成功的 chaos 实验 + 报告
- **工具**：Litmus / Chaos Mesh（K8s）/ Gremlin / 自建 fault injection

### L3 出口信号

- reconciler dry-run 零误判
- R1 实验态自治跑通
- 决策审计可结构化查询
- （可选）至少 1 次成功 chaos 实验

→ **本手册功成身退**。后续按 [`three-leaps.md`](./three-leaps.md) §11 全景闭环 + §14 度量框架持续推进。

---

## 7 · 跨能力反模式

| 反模式 | 症状 | 矫正 |
|---|---|---|
| 跳能力 | L0 未出口直接做 L1 | 严格门控：上能力出口未达成不进入下一项 |
| 一步到位 | L0 即上 K8s+Temporal+DataDog | 按映射顺序，每能力只做必备 |
| 工具撞栈 | 同时用 GitHub Projects+Linear+Jira | 每能力只选 1 个工具 |
| 信号填空 | 让人手填 manifest / 健康度信号 | 必须机械化采集 |
| AI 崇拜 | 接受率 100% 否决率 0 | 强制 ≥ 10% 否决率作为健康下限 |
| 治理 ROI 倒挂 | 治理时间 > 编码 30% 持续两个里程碑 | 暂停推进，重审本能力范围 |
| 假覆盖率 | 全仓 80% 门禁逼出 fake test | 仅新增代码门禁 |
| 框架超前 | L0 即建 12 层 Clean Architecture | L0 只 3 层（domain / shared / adapters） |
| 跳过桥 | L1 出口直接做 reconciliation 自治 | 必须经 L2 Harness 五件套 |
| K8s 超前 | 服务数 < 5 上 K8s | Cloud Run / Container Apps 起步 |

---

## 8 · 倒退信号（不是失败，是诚实）

如果出现下列情况，**回退到前一能力重做**，而非继续推进：

- **倒退到 L0 重做**：仓库结构混乱到新成员 1 天内无法 onboard
- **倒退到 L0 守卫**：故意越界 PR 居然过了 CI（守卫失效）
- **倒退到 L0 漏洞扫描**：连续 2 周生产事件源于已知 CVE 但 Dependabot 未拦
- **倒退到 L1 OTel**：生产事件无法定位（无 trace / SLO 永远不 burn）
- **倒退到 L1 DORA**：DORA Lead Time 持续上升 3 个里程碑
- **倒退到 L1 接受率**：AI 接受率持续 < 30% 或持续 > 95%
- **倒退到 L3 reconciler**：reconciler 误退役活跃模块 ≥ 1 次

倒退不是失败，是诚实——**继续往下走**会把基础不稳的脆弱叠加扩大化。

---

## 9 · 验证清单（每跃迁出口）

| 跃迁 | 客观可验证清单 |
|---|---|
| L0 | [ ] CI 全绿；[ ] main 可运行；[ ] ADR；[ ] README+CONTRIBUTING+CODEOWNERS；[ ] 越界 PR 被拦；[ ] migration 演练；[ ] 4 层扫描全绿 ≥ 4 周；[ ] 0 secret 进 git；[ ] feature flag 起步 |
| L1 | [ ] 100% 模块 manifest+lifecycle；[ ] trace_id 反追 PR；[ ] SLO 已 burn；[ ] on-call 有人；[ ] DORA daily ≥ 4 周；[ ] retro+action；[ ] post-mortem；[ ] VSM；[ ] 健康度评分有趋势 |
| L2 | [ ] Harness 五件套就位；[ ] AI 接受率有数据；[ ] 决策审计 ≥ 30 条；[ ] flag canary 回滚验证；[ ] IaC 一键环境 |
| L3 | [ ] reconciler dry-run 零误判；[ ] R1 自治跑通；[ ] 决策审计可结构化查询；[ ] R5 永不放开 |

---

## 10 · 持续修订机制（本手册自身的治理）

本手册仍是**探索性文档**，必须接受实践质疑：

- 每个真实项目应用本手册时开 `bootstrap-feedback` issue（在该项目仓库内）
- 至少 3 个不同项目走过 L0-L3 后才考虑发布"v1"版本（在此之前是 v0.x 探索版）
- 每条工具推荐配实践证据（哪个项目用过 + 反馈），无证据的不进首选
- 每年至少 1 次审视：哪些工具下架、哪些新工具上架

**自治理红线**：

- ❌ 本手册声称自己是"最佳实践" → 删除该措辞，改回"探索性"
- ❌ 工具菜单 ≥ 6 个月未更新 → 触发审视
- ❌ 项目走完 L0-L3 但主方法论 §11 全景闭环跑不通 → 反向修订本手册

---

## 附录 A · 工具菜单矩阵（5 栈 × 关键能力）

**首选 = 单人/小团队起步**，**升级 = 团队 ≥ 5 人或服务数 ≥ 5 时考虑**。

| 能力 | TS/Node | Go | Python | Java/Kotlin | .NET |
|---|---|---|---|---|---|
| 包/构建 | npm/pnpm + tsx / esbuild | go modules | poetry / uv | maven / gradle | dotnet sdk |
| Lint | ESLint | golangci-lint | ruff | Checkstyle / ktlint | Roslyn analyzers |
| Type | tsc strict | go vet+staticcheck | mypy | 编译器内置 | 编译器内置 |
| 静态守卫 | dependency-cruiser | 自写 archtest | import-linter | ArchUnit | NetArchTest |
| 测试 | Jest / Vitest | testing+testify | pytest | JUnit 5 | xUnit |
| 覆盖率 | c8 / Istanbul → Codecov | -cover → Codecov | pytest-cov → Codecov | JaCoCo → Codecov | coverlet → Codecov |
| 依赖漏洞 | npm audit + Dependabot | govulncheck + Dependabot | pip-audit + Dependabot | OWASP DC + Dependabot | dotnet vulnerable + Dependabot |
| DB migration | Prisma Migrate / Knex | golang-migrate | Alembic | Flyway / Liquibase | EF Core Migrations |
| 性能基线 | k6 / Artillery / Lighthouse CI | k6 | Locust / k6 | JMeter / Gatling | NBomber / k6 |
| BDD | Cucumber.js | godog | behave | Cucumber-JVM | SpecFlow |
| Runtime agent | node-cron / BullMQ | time.Tick / robfig/cron | APScheduler / Celery | @Scheduled / Quartz | IHostedService + Quartz.NET |

**通用层**（不分栈）：

| 能力 | 起步首选 | 升级 |
|---|---|---|
| 仓库 + CI/CD + 看板 | GitHub（一站式）| Azure DevOps（Boards/Pipelines/Repos/Artifacts/Test Plans 五件套）|
| 漏洞 SAST | CodeQL（GitHub）/ Semgrep | SonarCloud / Snyk |
| 容器 | Docker | Buildah / nerdctl |
| 编排 | Cloud Run / Container Apps / ECS Fargate / 直接 systemd | Kubernetes（EKS / AKS / GKE） |
| IaC | Terraform | Pulumi / OpenTofu / Bicep（Azure） |
| GitOps | ArgoCD | Flux / Azure Deployment Environments |
| Telemetry | OpenTelemetry SDK + Grafana Cloud free | Application Insights / DataDog / New Relic / Honeycomb |
| Feature flag | Flipt / Unleash（OSS） | LaunchDarkly |
| Secrets | HashiCorp Vault / Azure Key Vault | Doppler / AWS Secrets Manager |
| AI Harness | Claude Code / Cursor / Copilot 选一 | 多角色 agent 分离 |
| DORA 采集 | 自建脚本 | Apache DevLake / Sleuth / DX |
| 事件管理 | PagerDuty free | Opsgenie / FireHydrant |

**Kubernetes 引入时机**：
- 单人 / 小团队 / 服务数 < 5：**不要上 K8s**，用 Cloud Run / Azure Container Apps / ECS Fargate / VM systemd
- 中团队 / 服务数 5-30：考虑托管 K8s（EKS / AKS / GKE）
- 大团队 / 服务数 30+：托管或自管 K8s，按需引入服务网格

---

## 附录 B · 单人 / 小团队 / 中团队 工具差异化

| 能力 | 单人 | 小团队（2-5）| 中团队（5-30）|
|---|---|---|---|
| 仓库+CI | GitHub Free | GitHub Team / Azure DevOps Basic | GitHub Enterprise / Azure DevOps Server |
| Issue+看板 | GitHub Issues+Projects | + Linear / Azure Boards | Linear / Jira / Azure Boards Pro |
| 通讯 | – | Slack free / Teams | Slack paid + PagerDuty |
| 漏洞 | Dependabot+CodeQL | + Snyk free / Semgrep | + Snyk team / SonarCloud |
| 覆盖率 | Codecov free | Codecov team | SonarCloud |
| Telemetry | Grafana Cloud free | + Sentry free | DataDog / Application Insights / New Relic |
| Secrets | Vault OSS / 1Password | Doppler / Vault Cloud | Vault Enterprise / AWS SM / Azure Key Vault |
| Feature flag | Flipt OSS / env 开关 | Unleash OSS | LaunchDarkly |
| AI Harness | Claude Code 个人 | Cursor Team / Claude for Teams | Cursor Enterprise / 自建评估 |
| Runtime | Cloud Run / Container Apps | 托管 K8s（如需）| 完整 K8s + 服务网格 |
| DORA | 自建脚本 | Apache DevLake | DevLake / Sleuth / DX |
| 决策审计 | append-only markdown | + SQLite | EventStoreDB / Postgres |
| 事件管理 | PagerDuty free（自己 on-call）| PagerDuty 5-user free | Opsgenie / FireHydrant |

**升级原则**：每升一档，**只换最痛的 1-2 个工具**。一次性换 5 个工具会导致团队工作流崩溃 4-6 周。

---

## 相关文档

- [主方法论 · three-leaps.md](./three-leaps.md)
- [配套幻灯片 · deck/index.html](./deck/index.html)
- English version: [three-leaps-bootstrap.en.md](./three-leaps-bootstrap.en.md)
- [Anthropic Harness 五件套](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [DORA 官方报告](https://dora.dev/)
- [Apache DevLake](https://devlake.apache.org/)
