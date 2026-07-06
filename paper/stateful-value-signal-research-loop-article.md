# 从 `/autoresearch` 看长期 AI 技能设计：状态化价值信号研究循环

## 摘要

`/autoresearch` 并不是一个普通的“研究问题回答器”，而是一种长期 AI 研究技能的系统化范式。它把开放式研究任务从一次性对话，转化为一个由状态文件、研究日志、发现文档、实验目录、人类报告和最终论文组成的持续性研究系统。本文基于对 `/autoresearch` 工作机制的拆解，提出一个可复用框架：**Stateful Value-Signal Research Loop**，即“状态化价值信号研究循环”。

这个框架认为：长期 AI 技能的关键不在于让 AI 完全自主，也不在于让人类逐步指挥，而在于建立一种分层协作结构：人类生产价值信号，AI 生产状态化研究 artifact；内循环生产证据，外循环生产意义；进展报告则成为人类治理 AI 研究过程的主要界面。

---

## 1. 问题：为什么普通对话不足以支持长期研究？

普通 AI 对话通常遵循这样的模式：

```text
人类提出问题 → AI 给出答案
```

这种模式适合一次性任务，例如解释概念、生成代码片段、总结一篇文章。但它不适合长期开放式研究。原因在于，研究任务通常具有四个特征：

1. **目标会演化**：一开始的问题不一定是最终值得研究的问题。
2. **路径不确定**：无法提前列出完整步骤。
3. **结果有噪声**：单次实验或分析不一定可靠。
4. **理解需要积累**：价值来自多轮证据、反思和综合。

如果长期研究只依赖聊天记录，就会出现几个问题：状态难以恢复，证据与结论混杂，决策过程不可审计，人类难以判断 AI 是否仍在正确方向上推进。

`/autoresearch` 的设计正是为了解决这个问题。它把研究任务外化为一组可持续维护的 artifact，并通过内外双循环不断推进。

---

## 2. 第一性原理：目标、信息、行动、反馈

从第一性原理看，任何人机协作研究系统都可以还原为四个基本原语：

```text
目标 → 信息 → 行动 → 反馈
```

对应到 `/autoresearch`：

| 原语 | 人类责任 | AI 责任 | 关键 artifact |
|---|---|---|---|
| 目标 | 定义研究意图、价值函数、约束 | 转化为研究问题和假设 | `research-state.yaml` |
| 信息 | 提供背景和判断标准 | 搜索文献、保存证据、压缩发现 | `literature/`, `findings.md` |
| 行动 | 设定风险边界 | 执行实验、记录结果、更新状态 | `experiments/`, `data/` |
| 反馈 | 通过报告校准方向 | 将反馈写回状态并重新排序 | `to_human/`, `research-log.md` |

这说明，`/autoresearch` 的核心不是“AI 多做一些事”，而是重新组织人类与 AI 在长期任务中的职责边界。

---

## 3. H1：Artifact 是消费者界面

第一个核心发现是：`/autoresearch` 中的文件不是被动存储，而是**消费者界面**。

每个 artifact 都服务于某类未来消费者：

| Artifact | 主要消费者 | 功能 |
|---|---|---|
| `research-state.yaml` | AI | 记录当前状态和下一步行动 |
| `research-log.md` | AI + 人类审计者 | 保存决策时间线 |
| `findings.md` | AI + 人类 | 压缩当前理解 |
| `literature/` | AI + 论文写作者 | 保存外部知识依据 |
| `experiments/` | AI + 复现者 | 保存协议、结果和分析 |
| `to_human/` | 人类 | 提供治理和校准界面 |
| `paper/` | 传播受众 | 封装最终贡献 |

因此，设计长期 AI 技能时，不应先问“我要建哪些文件”，而应先问：

```text
谁会消费这个信息？
他需要什么压缩级别？
这个 artifact 支持什么决策？
如果没有它，什么能力会失效？
```

这就是 artifact-as-interface 的设计原则。

---

## 4. H2：人机协作是价值信号交换

第二个核心发现是：`/autoresearch` 中的人机协作，不是简单的命令执行，也不是完全委托，而是一种**价值信号交换**。

人类主要生产：

- objective：研究目标；
- audience：目标受众；
- success criteria：成功标准；
- constraints：约束；
- risk boundaries：风险边界；
- feedback cadence：反馈节奏。

AI 主要生产：

- state updates：状态更新；
- evidence packages：证据包；
- synthesis：综合发现；
- decision options：方向选项；
- reports：人类报告。

这个关系可以表示为：

```text
人类价值信号 → AI 研究生产 → 压缩后的意义 → 人类方向校准 → AI 重新排序
```

这带来一个重要原则：

> 人类应该通过价值函数控制 AI，而不是通过逐步命令控制 AI。

如果人类逐步 micromanage，AI 就退化为被动执行器；如果人类完全不参与，AI 又容易目标漂移。最优结构是：人类低频高层校准，AI 高频低层执行。

---

## 5. H3：内循环生产证据，外循环生产意义

第三个核心发现是：`/autoresearch` 的双循环不是普通任务调度，而是认识论分工。

### 内循环：证据生产

内循环负责快速、局部、可验证的工作：

```text
选择假设 → 写 protocol → 执行实验/分析 → sanity check → 测量 → 记录 → 更新状态
```

它的产物是：协议、数据、结果、局部分析。

### 外循环：意义生产

外循环负责慢速、全局、解释性的工作：

```text
回顾结果 → 聚类模式 → 追问为什么 → 更新 findings → 生成新假设 → 决定方向
```

它的产物是：模式、机制解释、方向判断、叙事主线。

这两个循环解决了两个相反问题：

- 只有内循环，会变成“有活动无理解”；
- 只有外循环，会变成“有框架无证据”。

因此，长期 AI 技能需要把“生产证据”和“生产意义”分开设计。

---

## 6. H4：进展报告是治理接口

第四个核心发现是：`to_human/` 中的报告不是展示材料，而是**人类治理接口**。

长期 AI 研究代理会产生一个控制问题：

```text
每步都审批 → AI 失去自主性
完全不看 → AI 可能漂移
阅读全部日志 → 人类认知成本过高
```

进展报告提供了中间解：

```text
内部 artifacts → 报告综合 → 人类判断 → 更新价值信号 → AI 重新排序
```

一个好的治理报告应该回答：

1. 我们是否仍在解决正确问题？
2. 当前真正学到了什么？
3. 证据是什么？
4. 还有什么不确定？
5. 应该深化、拓展、转向还是收束？
6. 如果人类不干预，AI 下一步会做什么？
7. 现在最需要人类提供什么反馈？

因此，报告不是“工作总结”，而是人类对长期 AI 系统施加方向控制的界面。

---

## 7. 最终框架：Stateful Value-Signal Research Loop

综合 H1-H4，可以得到最终框架：

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

这个框架可以定义为：

> 一种长期 AI 交互模式：人类提供价值信号与治理，AI 维护 artifact-mediated state，内循环生产证据，外循环生产意义，进展报告关闭人类方向控制循环。

它的核心价值在于，让 AI 既能持续自主推进，又能保持人类可治理。

---

## 8. 通用设计模板

任何长期 AI 技能都可以按以下模板设计。

### 8.1 Human Value Signal

```yaml
objective:
audience:
success_criteria:
constraints:
risk_boundaries:
feedback_cadence:
```

### 8.2 Artifact Interfaces

```yaml
state_artifact:
log_artifact:
findings_artifact:
evidence_artifact:
human_report_artifact:
final_deliverable_artifact:
```

每个 artifact 应声明：

```yaml
producer:
consumer:
compression_level:
decision_enabled:
failure_if_missing:
update_cadence:
```

### 8.3 Loop Design

```yaml
inner_loop:
  function: produce local evidence
outer_loop:
  function: produce global meaning
human_loop:
  function: update value signal
```

### 8.4 Health Checks

```yaml
artifact_health:
value_signal_health:
loop_health:
governance_report_health:
```

---

## 9. 常见失败模式

| 失败模式 | 症状 | 根因 | 修复 |
|---|---|---|---|
| 输出无价值 | 内容很多，但不知有什么用 | 价值信号弱 | 明确目标、受众、成功标准 |
| 有活动无理解 | 实验多，`findings.md` 薄 | 外循环弱 | 强制综合和方向判断 |
| 有框架无证据 | 叙事漂亮但无支撑 | 内循环弱 | 补 protocol、结果、案例或数据 |
| 人类瓶颈 | 频繁小审批 | 步骤控制过强 | 只审批高风险/不可逆动作 |
| AI 漂移 | 越做越偏 | 报告少或价值信号过期 | 生成治理报告，刷新优先级 |
| 虚假确定性 | 弱证据被写成强结论 | 报告缺少置信度 | 标注 evidence type 和 confidence |

---

## 10. 对 AI 技能设计的启发

`/autoresearch` 的价值不只是“自动研究”。它展示了长期 AI 技能应该如何设计：

1. 用 artifact 外化记忆；
2. 用价值信号定义人机分工；
3. 用内外循环管理证据和意义；
4. 用报告实现人类治理；
5. 用 findings 保持认知积累；
6. 用 state 保持操作连续性；
7. 用 log 保持决策可审计；
8. 用 experiments 保持证据可追溯。

这套结构不只适用于研究代理，也适用于：

- 长期编码代理；
- 产品探索代理；
- 数据科学代理；
- 安全审计代理；
- 课程生成代理；
- 企业知识管理代理。

只要任务是开放式、多步、长期、需要持续减少不确定性，就可以使用这个框架。

---

## 11. 结论

`/autoresearch` 的本质不是一个命令，而是一种长期人机协作协议。

它告诉我们：未来的高级 AI 技能不应只是更强的 prompt，也不应只是更复杂的工具调用，而应该是一个可治理的状态化系统。

这个系统中：

```text
人类定义价值；
AI 生产证据；
artifact 保存状态；
外循环生成意义；
报告形成治理；
反馈更新方向。
```

这就是 **Stateful Value-Signal Research Loop** 的核心。

如果说普通 AI 对话是在回答问题，那么 `/autoresearch` 代表的是另一种范式：

> 把 AI 从一次性回答者，转化为可治理的长期研究合作者。
