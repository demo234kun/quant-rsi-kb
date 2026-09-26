# Q05 · AlphaBench：LLM 公式化 Alpha 因子挖掘基准

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | AlphaBench: Benchmarking Large Language Models in Formulaic Alpha Factor Mining |
| 作者 | Haochen Luo; Ho Tin Ko; Jiandong Chen; David Sun; Yuan Zhang; Chen Liu |
| 出处 | **ICLR 2026**（第十三届 ICLR，会议论文） |
| 类型 | 基准 / 评测论文（FAFM 评测协议） |
| 链接 | [ICLR proceedings PDF](https://proceedings.iclr.cc/paper_files/paper/2026/file/4f3820576130a8f796ddbf204c841487-Paper-Conference.pdf) · [项目主页 alphabench.cc](https://alphabench.cc/) |

---

## 一句话结论

> 首个系统评测 LLM 在 **公式化 Alpha 因子挖掘（FAFM，Formulaic Alpha Factor Mining）** 能力的基准：把 FAFM 拆解为**因子生成 / 因子评估 / 因子搜索**三个核心子任务，提供标准化的模型能力画像——是 RSI 因子发现系统"评估器（evaluator）"的标准件候选。

## 问题背景

- FAFM 是量化投资的核心问题，但此前**缺乏统一评测协议**：不同论文用不同数据集、不同评估口径，无法横向比较 LLM 的挖掘能力。
- 评测缺失让"自改进系统到底改进了什么"无法被验证——基准是 RSI 闭环（generate→evaluate→improve）里 evaluate 的基石。

## 方法（基准设计要点）

1. **三子任务定义**：factor generation（给定市场数据直接生成因子）、factor evaluation（判断给定因子的质量/执行评估流程）、factor searching（在搜索空间中迭代寻找更优因子）。
2. **系统评测维度**：对比模型类型、prompting 范式、推理策略等配置对 FAFM 能力的影响。
3. **统一评估口径**：为所有参赛配置提供一致的评估 API 与评分标准（项目主页 alphabench.cc 提供交互式评测）。

## 关键结果

| 维度 | 结论（基准公开可得，数值见论文） |
|---|---|
| LLM 在 FAFM 的总体能力 | 展示出自动化挖掘的潜力，但**鲁棒性、搜索效率、实用可用性**仍有明显短板 |
| 模型/配置消融 | 模型类型与推理策略显著影响生成/评估/搜索三个任务的相对表现 |
| 工程价值 | 为"自进化挖掘系统"提供可复现的 fitness（评估函数）标准件 |

## 与 RSI 知识库的关系

- **基准 = RSI 的评估器组件**：一个自改进系统必须有人类可复核的 fitness；AlphaBench 试图承担 FAFM 领域的 SWE-bench 角色（类比 [P 区]SICA 用 SWE-bench 当 fitness）。
- 与 [Q01 AQuA] 的"固定评估器"密封沙箱设计对接：AlphaBench 提供被测方不可改的公开评估器。
- 三子任务拆分 = 把"研究能力"分解为可分别进化的组件（生成/评估/搜索），呼应研究流程级 RSI。

## 解读与批判

- ✅ 首次为 FAFM 定义统一任务边界与评测协议，填补方向 1 的基准空白。
- ✅ 配置消融对工程选型有直接参考价值（模型类型 vs prompting vs 推理策略）。
- ⚠️ 基准以美国市场代理数据为主，跨市场（A 股/crypto）的外推需验证。
- ⚠️ 若评测含 LLM judge 环节，需警惕 judge 偏置；基准本身也要防"benchmark-gaming"（agent 过拟合基准而非真实 alpha）。

---

**相关卡片**：[Q01 AQuA](Q01_AQuA_2608.12841.md) · [Q02 FactorMiner](Q02_FactorMiner_2602.14670.md) · [Q03 QuantaAlpha](Q03_QuantaAlpha_2602.07085.md) · [Q04 Hubble](Q04_Hubble_2604.09601.md) · [Q12 QuantCode-Bench](Q12_QuantCodeBench_2604.15151.md)

[返回目录](../README.md)