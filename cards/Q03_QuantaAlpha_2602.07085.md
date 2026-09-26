# Q03 · QuantaAlpha：LLM 驱动的轨迹级进化 Alpha 挖掘框架

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | QuantaAlpha: An Evolutionary Framework for LLM-Driven Alpha Mining |
| 作者 | Jun Han; Shuo Zhang; Wei Li; Yifan Dong; Tu Hu; Yumo Zhu; Xiaomin Yu; Xin Guo; Zhaowei Liu; Kunyi Wang; Jingping Liu; Tianyi Jiang; Ruichuan An; Sen Hu; Zhi Yang; Ronghao Che; Huacan Wang |
| 出处 | arXiv:2602.07085（2026-02-06） |
| 类型 | 方法论文（轨迹级进化挖掘，OpenEvolve/ShinkaEvolve 路线） |
| 链接 | [arXiv](https://arxiv.org/abs/2602.07085) · [PDF v2](https://arxiv.org/pdf/2602.07085v2) |

---

## 一句话结论

> 把**每一条端到端挖掘 run 当作一个"轨迹个体"**，用轨迹级变异（定位次优步骤做定向修订）与轨迹级交叉（重组互补高奖励片段）驱动进化：在 CSI 300 上以 GPT-5.2 取得 IC=0.0472、ARR=4.68%、MDD=11.8%，且 CSI 300 挖出的因子迁移至 CSI 500 / S&P 500 四年累计超额约 40.28% / 19.1%。

## 问题背景

- 金融市场噪声大且非平稳，alpha 挖掘对回测噪声与 regime 切换高度敏感。
- 现有 agentic 框架提升了自动化，但缺乏**可控的多轮搜索**与**对已验证经验的可复用**。
- 因子级个体（单表达式）丢失了"这条因子是怎么挖出来的"上下文。

## 方法

1. **轨迹即个体**：一次端到端挖掘 run = 一条轨迹（假设 → 表达式 → 代码 → 回测 → 反思），作为进化的基本单位。
2. **轨迹级 mutation**：定位轨迹中的**次优步骤**，进行定向修订（而非盲目重写整条轨迹）。
3. **轨迹级 crossover**：重组互补的高奖励片段，复用已验证的有效模式。
4. **生成时语义一致性约束**：强制 假设（hypothesis）→ 因子表达式 → 可执行代码 三者语义一致。
5. **复杂度与冗余约束**：抑制因子拥挤与过工程化（crowding mitigation）。

## 关键结果

| 实验 | 结果 |
|---|---|
| CSI 300（GPT-5.2） | IC **0.0472** · ARR **4.68%** · MDD **11.8%** |
| 迁移 CSI 500 | 四年累计超额 **≈40.28%** |
| 迁移 S&P 500 | 四年累计超额 **≈19.1%** |
| 对比基线 | 一致优于强基线及既有 agentic 系统 |

## 与 RSI 知识库的关系

- 进化单位从"因子"升级为"轨迹"，是把 **OpenEvolve / ShinkaEvolve 的 population + parent sampling** 落地到金融的样例（热点文件方向1 辅助思想）。
- 交叉/变异复用"已验证经验" = 倾向性复用教训的 RSI 特征；语义一致性约束 = 防止自改进生成"幻觉因子"。
- 与 [P01] 综述中"进化谱系类自改进"直接对应。

## 解读与批判

- ✅ 轨迹级个体是新抽象层次：保留搜索上下文，使变异/交叉比因子级更有信息量。
- ✅ 跨市场迁移实验（CSI500/S&P500）提供了 distribution shift 下的稳健性证据。
- ✅ 显式处理 crowding（复杂度/冗余约束），回应金融进化搜索的公开痛点是 alpha decay。
- ⚠️ 结果依赖 GPT-5.2 级别模型，成本与复现门槛未披露。
- ⚠️ 迁移收益为累计超额口径，未报告回撤/费用敏感性。

---

**相关卡片**：[Q01 AQuA](Q01_AQuA_2608.12841.md) · [Q02 FactorMiner](Q02_FactorMiner_2602.14670.md) · [Q04 Hubble](Q04_Hubble_2604.09601.md) · [Q20 AlphaAgent](Q20_AlphaAgent_2502.16789.md)

[返回目录](../README.md)