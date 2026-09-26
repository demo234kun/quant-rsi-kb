# Q20 · AlphaAgent：正则化探索对抗 Alpha 衰减的 LLM 因子挖掘

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | AlphaAgent: LLM-Driven Alpha Mining with Regularized Exploration to Counteract Alpha Decay |
| 作者 | Ziyi Tang; Zechuan Chen; Jiarui Yang; Jiayao Mai; Yongsen Zheng; Keze Wang; Jinrui Chen; Liang Lin |
| 出处 | arXiv:2502.16789（2025-02-24） |
| 类型 | 方法论文（AST 原创性约束 · 抗衰退 · 方向6 辅助） |
| 链接 | [arXiv](https://arxiv.org/abs/2502.16789) · [PDF v2](https://arxiv.org/pdf/2502.16789v2) |

---

## 一句话结论

> 针对 LLM 因子挖掘"过度依赖已有知识 → 因子同质化 → 拥挤 → 加速 alpha 衰减"的链路，用三机制正则化约束探索：① **AST 相似度原创性强制**（对新因子与已有 alpha 的语法树相似度设限）；② **假设-因子语义一致性**（LLM 评估市场假设与生成因子是否对齐）；③ **AST 复杂度控制**——在 A 股 CSI 500 与美股 S&P 500 市场上连续四年（牛熊兼有）显著缓解 alpha 衰减，超越传统与 LLM 基线。

## 问题背景

- Alpha 挖掘的关键挑战是 **alpha decay**：因子随时间失去预测力。
- 传统遗传编程因过拟合与复杂度快速衰减；LLM 驱动方法易**过度依赖现有知识**，制造同质因子 → 拥挤（crowding）→ 衰减加速。
- 需要让探索在"金融合理性"与"新颖性"之间平衡。

## 方法

1. **AST 相似度原创性强制**：用抽象语法树相似度量衡对新因子与既有 alphas 的差异，惩罚重复（原创性正则）。
2. **假设-因子对齐**：LLM 评估"市场假设 ↔ 生成因子"的语义一致性（金融 rationale 正则）。
3. **AST 结构复杂度控制**：防止过工程化、易过拟合的构造（复杂度正则）。
4. 三机制共同引导生成：平衡原创性、金融理由、对演化市场条件的适应。

## 关键结果

| 实验 | 结果 |
|---|---|
| 市场 | 中国 CSI 500 + 美国 S&P 500 |
| 周期 | 过去四年（含牛熊市场） |
| 结论 | 显著优于传统与 LLM 方法，对抗 alpha 衰减能力突出 |
| 机制 | AST 原创性 + 语义对齐 + 复杂度控制 |

## 与 RSI 知识库的关系

- 方向6 的"拥挤因子/alpha decay"痛点直接命中：alpha decay 是热点文件明确列出的进化后期难点。
- "原创性正则"机制与 [Q04 Hubble] 的公式相似度惩罚、[Q03 QuantaAlpha] 的 crowding 约束同族——三条路线殊途同归地给"探索"加纪律。
- 属于**有界 RSI**：不进化搜索策略本身，而是约束搜索的输出分布（防止自我同质化）。

## 解读与批判

- ✅ 把"抗衰减"这一金融独有的退化问题显式化为三种可操作的基于 AST 的正则，机制干净可复现。
- ✅ 牛熊都测（四年周期），时间跨度支撑了"缓解衰减"的主张。
- ⚠️ AST 相似度只覆盖表达式结构，不覆盖语义等价（不同写法同逻辑的冗余可能漏判）。
- ⚠️ 结果在摘要为相对性语句（无具体 IC/收益数值），需读正文核实幅度。

---

**相关卡片**：[Q18 MadEvolve](Q18_MadEvolve_2605.23007.md) · [Q19 EvoFactorSearch](Q19_EvoFactorSearch_2507.17211.md) · [Q03 QuantaAlpha](Q03_QuantaAlpha_2602.07085.md) · [Q07 FactorEngine](Q07_FactorEngine_2603.16365.md)

[返回目录](../README.md)