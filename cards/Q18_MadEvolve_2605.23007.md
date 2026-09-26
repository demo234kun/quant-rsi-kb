# Q18 · MadEvolve：LLM 驱动的交易系统进化优化

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | MadEvolve: Evolutionary Optimization of Trading Systems with Large Language Models |
| 作者 | Yurii Kvasiuk; Tianyi Li; Owen Colegrove; Moritz Münchmeyer |
| 出处 | arXiv:2605.23007（2026-05-21） |
| 类型 | 方法论文（AlphaEvolve 启发 · 交易系统组件进化 · 方向6） |
| 链接 | [arXiv](https://arxiv.org/abs/2605.23007) · [PDF](https://arxiv.org/pdf/2605.23007) |

---

## 一句话结论

> 把 DeepMind **AlphaEvolve** 启发的通用算法优化框架 MadEvolve（原本用于计算宇宙学）移植到量化交易：在 Bitcoin 交易上，对"特征集进化、策略组件分别优化、特征管线+执行策略联合进化"全部任务取得显著改进，并与 Claude Code 等 agentic 搜索对比，**显式评估 p-hacking 概率**——"进化优化交易系统"路线的实证代表。

## 问题背景

- LLM 进化算法在通用算法优化（计算宇宙学）上已成功，但应用到量化交易系统的系统性验证缺失。
- 交易系统分多组件（特征、策略逻辑、执行策略），组件间耦合，需要结构化进化而非盲目重写。
- agentic 方法（如 Claude Code 直接改代码）缺少对"多重检验/过拟合到回测"风险的显式控制。

## 方法

1. **AlphaEvolve 式框架**：通用算法优化框架 MadEvolve（进化种群 + LLM 变异/重组）。
2. **三类任务**：① 进化特征集用于信号生成；② 分别优化交易策略各组件；③ **联合进化特征管线 + 执行策略**。
3. **对比基准**：与其他 agentic 搜索方法（Claude Code）比较。
4. **p-hacking 评估**：在模拟设置上显式估算"进化的好结果来自随机性/多重检验"的概率。

## 关键结果

| 实验 | 结果 |
|---|---|
| 任务覆盖 | 特征集进化 / 组件优化 / 特征+执行联合进化 全任务显著改进 |
| 对比 | 优于其他 agentic 搜索方法（含 Claude Code） |
| 风险控制 | 显式评估 p-hacking 概率（进化搜索的统计真实性） |

## 与 RSI 知识库的关系

- **方向6 主范式（I）**：ShinkaEvolve（样本高效）+ OpenEvolve（通用 population）+ MadEvolve（AlphaEvolve 移植）三位一体中的"AlphaEvolve 移植"成员。
- 勘误：热点文件写作 **"Made Evolve"**，arXiv 官方标题为 **MadEvolve**，本库以 arXiv 为准（见 README 勘误记录）。
- "显式评估 p-hacking 概率"是有价值的范式贡献：金融进化搜索必须回答"这个结果是不是搜出来的幻觉"。

## 解读与批判

- ✅ 把 AlphaEvolve 类通用进化框架首次系统化应用到交易系统，示范性强。
- ✅ 把 p-hacking 概率评估纳入进化结果报告——这是金融 RSI 的关键诚实性机制。
- ✅ 联合进化（特征+执行）验证了"组件间协同进化"的价值。
- ⚠️ 只测 Bitcoin（单资产类），对股票/多资产推广需验证。
- ⚠️ 热点文件方向6 创新点：可进一步把 Deflated Sharpe Ratio 当进化约束（本工作只评估概率，未把其作为选择压力）。

---

**相关卡片**：[Q19 EvoFactorSearch](Q19_EvoFactorSearch_2507.17211.md) · [Q20 AlphaAgent](Q20_AlphaAgent_2502.16789.md) · [Q03 QuantaAlpha](Q03_QuantaAlpha_2602.07085.md) · [Q22 CogAlpha](Q22_CogAlpha_2511.18850.md)

[返回目录](../README.md)