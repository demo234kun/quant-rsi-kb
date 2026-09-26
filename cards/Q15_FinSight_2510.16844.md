# Q15 · FinSight：面向真实世界的金融深度研究

## 元信息

| 字段 | 内容 |
|---|---|
| 标题 | FinSight: Towards Real-World Financial Deep Research |
| 作者 | Jiajie Jin; Yuyao Zhang; Yimeng Xu; Hongjin Qian; Yutao Zhu; Zhicheng Dou |
| 出处 | arXiv:2510.16844（2025-10-19） |
| 类型 | 方法论文（CAVM 代码 agent · 迭代视觉增强 · 两阶段写作） |
| 链接 | [arXiv](https://arxiv.org/abs/2510.16844) · [HTML v1](https://arxiv.org/html/2510.16844v1) |

---

## 一句话结论

> 提出 **FinSight（Financial InSight）**：以 **Code Agent with Variable Memory（CAVM）** 为底座——把外部数据、设计工具、agents 统一进"可编程变量空间"，用可执行代码完成数据收集、分析与报告生成——叠加**迭代视觉增强机制**（把原始可视化逐步精修成专业金融图表）与**两阶段写作框架**（把链式分析展开成连贯、带引用的多模态报告），在事实准确性、分析深度、呈现质量上显著超越包括领先 deep-research 系统在内的全部基线。

## 问题背景

- 生成专业金融报告劳动密集且智力要求高，现有 AI 系统难以全自动完成。
- 金融报告要求**多模态**（数据 + 图表 + 文本）、**事实准确**、**结构一致**、**可引用**。
- 既有 deep research 系统在金融域的事实准确性与呈现质量不足。

## 方法

1. **CAVM 架构**：Code Agent with Variable Memory——数据、工具、agent 统一进可编程变量空间，agent 通过可执行代码"写变量"式地完成数据收集➜分析➜报告。
2. **迭代视觉增强（Iterative Vision-Enhanced）**：逐步把原始视觉输出精修为专业金融图表。
3. **两阶段写作框架**：从简洁 Chain-of-Analysis 片段展开为连贯、citation-aware、多模态报告（分析深度 + 结构一致性）。

## 关键结果

| 实验 | 结果 |
|---|---|
| 评测 | 公司级与行业级多类任务 |
| 对比 | 显著优于全部基线，含领先 deep-research 系统 |
| 三维度 | 事实准确性 / 分析深度 / 呈现质量全面领先 |

## 与 RSI 知识库的关系

- 属于 **HyperAgents 路线**（方向5 主范式）的金融实现：CAVM 的"可编程变量空间"让 agent 的可执行代码成为统一改进载体（代码即记忆）。
- "迭代视觉增强" = 对"报告产物"做多轮精修——轻量级、固定目标的自改进闭环。
- 与 [Q14 FinRpt] 的区别：FinSight 强在工程化多模态产出，FinRpt 强在评测指标与数据集；两者均无跨周期记忆成长（RSI 空白点）。

## 解读与批判

- ✅ CAVM 把"外部数据/工具/agent 统一进变量空间"是很实用的抽象，工程复用价值高。
- ✅ 多模态 + citation-aware 直接面向真实研报工作流。
- ⚠️ 未报告跨周期/跨报告的学习与成长（长期记忆改进工具）——方向5 的 RSI 仍待实现。
- ⚠️ 公司/行业级任务规模与市场覆盖面（A股/美股）细节需正文确认。

---

**相关卡片**：[Q14 FinRpt](Q14_FinRpt_2511.07322.md) · [Q16 FinDebate](Q16_FinDebate_2509.17395.md) · [Q17 Amazon Analyst](Q17_AmazonAnalyst_2026.md)

[返回目录](../README.md)