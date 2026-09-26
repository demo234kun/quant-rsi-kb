# Q08 · EvolveTrade：经验驱动的 LLM 交易 Agent 策略精炼

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | EvolveTrade: Experience-Driven Policy Refinement for Self-Evolving LLM Trading Agents |
| 作者 | Sehee Kim; Yumin Choi; Minki Kang; Sung Ju Hwang |
| 出处 | arXiv:2609.17632（2026-09-15） |
| 类型 | 方法论文（文本策略自进化 · Policy Agent，Gödel Agent 路线） |
| 链接 | [arXiv](https://arxiv.org/abs/2609.17632) · [PDF](https://arxiv.org/pdf/2609.17632) |

---

## 一句话结论

> 不微调 LLM 权重，而是把**系统提示词当作可参数化的策略文本 π_t**：每个更新周期结束后，一个独立的 **Policy Agent** 读取累计决策轨迹与已实现组合反馈，精炼出 π_{t+1} 供下一批交易使用——在多个市场 regime 与两个 LLM backbone 下，多数设置中 Sharpe Ratio 与累计收益超越固定策略基线，且行为分析显示自进化策略提升了"代码中介分析"并激活了 regime 相关计算。

## 问题背景

- LLM 交易 agent 能融合行情、新闻与可执行分析，但行为常被**部署前固化的人写工具使用策略**控制。
- 静态策略无法按市场 regime 调整"如何收集证据、调用工具、核验信号、管理风险"。
- 权重级自进化（微调）在金融场景成本高、不可审计、容易灾难性遗忘。

## 方法

1. **系统提示 = 文本参数化策略**：把 agent 的 tool-use policy 视为文本 π。
2. **周期式精炼循环**：每个 update interval 之后，Policy Agent 读取 accumulated decision traces + realized portfolio feedback。
3. **固定 backbone LLM**：只改策略文本，不改模型权重（轻量、可审计、可回滚）。
4. **策略 → 归因分析**：case-level 归因，追溯"策略诱导的仓位变化"如何贡献于收益差异。

## 关键结果

| 实验 | 结果 |
|---|---|
| 主要指标 | 多数评估设置下 **Sharpe Ratio（SR）与 Cumulative Return（CR）** 优于固定策略 LLM baseline |
| 覆盖 | 多个市场 regime + 两个 LLM backbone |
| 行为学证据 | 自进化策略增加 code-mediated analysis、激活 regime 相关计算 |
| 归因 | case 级策略→收益归因成立 |

## 与 RSI 知识库的关系

- 与 **Gödel Agent（ACL 2025）** 同为"运行时修改自身策略"路线；EvolveTrade 把 Gödel Agent 的 self-reference 具体化为"工具使用策略文本精炼"。
- 是最"轻量化"的 RSI：不碰权重、失败可回滚（策略文本版本可 git 管理）——低风险自改进范式的金融样例。
- 热点文件方向3 创新点提醒：目前 EvolveTrade/SHARP 的"修改规则本身"仍由人写，**把 Gödel Agent 的"连修改逻辑一起改"引入金融仍是空白**。

## 解读与批判

- ✅ 固定 backbone + 文本策略 = 每次自改进成本极低、可审计、可回滚（对机构合规友好）。
- ✅ 带行为学与归因分析，不只是终极指标对比——回答"策略往哪变了"。
- ⚠️ 改进幅度是"多数设置"而非全部；regime 过拟合风险（策略可能过拟合上一段 regime）未被充分讨论。
- ⚠️ 未处理执行滑点与市场冲击（SHARP 自陈的同款局限）。

---

**相关卡片**：[Q09 SHARP](Q09_SHARP_2605.06822.md) · [Q10 ATLAS](Q10_ATLAS_2510.15949.md) · [Q11 FLAG-Trader](Q11_FLAGTrader_2502.11433.md) · [Q24 RSI 综述](Q24_RSI综述_saulius_2026.md)

[返回目录](../README.md)