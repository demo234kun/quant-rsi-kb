# Q02 · FactorMiner：带技能与经验记忆的自进化因子发现 Agent

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | FactorMiner: A Self-Evolving Agent with Skills and Experience Memory for Financial Alpha Discovery |
| 作者 | Yanlong Wang; Jian Xu; Hongkang Zhang; Shao-Lun Huang; Danny Dongning Sun; Xiao-Ping Zhang |
| 出处 | arXiv:2602.14670（2026-02-16, v2）· **KDD 2026** |
| 类型 | 方法论文（Ralph Loop + 技能架构 + 经验记忆） |
| 链接 | [arXiv](https://arxiv.org/abs/2602.14670) · [HTML v2](https://arxiv.org/html/2602.14670v2) |

---

## 一句话结论

> 用"模块化技能架构（60+ 金融算子封装为可执行工具）+ 结构化经验记忆（把历史挖掘试验蒸馏成成功模式与失败约束）"实例化 **Ralph Loop（retrieve→generate→evaluate→distill）**，专门对抗因子库增长带来的 "Correlation Red Sea"（相关性红海）问题，使高质量候选产出率从约 20% 提升到约 60%，并释放 110 个 A 股因子。

## 问题背景

- 公式化 alpha 因子挖掘搜索空间巨大，且需要领域知识 + 可解释信号。
- 关键难点：**因子库越大，新信号越难找**——高冗余使新候选与已有因子高度相关（"Correlation Red Sea"）。
- 先验知识（业界经验/历史失败）难以被 agent 有效复用，导致重复探索。

## 方法

1. **模块化技能架构（Modular Skill Architecture）**：把系统性金融评估封装成可执行工具（GPU 加速后端 + 多阶段验证：IC 筛选 → 相关性检查 → 去重 → 全量验证），agent 直接"调用技能"而非"写评估代码"。
2. **结构化经验记忆（Experience Memory）**：把历史挖掘试验蒸馏为可操作洞察——**成功模式**（往前走的配方）与**失败约束**（别再踩的坑）。
3. **Ralph Loop 实例化**：retrieve（取记忆先验）→ generate（生成候选）→ evaluate（技能评估）→ distill（把本轮经验写回记忆）。
4. 记忆先验引导探索：减少冗余搜索、聚焦有前途的方向，实现"轻量、灵活"的自进化。

## 关键结果

| 指标 | 结果 |
|---|---|
| 高质量候选产出率 | 经验记忆使 **20% → 60%**（对比无记忆/记忆引导） |
| 因子库质量 | 多数据集、多资产、多市场下保持低冗余、可解释、可扩展 |
| 释放成果 | 公开 110 个 A 股因子作为参考库 |

## 与 RSI 知识库的关系

- **经验记忆 = 自生成的训练数据**：agent 从自己的历史试验中学习，是最直接的"用证据改进自身"机制。
- Ralph Loop 的 distil 环节对应 RSI 知识库中"把运行经验固化回系统"的一环；属于**部署期 RSI** 方法族。
- 与方向 2（预算化研究控制器）不同：FactorMiner 的改进对象是"记忆与技能"，而非"调度策略"。

## 解读与批判

- ✅ "技能 + 记忆"双通道设计直击搜索空间膨胀 + 冗余问题；工程完整（GPU 加速、多阶段验证、去重）。
- ✅ Ralph Loop 落地清晰，产出可审计的因子库（110 个 A 股因子可复现）。
- ⚠️ 属于"经验累积"而非**进化谱系**（无 DGM 式 archive 多样性采样），探索多样性的理论保障弱于谱系方法。
- ⚠️ 记忆可能存在 stalgation/自证偏差（早期失败约束可能过度限制后续搜索）；论文对记忆污染的讨论有限。

---

**相关卡片**：[Q01 AQuA](Q01_AQuA_2608.12841.md) · [Q03 QuantaAlpha](Q03_QuantaAlpha_2602.07085.md) · [Q06 AutoScientist-Quant](Q06_AutoScientistQuant_2608.28632.md)

[返回目录](../README.md)