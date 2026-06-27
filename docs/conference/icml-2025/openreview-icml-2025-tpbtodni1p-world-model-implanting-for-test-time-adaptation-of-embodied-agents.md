---
title: World Model Implanting for Test-time Adaptation of Embodied Agents
title_zh: 具身智能体测试时适应的世界模型植入框架
authors: "Minjong Yoo, Jinwoo Jang, Sihyung Yoon, Honguk Woo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tpbtodnI1p"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 结合LLM的世界模型组合用于具身智能体适应，与VLM/VLA主题相关
tldr: 具身智能体在新领域适应需要大量重训。本文提出世界模型植入框架（WorMI），通过测试时组合大语言模型推理与独立学习的领域世界模型，实现跨域适应。该方法利用基于原型的检索高效整合相关世界模型，在多个仿真环境中验证了其有效性，为多智能体系统中智能体的迁移提供了可扩展方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1631, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 832, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 832, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 829, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1590, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1748, \"height\": 299, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1520, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 694, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1109, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 967, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1001, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1195, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1029, \"height\": 1011, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 610, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 756, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 487, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 579, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 704, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 533, \"height\": 422, \"label\": \"Table\"}]"
motivation: 具身智能体适应新领域需大量数据或重训。
method: 提出WorMI框架，结合LLM推理与领域世界模型组合。
result: 在多个仿真环境测试时适应任务中表现优异。
conclusion: 测试时组合世界模型可实现高效跨域适应。
---

## Abstract
In embodied AI, a persistent challenge is enabling agents to robustly adapt to novel domains without requiring extensive data collection or retraining. To address this, we present a world model implanting framework (WorMI) that combines the reasoning capabilities of large language models (LLMs) with independently learned, domain-specific world models through test-time composition. By allowing seamless implantation and removal of the world models, the embodied agent's policy achieves and maintains cross-domain adaptability. In the WorMI framework, we employ a prototype-based world model retrieval approach, utilizing efficient trajectory-based abstract representation matching, to incorporate relevant models into test-time composition. We also develop a world-wise compound attention method that not only integrates the knowledge from the retrieved world models but also aligns their intermediate representations with the reasoning model's representation within the agent's policy. This framework design effectively fuses domain-specific knowledge from multiple world models, ensuring robust adaptation to unseen domains. We evaluate our WorMI on the VirtualHome and ALFWorld benchmarks, demonstrating superior zero-shot and few-shot performance compared to several LLM-based approaches across a range of unseen domains. These results highlight the framework’s potential for scalable, real-world deployment in embodied agent scenarios where adaptability and data efficiency are essential.

---

## 论文详细总结（自动生成）

# 论文总结：World Model Implanting for Test-time Adaptation of Embodied Agents (WorMI)

## 1. 核心问题与整体含义（研究动机与背景）
- **核心问题**：具身智能体在部署到新领域时，通常需要大量数据收集或重新训练，这限制了其在真实世界中的可伸缩性和适应性。
- **研究背景**：现有方法包括基于上下文的适应（in-context adaptation）和模型集成（model integration），但前者检索开销大，后者缺乏对未知领域的泛化能力。
- **整体含义**：本文提出 **WorMI 框架**，通过测试时将多个独立预训练的领域世界模型动态“植入”到LLM推理模型中，实现无需重训的跨域适应，兼顾知识利用的灵活性与效率。

## 2. 方法论：核心思想、关键技术、算法流程
### 核心思想
- 将 **LLM 作为通用推理模型（reasoning model）**，同时维护多个**轻量域世界模型（world models）**。在测试时，通过双阶段组合（world-to-world 集成 + world-to-reasoning 对齐）动态融合领域知识。

### 关键技术
1. **基于原型的世界模型检索（Prototype-based World Model Retrieval）**
   - 每个世界模型对应一个原型集，通过 **k-center 聚类** 从对象级状态嵌入中提取少量原型。
   - 测试时，计算当前观测嵌入集与各模型原型集的 **Wasserstein 距离**，选择 Top-K 最相关的世界模型。
   - 公式：
     \[
     \mathcal{M}_{\text{ret}} = \left\{ M_j \mid j \in \text{TopK}\left( \{ -\delta(p_j, p) \}_{j=1}^N, K \right) \right\}
     \]
   - 理论保证：原型集距离可作为数据集距离的有界近似（\(\delta(p_i, p_j) \le \delta(E_i, E_j) + 2\rho\)）。

2. **世界级复合注意力（World-wise Compound Attention）**
   - 包含 **线性投影层**、**世界级交叉注意力（World-level Cross-attention）** 和 **推理级交叉注意力（Reasoning-level Cross-attention）**。
   - 世界级注意力：以推理模型当前层输出为 query，多个世界模型的表示为 key/value，加权集成。
   - 推理级注意力：将集成后的世界知识对齐到推理模型的表示空间。
   - 公式化流程：
     \[
     l_{\pi_R} \leftarrow l_{\pi_R} + C_\theta(\{l_{M_1},...,l_{M_K}\}, l_{\pi_R})
     \]
     - 其中 \(C_\theta\) 包含 \(L_\theta, \text{Attn}_\theta^W, \text{Attn}_\theta^R\)。

3. **元学习训练（Meta-Learning for Model Implanting）**
   - 通过 **MAML 风格** 的元学习更新复合注意力的参数 \(\theta\)：内循环在随机采样的世界模型子集上微调，外循环聚合更新元参数。
   - 损失函数：行为克隆负对数似然 \(\mathcal{L}(\theta_j, B) = -\sum_{(s,a)\in B} \log \pi_{\theta_j}(a|s)\)。

### 算法流程
- 预训练 \(N\) 个世界模型（每个模型在单一域上训练三种任务：动力学、动作可能性、行为克隆）。
- 训练阶段：元学习复合注意力模块。
- 测试阶段：对每个状态 \(s_t\)，提取原型，检索 K 个相关世界模型，通过复合注意力植入策略，输出动作 \(a_t\)。

## 3. 实验设计
### 数据集与场景
- **VirtualHome**：3D 家庭模拟环境。共 1,023 条轨迹，涵盖 78 个任务（16 训练/62 测试）、20 个场景（6 训练/14 测试）。
- **ALFWorld**：文本家庭模拟环境。共 3,554 条轨迹，4 种场景类型（3 训练/1 测试）、6 种任务类型（4 训练/2 测试）。
- 领域定义：任务和场景的组合作为独立域。训练集仅包含已见域，测试集包含未见域（任务和/或场景）。

### 评估指标
- **成功率（SR）**：任务完成比例（VirtualHome 中完整任务，ALFWorld 中子目标）。
- **待执行步数（PS）**：完成任务所需的平均时间步，越低越好。

### 对比方法
- **ZSP**：零样本预训练 LLM 直接推理。
- **LLM+FT**：在少量目标域数据上微调。
- **LLM-Planner**：基于上下文学习检索示例并生成计划。
- **SayCanPay**：SOTA 模型集成方法，结合 LLM 推理与启发式成本最小化。

### 实验设置
- 推理模型固定为 **Llama-3.2-3B**，世界模型和 Pay 模型使用可训练的 **Llama-3.2-1B**。超参数详见附录。

## 4. 资源与算力
- 论文**未明确说明**使用的 GPU 型号、数量或总训练时长。
- 可推断：使用了中等规模模型（3B+1B），且包含元学习过程，可能需多卡训练，但具体算力细节缺失。

## 5. 实验数量与充分性
- **实验组数量丰富**：
  - 零样本（表 1）
  - 少样本（1/5/10 样本，表 2）
  - 消融研究（检索方法、注意力聚合方式，表 3a/3b）
  - 不同 LLM 规模影响（表 4）
  - 世界模型数量影响（表 5）
  - 复杂指令场景（表 6）
  - 持续模型植入（图 5a/b）
  - 多模态扩展（附录 D.2）
  - 对抗鲁棒性（附录 D.4）
  - 推理时间与内存（附录 D.3）
- **充分性与客观性**：
  - 报告 95% 置信区间（5 个随机种子），统计可靠。
  - 在两个不同环境（3D 模拟和文本）验证，领域类型多样。
  - 消融实验分别验证了两个核心组件的贡献，公平。
  - 对比方法均为公开基线，且使用相同 LLM 后端（除 ZSP 外），控制变量。

## 6. 主要结论与发现
- **零样本**：WorMI 在 VirtualHome 未见任务场景上 SR 66.12% (+20.41% vs SayCanPay)，PS 15.17；ALFWorld 上 SR 51.67% (+12.01%)。
- **少样本**：平均 10 样本下 VirtualHome 中 SR 79.61%，ALFWorld 中 64.46%，超越所有基线。
- **注意力分析**：世界级交叉注意力可动态关注与当前任务最相关的世界模型（如任务需特定物体时激活对应模型）。
- **可扩展性**：使用 2–4 个世界模型效果最优，更多或更少性能下降；原型检索显著降低计算开销。
- **持续学习**：可灵活添加/移除世界模型，性能随相关模型增加而提升，移除导致下降（类似机器遗忘）。

## 7. 优点（方法/实验亮点）
1. **新颖的组合范式**：首次提出将多个领域世界模型通过可学习的复合注意力“植入”LLM，实现测试时动态知识融合，不同于传统的上下文学习或模型拼接。
2. **高效原型检索**：通过 k-center 聚类将数据集压缩为极少量原型（~0.1%），降低检索代价并维持表示多样性，有理论边界支撑。
3. **轻量化元学习**：仅更新复合注意力参数（而非整个 LLM），适应到新域仅需少量梯度步骤，数据效率高。
4. **广泛的实验验证**：涵盖零样本、少样本、复杂指令、模型规模、鲁棒性、资源分析等多维度，评估全面。
5. **可扩展性与可维护性**：世界模型可独立训练、添加或移除，无需重训主模型，适合持续进化环境。

## 8. 不足与局限
1. **计算开销**：推理时需同时运行多个世界模型（即使经过检索），在资源受限设备上可能不现实。附录显示 K=3 时推理时间 385ms，内存 33GB。
2. **依赖 LLM 能力**：性能受限于底层 LLM 的推理、语言理解能力。实验显示使用更小 LLM 时优势缩小。
3. **世界模型预训练假设**：假设已有高质量的领域特定世界模型，这在真实机器人场景中难以获得（需要大量领域数据）。
4. **仅在模拟环境验证**：未在真实机器人或更复杂环境中测试，泛化性尚未完全证实。
5. **对抗模型风险**：若检索到无效或错误的世界模型，性能可能下降（附录显示 >16% 对抗比例时显著下降）。
6. **领域定义较窄**：任务/场景简单，未考虑动态环境、连续动作空间等复杂因素。

（完）
