---
title: Towards Learning to Complete Anything in Lidar
title_zh: 迈向在激光雷达中学习完成任何形状
authors: "Ayça Takmaz, Cristiano Saltori, Neehar Peri, Tim Meinhardt, Riccardo de Lutio, Laura Leal-Taixé, Aljosa Osep"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vWPzKn6usZ"
tags: ["query:mmseg"]
score: 6.0
evidence: 利用多模态时序上下文进行零样本激光雷达形状补全
tldr: 现有激光雷达形状补全方法受限于封闭词汇。该文提出CAL，从多模态传感器序列中挖掘部分形状，蒸馏为仅激光雷达的补全模型，实现零样本开放集补全。实验表明模型能从多部分观测推断完整形状，在自动驾驶等场景具有应用价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1652, \"height\": 946, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 838, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1514, \"height\": 850, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 815, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1771, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1311, \"height\": 2042, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vwpzkn6usz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1516, \"height\": 842, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1765, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1077, \"height\": 1938, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1249, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1247, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1245, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1244, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1245, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1767, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vwpzkn6usz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1720, \"height\": 849, \"label\": \"Table\"}]"
motivation: 当前LiDAR形状补全局限于已知类别，无法处理开放场景。
method: 利用时序多模态数据挖掘对象部分形状，通过知识蒸馏构建LiDAR-only模型。
result: 零样本补全性能优异，能处理未见过的类别。
conclusion: 零样本补全范式扩展了LiDAR感知在开放世界的适用性。
---

## Abstract
We propose CAL (Complete Anything in Lidar) for Lidar-based shape-completion in-the-wild. This is closely related to Lidar-based semantic/panoptic scene completion. However, contemporary methods can only complete and recognize objects from a closed vocabulary labeled in existing Lidar datasets. Different to that, our zero-shot approach leverages the temporal context from multi-modal sensor sequences to mine object shapes and semantic features of observed objects. These are then distilled into a Lidar-only instance-level completion and recognition model. Although we only mine partial shape completions, we find that our distilled model learns to infer full object shapes from multiple such partial observations across the dataset. We show that our model can be prompted on standard benchmarks for Semantic and Panoptic Scene Completion, localize objects as (amodal) 3D bounding boxes, and recognize objects beyond fixed class vocabularies.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有激光雷达（LiDAR）形状补全方法只能处理封闭词汇表中的已知类别（通常约20个类），无法在开放场景中识别和补全任意物体。例如，Semantic Scene Completion (SSC) 和 Panoptic Scene Completion (PSC) 模型高度依赖人工标注的LiDAR数据集，泛化能力差。
- **研究动机**：希望利用未标注的LiDAR序列中的时序上下文，结合多模态传感器（RGB相机+LiDAR）和视觉基础模型（如SAM、CLIP）自动挖掘对象形状先验和语义特征，实现真正的“零样本”任意物体补全。
- **整体含义**：首次提出**零样本LiDAR全景场景补全**方法，允许在测试时通过自然语言提示完成任意类别的物体检测、语义/全景场景补全，打破了固定类标的限制，具有重要的实用价值（如自动驾驶、机器人导航）。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用未标注LiDAR序列的时序多模态数据，从RGB视频中通过2D基础模型定位和追踪物体，将其投影到LiDAR空间并时序聚合得到部分形状完成，再通过蒸馏训练一个仅使用LiDAR输入的实例级补全模型，实现零样本推理。
- **关键技术细节**：
  - **伪标签引擎（Pseudo-Labeling Engine）**：
    1. **视频物体定位**：用SAM和SAM2对RGB视频进行物体分割和追踪，获得时空一致的masklet。
    2. **语义特征聚合**：对每个masklet计算CLIP特征并时序平均得到语义嵌入。
    3. **提升和细化**：将2D mask反投影到LiDAR帧，经过DBSCAN修正投影伪影。
    4. **时序聚合**：利用自车位姿将多帧3D mask聚合到参考坐标系，得到密集的实例级占用网格（部分补全），同时聚合360° LiDAR点云获得二进制占用信号。
    5. **CRF细化**：用条件随机场（DenseCRF）将实例标签传播到未标注的占用区域，提高标签覆盖率。
  - **模型架构（CAL）**：基于稀疏-生成式3D U-Net（类似PaSCo）和Transformer实例解码器。
    - **生成式解码器**：多尺度预测场景级二进制占用和每个体素的CLIP原型类别（通过K-means聚类获得伪原型，辅助学习语义先验）。
    - **Transformer解码器**：对每个查询预测类无关的实例掩码、物体性得分，并回归一个CLIP特征向量。
  - **零样本推理**：在测试时，将语义词汇（如“car”、“tree”）编码为文本特征，与预测的实例CLIP特征计算余弦相似度，分配类别。
- **训练损失**：包括二进制占用损失（L_occ）、原型分类损失（L_prot，交叉熵+Lovász）、掩码损失（L_mask，二进制交叉熵+Dice）和CLIP蒸馏损失（L_CLIP，余弦相似度）；忽略无伪标签区域。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - SemanticKITTI（语义、实例标注，20类，其中8个thing类）
  - SSCBench-KITTI360（19类，6个thing类）
  - 注：仅用于评估，训练时模型从未见过真实标签，只用自动生成的伪标签。
- **基准任务**：
  - Semantic Scene Completion (SSC) — 指标：mean IoU (mIoU)
  - Panoptic Scene Completion (PSC) — 指标：Panoptic Quality (PQ†, PQ, SQ, RQ)，遵循Cao et al. (2024)的修改版（对stuff类去掉IoU≥0.5限制）
- **对比方法**：
  - **全监督基线**：LMSCNet+MaskPLS, JS3CNet+MaskPLS, SCPNet+MaskPLS, PaSCo (单模型M=1和集成版)。
  - **零样本基线**：LODE+SAL (LODE完成LiDAR点云，SAL进行零样本全景分割)，LiDiff+SAL。这些基线也使用无语义标签训练的补全模型。
- **消融与验证**：
  - 伪标签引擎消融：前向/后向传播帧数、步长、CRF细化效果、标签覆盖率。
  - CAL模型消融：二进制占用头使用部分/全覆盖、原型头S、额外二进制头Bs、CLIP原型数量。
  - 语义oracle (SO) 对比：将预测掩码通过体素多数投票分配真实语义类别，去除识别误差，单独评估补全质量。

## 4. 资源与算力

- **文中明确说明**：CAL模型训练使用**8块NVIDIA A100 GPU**，批量大小8（每GPU 1个样本），学习率0.0001，训练**50个epoch**。模型总共1.18亿参数，其中Transformer预测器820万参数。
- 伪标签生成的计算量：视频物体定位（SAM2）较慢，每个伪标签样本需数分钟。文中提供了时间效率对比（见表9的“Time tk”列），T_fw=32, T_bw=8, w=2时需约527个时间单位（未定义具体单位）。其他参数调整会影响时间。
- 总体算力需求中等但伪标签生成环节耗时，可进一步优化。

## 5. 实验数量与充分性

- **实验数量**：丰富。包括：
  - 主表（表1、表14）：在两个数据集上与全监督方法对比。
  - 零样本基线对比（表2）：与LODE+SAL、LiDiff+SAL对比。
  - CRF细化消融（表3）：有/无CRF的伪标签质量和模型性能。
  - 帧数/步长消融（表4、表9）：伪标签质量随T_fw、T_bw、w的变化。
  - 覆盖率分析（表5）：伪标签和二进制占用覆盖率。
  - CAL模型组件消融（表6）：B_pc o、B_fc o、S、Bs的影响。
  - CLIP原型数量消融（表7）：C=1,6,18,50,100,500。
  - 伪标签 vs 模型预测差距分析。
  - 每类性能（表15）。
  - 伪标签质量与CRF、短帧数的组合（表11、12、13）。
- **充分性**：实验设计全面，涵盖了伪标签生成策略、模型架构选择、超参数敏感性和不同测试场景。零样本基线对比客观（未用任何标注数据）。但语义oracle实验与全监督方法对比时，公平性存在一定差异（全监督方法也使用相同GT标注，但CAL使用伪标签）。作者指出“全监督基线有天然优势”，评价比较客观。
- **潜在的不足**：缺乏与更多最新零样本3D检测/补全方法的对比（如直接使用预训练3D基础模型），但考虑到问题定义新颖（零样本LiDAR全景场景补全），现有基线已足够。

## 6. 论文的主要结论与发现

- **核心结论**：结合多模态时序上下文和2D视觉基础模型，可以从无标注LiDAR序列中自动挖掘出有效的物体形状先验和语义信息，进而训练出零样本全景场景补全模型。
- **主要发现**：
  - 即使只有部分补全的伪标签，模型也能学习从多个部分观测推断完整物体形状。
  - CRF细化显著提升伪标签质量和模型性能（表3，SO下PQ†从12.78提升到25.90）。
  - CLIP原型（S头）对学习类别无关的形状先验至关重要（表6，引入S后PQ†从4.81提升到16.08）。
  - CAL在零样本设置下能达到全监督方法PaSCo约50%的PQ†（SemanticKITTI上13.12 vs 26.49），在语义oracle下达到约65%，表明主要瓶颈在零样本识别而非几何补全。
  - 零样本识别性能受限于CLIP的通用能力，对小众类（如行人、骑车人）表现差。

## 7. 优点

- **创新性**：首个零样本LiDAR全景场景补全方法，突破了封闭词汇表的限制，提出了完整的数据驱动范式：自动伪标签 → 蒸馏 → 零样本推理。
- **实用性**：无需人工标注3D数据，可扩展至任意类别；仅需测试时提供文本提示，灵活适配不同任务（SSC、PSC、amodal 3D检测）。
- **系统性**：方法设计考虑周全，如处理动态物体、CRF提高覆盖率、多尺度生成式解码器、CLIP原型辅助学习等。
- **实验充分**：在两个主流数据集上进行了大量消融和分析，证明了各个组件的贡献。
- **开源友好**：代码和训练细节公开（论文附有开源声明）。

## 8. 不足与局限

- **伪标签质量有限**：
  - 依赖2D基础模型（SAM/SAM2）的鲁棒性，在视角变化大、遮挡严重时可能出现追踪失败（ID switch），导致标签噪声。
  - 标签覆盖率低（SemanticKITTI上70%，KITTI-360上50%），虽经CRF改善但仍不完美。
- **计算成本高**：伪标签生成过程耗时长（每条需数分钟），难以大规模快速扩展。
- **零样本识别性能**：远低于全监督方法，主要瓶颈在CLIP跨模态特征的对齐能力，对小众、细粒度类别识别差。
- **动态物体处理**：对语义KITTI未进行动态物体去除，导致运动物体部分观测不完整；对KITTI-360依赖预提供的3D轨迹去除动态物体，限制了通用性。
- **场景依赖**：方法依赖RGB摄像头输入来获得伪标签，但推理时仅用LiDAR，隐式假设多模态传感器配置固定；若摄像头视野或标定发生变化，伪标签生成会受影响。
- **未见类别限制**：虽然理论上可处理任意类别，但实际性能受CLIP预训练类别分布影响，长尾类别效果不佳。
- **实验偏差风险**：仅在城市驾驶场景（KITTI系列）评估，未验证在室内或非结构化环境的表现。

（完）
