---
title: "FeatSharp: Your Vision Model Features, Sharper"
title_zh: FeatSharp：让你的视觉模型特征更锐利
authors: "Mike Ranzinger, Greg Heinrich, Pavlo Molchanov, Bryan Catanzaro, Andrew Tao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=lioemOcq3H"
tags: ["query:mmseg"]
score: 7.0
evidence: 增强视觉基础模型特征以服务于分割等任务
tldr: 当前ViT编码器（如CLIP）分辨率固定且低，限制了下游任务。本文提出FeatSharp方法，以低成本对低分辨率编码器特征进行上采样，同时捕获高频细节。实验证明FeatSharp在语义分割、目标检测、深度估计和VLM任务中均带来性能提升，是一种即插即用的特征增强工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 843, \"height\": 1438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 477, \"height\": 1088, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1674, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 534, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 847, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1752, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1777, \"height\": 1267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1777, \"height\": 1125, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1757, \"height\": 1214, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1288, \"height\": 1086, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1760, \"height\": 2126, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1752, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1215, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 633, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1768, \"height\": 1624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lioemocq3h/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 719, \"height\": 1258, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 680, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1289, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1754, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 885, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1516, \"height\": 683, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1763, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1307, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1265, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 691, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1331, \"height\": 575, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lioemocq3h/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1767, \"height\": 505, \"label\": \"Table\"}]"
motivation: 视觉编码器分辨率低且固定，影响下游感知和多模态任务性能。
method: 提出FeatSharp，通过学习低分辨率特征到高分辨率细节的映射，实现高效上采样。
result: 在多个视觉和VLM任务上，FeatSharp显著提升准确率。
conclusion: 低成本的特征上采样是提升视觉模型泛化能力的有效手段。
---

## Abstract
The feature maps of vision encoders are fundamental to myriad modern AI tasks, ranging from core perception algorithms (e.g. semantic segmentation, object detection, depth perception, etc.) to modern multimodal understanding in vision-language models (VLMs). Currently, in computer vision, the frontier of general purpose vision backbones is Vision Transformers (ViT), typically trained using contrastive loss (e.g. CLIP). A key problem with most off-the-shelf ViTs, particularly CLIP, is that these models are inflexibly low resolution. Most run at $224 \times 224$px, while the "high-resolution" versions are around $378-448$px, but still inflexible. We introduce a novel method to coherently and cheaply upsample the feature maps of low-resolution vision encoders while picking up on fine-grained details that would otherwise be lost due to resolution. We demonstrate the effectiveness of this approach on core perception tasks as well as within agglomerative model training using RADIO as a way of providing richer targets for distillation. Code available at https://github.com/NVlabs/FeatSharp

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：当前主流的视觉基础模型（VFM）如 ViT、CLIP 系列，通常工作在低分辨率（224×224 或 378–448 像素），且对输入分辨率不灵活，限制了细粒度特征的提取。高分辨率下 Transformer 的 O(n²) 计算成本高昂，且许多模型（如 CLIP）不能很好地对位置编码进行插值。
- **背景**：视觉特征是许多下游任务（语义分割、目标检测、深度估计、VLM）的核心。现有特征上采样方法如 FeatUp 的 JBU 方法虽然能保留边缘，但物体内部特征模糊，且无法引入原分辨率不可见的小细节。VLM 中使用的图像平铺（tiling）策略虽能提供细节，但存在平铺边界的不连续性。
- **整体含义**：本文提出一种低成本、高质量的特征上采样方法 FeatSharp，在保持原模型特征空间的同时，为低分辨率编码器“锐化”特征，提升下游任务性能，并可用于聚合模型（如 RADIO）训练时的教师特征增强。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：结合 FeatUp 的联合双边上采样（JBU）与基于平铺（tiling）的局部细节信息，通过一个轻量级的注意力融合模块（FeatSharp module）将两种上采样结果融合，得到细节更丰富、一致性更高的高分辨率特征图。
- **关键技术细节**：
  - **基础上采样**：使用 FeatUp 的 JBU 堆栈（可分解为质因子上采样）从低分辨率特征和原始图像像素上采样，得到初始高分辨率特征。
  - **平铺引导**：将输入图像分割为多个重叠/不重叠的块（例如 2×2 或 4×4），每个块独立通过编码器得到特征，再拼接成高分辨率特征图。这能捕获原分辨率下不可见的小目标细节。
  - **去偏置（De-bias）**：受 ViT-Denoiser 启发，为每个编码器学习一个可加性的位置偏置缓冲器，用于消除固定噪声模式，提高多视图一致性。
  - **FeatSharp 模块**：将 JBU 上采样特征与平铺特征沿通道拼接，送入一个包含局部窗口注意力（Local MHSA）和 SwiGLU MLP 的 Transformer 块，输出取前一半通道作为最终精炼特征。这样模型可通过注意力机制在局部融合两种信息。
  - **训练目标**：基于多视图一致性损失（MSE），与 FeatUp 类似，但不使用总变分（TV）和条件随机场（CRF）损失。
  - **特征归一化**：使用 PHI-S 标准化（基于统计数据）替代 LayerNorm，保留原始特征分布，便于后续使用。
- **公式与流程**：见论文式 (1)-(5) 及图 2、3、4，大致流程为：输入图像 → 低分辨率编码器 → 得到低分辨率特征 → 同时进行 JBU 上采样和平铺编码 → 拼接 → 注意力混合 → 输出高分辨率特征。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **训练**：FeatSharp/FeatUp 模型在 SA-1B（Segment Anything 1B 数据集）上训练。
  - **评估**：ADE20K 语义分割、COCO 2017 目标检测（使用 Detectron2 + ViTDet + DINO）、NYUDv2 多任务、Probe3D 深度/对应关系、VILA 视觉语言任务。此外，在 RADIO 训练中使用 DFN CLIP 和 SigLIP 作为教师模型，评估 RADIO 最终性能。
- **基准**：与多种上采样方法对比：
  - 双线性插值（Bilinear）
  - FeatUp（JBU 版本）
  - SAPA、ReSFU（其他特征上采样方法）
  - 平铺直接拼接（Tile）、S2 策略（低分辨率+平铺）
  - 原模型直接在高分辨率下运行（Baseline 1×/2× Input）
- **对比方法**：在多个视觉编码器上测试：DFN CLIP、SigLIP、DINOv2-L、PaliGemma、RADIOv2.5-L、SAM-H、ViT 等。
- **评价指标**：多视图一致性 fidelity、mIoU、AP（目标检测）、深度 RMSE、表面法线误差、VLM 任务准确率等。

## 4. 资源与算力

- **论文明确说明**：
  - FeatSharp/FeatUp 训练：8 个 GPU，批量大小每 GPU 4，总 32；短训练 3000 步，长训练 9000 步（约 3 倍）。使用 SA-1B 数据集。
  - RADIO 训练：参考 Heinrich et al. (2024) 的配置，具体 GPU 数量未在本文中重复，但应是大规模分布式训练（推测 8×A100 或更多）。
  - 推理时 FeatSharp 需要额外调用编码器（每张图约 1 + tiles² 次推理），但比直接全分辨率推理更高效（线性 vs 二次复杂度），实验证明约在 3.3× 上采样因子以上开始加速。
- **未明确说明**：完整训练总 GPU 时，单次训练具体天数。

## 5. 实验数量与充分性

- **实验数量**：非常丰富，包括：
  - 主实验：7 种视觉编码器的 2×/3×/4× 上采样 fidelity 测量（图 6）。
  - 语义分割：6 种编码器 × 3 种上采样因子 × 2 种输入尺寸，每个设置多次运行（图 7）。
  - 目标检测：2 种编码器（RADIOv2.5-L, SigLIP2）× 多种上采样方法（表 1）。
  - 聚合模型（RADIO）：7 种基准任务（分类、密集预测、3D、检索、Pascal Context、NYUDv2、VILA），对比 5 种上采样策略（表 2，附录多个表格）。
  - 消融实验：去偏置模块效果（表 7），FeatSharp 架构选择（输入特征组合、窗口大小、注意力/MLP 必要性）（表 8–10，图 13）。
  - 其他：Probe3D（表 12–13），NYUDv2 多任务（表 14）。
- **充分性与公平性**：实验设计较为全面，覆盖了多种编码器和任务类型；对比方法包括核心基线（双线性、FeatUp、平铺、S2），且使用相同训练框架和超参数。但部分实验仅报告了一次运行结果，未给出多次运行方差（除图 7 外）。此外，FeatSharp 在训练时使用了更长的步数和更大批量，与 FeatUp 原设置不完全一致，论文中已说明调整。

## 6. 主要结论与发现

- FeatSharp 在所有测试任务上均显著优于 FeatUp 和双线性上采样，尤其在细节保留和多视图一致性上。
- 在语义分割中，FeatSharp 在多数编码器上达到最佳 mIoU，甚至在 RADIO 上比原 2× 输入还高 +1.66 mIoU，同时速度快 57%。
- 在 COCO 目标检测中，FeatSharp 在小物体 AP 上有大幅提升（+6.39 相对于基线），证明平铺帮助捕获小目标。
- 用于 RADIO 训练时，使用 FeatSharp 将低分辨率教师特征转化为高分辨率，训练出的 RADIO 在整体 MTL 增益上获得 +0.39%，超越当前 SOTA（RADIOv2.5-L）。
- 去偏置模块一致提升 fidelity，且可以移除固定噪声模式。
- FeatSharp 的计算复杂度优于直接全分辨率推理，当上采样因子 >3.3 时开始加速。

## 7. 优点：方法或实验设计的亮点

- **创新性**：巧妙结合 JBU 的边缘保留和平铺的细节注入，并通过轻量局部注意力融合，实现高质量上采样。
- **实用性强**：直接适用于现有多种预训练编码器（CLIP、DINOv2、SAM、RADIO 等），无需修改模型结构，可即插即用。
- **实验充分**：覆盖多个代表性编码器和多种下游任务，包含显式消融和组件分析。
- **公平比较**：与 FeatUp 使用相同训练框架，并统一特征归一化（PHI-S）。
- **开源**：代码已开源，可复现。

## 8. 不足与局限

- **计算开销**：FeatSharp 仍需要额外多次编码器推理（1 + tile² 次），在小上采样因子（如 2×）下可能比直接全分辨率推理更慢（仅 4 个 tile 时优于全分辨率，但比 FeatUp 更慢）。
- **对模型依赖性**：平铺效果依赖于编码器对局部上下文的鲁棒性，某些模型（如 DFN CLIP）在平铺时可能出现特征偏移（图 8 中的颜色跳跃）。
- **训练复杂度**：需要为每个编码器训练专门的 FeatSharp 模型，增加了部署成本。
- **未测试所有任务**：未在视频、点云、医疗图像等更多模态或任务上验证。
- **无理论保证**：没有对多视图一致性与实际下游性能之间的关系给出理论证明，仅凭经验评估。
- **局限性说明**：论文中只展示了整数倍上采样（2×,3×,4×），非整数倍上采样的效果未验证。
- **公平性细节**：FeatSharp 使用的训练步数是 FeatUp 的 3 倍（9000 vs 3000），虽然消融显示长训练有益，但可能部分优势来自更多迭代而非架构本身。论文在附录中对此进行了讨论，但未做控制变量对比。

（完）
