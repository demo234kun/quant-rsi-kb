# Q06 · AutoScientist-Quant：预算化自进化编码 Agent 自动量化研究

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | AutoScientist-Quant: Self-Evolving Coding Agents for Automatic Research in Quantitative Investment |
| 作者 | Zongqian Li; Yaoyiran Li; Yaohui Guo; Ming Zhang; Nigel Collier; Eugene Ie |
| 出处 | arXiv:2608.28632（2026-08-05） |
| 类型 | 方法论文（Google/Cambridge；预算化树搜索 + 三阶段闭环） |
| 链接 | [arXiv](https://arxiv.org/abs/2608.28632) · [HTML](https://arxiv.org/html/2608.28632) |

---

## 一句话结论

> 把量化研究整体当作**一个有预算的搜索问题**：单一控制器在每轮根据剩余预算决定 **improve / combine / pivot / stop**、扩展哪个节点、生成几个 alpha、检索哪条历史轨迹，并用同一核心完成因子库选择与模型调优，闭环"假设 → 可部署策略"；在 CSI 系列 universe 上几乎"所有指标、所有设置"达最优，并修复了既有评估管线的 **2 个 lookahead 问题**。

## 问题背景

- LLM agent 能挖 alpha，但有三个弱点：① 运行中搜索**不可自适应**（不知道何时转向/停止）；② 自动化止于 alpha 生成，**因子库选择与模型选择仍靠手动**；③ alpha 发现可能通过循环反馈或代码问题**读到测试窗**（leakage）。

## 方法

1. **单控制器 + 预算感知决策**：每轮观测共享 pool P_r 与剩余预算 b_r，输出 (动作 o, 父节点 σ, 生成数量 n)；动作空间 = {Improve, Combine, Pivot, Stop}；预算规则 b_{r+1} = b_r − Σn。
2. **共享记忆轨迹检索**：从共享 pool 检索历史轨迹，指导新一轮生成。
3. **同一核心做库选择与模型调优**：打通"alpha → 因子库 → 模型"，闭环到可部署策略。
4. **评估管线审查与修复**：修复 2 个 lookahead 问题，保证 **feedback window 与 held-out test window 不相交**——所有对比都测真实泛化。

## 关键结果

| 实验 | 结果 |
|---|---|
| CSI universes | 几乎所有指标、几乎所有设置下取得最优值 |
| CSI 1000 超额收益 | 最佳 baseline 的 **6.4% → 7.1%** |
| 鲁棒性 | 跨多个 backbone 与多个市场的结论保持一致 |
| Lookahead 修复 | 2 个既有评估管线 lookahead 问题被修复并公开 |

## 与 RSI 知识库的关系

- 是 **AutoResearch（karpathy）"改代码→跑短实验→看指标→保留或回滚"** 极简 loop 的金融化：一次回测 = 一次"5 分钟实验"。
- **预算感知停止 = 把"停止/转向"从排程改为证据驱动**——比纯 LLM 直觉决策更可审计（热点文件方向2 创新点：可升级为带后悔界的 bandit 决策）。
- 显式密封 feedback window 与 test window = [Q01 AQuA] 密封思想的延续，堵住"自改进系统自我作弊"通道。

## 解读与批判

- ✅ 把"预算"作为一等公民：搜索的大小/广度/止点全部条件于预算，可复现、可审计、可解释。
- ✅ 主动修复 lookahead 并公开，说明作者把"评估可信度"当作系统正确性的一部分。
- ✅ 跨 backbone/跨市场稳健性实验设计扎实。
- ⚠️ 需求同级别的成本透明：预算消耗的绝对量与收益曲线未在摘要层面披露。
- ⚠️ 成本后收益是硬指标（热点文件指出部分 agentic baseline 在 CSI500 扣成本后为负超额），论文需看 Table 1 的 after-cost 口径。

---

**相关卡片**：[Q07 FactorEngine](Q07_FactorEngine_2603.16365.md) · [Q11 FLAG-Trader](Q11_FLAGTrader_2502.11433.md) · [Q12 QuantCode-Bench](Q12_QuantCodeBench_2604.15151.md) · [Q24 RSI 综述](Q24_RSI综述_saulius_2026.md)

[返回目录](../README.md)