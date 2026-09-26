# Q04 · Hubble：安全、多样、可复现的 LLM Agent 因子发现框架

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | Hubble: An LLM-Driven Agentic Framework for Safe, Diverse, and Reproducible Alpha Factor Discovery |
| 作者 | Runze Shi; Shengyu Yan; Yuecheng Cai; Chengxi Lv |
| 出处 | arXiv:2604.09601（2026-03-09） |
| 类型 | 方法论文（AST 沙箱 + 家族感知选择，进化反馈） |
| 链接 | [arXiv](https://arxiv.org/abs/2604.09601) · [HTML v1](https://arxiv.org/html/2604.09601v1) |

---

## 一句话结论

> 不把 LLM 当"无约束代码生成器"，而是限制其生成**可解释的算子树**，经 **AST 执行沙箱** + 双通道 RAG + 家族感知选择评估每个候选：在约 500 只美股上三轮评估 104 个有效候选、**零运行时崩溃**；样本外（2025-06-01 → 2026-03-13）top 因子中 range 与 volatility 族保持为正，最弱 in-sample trend 因子明显衰减。

## 问题背景

- 公式化因子搜索空间是组合爆炸的；日频数据信噪比极低。
- **无约束程序生成在操作上不安全**（可能执行越权操作、崩溃、产生无法审计的代码）。
- 过往 LLM 因子的**选择性偏差**严重：只报告 in-sample 最优因子，不做 held-out 泛化检验。

## 方法

1. **领域专用算子语言**：限制 LLM 只能生成解释性算子树（可审计的白名单算子）。
2. **AST 执行沙箱**：安全执行、防越权。
3. **双通道 RAG（positive/negative）**：正例教"对的样子"，负例教"别踩的坑"。
4. **家族感知选择机制**：公式相似度惩罚 + 标准化多指标评分 + **RankIC 与 Pearson IC 双报告** + 持久化诊断工件。
5. **确定性截面评估管线 + 结构族级诊断反馈**：把 top 公式与"家族级诊断"反馈给后续轮次，做跨轮自改进。

## 关键结果

| 实验 | 结果 |
|---|---|
| 主运行 | ~500 只美股 · 3 轮 · **104 个有效候选 · 零崩溃** |
| Top 因子构成 | range / volatility / trend 族主导（而非拥挤的 volume-only） |
| 样本外窗口 | 2025-06-01 → 2026-03-13（固定 top-5） |
| 样本外表现 | 2 个 range 因子 + 2 个 volatility 因子保持正值，部分达到 HAC 显著 Pearson IC 与多空证据；最弱 in-sample trend 因子明显衰减 |

## 与 RSI 知识库的关系

- "评估 → 家族级诊断 → 反馈下一轮" = 有界的部署期自改进回路；AST 白名单沙箱 = RSI 金融安全护栏的雏形。
- 家族级诊断 ≈ 结构化记忆（类比 [Q02 FactorMiner] 的经验记忆，但以家族为单位）。
- 与 [Q01 AQuA] 的密封沙箱互补：AQuA 密封"数据/标签/评估器"，Hubble 密封"可执行代码本身"。

## 解读与批判

- ✅ 工程上最"可复现派"的因子发现系统：确定性评估、持久化工件、双指标报告、固定 top-5 的 held-out 验证。
- ✅ 用 HAC 显著性处理低信噪比下的多重检验问题（呼应 p-hacking 隐患）。
- ✅ 显式把"零运行时崩溃"当作质量门槛，回应操作性安全。
- ⚠️ 约 500 只股票的 universe 偏小；三轮迭代的长期进化行为未经检验。
- ⚠️ 固定 top-5 的 select 之后仍存在选择偏差残余（top 集合本身来自 in-sample 排序）。

---

**相关卡片**：[Q01 AQuA](Q01_AQuA_2608.12841.md) · [Q03 QuantaAlpha](Q03_QuantaAlpha_2602.07085.md) · [Q05 AlphaBench](Q05_AlphaBench_ICLR2026.md)

[返回目录](../README.md)