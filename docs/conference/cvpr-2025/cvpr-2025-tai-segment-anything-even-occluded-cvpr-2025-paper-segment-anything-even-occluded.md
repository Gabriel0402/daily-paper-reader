---
title: "Segment Anything, Even Occluded"
title_zh: 分割一切，包括遮挡
authors: "Tai, Wei-En, Shih, Yu-Lin, Sun, Cheng, Wang, Yu-Chiang Frank, Chen, Hwann-Tzong"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Tai_Segment_Anything_Even_Occluded_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 将SAM应用于amodal实例分割
tldr: 现有amodal分割需要联合训练检测器和分割网络，缺乏灵活性。本文提出SAMEO，将Segment Anything Model（SAM）改造为通用掩码解码器，与多种前端检测器配合实现遮挡物体分割，并构建大规模数据集Amodal-LVIS，显著提升遮挡场景下的分割性能。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 810, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1791, \"height\": 2118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 864, \"height\": 374, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1659, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1732, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1529, \"height\": 647, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-tai-segment-anything-even-occluded-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 747, \"height\": 281, \"label\": \"Table\"}]"
motivation: 现有amodal实例分割方法缺乏灵活性，无法利用预训练检测器。
method: 将SAM作为掩码解码器，与前端检测器解耦，通过提示调整适应遮挡。
result: 在COCO及Amodal-LVIS数据集上，遮挡物体分割性能大幅提升。
conclusion: SAMEO为amodal分割提供了灵活高效的框架。
---

## Abstract
Amodal instance segmentation, which aims to detect and segment both visible and invisible parts of objects in images, plays a crucial role in various applications, including autonomous driving, robotic manipulation, and scene understanding. While existing methods require training both front-end detectors and mask decoders jointly, this approach lacks flexibility and fails to leverage the strengths of pre-existing modal detectors. To address this limitation, we propose SAMEO, a novel framework that adapts the Segment Anything Model (SAM) as a versatile mask decoder capable of interfacing with various front-end detectors to enable mask prediction even for partially occluded objects. Acknowledging the constraints of limited amodal segmentation datasets, we introduce Amodal-LVIS, a large-scale synthetic dataset comprising 300K images derived from the modal LVIS and LVVIS datasets. This dataset significantly expands the training data available for amodal segmentation research. Our experimental results demonstrate that our approach, when trained on the newly extended dataset, including Amodal-LVIS, achieves remarkable zero-shot performance on both COCOA-cls and D2SA benchmarks, highlighting its potential for generalization to unseen scenarios.

---

## 论文详细总结（自动生成）

# 论文《Segment Anything, Even Occluded》详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题焦点**：**Amodal实例分割**（amodal instance segmentation）旨在同时检测并分割图像中物体的可见部分和不可见（被遮挡）部分，在自动驾驶、机器人操作、场景理解等应用中至关重要。
- **现有局限**：现有方法通常需要将前端检测器（object detector）和后端掩码解码器（mask decoder）联合训练，导致缺乏灵活性，无法充分利用已预训练好的模态检测器（modal detectors）。
- **核心动机**：如何将强大的基础分割模型（如Segment Anything Model, SAM）改造为通用的掩码解码器，使其能够与多种前端检测器（包括模态检测器和非模态检测器）配合，实现对部分遮挡物体的完整形状预测，同时保持零样本泛化能力。
- **数据瓶颈**：现有amodal数据集规模小、标注质量参差不齐、含有大量无意义物体（如墙壁、地板）。因此本文还构建了大规模合成数据集Amodal-LVIS。

## 2. 方法论：核心思想与关键技术细节

### 核心思想：SAMEO（Segment Anything Even under Occlusion）
- 将EfficientSAM（SAM的高效变体）作为基础架构，仅微调其**掩码解码器**，保持图像编码器和提示编码器权重冻结。
- 输入：**图像** + **边界框提示**（可以是模态框或amodal框，训练时以等概率随机选择）。
- 输出：**amodal掩码** + **估计的IoU**（预测置信度）。
- 通过特殊训练使模型能够处理两种提示类型，从而实现与任何前端检测器（模态或amodal）的解耦集成。

### 关键技术细节
- **模型架构**：轻量级图像编码器（ViT变体）+ 变换器提示编码器 + 双交叉注意力掩码解码器。
- **训练损失**：Dice损失 + Focal损失（γ=2）+ L1损失用于IoU估计（λ=0.05）。
- **推理流程**：前端检测器输出边界框作为提示，SAMEO生成对应的amodal掩码，并使用预测的IoU对前端置信度进行加权（式6：\(\hat{\rho}_{ref} = \hat{\rho}_{front} \times \hat{\rho}_{ours}\)）。
- **Amodal-LVIS数据集生成**：
  - 从LVIS和LVVIS中收集完整无遮挡物体（利用预训练SAMEO生成伪标签与可见掩码对比筛选）。
  - 合成遮挡：将随机挑选的完整物体配对，控制位置和遮挡率生成逼真遮挡。
  - 双标注机制：同时保留合成遮挡后的图像和原始无遮挡图像（各占50%），防止模型产生“总是输出遮挡”的偏差。

## 3. 实验设计

### 使用数据集
- **训练数据**：组合并清洗后的现有amodal数据集（COCOA、COCOA-cls、KINS、KITTI-360-APS、D2SA、MUVA、WALT、DYCE、MP3D-amodal、pix2gestalt）加上新建的**Amodal-LVIS**（约300k图像，399k实例）。总计约1M图像、2M实例。
- **测试数据（零样本评估）**：COCOA-cls（10,562实例）、D2SA（28,720实例）。MUVA用于有监督对比。
- **基准（Benchmark）**：COCOA-cls、D2SA、MUVA。

### 对比方法
- **主要基线**：AISFormer（现有SOTA amodal实例分割方法）。
- **模态前端检测器**：RTMDet、ConvNeXt-V2、ViTDet、CO-DETR、DINO、RetinaNet等。
- **消融版本**：将原始EfficientSAM替换为本文SAMEO进行对比。
- **零样本设置**：SAMEO在除测试数据集外的所有训练集上训练，然后直接测试COCOA-cls和D2SA。

### 评估指标
- **类无关的AP**（AP, AP50, AP75）和**AR**。

## 4. 资源与算力
- **文中明确说明**：训练使用NVIDIA Tesla V100/A100 GPU。
- 具体迭代数：
  - 有监督训练（每个数据集单独）：COCOA-cls 1,440次迭代，D2SA 2,340次迭代，MUVA 22,500次迭代。
  - 零样本训练（混合数据集）：batch size=32，40,000次迭代。
- **未说明**：具体GPU数量、显存大小、总训练耗时。仅强调使用V100/A100，未提及多个GPU并行等细节。

## 5. 实验数量与充分性

### 实验组数
| 实验类型 | 组数/对比 |
|---------|----------|
| 有监督对比（表2） | 3个数据集 × 多种前端组合 ≈ 15+组 |
| 零样本评估（表3） | 2个数据集 × 多种前端组合 ≈ 14组 |
| 消融实验（表4、5） | IoU预测消融、提示类型消融、数据集组成消融（图6） |
| 定性对比（图5） | COCOA-cls和MUVA的多张示例对比 |

### 充分性与公平性
- **充分**：覆盖了主流amodal数据集（COCOA-cls、D2SA、MUVA），对比方法包括SOTA（AISFormer）和多种模态前端；进行了零样本评估，验证泛化能力。
- **客观**：所有指标计算时均保持类无关AP/AR，并统一了置信度精炼策略。基线的复现使用相同设置。
- **公平**：零样本设置中，训练集排除了测试数据集；消融实验验证了各设计组件的贡献（IoU预测、提示类型、数据集平衡）。

## 6. 主要结论与发现
- **SAMEO显著超越现有SOTA**：在有监督设置下，AP提升约10-20个点；零样本设置在COCOA-cls上AP最高达54.4（比AISFormer高13.8），在D2SA上达75.0（高8.7）。
- **灵活解耦**：SAMEO可无缝替换任何前端检测器的掩码解码部分，且无论前端输出模态还是amodal框，都能生成高质量amodal掩码。
- **Amodal-LVIS数据有效性**：引入双标注机制（遮挡/非遮挡各半）消除了模型对遮挡的过度预测偏差，显著提升鲁棒性。
- **IoU预测改进排序**：使用SAMEO预测的IoU对前端置信度精炼后，AP进一步提升（表4）。

## 7. 优点

### 方法亮点
1. **模块化解耦**：将amodal分割中的掩码解码与检测分离，允许复用任意成熟的前端检测器，大幅提升灵活性和实用性。
2. **基础模型适配**：成功将SAM（EfficientSAM）从模态分割扩展至amodal分割，保留其零样本能力。
3. **数据工程创新**：
   - 系统清洗和整合现有amodal数据集，解决质量问题（过滤墙体/地板、极小物体、不自然遮挡）。
   - 构建Amodal-LVIS，提供大规模配对数据（遮挡/无遮挡），且设计双标注防止偏差。

### 实验亮点
- **零样本性能突出**：在未训练过的数据集上达到甚至超越有监督方法，验证了框架的泛化能力。
- **全面的消融**：从损失函数、提示类型、数据集组成多角度分析，结论可靠。

## 8. 不足与局限

### 实验覆盖与偏差风险
- **类无关评估**：论文采用类无关AP/AR，未报告按类别划分的性能，无法评估对罕见类别或特定形状物体的能力。
- **测试数据集有限**：零样本评估仅限COCOA-cls和D2SA（均为室内/城市场景），缺乏野外复杂场景（如遮挡严重、杂乱背景）的评估。
- **合成数据集Amodal-LVIS**：虽然规模大，但遮挡是合成的，可能不完全代表真实遮挡分布；且仅包含单实例对（每图一个实例），未处理多实例复杂交互。

### 算法局限
- **依赖前端检测器**：SAMEO无法自主检测物体，需依赖已有检测框；若前端漏检，则无法产生掩码。论文未讨论这种情况。
- **训练收敛速度未知**：仅给出迭代次数，未提供收敛曲线或早停等分析。
- **计算资源描述模糊**：未明确GPU数量与型号细节，不利于复现和比较效率。

### 应用限制
- **实时性**：基于EfficientSAM，但未报告推理速度（FPS），在自动驾驶等实时场景中可能受限。
- **遮挡程度鲁棒性**：当遮挡率极高（>90%）或物体极小，模型可能难以准确恢复完整形状，论文未分析此类极端情况。

（完）
