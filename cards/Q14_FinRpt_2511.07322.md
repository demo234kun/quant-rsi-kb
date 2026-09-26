# Q14 · FinRpt：股权研究报告生成的数据集、评测与多 Agent 框架

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | FinRpt: Dataset, Evaluation System and LLM-based Multi-agent Framework for Equity Research Report Generation |
| 作者 | Song Jin; Shuqi Li; Shukun Zhang; Rui Yan |
| 出处 | arXiv:2511.07322（2025-11-10） |
| 类型 | 方法论文（ERR 任务定义 · 数据集 + 评测系统 + 9 agent 框架） |
| 链接 | [arXiv](https://arxiv.org/abs/2511.07322) · [HTML v2](https://arxiv.org/html/2511.07322v2) |

---

## 一句话结论

> 首次系统定义 **Equity Research Report（ERR）生成任务**：提供 FinRpt 开源基准（7 类金融数据的自动化数据集构建管线 + **11 个指标**的评测系统）+ FinRpt-Gen 多 agent 框架（信息抽取/分析/预测三个模块、约 9 个 agent，用 SFT 与 RL 训练）——为"研报生成"这个方向5 的核心任务立起可复现的度量与基线。

## 问题背景

- LLM 在股票预测、QA 上已有成功，但**全自动生成券商研报**仍是未开垦地。
- 痛点：数据不足（无公开 ERR 数据集）、指标缺失（没有统一评测标准）、生成框架未定。
- 研报质量难以客观打分（股价是迟滞且噪声大的信号）。

## 方法

1. **任务定义**：首次形式化 Equity Research Report Generation（ERR）任务。
2. **数据集构建管线**：整合 **7 种金融数据类型**，自动化产出高质量 ERR 数据集（可用于训练与评测）。
3. **评测系统**：**11 个指标**综合评估生成的研报。
4. **FinRpt-Gen 多 Agent 框架**：信息抽取、分析、预测三大模块（热点文件：约 9 个 agent）。
5. **训练**：基于自建数据集对多个 LLM agent 做 SFT（监督微调）+ RL（强化学习）。
6. 全部代码与数据集公开。

## 关键结果

| 实验 | 结果 |
|---|---|
| 数据集 | 7 类金融数据 → 高质量 ERR 数据集，开源 |
| 评测 | **11 指标**综合评估，指标有效性经实验验证 |
| 生成框架 | FinRpt-Gen（SFT + RL 训练的多 agent）表现强 |
| 公开性 | 代码与数据集全部公开 |

## 与 RSI 知识库的关系

- 与 **HyperAgents（Meta）** 同属方向5 主范式：FinRpt-Gen 的多 agent 分工 + 训练优化，是"Task Agent 体系"在研报域的实现。
- FinRpt 目前是**静态评测**（无跨周期学习）——热点文件明确指出"随财报季逐月进化的研报质量纵向评测"是空白，即 RSI (周期式自我成长) 尚未被本系统实现。
- 11 指标评测系统为"研报质量"提供相对客观的 fitness，是未来自进化研报系统的评估器基础。

## 解读与批判

- ✅ 首次把 ERR 任务、数据、指标、框架一次性补齐，开源，可复现性强。
- ✅ SFT+RL 双阶段训练体现"从数据到行为"的完整学习闭环。
- ⚠️ 逐月/跨报告周期的自我成长未实现——方向5 的 RSI 核心（"入职→每月复盘→积累长期记忆"）仍是空白。
- ⚠️ 研报质量的 ground truth 天然主观：11 指标仍是代理度量，与真实研报价值之间有 gap。

---

**相关卡片**：[Q15 FinSight](Q15_FinSight_2510.16844.md) · [Q16 FinDebate](Q16_FinDebate_2509.17395.md) · [Q17 Amazon Analyst](Q17_AmazonAnalyst_2026.md)

[返回目录](../README.md)