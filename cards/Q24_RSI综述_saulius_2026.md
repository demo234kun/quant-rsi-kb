# Q24 · saulius.io：交易中的递归自我改进综述

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | Recursive Self-Improvement for Trading: How LLMs Can Teach Themselves to Invest |
| 作者 | Saulius（saulius.io） |
| 出处 | 博客文章（2026-03-02） |
| 类型 | 深度综述 / 博客（Mind Evolution → 交易映射 · 风险清单） |
| 链接 | [saulius.io](https://saulius.io/blog/recursive-self-improvement-llm-trading) |

---

## 一句话结论

> 以 Mind Evolution（一种以 LLM 为主体的搜索式 RSI 方法，在受限任务上取得 95.6%/100% 的解题成功率）为锚点，系统梳理"LLM 自我教学投资"的三条路线——**内省 agent、工具使用 agent（含进化式搜索）、直接优化交易策略**，并给出金融 RSI 的风险清单；是理解"为什么/如何"把 RSI 嫁接到交易的全景综述。

## 问题背景

- LLM 已强大但**静态**：如何让它们系统性改进自己的交易表现（而非只靠 prompt 手工调优）？
- RSI 方法很多（Mind Evolution、进化、反思、工具改进），各自适用边界不同；金融场景噪声、延迟奖励、leakage 风险使大部分通用 RSI 做法失效。
- 需要一个把"通用 RSI 方法库 ↔ 金融交易适配"串起来的框架性认知。

## 方法（综述框架）

1. **以 Mind Evolution 为锚**：展示"LLM 驱动的搜索式自改进"在受限推理任务上的强结果（95.6%/100% 级成功率）作为"为什么值得做"的证据。
2. **三条路线映射**：① 内省 agent（自我反思/自我批判）；② 工具使用 agent + 进化式搜索（让 LLM 改进自己的工具与搜索流程）；③ 直接优化交易策略（策略文本/代码/权重）。
3. **金融专用风险清单**：回测过拟合、p-hacking/多重检验、数据 leakage、延迟噪声奖励、regime 非平稳等。

## 关键结果

| 主题 | 结论 |
|---|---|
| Mind Evolution 先例 | 受限任务接近 95.6%–100% 成功率（作为 RSI 有效性锚点） |
| 路线分类 | 内省 / 工具+进化搜索 / 直接优化策略 三条路线 |
| 风险 | 过拟合、p-hacking、leakage、噪声奖励、regime 漂移是金融 RSI 头号失败源 |

## 与 RSI 知识库的关系

- **本库的综述锚**：Q01–Q23 可对照本卡的三路线框架归类（如 [Q08][Q09][Q10] = 直接优化策略文本；[Q18][Q19] = 工具/进化搜索；[Q21] = 内省 + 知识库）。
- 与 RSI 知识库 [P01] 综述、热点文件（FINANCE_HOTSPOTS.md，检索 2026-09-24）共同构成"范式缩写（DGM/HyperAgents/SICA/Gödel Agent/SEAL/ADAS/ShinkaEvolve/OpenEvolve/AutoResearch）+ 金融适配"的坐标系。
- 搜到本卡即进入本库的"全貌 + 风险"阅读路径（README 推荐路径末站）。

## 解读与批判

- ✅ 把碎片化的 RSI 方法归类成可对照金融场景的路线图，提供"为什么 RSI 在金融难"的分析框架。
- ✅ 风险清单与 [Q01 AQuA] 的 leakage 警告、[Q18 MadEvolve] 的 p-hacking 评估互相印证。
- ⚠️ 独立博客、非同行评审；部分数值（95.6%/100%）来自受限实验环境，不能直接外推金融实盘。
- ⚠️ 未给出具体可复现系统；作为"认知地图"价值高于"工程手册"价值。

---

**相关卡片**：[Q01 AQuA](Q01_AQuA_2608.12841.md) · [Q06 AutoScientist-Quant](Q06_AutoScientistQuant_2608.28632.md) · [Q08 EvolveTrade](Q08_EvolveTrade_2609.17632.md) · [Q09 SHARP](Q09_SHARP_2605.06822.md) · [Q17 Amazon Analyst](Q17_AmazonAnalyst_2026.md)

[返回目录](../README.md)