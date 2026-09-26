# Q12 · QuantCode-Bench：可执行算法交易策略生成基准

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | QuantCode-Bench: A Benchmark for Evaluating the Ability of Large Language Models to Generate Executable Algorithmic Trading Strategies |
| 作者 | Alexey Khoroshilov; Alexey Chernysh; Orkhan Ekhtibarov; Nini Kamkia; Dmitry Zmitrovich |
| 出处 | arXiv:2604.15151（2026-04-16） |
| 类型 | 基准 / 评测论文（400 任务 · Backtrader · 多阶段评测管线） |
| 链接 | [arXiv](https://arxiv.org/abs/2604.15151) · [HTML](https://arxiv.org/html/2604.15151) |

---

## 一句话结论

> 首次系统评测 LLM "从英文自然语言描述生成可执行算法交易策略" 的能力：400 个任务（采集自 Reddit/TradingView/StackExchange/GitHub/合成源）× 多阶段评测管线（语法正确性 → 回测可执行 → 确实产生交易 → LLM judge 语义对齐）；核心结论：**当前模型的主要瓶颈不在语法，而在交易逻辑的操作化、专业 API 的正确使用与任务语义对齐**——这正是 SICA 式自调试 agent 的目标域。

## 问题背景

- LLM 在通用编程任务上很强，但"生成可执行交易策略"未被系统评测。
- 与标准代码基准不同，交易策略生成要求同时掌握：金融领域逻辑、专用 API（Backtrader）、产出不仅有语法正确还要在历史数据上真正产生交易。
- 缺少基准 → 无法度量"自改进交易代码 agent"的起点与进步。

## 方法

1. **任务集**：400 个不同难度的策略生成任务（Reddit、TradingView、StackExchange、GitHub + 合成源）。
2. **评价管线**：① 语法正确性 → ② 回测成功执行 → ③ 产生交易 → ④ LLM judge 判断与任务描述的语义对齐。
3. **两种评测设置**：single-turn（一次生成正确）与 **agentic multi-turn**（模型接收迭代反馈、可修复自身错误）。
4. **失败模式分析**：跨管线各阶段定位模型失败原因。

## 关键结果

| 实验 | 结果 |
|---|---|
| 任务规模 | **400** 个策略生成任务，多源、多难度 |
| 主要失败原因 | 非语法层面：**交易逻辑操作化 / 专用 API 使用 / 任务语义对齐** |
| 修复行为 | agentic multi-turn 下"很多错误是局部可修的"，但仍有失败源于对自然语言 spec 的错误理解 |
| 定位 | 交易策略生成是**区别于通用代码生成的独立领域类别** |

## 与 RSI 知识库的关系

- 为 **SICA（Self-Improving Coding Agent）类金融自调试系统**提供 fitness/评测协议（热点文件方向4：把 SICA 搬到"修回测偏差"任务的评测件）。
- 与 [Q05 AlphaBench] 并列：AlphaBench 评"因子挖掘能力"，QuantCode-Bench 评"策略代码生成能力"——两者共同构成金融 RSI 的评测基础设施。
- "错误局部可修"的发现直接支撑 agentic 多轮修复循环的可行性。

## 解读与批判

- ✅ 首个把"可交易性"（产生真实交易）纳入评测的基准，管线分阶段定位失败，工程价值高。
- ✅ multi-turn 设置与 RSI 循环（generate→feedback→repair）天然对接。
- ⚠️ 评测基于 Backtrader 单一框架；LLM judge 用于语义对齐可能引入 judge 偏置。
- ⚠️ 400 任务的金融覆盖面（主要为英语描述的策略）不代表真实研究/workflow 的全部复杂性与市场多样性。

---

**相关卡片**：[Q13 QRAFTI](Q13_QRAFTI_2604.18500.md) · [Q05 AlphaBench](Q05_AlphaBench_ICLR2026.md) · [Q01 AQuA](Q01_AQuA_2608.12841.md) · [Q06 AutoScientist-Quant](Q06_AutoScientistQuant_2608.28632.md)

[返回目录](../README.md)