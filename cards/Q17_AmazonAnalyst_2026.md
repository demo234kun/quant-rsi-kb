# Q17 · Amazon Analyst-Like Agents：类分析师智能体（企业技术报告）

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | Building Analyst-Like Agents: A Self-Improving Multi-Agent Framework for Financial Reasoning in the Enterprise |
| 作者 | Xiaoli Zhang; Daksha Yadav; Boyang Tom Jin; Miriam Teng |
| 出处 | Amazon Science 技术报告（2026-04 公开更新版） |
| 类型 | 企业技术报告（自改进多 Agent · 月度周期学习） |
| 链接 | [Amazon Science PDF](https://cdn.amazon.science/97/5d/d027be664fa2bfa38bb58adececa/building-analyst-like-agents-a-self-improving-multi-agent-framework-for-financial-reasoning-in-the-enterprise-updated.pdf) |

---

## 一句话结论

> 模仿初级分析师"入职→月度复盘→积累长期记忆→反推工具改进"的成长路径：**Junior Analyst Agent** 从每月月末周期中主动学习并建立长期记忆，向 **Accountant Agent** 澄清歧义、与 **Engineer Agent** 协作改进分析工具——在 200 个问题 × 4 个月末周期的评测中，推理准确率从 **44.5% 提升到 81.3%**，是方向5"周期式自我成长"最有分量的实证。

## 问题背景

- 企业级金融推理（财报数据到投资/分析决策）需要分析师式的长期积累，一次性问答系统的准确率与稳定性不足。
- 自改进多 agent 在企业金融域（合规、隐私、数据时序）的工程化落地鲜有公开先例。
- "研报/分析系统如何随月度财报季持续变好"需要真实周期数据支撑。

## 方法

1. **Junior Analyst Agent**：承担具体分析任务（Task Agent 角色），跨周期主动学习。
2. **长期记忆**：把历史周期经验沉淀为可复用的记忆（跨 run 继承）。
3. **Accountant Agent 协作**：对财报数字的歧义进行澄清式交互（防幻觉）。
4. **Engineer Agent 协作**：根据分析师反馈改进工具（Meta 级自改进）。
5. 评测：**200 个问题 × 4 个月末周期**的纵向实验。

## 关键结果

| 实验 | 结果 |
|---|---|
| 推理准确率 | **44.5% → 81.3%**（200 问题 × 4 月末周期） |
| 学习机制 | 月度周期主动学习 + 长期记忆 + 工具改进 |
| 协作结构 | Junior Analyst / Accountant / Engineer 三 Agent 分工 |

## 与 RSI 知识库的关系

- 最贴近 **HyperAgents（Meta）** 的"Task Agent + Meta Agent 双层递归"：Junior=Task，Engineer=Meta（改工具）。
- **唯一公开了"跨周期纵向改进曲线"的金融多 agent 系统**——直接命中热点文件方向5 的空缺点（"随财报季逐月进化的研报质量"纵向评测）。
- 澄清式协作（Accountant）≈ 防幻觉的交互式 grounding，是金融 RSI 系统必需的"事实层"保护。

## 解读与批判

- ✅ 44.5%→81.3% 的周期式提升是最强的"金融 RSI 有效"实证信号之一。
- ✅ 企业级约束（澄清歧义 = 数字正确性优先）比纯学术演示更贴近真实部署。
- ⚠️ 企业报告未开源：具体 prompt/架构/成本不可复现。
- ⚠️ 评测基于内部问题集与内部事实标准，外部推广需谨慎；未披露提升的误差带与分周期明细。

---

**相关卡片**：[Q14 FinRpt](Q14_FinRpt_2511.07322.md) · [Q15 FinSight](Q15_FinSight_2510.16844.md) · [Q16 FinDebate](Q16_FinDebate_2509.17395.md) · [Q24 RSI 综述](Q24_RSI综述_saulius_2026.md)

[返回目录](../README.md)