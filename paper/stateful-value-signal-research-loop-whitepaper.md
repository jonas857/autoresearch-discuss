# 白皮书草案：状态化价值信号研究循环

副标题：从 `/autoresearch` 看长期 AI 技能的人机协作、治理与 artifact 设计

> Citation-aware draft. 本文已加入相关理论定位，但部分外部来源仍需正式 citation verification。适合作为白皮书/方法论草稿；若用于学术投稿，应进一步核验引用元数据、页码、DOI 与原文表述。

---

## 摘要

本文基于对 Claude Code `/autoresearch` 技能的机制拆解，提出一个用于设计长期 AI 技能的框架：**Stateful Value-Signal Research Loop**，即“状态化价值信号研究循环”。该框架认为，长期 AI 协作系统不应被设计为简单命令执行器，也不应被理解为完全自主代理，而应被设计为一种可治理的状态化系统：人类提供价值信号与方向治理，AI 维护 artifact-mediated state，内循环生产局部证据，外循环生产全局意义，进展报告则作为人类治理接口关闭反馈循环。

本文将该框架拆解为四个机制：

1. **Artifact Interfaces**：持久化文件是消费者界面，而不是被动存储。
2. **Value-Signal Exchange**：人机协作的核心是价值信号交换，而不是命令传递。
3. **Epistemic Loop Separation**：内循环生产证据，外循环生产意义。
4. **Governance Reports**：进展报告是长期 AI 代理的人类治理接口。

该框架与 mixed-initiative interaction、provenance、AI risk management、distributed cognition 等外部理论传统存在自然连接。

---

## 1. 引言：从一次性回答到长期协作系统

传统 AI 对话通常遵循：

```text
Human asks → AI answers
```

这种模式适合一次性任务，但不适合长期开放式研究。长期研究具有路径不确定、目标会演化、证据需要积累、意义需要反复综合等特点。若仅依赖聊天记录，系统容易出现状态丢失、证据不可追溯、结论不可审计、人类难以治理等问题。

`/autoresearch` 提供了另一种范式：

```text
Human defines value and boundaries
  → AI continuously produces structured research work
  → human periodically consumes compressed insight and redirects if needed
```

因此，本文将 `/autoresearch` 视为一种长期 AI 技能的原型，并抽象出可复用设计框架。

---

## 2. 相关理论定位：本文框架连接哪些传统？

> 注：本节是 citation-aware positioning。当前环境已识别相关来源方向，但部分页面直接抓取受阻。正式出版前应进一步验证引用细节。

### 2.1 Mixed-Initiative Interaction

Mixed-initiative interaction 关注人类与计算系统如何共享问题求解中的主动权。Eric Horvitz 的 “Principles of Mixed-Initiative User Interfaces” 是该方向的重要参考之一。

与本文框架的连接：

- `/autoresearch` 不是人类逐步命令 AI，也不是 AI 完全自主。
- 主动权按层级分配：人类在目标、价值、约束、反馈层占主导；AI 在搜索、执行、综合、报告生成层占主导。
- 进展报告是主动权从 AI 转回人类的关键界面。

因此，Stateful Value-Signal Research Loop 可以被理解为一种面向长期研究任务的 mixed-initiative architecture。

### 2.2 Provenance and Traceability

W3C PROV 模型关注 entities、activities、agents 之间的 provenance 关系。该思想与 `/autoresearch` 的 artifact 结构高度一致。

对应关系：

| PROV-like concept | `/autoresearch` equivalent |
|---|---|
| Entity | findings、report、result file、protocol |
| Activity | experiment、literature search、outer-loop synthesis |
| Agent | human reviewer、AI assistant、domain skill |
| Derivation | data → analysis → findings → report |

这支持 H1：artifact 不是简单文件，而是可追溯关系的承载体。

### 2.3 AI Risk Management and Human Oversight

AI 风险管理框架强调监控、问责、透明度、风险识别与人类监督。NIST AI Risk Management Framework 是相关参考之一。

与本文框架的连接：

- 长期 AI 代理需要暴露目标、证据、风险、未确定性和下一步行动。
- 进展报告为人类提供监督界面。
- 报告不是展示材料，而是治理机制。

这支持 H4：progress report 是 governance interface。

### 2.4 Distributed Cognition and Artifact-Mediated Work

Distributed cognition 关注认知如何分布在个体、工具、环境与外部表征之间。`/autoresearch` 的工作区正是一个 artifact-mediated cognitive system：

```text
human values + AI operations + artifact memory + reports + feedback
```

这支持一个更强的结论：长期 AI 技能的智能不只存在于模型内部，也存在于工作区 artifact 结构中。

---

## 3. 第一性原理：目标、信息、行动、反馈

任何人机研究系统都可以还原为四个原语：

```text
Goal → Information → Action → Feedback
```

在 `/autoresearch` 中：

| 原语 | 人类责任 | AI 责任 | 关键 artifact |
|---|---|---|---|
| Goal | 定义目标、受众、成功标准 | 转化为研究问题和假设 | `research-state.yaml` |
| Information | 提供背景和价值判断 | 搜索、记录、压缩信息 | `literature/`, `findings.md` |
| Action | 设定边界和风险阈值 | 执行实验与分析 | `experiments/`, `data/` |
| Feedback | 通过报告校准方向 | 将反馈写回状态 | `to_human/`, `research-log.md` |

长期 AI 技能的设计重点，就是让这四个原语在多轮循环中稳定运作。

---

## 4. H1：Artifact 是消费者界面

`/autoresearch` 的 artifact 并非普通文件组织，而是面向不同消费者的信息界面。

| Artifact | Primary Consumer | Role |
|---|---|---|
| `research-state.yaml` | AI | 机器可读状态和下一步行动 |
| `research-log.md` | AI + human auditor | 决策时间线和可审计性 |
| `findings.md` | AI + human | 当前理解和认知压缩 |
| `literature/` | AI + paper writer | 外部知识 grounding |
| `experiments/` | AI + reproducibility reviewer | 协议、证据和分析 |
| `to_human/` | Human | 治理和方向校准界面 |
| `paper/` | Publication audience | 最终贡献封装 |

设计原则：

```text
Do not design files first.
Design consumers first.
```

每个 artifact 都应声明：

```yaml
producer:
consumer:
compression_level:
decision_enabled:
failure_if_missing:
update_cadence:
```

---

## 5. H2：人机协作是价值信号交换

本文将 `/autoresearch` 中的人机协作定义为 value-signal exchange。

人类主要生产：

```yaml
objective:
audience:
success_criteria:
constraints:
risk_boundaries:
feedback_cadence:
```

AI 主要生产：

```yaml
state_updates:
evidence_packages:
synthesis:
decision_options:
governance_reports:
```

完整交换关系：

```text
Human value signal
  → AI research production
  → compressed meaning
  → human steering signal
  → AI reprioritization
```

核心原则：

> Control by value function, not by step-by-step procedure.

这解释了为什么 `/autoresearch` 不适合被 micromanage，也不能完全无监督运行。

---

## 6. H3：内循环生产证据，外循环生产意义

长期研究需要区分两类生产：

| Loop | Function | Output | Failure if weak |
|---|---|---|---|
| Inner loop | Produce evidence | protocols, metrics, local analyses | 框架无证据 |
| Outer loop | Produce meaning | patterns, mechanisms, direction | 活动无理解 |
| Human loop | Update value signal | steering, constraints, priorities | AI 漂移 |

内循环负责：

```text
Pick hypothesis → protocol → run/analysis → sanity check → measure → record
```

外循环负责：

```text
Review → cluster → explain → update findings → decide deepen/broaden/pivot/conclude
```

这就是 epistemic loop separation：不同循环承担不同认识论功能。

---

## 7. H4：进展报告是治理接口

进展报告不是展示材料，而是治理界面。它把 AI 内部工作转化为人类可判断、可校准、可介入的信息结构。

```text
Internal artifacts
  → report synthesis
  → human judgment
  → updated value signal
  → AI reprioritization
```

一个合格治理报告至少应包含：

1. Objective and value function
2. What changed since last report
3. Key claims with evidence
4. Negative results
5. Open questions and uncertainty
6. Direction recommendation
7. Human feedback surface
8. Next autonomous actions

没有 decision surface 的报告只是状态更新；有 decision surface 的报告才是治理接口。

---

## 8. 最终框架：Stateful Value-Signal Research Loop

最终闭环：

```text
Human Value Signal
  → Artifact-Mediated State
  → Inner Loop Evidence
  → Outer Loop Meaning
  → Governance Report
  → Updated Value Signal
```

定义：

> Stateful Value-Signal Research Loop 是一种长期 AI 交互模式：人类提供价值信号与治理，AI 维护 artifact-mediated state，内循环生产证据，外循环生产意义，治理报告关闭人类方向控制循环。

---

## 9. 诊断矩阵

| Failure Mode | Symptom | Cause | Fix |
|---|---|---|---|
| Output without value | 很多内容但不知有何用 | 价值信号弱 | 明确 objective/audience/success criteria |
| Activity without understanding | 实验多但 findings 薄 | 外循环弱 | 强制综合和模式提取 |
| Framework without grounding | 叙事漂亮但无证据 | 内循环弱 | 补协议、案例、数据 |
| Human bottleneck | 频繁小审批 | 程序控制过强 | 只审批高风险动作 |
| AI drift | 越做越偏 | 报告少或价值信号过期 | 生成治理报告，刷新优先级 |
| False certainty | 弱证据写成强结论 | 报告无置信度 | 标注 evidence type/confidence |

---

## 10. 对长期 AI 技能设计的启发

长期 AI 技能不应只设计 prompt，也不应只设计工具链，而应设计：

1. 价值信号输入协议；
2. artifact schema；
3. evidence loop；
4. meaning loop；
5. governance report；
6. health checks；
7. failure recovery rules。

该框架适用于：

- 自动研究代理；
- 长期编码代理；
- 产品探索代理；
- 安全审计代理；
- 数据科学代理；
- 企业知识管理代理；
- 课程/内容生产代理。

只要任务是长期、开放、多步、需要逐步减少不确定性，就可以使用该框架。

---

## 11. 引用状态与待验证来源

| Area | Candidate source | Status |
|---|---|---|
| Mixed-initiative interaction | Horvitz, “Principles of Mixed-Initiative User Interfaces” | Candidate identified; needs full verification |
| Provenance | W3C PROV Overview / PROV Recommendations | Candidate identified; needs full verification |
| AI governance | NIST AI Risk Management Framework | Candidate identified; needs full verification |
| Distributed cognition | Hutchins / external representation literature | Needs source collection |
| Scientific workflows | workflow provenance / experiment tracking literature | Needs source collection |

正式论文版本需要补充：作者、年份、venue、DOI/URL、BibTeX、准确引用语境。

---

## 12. 结论

`/autoresearch` 的意义不只是自动化研究流程，而是展示了一种长期 AI 技能设计范式。

它让 AI 从一次性回答者转变为长期研究合作者；同时，它并没有取消人类治理，而是将人类治理提升到价值函数、方向校准和报告审阅层。

最终结论是：

```text
人类定义价值；
AI 生产证据；
artifact 保存状态；
外循环生成意义；
报告形成治理；
反馈更新方向。
```

这就是状态化价值信号研究循环。
