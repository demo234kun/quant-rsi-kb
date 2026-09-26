# 📈 quant-rsi-kb · 量化金融 × 递归自我改进（QUANT × RSI）论文精读卡片集

> **本库定位**：收集 **2024–2026 年"量化金融 × RSI（Recursive Self-Improvement）"** 的公开论文与深度文章，每篇一张"精读卡片"：元信息 / 一句话结论 / 问题背景 / 方法要点 / 关键结果 / 与 RSI 的关系 / 解读与批判。
> 共 **24 张卡片**（21 篇 arXiv 论文 + AlphaBench(ICLR 2026) + Amazon 企业技术报告 + saulius 综述博客），按 **[金融领域 RSI 可做研究方向清单](https://github.com/demo234kun/rsi-research)_finance_research/FINANCE_HOTSPOTS.md** 的 7 大方向组织。
> 所有元信息均已核验（arXiv API / ICLR 官方 proceedings / Amazon Science PDF / 博客原文）。

> 姊妹库：[RSI 知识库 RSI-KB](https://github.com/demo234kun/RSI-Knowledge-Base)（通用 RSI 论文区 P01–P17 与代码区 9 项目）；本库是其"金融应用"延伸的论文侧，卡片编号用 **Q** 前缀。RSI 范式缩写对照：DGM=Darwin Gödel Machine；HyperAgents=Meta/HyperAgents；SICA=Self-Improving Coding Agent；Gödel Agent=Arvid-pku 版；SEAL=Self-Adapting LLMs；ADAS=Automated Design of Agentic Systems；ShinkaEvolve=SakanaAI；OpenEvolve=社区版 AlphaEvolve；AutoResearch=karpathy/autoresearch。

---

## 精读卡片索引

| # | 论文 | 年份/venue | 方向 | 主题 | 卡片 |
|---|---|---|---|---|---|
| Q01 | **AQuA: Recursively Self-Improving Quantitative Trading Research Agents** | 2026-08 / arXiv:2608.12841 | 方向1 | 密封沙箱 · 双系统因子发现+模型开发 | [📄 打开](cards/Q01_AQuA_2608.12841.md) |
| Q02 | **FactorMiner: A Self-Evolving Agent with Skills and Experience Memory** | 2026-02 / KDD 2026 + arXiv:2602.14670 | 方向1 | Ralph Loop · 技能+经验记忆因子发现 | [📄 打开](cards/Q02_FactorMiner_2602.14670.md) |
| Q03 | **QuantaAlpha: An Evolutionary Framework for LLM-Driven Alpha Mining** | 2026-02 / arXiv:2602.07085 | 方向1 | 轨迹级变异/交叉进化挖掘 | [📄 打开](cards/Q03_QuantaAlpha_2602.07085.md) |
| Q04 | **Hubble: Safe, Diverse, Reproducible Alpha Factor Discovery** | 2026-03 / arXiv:2604.09601 | 方向1 | AST 沙箱 · 家族感知选择 | [📄 打开](cards/Q04_Hubble_2604.09601.md) |
| Q05 | **AlphaBench: Benchmarking LLMs in Formulaic Alpha Factor Mining** | 2026 / ICLR 2026 | 方向1 | FAFM 基准 · 生成/评估/搜索三任务 | [📄 打开](cards/Q05_AlphaBench_ICLR2026.md) |
| Q06 | **AutoScientist-Quant: Self-Evolving Coding Agents for Automatic Quant Research** | 2026-08 / arXiv:2608.28632 | 方向2 | 预算化树搜索 · 三阶段闭环 | [📄 打开](cards/Q06_AutoScientistQuant_2608.28632.md) |
| Q07 | **FactorEngine: Program-level Knowledge-Infused Factor Mining** | 2026-03 / arXiv:2603.16365 | 方向2 | 宏微共进化 · 知识注入启动 | [📄 打开](cards/Q07_FactorEngine_2603.16365.md) |
| Q08 | **EvolveTrade: Experience-Driven Policy Refinement for Self-Evolving LLM Trading** | 2026-09 / arXiv:2609.17632 | 方向3 | 文本策略自进化 · Policy Agent | [📄 打开](cards/Q08_EvolveTrade_2609.17632.md) |
| Q09 | **SHARP: Self-Evolving Human-Auditable Rubric Policy** | 2026-05 / arXiv:2605.06822 | 方向3 | 符号化 rubric 演化 · 归因编辑 | [📄 打开](cards/Q09_SHARP_2605.06822.md) |
| Q10 | **ATLAS: Adaptive Trading via Dynamic Prompt Optimization & Multi-Agent Coordination** | 2025-10 / arXiv:2510.15949 | 方向3 | Adaptive-OPRO 动态指令适配 | [📄 打开](cards/Q10_ATLAS_2510.15949.md) |
| Q11 | **FLAG-Trader: Fusion LLM-Agent with Gradient-based RL** | 2025-02 / ACL 2025 + arXiv:2502.11433 | 方向3 | LLM 当策略网络 · PPO 微调 | [📄 打开](cards/Q11_FLAGTrader_2502.11433.md) |
| Q12 | **QuantCode-Bench: Executable Trading Strategy Generation Benchmark** | 2026-04 / arXiv:2604.15151 | 方向4 | 400 任务 · 多阶段评测管线 | [📄 打开](cards/Q12_QuantCodeBench_2604.15151.md) |
| Q13 | **QRAFTI: Agentic Framework for Empirical Quant Research** | 2026-04 / arXiv:2604.18500 | 方向4 | 研究工具包 · MCP 服务 · 反思规划 | [📄 打开](cards/Q13_QRAFTI_2604.18500.md) |
| Q14 | **FinRpt: Equity Research Report Generation (Dataset + Multi-agent)** | 2025-11 / arXiv:2511.07322 | 方向5 | ERR 任务定义 · 9 agent · 11 指标 | [📄 打开](cards/Q14_FinRpt_2511.07322.md) |
| Q15 | **FinSight: Towards Real-World Financial Deep Research** | 2025-10 / arXiv:2510.16844 | 方向5 | CAVM 代码 agent · 迭代视觉增强 | [📄 打开](cards/Q15_FinSight_2510.16844.md) |
| Q16 | **FinDebate: Multi-Agent Collaborative Intelligence** | 2025-09 / arXiv:2509.17395 | 方向5 | 安全辩论协议 · 五专家并行 | [📄 打开](cards/Q16_FinDebate_2509.17395.md) |
| Q17 | **Building Analyst-Like Agents (Amazon)** | 2026-04 / Amazon Science | 方向5 | 初级分析师成长路径 · 企业落地 | [📄 打开](cards/Q17_AmazonAnalyst_2026.md) |
| Q18 | **MadEvolve: Evolutionary Optimization of Trading Systems** | 2026-05 / arXiv:2605.23007 | 方向6 | AlphaEvolve 移植 · Bitcoin 交易 | [📄 打开](cards/Q18_MadEvolve_2605.23007.md) |
| Q19 | **Evolutionary Factor Searching for Sparse Portfolio Optimization** | 2025-07 / arXiv:2507.17211 | 方向6 | 排序重构 + RMT 冗余感知分配 | [📄 打开](cards/Q19_EvoFactorSearch_2507.17211.md) |
| Q20 | **AlphaAgent: Regularized Exploration to Counteract Alpha Decay** | 2025-02 / arXiv:2502.16789 | 方向6 | AST 原创性约束 · 抗衰退 | [📄 打开](cards/Q20_AlphaAgent_2502.16789.md) |
| Q21 | **QuantAgent: Seeking Holy Grail in Trading** | 2024-02 / arXiv:2402.03755 | 方向7 | 双层 loop · 知识库自增强 | [📄 打开](cards/Q21_QuantAgent_2402.03755.md) |
| Q22 | **CogAlpha: Cognitive Alpha Mining via Code-Based Evolution** | 2025-11 / arXiv:2511.18850 | 方向7 | 代码级进化 · 认知式搜索 | [📄 打开](cards/Q22_CogAlpha_2511.18850.md) |
| Q23 | **EVOQUANT: Self-Evolving Verifier-Guided Strategy Optimization** | 2026-07 / arXiv:2607.12455 | 方向7 | 诊断→受控编辑→多阶段验证→蒸馏 | [📄 打开](cards/Q23_EVOQUANT_2607.12455.md) |
| Q24 | **RSI for Trading 综述（saulius.io）** | 2026-03 / Blog | 综述 | Mind Evolution → 交易映射 · 风险清单 | [📄 打开](cards/Q24_RSI综述_saulius_2026.md) |

## 阅读路径建议

- **只要时间读 1 篇** → Q01（AQuA：密封沙箱 + 双系统 RSI 的完整范例，IC≈0.190 / Sharpe +2.50）
- **想做因子发现研究（方向1）** → Q01 → Q02 → Q03 → Q04 → Q05（基准）
- **想做端到端自动研究（方向2）** → Q06 → Q07
- **想看交易策略自进化（方向3）** → Q08 → Q09 → Q10（→ Q11 互补的 RL 微调路线）
- **想做研报/分析系统（方向5）** → Q14 → Q15 → Q16 → Q17
- **想理解进化式组合优化（方向6）** → Q18 → Q19 → Q20
- **想了解全貌 + 风险** → Q24（综述）→ 热点文件 [FINANCE_HOTSPOTS.md](https://github.com/demo234kun/rsi-research/blob/main/_finance_research/FINANCE_HOTSPOTS.md)

## 分类速览表（按 RSI 范式归属）

| 类别(范式) | 卡片 |
|---|---|
| DGM / 进化谱系（方向1 主范式） | Q01, Q03, Q04 |
| Ralph Loop / 记忆精馏（FactorMiner） | Q02 |
| OpenEvolve / AlphaEvolve 移植 | Q07, Q18, Q22 |
| ShinkaEvolve（样本高效进化） | Q03, Q18, Q19 |
| AutoResearch（预算化循环） | Q06 |
| Gödel Agent（文本/策略自修改） | Q08, Q09, Q10 |
| RL 微调路线（与文本自进化互补） | Q11 |
| SICA（代码自改进 / 自调试） | Q12, Q13 |
| HyperAgents（Meta Agent 双层递归） | Q14, Q15, Q16, Q17 |
| ADAS / 归因自进化 | Q21, Q23 |
| 基准 / 评测 | Q05, Q12 |
| 综述 | Q24 |

## BibTeX

全部条目见 [references.bib](references.bib)（key 规则：`作者首姓+arXiv尾号`；非 arXiv 条目 key 用 `首作者首姓+年份`，可直接导入 Zotero/EndNote）。

## 引用约定

本库中引用风格：`[Q0X]` 指本库卡片编号；纯 arXiv 编号直接给出（如 arXiv:2608.12841）。

## 数据来源与维护

- 全部 arXiv 元信息（标题/作者/日期/摘要）经 export.arxiv.org API 逐篇核验（2026-09-27）；AlphaBench 经 ICLR 2026 官方 proceedings PDF 核验；Amazon 经 Amazon Science PDF 首页核验；saulius 综述经博客原文核验。
- 勘误记录：热点文件中的 **"Made Evolve"** 实为 arXiv 官方的 **MadEvolve**（arXiv:2605.23007），本库以 arXiv 为准。
- 方向分类与 RSI 范式映射依据 [FINANCE_HOTSPOTS.md](https://github.com/demo234kun/rsi-research/blob/main/_finance_research/FINANCE_HOTSPOTS.md)（检索时间 2026-09-24）。