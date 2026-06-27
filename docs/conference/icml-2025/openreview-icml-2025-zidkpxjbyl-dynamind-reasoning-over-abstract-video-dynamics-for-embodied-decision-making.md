---
title: "DynaMind: Reasoning over Abstract Video Dynamics for Embodied Decision-Making"
title_zh: DynaMind：基于抽象视频动态推理的具身决策
authors: "Ziru Wang, Mengmeng Wang, Jade Dai, Teli Ma, Guo-Jun Qi, Yong Liu, Guang Dai, Jingdong Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ziDKPXJBYL"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 视觉语言用于具身决策
tldr: 针对具身智能体在融合自然语言指令与视频内容进行决策时面临的模态平衡挑战，本文提出DynaMind框架，通过自适应FrameScorer评估视频帧的语义一致性和视觉显著性，提取关键时空动态表征，从而增强决策推理。实验验证了该方法在具身决策任务中的有效性，促进了视觉-语言与决策的深度融合。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1750, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1759, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 815, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1735, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 810, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 831, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 855, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 990, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1082, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1025, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1028, \"height\": 809, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 547, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 969, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1299, \"height\": 1010, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 970, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 842, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1034, \"height\": 333, \"label\": \"Table\"}]"
motivation: 现有方法难以平衡语言指令的简洁性与视频内容的丰富性，导致决策效果不佳。
method: 设计自适应FrameScorer评估帧重要性，提取动态表征以增强决策推理。
result: 在具身决策基准上取得了优于已有方法的性能。
conclusion: DynaMind有效连接了视觉、语言与决策，提升了具身智能体的决策能力。
---

## Abstract
Integrating natural language instructions and visual perception with decision-making is a critical challenge for embodied agents. Existing methods often struggle to balance the conciseness of language commands with the richness of video content. To bridge the gap between modalities, we propose extracting key spatiotemporal patterns from video that capture visual saliency and temporal evolution, referred to as dynamic representation. Building on this, we introduce DynaMind, a framework that enhances decision-making through dynamic reasoning. Specifically, we design an adaptive FrameScorer to evaluate video frames based on semantic consistency and visual saliency, assigning each frame an importance score. These scores are used to filter redundant video content and synthesize compact dynamic representations. Leveraging these representations, we predict critical future dynamics and apply a dynamic-guided policy to generate coherent and context-aware actions. Extensive results demonstrate that DynaMind significantly outperforms the baselines across several simulation benchmarks and real-world scenarios.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：具身智能体需要将自然语言指令与视觉感知结合起来进行决策，但语言指令简洁抽象（一个指令可对应多个视频），而视频内容丰富具体，两者存在天然的模态差异。现有方法要么直接对齐两者，要么通过细化语言指令来弥补差距，但都难以有效平衡。
- **核心问题**：如何从视频中抽象出关键时空动态信息，缩小语言与视频之间的鸿沟，从而提升具身决策的性能和泛化能力。

## 2. 论文提出的方法论

- **核心思想**：不直接对视频帧进行逐帧生成或对齐，而是从视频中提取**动态表征**（dynamic representations）——即捕捉视觉显著性和时序演化的高层时空模式，然后基于这些表征进行未来动态预测和动作决策。
- **关键技术细节**：DynaMind框架包含三个紧密集成的模块：
    1. **视频动态抽象（Video Dynamic Abstraction）**：
        - **自适应FrameScorer**：对每一帧图像，基于**语义一致性**（与语言指令的相似度）和**视觉显著性**（帧内方差）计算重要性得分 \(w_t = F(e_t)\)。
        - **滑动窗口融合**：将视频分为固定窗口（大小C），在每个窗口内用重要性得分加权融合帧特征，得到动态表征 \(h_n = \frac{\sum w_t e_t}{\sum w_t}\)。
        - 训练损失：\(L_{fs} = L_{\text{consistency}} + \lambda L_{\text{saliency}}\)，其中一致性损失鼓励动态序列与语言嵌入对齐，显著损失惩罚高方差但与语义无关的帧。
    2. **视频动态推理（Video Dynamic Reasoning）**：
        - 使用**自回归Transformer**，以历史动态序列和语言嵌入为输入，预测未来动态序列 \(\tilde{H}_{2:n} = \text{Tformer}([q_i, H_{1:n-1}] + f_{\text{pos}})\)。
        - 训练损失：MSE损失，最小化预测动态与真实动态的差距。
    3. **动态引导动作决策（Dynamic-Guided Action Decision）**：
        - 以历史帧特征、历史动作序列和预测的未来动态表征为输入，通过**动作Transformer**预测当前动作。
        - 训练时采用**混合赋值策略**：早期使用真实未来帧特征稳定训练，后期逐渐切换到预测动态，实现端到端优化。

## 3. 实验设计

- **数据集/场景**：
    - **LOReL Sawyer**：机器人操作任务，6个子任务（关门、开门、扭水龙头等），50,000条轨迹，数据包含噪声和随机性。
    - **Franka Kitchen**：长序列厨房操作，7个交互对象，每集需顺序完成4个子任务，使用Relay Policy Learning数据集。
    - **BabyAI**：导航任务，部分可观测网格世界，1k条轨迹（0.1%数据）用于训练，评估泛化到困难级别（GoToSeq, SynthSeq, BossLevel）。
    - **真实世界**：Franka Research 3臂，5个任务（按按钮、拿起牛奶盒、推箱子、放零食、叠毛巾），每任务20条示范，10次试验。
- **Benchmark**：在仿真基准上对比平均成功率；在Kitchen上还统计完成1-4个子任务的成功率。
- **对比方法**：
    - 朴素模仿学习：Vanilla BC, Decision Transformer (DT)
    - 多模态对齐：GR-1, MT-R3M（使用预训练R3M编码器）
    - 语言分解方法：LISA（分解指令为细粒度技能）, SkillDiffuser（技能+扩散生成+逆动力学）

## 4. 资源与算力

- 论文明确提到在LOReL Sawyer上训练时，使用**NVIDIA A800 GPU**，batch size = 64。
- 提供了**参数数量和GPU内存**对比：LISA 7.52M/690MiB，SkillDiffuser 60.29M/1136MiB，DynaMind 7.84M/854MiB。
- **未明确说明**训练时长、GPU数量、总耗时等。BabyAI仅使用1k轨迹，计算成本较低。

## 5. 实验数量与充分性

- **实验数量**：涵盖3个仿真环境（共约9个任务变体）、1个真实环境（5个任务），包括：
    - 主性能对比（表1、图3、表3）
    - 消融实验（动态抽象、推理间隔、动作决策，图6、图7）
    - 泛化实验（新指令、新任务、组合任务，表2、表5、表6）
    - 计算效率对比（表4）
    - 数据量影响（图12）
    - 架构配置消融（表8）
    - 互信息分析（图8）
- **充分性**：实验设计较为全面，覆盖多种场景和条件，消融分析验证了各模块贡献。泛化实验考察了语言理解、任务迁移和组合能力。但缺少统计显著性检验（如置信区间或重复种子次数）。
- **公平性**：保持相似参数规模和相同编码器架构，但未对所有方法进行相同条件的超参数调优。

## 6. 论文的主要结论与发现

- DynaMind**显著优于所有基线**，在LOReL Sawyer上平均成功率53.67%，超过SkillDiffuser（43%）和LISA（40%）。在Franka Kitchen上平均成功率39.81%，优于GR-1（32.94%）和MT-R3M（30.50%）。
- 动态抽象模块能有效识别关键帧，随训练过程重要性得分越来越集中于任务相关帧（图5）。
- 动态推理的间隔C过大或过小都会损害性能，中等间隔（C=30）最佳。
- 动态引导动作决策优于语言引导或混合引导。
- 从简单任务学到的动态表征可迁移到更复杂任务（表5、表6）。
- 真实实验中DynaMind平均成功率94%，优于LISA（82%），尤其在高难度任务（叠毛巾）上优势明显。

## 7. 优点

- **视角创新**：从“细化语言”转向“抽象视频”，直接处理模态差异的核心。
- **方法设计清晰**：三个模块分工明确，端到端训练，避免复杂流水线。
- **自适应FrameScorer**：无需人工标注，通过语义和显著性双损失自动学习帧重要性。
- **混合赋值策略**：缓解早期推理不稳定的问题，实现平稳训练。
- **实验全面**：覆盖模拟和真实、多样任务、消融和泛化分析，验证了方法的普适性和鲁棒性。
- **计算成本适中**：参数量与LISA相当（7.84M），远低于SkillDiffuser（60.29M），GPU内存需求合理。

## 8. 不足与局限

- **固定推理间隔**：论文承认使用固定窗口C可能不是最优的，尤其是在任务需要自适应时序推理时。
- **FrameScorer在简单环境贡献有限**：在BabyAI（视觉内容简单）中，消融实验显示动态抽象模块带来的提升较小，说明该方法对视觉复杂度敏感。
- **缺乏失败案例分析**：未系统讨论在哪些任务或条件下模型容易失败，可能隐藏偏差。
- **真实实验规模较小**：每个任务仅20条示范和10次试验，统计可靠性不足；任务种类有限，未覆盖更复杂的真实操作（如抓取、组装）。
- **无显著性检验**：性能差异未列出置信区间或p值，难以判断是否统计显著。
- **潜在过拟合风险**：在LOReL Sawyer的某些任务（如“move white mug down”）上所有方法成功率都很低（6-20%），DynaMind仅20%，未深入分析原因。

（完）
