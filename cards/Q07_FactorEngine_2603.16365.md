# Q07 · FactorEngine：程序级知识注入因子挖掘框架

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | FactorEngine: A Program-level Knowledge-Infused Factor Mining Framework for Quantitative Investment |
| 作者 | Qinhong Lin; Ruitao Feng; Yinglun Feng; Zhenxin Huang; Yukun Chen; Zhongliang Yang; Linna Zhou; Binjie Fei; Jiaqi Liu; Yu Li |
| 出处 | arXiv:2603.16365（2026-03-17） |
| 类型 | 方法论文（宏微共进化 + 知识注入启动，受 OpenEvolve 启发） |
| 链接 | [arXiv](https://arxiv.org/abs/2603.16365) · [PDF v2](https://arxiv.org/pdf/2603.16365v2) |

---

## 一句话结论

> 把因子表示为 **Turing-complete 代码**（而非受限表达式），并通过三分离（逻辑修订 vs 参数优化 / LLM 方向搜索 vs 贝叶斯超参搜索 / LLM 使用 vs 本地计算）显著提升有效性与效率，再以"财报→可执行因子程序"的知识注入引导 + 支持失败学习的经验知识库做轨迹级精炼——在真实 OHLCV 回测中取得更高 IC/ICIR（及 Rank IC/ICIR）与改进的 AR/Sharpe，达到 state-of-the-art。

## 问题背景

- 符号化（公式/DSL）方法受限于表达力；神经预测器以可解释性换性能，且对 regime shift 与过拟合脆弱。
- 实际要求：挖掘出的因子**可直接执行、可审计**，且发现过程在规模上**计算可承受**。
- 纯搜索难以利用已有的金融知识（研报、分析师逻辑）。

## 方法

1. **程序级因子表示**：因子 = Turing-complete 代码（程序），跳脱公式表达力天花板。
2. **三分离设计**：① 逻辑修订与参数优化分离；② LLM 引导的方向性搜索与贝叶斯超参搜索分离；③ LLM 使用与本地计算分离。
3. **知识注入引导模块（knowledge-infused bootstrapping）**：闭路多 agent "抽取→验证→代码生成" 管线，把非结构化金融研报转成可执行因子程序作为初始种群。
4. **经验知识库**：支持轨迹级精炼（trajectory-aware refinement），**包含从失败中学习**。

## 关键结果

| 指标 | 结果 |
|---|---|
| 预测稳定性 | 显著优于基线（更高 IC / ICIR，Rank IC / Rank ICIR） |
| 组合表现 | 改进 AR / Sharpe |
| 数据规模 | 真实市场 OHLCV 数据的广泛回测 |

## 与 RSI 知识库的关系

- 宏（逻辑进化）微（贝叶斯参数优化）**共进化**是双层自改进架构：逻辑层 = "改方法"，参数层 = "调超参"——与 HyperAgents 的 Task/Meta 双层思想同构，但在金融因子域实现。
- "从失败中学习"的经验库 = RSI 知识库中"负面经验反哺"的核心机制（与 [Q02 FactorMiner] 的 failure constraints 一致）。
- 知识注入启动把"人类金融知识"作为初始先验注入进化种群——自改进系统与外部知识融合的样例。

## 解读与批判

- ✅ 程序级表示 + 三分离解决"表达力 vs 可审计 vs 计算成本"三角问题，工程上可落地。
- ✅ 显式支持失败学习，契合金融"负样本更有信息量"的经验。
- ✅ 受 OpenEvolve（社区版 AlphaEvolve）启发，范式归属清晰。
- ⚠️ 论文页面/摘要层面未给关键数值（IC 值、AR/Sharpe 改善幅度），需读正文核实。
- ⚠️ 研报知识注入依赖财报文本质量；中文研报处理成本与噪声未披露。

---

**相关卡片**：[Q06 AutoScientist-Quant](Q06_AutoScientistQuant_2608.28632.md) · [Q02 FactorMiner](Q02_FactorMiner_2602.14670.md) · [Q20 AlphaAgent](Q20_AlphaAgent_2502.16789.md)

[返回目录](../README.md)