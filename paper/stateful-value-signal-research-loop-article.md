# 状态化价值信号研究循环：长期 AI 技能的方法论

## 摘要

长期 AI 技能不应被理解为“更长的聊天”或“更多工具调用”。当任务具有开放性、多步骤、不确定性和持续演化特征时，普通对话会很快遇到状态丢失、证据不可追溯、目标漂移和人类难以治理的问题。

本文基于对 `/autoresearch` 的机制拆解，提出一种可复用方法论：**Stateful Value-Signal Research Loop**，中文可称为**状态化价值信号研究循环**。

它的核心观点是：

> 长期 AI 技能的关键，不是让 AI 完全自主，也不是让人类逐步指挥，而是把人类价值信号、AI 证据生产、状态化 artifact、意义综合和治理报告组织成一个可持续循环。

这个方法论适用于长期研究、复杂软件开发、产品探索、数据分析、安全审计、课程生成、企业知识管理等开放式任务。

---

## 1. 为什么需要一种新的长期 AI 技能方法论？

普通 AI 对话通常是：

```text
人类提出问题 → AI 给出回答
```

这种模式适合一次性任务，例如解释概念、生成代码片段、总结文档。但长期任务具有不同性质：

1. **目标会演化**：一开始的问题往往不是最终最值得解决的问题。
2. **路径不确定**：无法提前完整规划每一步。
3. **证据会累积**：单次搜索、实验或分析都不足以形成可靠判断。
4. **理解需要综合**：价值来自多轮证据、反思、对比和抽象。
5. **人类需要治理**：人类不能看每个底层动作，但也不能完全失去方向控制。

如果长期任务只依赖聊天记录，就会出现五类问题：

| 问题 | 表现 | 后果 |
|---|---|---|
| 状态不可恢复 | 上下文越来越长，关键决策被埋没 | AI 难以接续工作 |
| 证据不可追溯 | 结论和来源混在一起 | 人类无法判断可信度 |
| 目标漂移 | AI 持续行动但方向变化 | 产出越来越偏 |
| 人类治理成本高 | 要么频繁审批，要么完全不看 | 自主性和控制力二选一 |
| 意义无法积累 | 活动很多，理解很薄 | 只有过程，没有研究成果 |

因此，长期 AI 技能需要一种不同于普通对话的方法论。

---

## 2. 方法论总览：Stateful Value-Signal Research Loop

**Stateful Value-Signal Research Loop** 可以概括为：

```text
Human Value Signal
  ↓
Artifact-Mediated State
  ↓
Inner Loop Evidence
  ↓
Outer Loop Meaning
  ↓
Governance Report
  ↓
Updated Value Signal
```

中文解释：

```text
人类价值信号
  ↓
artifact 中介的状态
  ↓
内循环生产证据
  ↓
外循环生产意义
  ↓
治理报告
  ↓
更新后的人类价值信号
```

这个循环包含五个关键层：

| 层 | 核心问题 | 主要产物 |
|---|---|---|
| 价值信号层 | 人类到底想要什么？ | objective、audience、success criteria、constraints |
| 状态 artifact 层 | 如何让长期任务可恢复、可审计？ | state、log、findings、protocol、report |
| 证据生产层 | 如何持续减少不确定性？ | 搜索结果、实验结果、案例、数据、分析 |
| 意义综合层 | 如何把证据变成方向判断？ | pattern、mechanism、hypothesis、recommendation |
| 治理报告层 | 人类如何低成本控制方向？ | progress report、decision options、risk surface |

这不是一个线性流程，而是一个循环系统。每一轮结束后，人类可以通过报告更新价值信号，AI 再根据新信号重新排序下一步行动。

---

## 3. 第一层：Human Value Signal

长期 AI 技能的起点不是 prompt，而是**价值信号**。

价值信号回答的问题是：

```text
这个长期任务为什么值得做？
为谁做？
做到什么程度算成功？
有哪些约束和风险边界？
什么时候需要人类介入？
```

一个最小可用的价值信号模板如下：

```yaml
objective: "要解决的核心问题"
audience: "主要受众或消费者"
success_criteria:
  - "成功标准 1"
  - "成功标准 2"
constraints:
  - "时间、资源、风格、合规或安全约束"
risk_boundaries:
  - "哪些动作需要先请示人类"
feedback_cadence: "什么时候生成报告，什么时候等待反馈"
```

### 方法原则

人类最重要的责任不是给 AI 安排每个步骤，而是提供高质量价值信号。

低质量价值信号：

```text
研究一下这个问题。
```

高质量价值信号：

```text
面向 AI skill 设计者，解释长期研究型 AI 技能如何在人类控制与 AI 自主之间取得平衡。产出要能复用为方法论模板，避免只做功能描述。若发现证据不足，需要标注不确定性并提出下一步验证路径。
```

后者能让 AI 自主行动，同时保持方向可控。

---

## 4. 第二层：Artifact-Mediated State

长期 AI 技能不能只靠聊天上下文运行。它需要一组状态化 artifact。

这些 artifact 不是“存档文件”，而是**消费者界面**：每个文件都服务于某类未来读者和决策。

| Artifact 类型 | 主要消费者 | 作用 |
|---|---|---|
| state | AI | 恢复当前状态、下一步动作、开放问题 |
| log | AI + 审计者 | 保存关键决策时间线 |
| findings | AI + 人类 | 压缩当前理解和稳定结论 |
| literature | 论文写作者 + AI | 保存外部理论依据 |
| experiments | 复现者 + AI | 保存协议、结果和分析 |
| reports | 人类 | 提供治理、校准和方向选择 |
| final deliverables | 传播受众 | 封装最终贡献 |

设计任何 artifact 前，都应该先回答六个问题：

```yaml
producer: "谁生产它？"
consumer: "谁消费它？"
compression_level: "它是原始证据、分析摘要，还是最终结论？"
decision_enabled: "它支持什么决策？"
failure_if_missing: "如果没有它，系统会失去什么能力？"
update_cadence: "什么时候更新？"
```

### 方法原则

> 先设计消费者，再设计文件。

如果一个 artifact 没有明确消费者，它很可能只是噪音；如果一个重要消费者没有对应 artifact，长期任务就会在那个环节失去可治理性。

---

## 5. 第三层：Inner Loop Evidence

内循环负责生产局部、可检查、可追溯的证据。

典型内循环如下：

```text
选择假设
  → 写 protocol
  → 执行搜索/实验/分析
  → sanity check
  → 记录结果
  → 更新 findings/state
```

内循环的目标不是写漂亮叙事，而是减少不确定性。

它应该产出：

- 搜索结果；
- 引文和来源；
- 实验协议；
- 运行结果；
- 对比表；
- 失败路径；
- 局部结论；
- confidence 标注。

### 方法原则

内循环必须满足三个要求：

1. **可追溯**：结论能回到证据来源。
2. **可复查**：未来可以理解为什么这么做。
3. **可比较**：不同轮次结果能被放在一起判断。

如果内循环弱，系统会出现“有框架无证据”：叙事很完整，但没有可靠支撑。

---

## 6. 第四层：Outer Loop Meaning

外循环负责把多轮证据转化为意义。

典型外循环如下：

```text
回顾多轮结果
  → 聚类模式
  → 识别机制
  → 更新假设
  → 判断方向
  → 生成报告或新任务
```

外循环回答的问题不是“刚才做了什么”，而是：

```text
我们现在真正学到了什么？
哪些假设被支持、削弱或重写？
哪些结果只是噪音？
下一步应该 deepen、broaden、pivot 还是 conclude？
```

### 四种方向判断

| 判断 | 含义 | 触发条件 |
|---|---|---|
| Deepen | 深化 | 当前方向有效，但证据还不够深 |
| Broaden | 拓展 | 需要更多案例、领域或比较对象 |
| Pivot | 转向 | 原问题或假设不再成立 |
| Conclude | 收束 | 已足够形成交付物或阶段结论 |

### 方法原则

> 内循环生产证据，外循环生产意义。

如果只有内循环，系统会变成“有活动无理解”；如果只有外循环，系统会变成“有框架无证据”。长期 AI 技能必须显式设计这两个循环。

---

## 7. 第五层：Governance Report

治理报告是人类控制长期 AI 系统的主要界面。

它不是工作总结，而是决策界面。

一个好的治理报告应该回答：

1. 我们是否仍在解决正确问题？
2. 当前真正学到了什么？
3. 证据是什么？
4. 哪些结论仍不确定？
5. 风险在哪里？
6. 建议深化、拓展、转向还是收束？
7. 如果人类不干预，AI 下一步会做什么？
8. 现在最需要人类提供什么反馈？

### 治理报告模板

```markdown
# Progress Report

## 1. Objective and Value Function
- Objective:
- Audience:
- Success criteria:
- Constraints:

## 2. What Changed
- New evidence:
- New synthesis:
- Updated hypotheses:

## 3. Key Claims
| Claim | Evidence | Confidence | Artifact Links |

## 4. Negative Results
- Failed paths:
- Ruled-out assumptions:
- Do not repeat:

## 5. Open Questions and Risks
- Uncertainties:
- Risks:

## 6. Direction Recommendation
- Deepen / Broaden / Pivot / Conclude:
- Rationale:

## 7. Human Feedback Surface
- Options:
- Most useful feedback:

## 8. Next Autonomous Actions
- If no correction arrives, AI will:
```

### 方法原则

报告应该在能改变治理判断的时候生成，而不是在每次活动后生成。

适合生成报告的时机包括：

- 完成一轮综合；
- 出现意外发现；
- 需要 pivot；
- 长时间停滞；
- 即将执行高成本或不可逆动作；
- 需要人类更新目标或约束。

---

## 8. 人机分工：Producer-Consumer 视角

长期 AI 协作可以看成一种非对称 producer-consumer 交换。

人类主要生产：

- 目标；
- 价值判断；
- 成功标准；
- 约束；
- 风险边界；
- 方向反馈。

人类主要消费：

- 压缩后的意义；
- 决策选项；
- 风险提示；
- 最终交付物。

AI 主要消费：

- 人类价值信号；
- 既有状态；
- 外部信息；
- 工具反馈；
- 人类校准。

AI 主要生产：

- 证据；
- 状态更新；
- artifact；
- 综合；
- 报告；
- 交付物。

这个视角的关键是：

> 人类通过价值函数控制 AI，而不是通过逐步命令控制 AI。

逐步命令会让 AI 退化成执行器；完全不管会导致漂移。更好的结构是：人类低频高层校准，AI 高频低层执行。

---

## 9. 实施步骤：如何设计一个长期 AI 技能？

### Step 1：定义价值信号

写清楚：

```yaml
objective:
audience:
success_criteria:
constraints:
risk_boundaries:
feedback_cadence:
```

检查问题：

- AI 是否知道什么叫“好”？
- AI 是否知道为谁优化？
- AI 是否知道什么不能做？
- AI 是否知道什么时候回来问人？

### Step 2：设计 artifact map

列出 artifact：

```yaml
state_artifact:
log_artifact:
findings_artifact:
evidence_artifact:
human_report_artifact:
final_deliverable_artifact:
```

每个 artifact 都填写：

```yaml
producer:
consumer:
compression_level:
decision_enabled:
failure_if_missing:
update_cadence:
```

### Step 3：定义内循环

写明：

```yaml
inner_loop:
  input:
  action:
  evidence_output:
  sanity_check:
  state_update:
```

内循环要保证证据能追溯、能复查、能比较。

### Step 4：定义外循环

写明：

```yaml
outer_loop:
  review_inputs:
  synthesis_method:
  hypothesis_update:
  direction_decision:
  report_trigger:
```

外循环要避免只做活动罗列，必须产出模式、机制或方向判断。

### Step 5：定义治理报告

写明：

```yaml
governance_report:
  cadence:
  required_sections:
  decision_options:
  human_feedback_surface:
  next_action_policy:
```

报告要服务于人类决策，而不是服务于展示 AI 很忙。

### Step 6：定义健康检查

```yaml
artifact_health:
  - 是否可恢复？
  - 是否可追溯？
  - 是否有消费者？
value_signal_health:
  - 目标是否仍有效？
  - 成功标准是否明确？
loop_health:
  - 内循环是否产生证据？
  - 外循环是否产生意义？
governance_health:
  - 报告是否帮助人类做方向判断？
```

---

## 10. 诊断矩阵：如何发现系统失效？

| 失败模式 | 症状 | 根因 | 修复 |
|---|---|---|---|
| 输出无价值 | 内容很多，但不知道有什么用 | 价值信号弱 | 明确目标、受众、成功标准 |
| 有活动无理解 | 搜索/实验很多，findings 很薄 | 外循环弱 | 强制综合、模式聚类、方向判断 |
| 有框架无证据 | 叙事完整但支撑不足 | 内循环弱 | 补 protocol、证据、案例、引用 |
| 人类瓶颈 | 每一步都要审批 | 步骤控制过强 | 改为只审批高风险/不可逆动作 |
| AI 漂移 | 越做越偏 | 报告少或价值信号过期 | 生成治理报告，刷新目标和约束 |
| 虚假确定性 | 弱证据被写成强结论 | 缺少 confidence 和 evidence type | 标注证据类型、置信度、不确定性 |
| Artifact 噪音 | 文件很多但没人读 | 未定义消费者 | 删除、合并或重新定义 artifact |
| 难以接续 | 下一轮不知道从哪开始 | state/log 缺失 | 维护 state、next actions、open questions |

---

## 11. 适用场景

这个方法论适用于：

- 长期研究代理；
- 复杂软件开发代理；
- 数据科学和实验分析代理；
- 安全审计和风险评估代理；
- 产品探索和用户研究代理；
- 课程设计和知识生产代理；
- 企业知识管理和决策支持代理。

共同特征是：

```text
开放式问题 + 多轮行动 + 不确定性减少 + 需要人类治理 + 需要最终交付
```

如果任务只是一条命令或一次性问答，就不需要完整循环；如果任务会持续数小时、数天甚至数周，就应该引入这个方法论。

---

## 12. 外部理论依据

这个方法论不是孤立发明，而是综合了五类外部研究传统。

### 12.1 Mixed-Initiative Interaction

Eric Horvitz 在 CHI 1999 的 mixed-initiative user interfaces 研究说明，人机系统不必在“人类全程指挥”和“机器完全自主”之间二选一。更好的结构是根据任务、风险和不确定性分配 initiative。

对应到本文框架：initiative 不是按每个微动作切分，而是按认识论层级切分。人类控制价值、约束和治理，AI 控制常规证据生产与综合，报告则在关键节点把 initiative 交还给人类。

### 12.2 W3C PROV

W3C PROV 系列标准把 provenance 建模为 entity、activity、agent 以及 generation、use、derivation、attribution 等关系。

对应到长期 AI 技能：protocol、result、analysis、findings、report 都可以被视为 provenance-bearing entities；实验、搜索、综合是 activities；AI、人类和领域 skill 是 agents。这样看，文件系统不是 housekeeping，而是可追溯的研究状态结构。

### 12.3 NIST AI RMF 1.0

NIST AI Risk Management Framework 1.0 强调 AI 风险是 socio-technical 的，并把 governance、measurement、management、trust calibration、accountability、transparency 等作为风险管理核心。

对应到本文框架：进展报告不是“总结做了什么”，而是让人类理解目标、证据、不确定性、风险和下一步行动的治理界面。

### 12.4 Distributed Cognition and Cognitive Artifacts

Hutchins 的 distributed cognition 和 Norman 的 cognitive artifacts 理论说明，复杂认知任务分布在人员、工具、表示和环境中。

对应到长期 AI 技能：workspace 本身就是认知系统的一部分。状态文件、日志、发现文档和报告共同承担记忆、比较、压缩和方向校准功能。

### 12.5 Scientific Workflow Provenance

Scientific workflow provenance 和 experiment tracking 文献说明，可复现研究系统必须保存执行上下文、依赖关系、参数、版本、输出和解释性元数据。

对应到本文框架：内循环证据生产和外循环意义生产需要由稳定 artifact 连接，否则研究就无法比较、审计、复用和治理。

---

## 13. 引用建议

可用于正式论文的核心引用：

1. Horvitz, Eric. "Principles of Mixed-Initiative User Interfaces." *Proceedings of CHI 1999*, pp. 159-166. DOI: 10.1145/302979.303030.
2. W3C PROV Working Group. *PROV-Overview*, *PROV-DM*, and *PROV-O*. W3C, 2013.
3. National Institute of Standards and Technology. *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*. NIST AI 100-1, 2023. DOI: 10.6028/NIST.AI.100-1.
4. Hutchins, Edwin. *Cognition in the Wild*. MIT Press, 1995.
5. Norman, Donald A. "Cognitive Artifacts." In *Designing Interaction*, Cambridge University Press, 1991.
6. Davidson, Susan B., and Juliana Freire. "Provenance and Scientific Workflows: Challenges and Opportunities." *SIGMOD 2008*. DOI: 10.1145/1376616.1376772.
7. Moreau, Luc, et al. "The Open Provenance Model Core Specification." *Future Generation Computer Systems*, 2011. DOI: 10.1016/j.future.2010.07.005.
8. Zaharia, Matei, et al. "Accelerating the Machine Learning Lifecycle with MLflow." *IEEE Data Engineering Bulletin*, 2018.

注意：这些引用支持本文框架的设计要求，但不代表这些作者或机构直接提出或认可 Stateful Value-Signal Research Loop。

---

## 14. 结论

长期 AI 技能的本质不是“让 AI 工作更久”，而是建立一个可治理的状态化协作系统。

这个系统中：

```text
人类定义价值；
AI 生产证据；
artifact 保存状态；
内循环减少不确定性；
外循环生成意义；
报告形成治理；
反馈更新方向。
```

**Stateful Value-Signal Research Loop** 的核心贡献，是把这些要素组织成一套可复用方法论。

如果说普通 AI 对话是在回答问题，那么长期 AI 技能应该做的是：

> 把 AI 从一次性回答者，转化为可治理、可追溯、可持续积累理解的长期合作者。
