# 状态化价值信号研究循环：面向可治理长期 AI 技能的框架

## 摘要

长期 AI 技能不同于一次性问答系统。它们面对的是目标会演化、路径不确定、证据需要积累、意义需要综合、人类仍需保持治理权的开放式任务。本文基于对 Claude Code `/autoresearch` 技能的机制分析，提出一个面向长期 AI 技能设计的框架：**状态化价值信号研究循环**（Stateful Value-Signal Research Loop）。该框架认为，一个可治理的长期 AI 技能需要四个相互耦合的机制：第一，持久化 artifact 应被设计为面向不同消费者的信息界面；第二，人机协作应被组织为价值信号交换，而不是逐步命令传递；第三，系统应区分生产局部证据的内循环与生产全局意义的外循环；第四，进展报告应作为人类治理接口，帮助人类在不 micromanage 的情况下校准方向。本文将该框架与 mixed-initiative interaction、provenance、AI risk management、distributed cognition、scientific workflow provenance 等相关理论传统进行定位，并给出长期 AI 技能的设计原则、失败模式和治理报告模板。

关键词：长期 AI 技能；人机协作；AI 治理；artifact；mixed initiative；provenance；autonomous research

---

## 1. 引言

多数 AI 交互仍然遵循一次性问答模式：

```text
人类提出问题 → AI 给出回答
```

这种模式适合解释概念、生成片段、总结文档、回答事实问题等边界清晰的任务。但在长期开放式任务中，它会迅速暴露局限。长期研究、复杂软件开发、产品探索、数据科学、安全审计、课程设计、企业知识管理等任务通常具有以下特点：

1. 初始目标不完整，并会随过程中发现而演化；
2. 行动路径无法预先完全规划；
3. 单次结果有噪声，需要多轮证据积累；
4. 价值不只来自执行动作，而来自对结果的解释与综合；
5. 人类既不能审批每一步，也不能完全放弃治理。

如果这类任务只依赖聊天上下文，系统会出现状态丢失、证据不可追溯、结论不可审计、方向漂移和人类治理成本过高等问题。

`/autoresearch` 提供了一个值得分析的案例。它不是简单回答研究问题，而是初始化研究工作区，维护状态文件、日志、发现文档、文献目录、实验目录、人类报告和最终论文目录，并通过内外双循环持续推进研究。

本文的问题是：

> `/autoresearch` 如何通过生产者/消费者角色、状态化 artifact 和双循环编排来调解人与 AI 的长期协作？

本文提出的回答是：长期 AI 技能应被设计为一种 **状态化价值信号研究循环**。

---

## 2. 相关工作与理论定位

本文框架不是对某一既有理论的直接复述，而是将多个相关传统综合到长期 AI 技能设计问题中。

### 2.1 Mixed-Initiative Interaction

Mixed-initiative interaction 研究人类和计算系统如何在问题求解中共享主动权。Horvitz 关于 mixed-initiative user interfaces 的工作为“主动权如何在人与系统之间转移”提供了重要参考。

在 `/autoresearch` 中，主动权不是简单归属于人类或 AI，而是按层级分配：

- 人类在目标、价值、约束、风险边界和方向校准层拥有主动权；
- AI 在搜索、记录、局部执行、综合和报告生成层拥有主动权；
- 进展报告是主动权从 AI 返回人类的界面。

因此，状态化价值信号研究循环可以被视为一种面向长期研究任务的 mixed-initiative 架构。

### 2.2 Provenance and Traceability

W3C PROV 系列标准以 entity、activity、agent 以及 generation、use、derivation、attribution 等关系描述 provenance。这为理解 `/autoresearch` 的 artifact 提供了形式化词汇。

在该框架中：

| PROV-like concept | `/autoresearch` equivalent |
|---|---|
| Entity | protocol、result、finding、report |
| Activity | experiment、literature search、outer-loop synthesis |
| Agent | human reviewer、AI assistant、domain skill |
| Derivation | data → analysis → findings → report |

这支持本文的 H1：artifact 不是普通文件，而是可追溯研究状态对象。

### 2.3 AI Risk Management and Human Oversight

NIST AI Risk Management Framework 强调治理、风险管理、透明度、问责、测量和社会技术语境。长期 AI 技能同样需要暴露目标、证据、不确定性、风险和下一步行动，使人类能够进行监督与方向校准。

因此，`to_human/` 中的进展报告不应被理解为展示材料，而应被理解为治理接口。

### 2.4 Distributed Cognition and Cognitive Artifacts

Distributed cognition 认为认知分布在人、工具、环境和外部表征之间。Cognitive artifacts 理论则强调外部表征如何改变认知任务本身。

`/autoresearch` 工作区可以被看作一个认知系统：

```text
human values + AI operations + artifact memory + reports + feedback
```

状态文件、日志、发现文档和报告共同承担记忆、比较、压缩、解释和治理功能。

### 2.5 Scientific Workflow Provenance

Scientific workflow provenance 研究强调记录数据依赖、执行上下文、参数、代码版本、输出和解释性元数据。该传统支持本文关于内循环证据生产的主张：如果没有 durable metadata 和 provenance，研究结果就难以比较、审计和复用。

---

## 3. 方法：对 `/autoresearch` 的概念分析

本文不是一个基准实验，而是对 `/autoresearch` 这一长期 AI 技能进行概念和设计分析。

分析围绕四个假设展开：

- **H1：状态化 artifact 是核心交互媒介。**
- **H2：人机协作是不对称生产者/消费者交换。**
- **H3：双循环架构分离证据生产与意义生产。**
- **H4：进展报告是主要治理接口。**

每个假设通过以下方式分析：

1. 将 skill 中的机制映射到生产者和消费者；
2. 识别对应 artifact 的压缩层级和决策功能；
3. 比较替代交互模型；
4. 分析缺失该机制时的失败模式；
5. 抽象为可复用设计原则。

---

## 4. 框架

### 4.1 H1：Artifact 是消费者界面

`/autoresearch` 的文件系统不是 housekeeping，而是 interaction architecture。

| Artifact | 主要消费者 | 功能 |
|---|---|---|
| `research-state.yaml` | AI | 操作状态和下一步行动 |
| `research-log.md` | AI + 人类审计者 | 决策时间线和可追溯性 |
| `findings.md` | AI + 人类 | 当前理解和认知压缩 |
| `literature/` | AI + 论文写作者 | 外部知识 grounding |
| `experiments/` | AI + 复现者 | 协议、证据、结果和分析 |
| `to_human/` | 人类 | 治理和方向校准接口 |
| `paper/` | 传播受众 | 最终贡献封装 |

因此，长期 AI 技能的 artifact 设计应从消费者出发：

```yaml
artifact:
  producer:
  consumer:
  compression_level:
  decision_enabled:
  failure_if_missing:
  update_cadence:
```

设计原则是：

> 不要先设计文件；先设计消费者。

### 4.2 H2：人机协作是价值信号交换

`/autoresearch` 的人机协作不是“人类下命令，AI 执行”，而是价值信号交换。

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

完整关系是：

```text
Human value signal
  → AI research production
  → compressed meaning
  → human steering signal
  → AI reprioritization
```

这说明，人类应通过价值函数控制 AI，而不是通过逐步过程控制 AI。

### 4.3 H3：内循环生产证据，外循环生产意义

`/autoresearch` 的双循环不是普通任务调度，而是认识论分工。

| Loop | Function | Main product | Failure if weak |
|---|---|---|---|
| Inner loop | Produce evidence | protocols, data, metrics, local analyses | 有框架无证据 |
| Outer loop | Produce meaning | patterns, mechanisms, direction decisions | 有活动无理解 |
| Human loop | Update value signal | steering, constraints, priorities | AI 漂移 |

内循环执行：

```text
select hypothesis → write protocol → execute → sanity check → measure → record
```

外循环综合：

```text
review results → cluster patterns → explain → update findings → decide direction
```

这防止了两个极端：盲目实验和无证据反思。

### 4.4 H4：进展报告是治理接口

进展报告是 AI 自主性与人类责任相遇的地方。

```text
Internal artifacts
  → report synthesis
  → human judgment
  → updated value signal
  → AI reprioritization
```

一个治理报告应回答：

| Report component | Human question | Governance function |
|---|---|---|
| Objective | 是否还在解决正确问题？ | 目标对齐 |
| Current status | 当前进度在哪里？ | 定位 |
| Key findings | 学到了什么？ | 意义消费 |
| Evidence summary | 为什么可信？ | 信任校准 |
| Negative results | 排除了什么？ | 避免重复浪费 |
| Open questions | 还有什么不确定？ | 风险意识 |
| Direction recommendation | 深化、拓展、转向还是收束？ | 方向控制 |
| Next actions | 人类不干预时 AI 会做什么？ | 预期管理 |
| Human decision points | 需要人类提供什么？ | 价值信号更新 |
| Artifact links | 哪里能查细节？ | 可审计性 |

---

## 5. 状态化价值信号研究循环

综合 H1-H4，得到最终框架：

```text
Human Value Signal
  → Artifact-Mediated State
  → Inner Loop Evidence
  → Outer Loop Meaning
  → Governance Report
  → Updated Value Signal
```

定义如下：

> 状态化价值信号研究循环是一种长期 AI 交互模式：人类提供价值信号与治理，AI 维护 artifact-mediated state，内循环生产证据，外循环生产意义，治理报告关闭人类方向控制循环。

该框架的价值在于澄清“自主性”和“可治理性”的关系。AI 可以自主执行大量低层动作，但系统仍然可治理，因为价值信号、artifact、证据、综合和报告都被组织成适合人类检查和校准的结构。

---

## 6. 设计启发

### 6.1 显式设计 artifact schema

长期 AI 技能至少应包含：

- 操作状态；
- 决策日志；
- findings / synthesis 文档；
- evidence directory；
- human report directory；
- final deliverable directory。

### 6.2 区分价值控制和过程控制

人类不应被迫审批每一步。人类应定义目标、约束、成功标准和风险边界；AI 应暴露下一步计划，只在高风险、不可逆、昂贵或外部可见动作前请求确认。

### 6.3 将综合视为必需操作

长期 AI 技能不能把“活动量”等同于“进展”。它必须周期性更新 synthesis artifact，说明学到了什么、失败了什么、还不确定什么、下一步建议是什么。

### 6.4 让报告具有决策面

报告不能只是 activity dump。报告必须包含 claim、evidence、uncertainty、direction recommendation 和 human feedback surface。

---

## 7. 失败模式

| Failure mode | Symptom | Cause | Fix |
|---|---|---|---|
| Output without value | 内容很多但不知有何用 | 价值信号弱 | 明确目标、受众、成功标准 |
| Activity without understanding | 实验多但 findings 薄 | 外循环弱 | 强制综合和方向判断 |
| Framework without grounding | 叙事漂亮但无证据 | 内循环弱 | 补协议、案例、数据 |
| Human bottleneck | 频繁小审批 | 程序控制过强 | 只审批高风险动作 |
| AI drift | 越做越偏 | 价值信号过期或报告弱 | 生成治理报告并刷新优先级 |
| False certainty | 弱证据写成强结论 | 缺少置信度标注 | 标注 evidence type 和 confidence |

---

## 8. 局限性

本文是对一个具体 AI 技能的概念分析，而不是跨多个系统的实证研究。虽然框架已经通过 artifact mapping、interaction-model comparison、loop mapping 和 governance-interface analysis 得到内部支持，并通过外部理论进行了初步定位，但仍有几个局限：

1. 尚未在多个长期 AI 技能中比较验证；
2. 尚未量化报告治理对效率、信任或对齐的影响；
3. 部分引用虽然已有元数据，但仍需要 quote-level verification；
4. 当前框架更适合解释和设计，不等同于严格预测模型；
5. 不应声称外部标准或作者“证明”或“背书”该框架。

未来工作可以在不同长期 AI 技能中测试该框架，比较不同 artifact schema 的效果，并研究报告节奏如何影响人类信任校准和 AI 方向稳定性。

---

## 9. 结论

`/autoresearch` 表明，高级 AI 技能不应只被理解为更强 prompt 或更多工具调用，而可以被设计为可治理的状态化系统。

在这样的系统中：

```text
人类定义价值；
AI 生产证据；
artifact 保存状态；
外循环生成意义；
报告形成治理；
反馈更新方向。
```

状态化价值信号研究循环为长期 AI 技能提供了一套可复用词汇和设计模板。它解释了 AI 如何在保持自主推进的同时，仍然能够被人类检查、校准和治理。

---

## 参考文献

当前引用包见 `paper/references.bib`。核心参考方向包括：Horvitz 的 mixed-initiative user interfaces、W3C PROV 标准、NIST AI RMF 1.0、Hutchins 的 distributed cognition、Norman 的 cognitive artifacts，以及 Davidson 与 Freire 关于 scientific workflow provenance 的研究。
