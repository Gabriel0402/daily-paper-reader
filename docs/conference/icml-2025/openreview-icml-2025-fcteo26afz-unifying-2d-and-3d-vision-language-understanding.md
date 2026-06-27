---
title: Unifying 2D and 3D Vision-Language Understanding
title_zh: 统一2D和3D视觉语言理解
authors: "Ayush Jain, Alexander Swerdlow, Yuzhou Wang, Sergio Arnaud, Ada Martin, Alexander Sax, Franziska Meier, Katerina Fragkiadaki"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=FcTeo26AfZ"
tags: ["query:mmseg"]
score: 6.0
evidence: 统一2D/3D视觉语言理解，共享掩码解码器用于物体定位
tldr: 该论文提出UniVLG，一种统一2D和3D视觉语言理解的架构。通过共享语言条件掩码解码器和2D到3D提升策略，UniVLG能有效利用2D数据增强3D性能。在多个基准上，该方法在物体定位和视觉推理任务上超越了基于框的方法，弥合了2D和3D视觉语言之间的差距。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 934, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 1332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 1254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1776, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1769, \"height\": 2068, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1748, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 889, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 441, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 418, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 868, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 870, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 381, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 874, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 876, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 853, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 891, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1528, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1509, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1397, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1764, \"height\": 320, \"label\": \"Table\"}]"
motivation: 3D视觉语言学习受限于大规模3D数据集缺乏，需要利用2D数据。
method: 提出UniVLG统一架构，共享掩码解码器并采用2D到3D提升策略。
result: UniVLG在2D和3D视觉语言任务上均优于基线，尤其在RGB-D物体定位上表现突出。
conclusion: 该工作为2D/3D视觉语言理解提供了有效的统一方案。
---

## Abstract
Progress in 3D vision-language learning has been hindered by the scarcity of large-scale 3D datasets. We introduce UniVLG, a unified architecture for 2D and 3D vision-language understanding that bridges the gap between existing 2D-centric models and the rich 3D sensory data available in embodied systems. Our approach initializes most model weights from pre-trained 2D models and trains on both 2D and 3D vision-language data. We propose a novel language-conditioned  mask decoder shared across 2D and 3D modalities to ground objects effectively in both RGB and RGB-D images, outperforming box-based approaches. To further reduce the domain gap between 2D and 3D, we incorporate 2D-to-3D lifting strategies, enabling UniVLG to utilize 2D data to enhance 3D performance. With these innovations, our model achieves state-of-the-art performance across multiple 3D vision-language grounding tasks, demonstrating the potential of transferring advances from 2D vision-language learning to the data-constrained 3D domain. Furthermore, co-training on both 2D and 3D data enhances performance across modalities without sacrificing 2D capabilities. By removing the reliance on 3D mesh reconstruction and ground-truth object proposals, UniVLG sets a new standard for realistic, embodied-aligned evaluation. Code and additional visualizations are available at https://univlg.github.io.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：3D视觉语言学习（如3D指代定位、问答）受限于大规模3D数据集稀缺且标注昂贵；而2D视觉语言模型虽已成熟，但无法直接利用机器人等具身系统常见的RGB-D传感器数据。
- **目标**：设计一个统一的2D/3D视觉语言模型，能够同时处理单目RGB图像和多视角带姿态的RGB-D图像，并利用丰富的2D数据来弥补3D数据不足。
- **意义**：摆脱对3D网格重建和地面真值物体提议的依赖，推动更接近真实具身场景的评估，弥合2D与3D视觉语言理解的鸿沟。

## 2. 方法论
### 核心思想
- 所有参数在2D和3D模态间共享，仅通过位置编码区分（2D用像素坐标，3D用XYZ坐标）。
- 利用2D-to-3D提升策略（使用单目深度估计模型MoGe预测点图）将2D图像转化为3D点图，从而与3D数据共用网络。
- 提出语言条件掩码解码器，通过点积生成分割掩码，取代传统的框解码或依赖提议的两阶段方法。

### 关键技术细节
1. **视觉编码器**：DINOv2 ViT（冻结/微调皆可），提取多尺度特征，随后叠加3D相对注意力层（k-NN注意力+相对位置编码），跨多视图融合信息。
2. **语言编码器**：JinaCLIP（支持长文本），生成文本token。
3. **语言条件掩码解码器**（以Mask2Former为基础，关键改进）：
   - 初始化M个可学习对象查询，与文本token拼接。
   - 交替进行**掩码交叉注意力**（仅关注上一轮预测掩码内的特征）和**自注意力**，更新查询和文本。
   - 同时使用**视觉特征更新**：视觉token也通过交叉注意力从更新后的查询和文本中吸收信息（此设计对3D指代定位至关重要）。
   - 最终通过对象查询与视觉特征的**点积**得到掩码logits，再经sigmoid和阈值得到分割掩码。
4. **辅助损失**：
   - 掩码损失：BCE + Dice（匈牙利匹配）。
   - 文本跨度损失：预测哪个文本token对应哪个对象查询。
   - 框损失（新提出）：从预测掩码计算包围框，用L1+GIoU监督，解决掩码包含离群点或多个实例问题。
   - 文本生成损失（用于问答任务）：使用T5解码器自回归生成答案。
5. **2D-to-3D提升**：训练时有50%概率将2D图像通过MoGe提升为3D点图，使得2D数据也能经过3D注意力层；测试时2D图像保留原始2D空间以免引入噪声。

### 算法流程（文字说明）
1. 输入：语言查询 + (a) 多视角RGB-D图像序列，或 (b) 单张RGB图像（可选提升为3D点图）。
2. 视觉编码器提取特征，3D相对注意力融合多视图。
3. 语言编码器生成文本token。
4. 解码器迭代更新对象查询和视觉特征（共N层）。
5. 对象查询与视觉特征点积得到掩码。
6. 对匹配的查询输出文本跨度或生成答案（QA任务）。

## 3. 实验设计
### 数据集与Benchmark
- **3D指代定位**：ScanRefer、SR3D、NR3D（基于ScanNet场景）。
- **2D指代定位**：RefCOCO、RefCOCO+、RefCOCOg。
- **3D问答**：ScanQA、SQA3D。
- **3D实例分割**：ScanNet200、Matterport3D。
- **域外泛化**：L3DD（含ScanNet++、HM3D、ARKitScenes等）。
- **模拟泛化测试**：AI2-THOR（2D监督类→3D测试）。

### 对比方法
- 3D-VisTA、PQ3D、BUTD-DETR、ODIN、LLaVA-3D、3D-LLM、NaviLLM等。
- 在传感器点云（原始RGB-D反投影）和网格点云两种输入下对比。

### 评估指标
- 指代定位：Top-1准确率，基于IoU阈值（0.25/0.5/0.75），分为GT（使用真实提议）和Det（无提议）设置。
- 问答：精确匹配（EM@1）及其他文本指标。
- 实例分割：mAP、mAP25。

## 4. 资源与算力
- **GPU型号与数量**：32块A100 80G GPU，数据并行，有效批大小64。
- **模型规模**：108M可训练参数 + 冻结的220M文本编码器（JinaCLIP）+ 304M图像编码器（DINOv2）。若使用Swin骨干则为88M。
- **训练时长**：文中未明确训练总时间，但提到一次前向推理（90帧场景）约1050ms，显存约15GB。

## 5. 实验数量与充分性
- **实验组数**：约6个主要实验表（表1-8），外加附录中多个补充表（表9-17）。
- **消融实验**：共7组关键消融（表5-8），涵盖：
  - 掩码解码 vs 框解码
  - 是否更新视觉特征
  - 是否使用预训练2D权重
  - 是否使用框损失
  - 参数化 vs 非参数化查询
  - 2D训练策略（无提升 vs 提升）
  - 视觉骨干（Swin vs DINOv2）
  - 微调 vs 冻结骨干
- **公平性**：在基准测试中，统一采用传感器点云输入（更真实），并重新训练已有方法（如3D-VisTA、BUTD-DETR）以确保公平；对比方法多数未提供GT提议。
- **客观性**：覆盖多个数据集、多种设置（Det/GT、域内/域外），并分析常见失败模式。实验设计充分，结论可信。

## 6. 主要结论与发现
1. **UniVLG在所有不依赖GT提议的真实设置中达到SOTA**，在SR3D/NR3D/ScanRefer上显著超越先前方法（如比3D-VisTA高15-20%）。
2. **联合2D+3D训练进一步增强3D性能**，且不损害2D能力。
3. **掩码解码优于框解码**，特别是在高IoU阈值（0.75）下优势明显（+32.1%）。
4. **2D-to-3D提升策略**有效缩小模态差异，带来额外增益。
5. **视觉特征更新**（解码器中更新视觉token）对3D指代定位至关重要，而框解码不需要。
6. **预训练2D权重**（DINOv2）显著提升性能。
7. 模型对姿态噪声和深度噪声具有高度鲁棒性（优于BUTD-DETR）。

## 7. 优点
- **统一架构**：共享所有参数，无需专门为2D/3D设计不同头部，输出统一为分割掩码。
- **语言条件掩码解码器**：创新性地结合了掩码交叉注意力和视觉特征更新，优于之前的方法（如ODIN的开放词汇头）。
- **2D-to-3D提升**：利用单目深度估计将2D数据转化为3D格式，使2D数据直接参与3D训练，降低数据需求。
- **真实评估标准**：首次在传感器点云（而非网格）上评估3D指代定位，并移除对GT提议的依赖，更接近实际机器人场景。
- **大量消融**：系统验证了每个设计选择的有效性，为后续研究提供指导。

## 8. 不足与局限
- **掩码预测的固有问题**：仍存在包含离群点、多个实例被合并为一个掩码的情况（尽管框损失部分缓解，但未完全解决）。
- **2D-to-3D泛化测试**：在AI2-THOR模拟器中，模型在仅有2D监督的类别上泛化到3D时，性能（53.8%）远低于完全3D监督的上界（84.2%），说明2D-to-3D迁移仍有提升空间。
- **2D数据规模有限**：当前仅使用RefCOCO/+/g等少量2D数据，未像先进2D VLM那样大规模扩展，可能限制3D性能的进一步提升。
- **静态场景假设**：模型针对静态3D场景设计，未考虑动态环境（如人体移动、物体交互）。
- **计算资源需求较高**：使用32块A100训练，且推理需要15GB显存，对资源要求较高。
- **缺少与更多最新方法的比较**：例如未与CoT3DRef、MiKASA等文献在一致设置下详细对比（附录中仅简单提及）。

（完）
