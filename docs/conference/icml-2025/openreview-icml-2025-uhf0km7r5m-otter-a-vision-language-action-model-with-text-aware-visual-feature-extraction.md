---
title: "OTTER: A Vision-Language-Action Model with Text-Aware Visual Feature Extraction"
title_zh: OTTER：一种具有文本感知视觉特征提取的视觉-语言-动作模型
authors: "Huang Huang, Fangchen Liu, Letian Fu, Tingfan Wu, Mustafa Mukadam, Jitendra Malik, Ken Goldberg, Pieter Abbeel"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UHF0km7R5M"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 视觉-语言-动作机器人模型
tldr: 针对现有VLA模型在机器人动作预测中需要微调预训练VLM、破坏语义对齐的问题，本文提出OTTER模型，通过显式的文本感知视觉特征提取，仅将与语言指令对齐的任务相关视觉特征传递给策略Transformer，从而保持视觉-语言编码器冻结。实验表明该方法在多个机器人操控任务上取得了更优的性能，为VLA模型的高效部署提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 836, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 798, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 828, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 773, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1603, \"height\": 920, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1751, \"height\": 492, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 513, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1412, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1582, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 881, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1106, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1414, \"height\": 935, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 998, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 695, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1087, \"height\": 147, \"label\": \"Table\"}]"
motivation: 现有VLA模型需要微调预训练VLM，导致预训练的语义对齐被破坏。
method: 提出OTTER架构，通过文本感知的视觉特征提取，仅选取与语言指令语义对齐的视觉特征传递给策略网络。
result: 在多个机器人操控任务上，OTTER相比基线方法取得了更优的动作预测性能。
conclusion: OTTER通过保持编码器冻结而实现了高效且语义一致的VLA模型。
---

## Abstract
Vision-Language-Action (VLA) models aim to predict robotic actions based on visual observations and language instructions. Existing approaches require fine-tuning pre-trained vision-language models (VLMs) as visual and language features are independently fed into downstream policies, degrading the pre-trained semantic alignments. We propose OTTER, a novel VLA architecture that leverages these existing alignments through explicit, text-aware visual feature extraction. Instead of processing all visual features, OTTER selectively extracts and passes only task-relevant visual features that are semantically aligned with the language instruction to the policy transformer. This allows OTTER to keep the pre-trained vision-language encoders frozen. Thereby, OTTER preserves and utilizes the rich semantic understanding learned from large-scale pre-training, enabling strong zero-shot generalization capabilities. In simulation and real-world experiments, OTTER significantly outperforms existing VLA models, demonstrating strong zero-shot generalization to novel objects and environments. Video, code, checkpoints, and dataset: https://ottervla.github.io/.

---

## 论文详细总结（自动生成）

# OTTER 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的视觉-语言-动作（VLA）模型通常需要微调预训练的视觉-语言模型（VLM），将视觉和语言特征独立输入策略网络，导致预训练阶段学到的语义对齐被破坏，从而在未见物体或环境上的泛化能力显著下降。
- **研究背景**：预训练的VLM（如CLIP）本身已具备强大的跨模态语义对齐和零样本能力，但直接微调会使模型过拟合于机器人数据集（语义多样性远低于通用视觉-语言数据集），造成泛化损失。
- **研究动机**：是否可以利用预训练VLM已有的对齐能力，避免微调带来的退化？本文提出一种新架构OTTER，通过冻结VLM编码器并仅提取与语言指令语义对齐的视觉特征，实现更好的泛化。

## 2. 论文提出的方法论

### 核心思想
- 保持预训练视觉-语言编码器（CLIP）**完全冻结**，通过文本感知的视觉特征提取，仅将任务相关的视觉特征（与语言指令语义对齐的部分）传递给策略Transformer，从而保留预训练的语义理解，同时避免微调带来的过拟合。

### 关键技术细节
1. **文本感知视觉特征提取（Text-Aware Visual Feature Extraction）**：
   - 使用CLIP的文本编码器提取每token语言特征 \( f_l \)（m个token）。
   - 视觉特征取自CLIP最后一个注意力层的输出 \( X_{attn} \)（而非最终输出 \( X_{out} \)），因其包含更干净的语义信息（借鉴ClearCLIP）。
   - 对语言和视觉特征进行L2归一化后，计算温度加权的余弦相似度注意力：
     \[ f_{vl} = \text{softmax}(\hat{f}_l \hat{f}_v^\top / \tau) (\hat{f}_v + PE) \]
     其中 \( \tau \) 是可学习的温度参数，\( PE \) 为2D位置编码。结果 \( f_{vl} \) 是文本感知的视觉token（每个语言token对应视觉patch的加权组合）。
   - 整个CLIP保持冻结，仅 \( \tau \) 可学习。

2. **模型架构**：
   - **输入处理**：每个摄像头的 \( f_{vl} \) 通过可学习的交叉注意力池化压缩为单个token \( f'_{vl} \)；语言特征 \( f_l \) 也经池化得到单文本token \( f'_l \)；机器人本体状态经MLP编码为 \( f_e \)。
   - 在时刻t，将 \( f'_l, f'_{vl}, f_e \) 拼接成单个token \( f_t \) 作为策略网络输入。
   - **策略网络**：4层8头因果Transformer，隐层维度512；上下文窗口T=12步，每步预测未来12步动作（delta末端执行器姿态，10维）。
   - 动作执行采用时间集成（temporal ensembling）和滚动时域控制。

## 3. 实验设计

### 数据集与场景
- **仿真环境**：LIBERO benchmark（包含 LIBERO-Spatial、LIBERO-Object、LIBERO-Goal、LIBERO-90），共30个训练任务 + 10个自行构建的未见任务（修改语言指令和对象）。
- **真实机器人环境**：使用Franka机器人，四个运动基元——拾取放置、戳、倒水、开/关抽屉。
  - DS-PnP：10个拾取放置任务，共724条演示。
  - DS-ALL：全部四个基元，共1,185条演示。
  - 19个训练任务 + 15个未见任务（新物体或新组合），每个任务10次试验。

### 基准方法
- **Octo**：从头训练的Transformer策略（基于OXE数据集）。
- **OpenVLA**：微调Prismatic-7B VLM。
- **π0-Fast-Droid**：基于PaliGemma和Fast动作分词器的VLA。
- **DFP-OTTER**：OTTER的变体，直接传递所有视觉和文本特征（无文本感知提取）。
- 其他消融：去掉本体状态、去掉文本token、去掉CLIP视觉、微调CLIP等。

## 4. 资源与算力

- 论文中明确说明：所有模型使用 **4块 NVIDIA A100 80GB GPU** 进行训练。
- 训练步数：40,000步（预训练OXE时60,000步），学习率3e-4，batch size 64。
- 未提供精确训练时长。

## 5. 实验数量与充分性

### 实验规模
- **仿真实验**：3个LIBERO子数据集 + 10个未见任务，每个任务50次试验，共约100组对比（包括基准和消融）。
- **真实实验**：
  - 单基元：训练任务100次试验，未见任务70次试验（表1）。
  - 多基元：4个基元各10次试验 × 多个任务，共150次未见任务试验（表2）。
  - 消融实验：多个变体在真实和仿真中均有评估（表1、表4）。
  - 缩放实验：三种CLIP大小（ViT-B/32、B/16、L/14）对比（图5）。

### 充分性与公平性
- **公平性**：所有基准均使用相同数据进行微调（Octo、OpenVLA、π0-Fast-Droid），超参数一致。
- **充分性**：覆盖了仿真和真实、单基元和多样本基元、分布内和分布外任务、多个消融分支，实验设计较为全面。
- **潜在偏差**：真实实验仅用Franka机器人，形态学局限（如无法处理多指手）。未见任务数量相对有限（10-15个），但已能体现趋势。

## 6. 论文的主要结论与发现

1. **OTTER显著优于现有VLA模型**：在仿真LIBERO未见任务上比OpenVLA高13%（61% vs 48%），在真实未见任务上比π0-Fast-Droid高约12% (62% vs 61%)，且在多基元任务中保持60-93%成功率，而基线在某些任务（如倒水）完全失败（0%）。
2. **冻结CLIP + 文本感知提取是关键**：消融实验表明，去掉CLIP、微调CLIP或直接传递特征都导致泛化大幅下降。OTTER通过冻结并提取任务相关特征，既保留预训练语义，又避免过拟合。
3. **性能可沿多个尺度扩展**：更大的CLIP模型（ViT-L/14）、更大的策略网络（OTTER-L）、更大的预训练数据集（OXE）均能提升OTTER性能，表明该架构可有效利用更大规模的视觉-语言预训练。

## 7. 优点

1. **方法创新性**：首次将“文本感知视觉特征提取”引入VLA，冻结VLM而非微调，思路新颖且简单有效。
2. **泛化能力突出**：在未见物体/环境上性能下降远小于现有方法，零样本迁移能力强。
3. **数据效率高**：即使在少量机器人数据（几百条演示）下仍能取得好结果，充分发挥预训练知识。
4. **可扩展性**：模型大小、CLIP大小、预训练数据量的增加均能提升性能，表明框架具有良好扩展性。
5. **实验设置全面**：覆盖仿真与真实、多基元、多任务，消融和缩放实验设计合理，结论可信。
6. **实际部署友好**：ViT-L/14可在单张NVIDIA 3090Ti上达到50Hz推理速度，满足实时控制需求。

## 8. 不足与局限

1. **形态学局限**：仅支持SE(3)变换即可参数化的末端执行器（如夹爪），无法处理多指灵巧手或其他异构机器人。
2. **任务范围有限**：未系统探索长时域任务（long-horizon）和复杂场景（如杂乱堆叠、精细操作），论文中承认这一点。
3. **CLIP的依赖**：完全依赖CLIP的零样本能力，若CLIP对某些物体/场景理解不佳，OTTER可能也受限。
4. **未见任务数量较少**：真实未见任务仅15个，每个任务10次试验，统计显著性可进一步提升。
5. **无细粒度误差分析**：未对不同失败模式（如识别错误、抓取失败、放置错误）进行分解，难以定位具体瓶颈。
6. **预训练数据规模**：OXE预训练仅用于部分模型，未完整验证在所有设置下大规模预训练的效果。

（完）
