---
title: Unlocking the Power of SAM 2 for Few-Shot Segmentation
title_zh: 释放SAM2在少样本分割中的潜力
authors: "Qianxiong Xu, Lanyun Zhu, Xuanyi Liu, Guosheng Lin, Cheng Long, Ziyue Li, Rui Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TQtUTC3eKv"
tags: ["query:mmseg"]
score: 9.0
evidence: SAM2用于少样本分割
tldr: 本文针对SAM2在少样本分割（FSS）中支持帧与查询帧目标身份不一致的问题，提出伪提示生成器，将支持前景特征编码为与查询匹配的伪提示。在多个FSS基准上取得领先性能，展示了将视频分割基础模型有效迁移至图像分割任务的新路径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 948, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1509, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1598, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1760, \"height\": 860, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 769, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1417, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1763, \"height\": 871, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1763, \"height\": 872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1490, \"height\": 1009, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tqtutc3ekv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1487, \"height\": 1012, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1553, \"height\": 615, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1553, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 827, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 701, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 842, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 818, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1627, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1418, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 814, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 705, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tqtutc3ekv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 780, \"height\": 355, \"label\": \"Table\"}]"
motivation: SAM2的视频分割能力与少样本分割的匹配步骤存在身份不一致问题。
method: 设计伪提示生成器，将支持前景特征转换为与查询匹配的伪提示，实现有效匹配和融合。
result: 在多个少样本分割基准上达到最先进性能。
conclusion: 通过适配身份匹配，视频分割基础模型可成功用于少样本图像分割。
---

## Abstract
Few-Shot Segmentation (FSS) aims to learn class-agnostic segmentation on few classes to segment arbitrary classes, but at the risk of overfitting. To address this, some methods use the well-learned knowledge of foundation models (e.g., SAM) to simplify the learning process. Recently, SAM 2 has extended SAM by supporting video segmentation, whose class-agnostic matching ability is useful to FSS. A simple idea is to encode support foreground (FG) features as memory, with which query FG features are matched and fused. Unfortunately, the FG objects in different frames of SAM 2's video data are always the same identity, while those in FSS are different identities, i.e., the matching step is incompatible. Therefore, we design Pseudo Prompt Generator to encode pseudo query memory, matching with query features in a compatible way. However, the memories can never be as accurate as the real ones, i.e., they are likely to contain incomplete query FG, and some unexpected query background (BG) features, leading to wrong segmentation. Hence, we further design Iterative Memory Refinement to fuse more query FG features into the memory, and devise a Support-Calibrated Memory Attention to suppress the unexpected query BG features in memory. Extensive experiments have been conducted on PASCAL-5$^i$ and COCO-20$^i$ to validate the effectiveness of our design, e.g., the 1-shot mIoU can be 4.2\% better than the best baseline.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **问题背景**：少样本分割（FSS）旨在利用少量标注的支持样本，分割任意新类别的目标，但传统方法容易在基类上过拟合。近期，基础模型（如SAM）被引入以缓解过拟合，但其视频扩展版本SAM 2具备强大的类无关匹配能力（在视频帧间匹配同一目标）。
- **核心矛盾**：SAM 2的视频匹配是“同身份”目标匹配（同一物体在不同帧中出现），而FSS中支持图像与查询图像的目标通常是不同身份（如支持为船、查询为飞机）。直接套用SAM 2的匹配机制会导致匹配不兼容，SAM 2的鲁棒参数反而退化为窄化参数，再度过拟合基类。
- **研究目标**：如何正确解锁SAM 2的匹配能力用于FSS，使其适应“不同身份”目标间的匹配。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：将原本“支持与查询不同目标匹配”转化为“查询与自身伪目标匹配”，从而与SAM 2的“同目标匹配”能力兼容。
- **关键技术细节**：
  - **Pseudo Prompt Generator (PPG)**：利用DINOv2生成查询前景（FG）先验掩膜和判别性先验掩膜（FG prior含更完整前景但更多背景噪声；Disc prior前景不完整但背景噪声少），将其作为伪掩膜提示，编码成伪查询记忆（`Mem_Q^FG` 和 `Mem_Q^Disc`），实现兼容的匹配。
  - **Iterative Memory Refinement (IMR)**：针对Disc记忆前景不完整的问题，设计迭代机制，从FG记忆中补充前景特征到Disc记忆，同时利用支持记忆（含纯净前景）抑制背景特征的传播。通过余弦相似度和背景抑制机制（公式8-9）逐步优化记忆。
  - **Support-Calibrated Memory Attention (SCMA)**：即使在IMR后，记忆仍可能包含背景特征。SCMA在交叉注意力中利用支持记忆计算全局前景原型，检测并抑制伪记忆中背景像素的注意力得分（公式12-13），使查询特征融合更纯净的前景信息。
- **整体流程**：支持图像和查询图像分别经DINOv2和SAM 2图像编码器提取特征，PPG生成伪提示并编码记忆，经IMR迭代优化，再经SCMA融合特征，最后用掩膜解码器输出预测。训练时仅微调SAM 2的记忆编码器、记忆注意力和掩膜解码器，其余冻结。

### 3. 实验设计
- **数据集**：PASCAL-5$^i$（20类，4折）和COCO-20$^i$（80类，4折）。额外在LVIS-92$^i$和PASCAL-Part上评估泛化性。
- **对比方法**：包括经典FSS方法（ABCNet、SCCAN、HDMNet、HMNet等）和基于基础模型的FSS方法（Matcher、VRP-SAM、GF-SAM、FounFSS等）。
- **评估指标**：平均交并比（mIoU）和前景-背景IoU（FB-IoU），在1-shot和5-shot设置下评测。

### 4. 资源与算力
- **硬件**：4块NVIDIA V100 (32GB) GPU进行训练，单块V100进行测试。
- **模型**：SAM 2-S (46M参数) + DINOv2-B (86M参数)，可学习参数约11M（仅微调SAM 2部分模块，本方法未引入额外可学习参数）。
- **训练细节**：优化器AdamW，初始学习率0.001，多项式调度；PASCAL-5$^i$训练300 epochs，COCO-20$^i$训练75 epochs；批次大小8（每GPU2个样本）；图像随机裁剪为512×512。论文未给出总训练时长，但测试FPS约2.8。

### 5. 实验数量与充分性
- **实验组数**：大量消融实验（组件消融、迭代次数参数研究、不同基础模型尺寸、不同测试集、不同测试样本数、误差条分析、SCMA定量影响等），共涉及12张表格和11张图。
- **充分性与公平性**：实验设计全面，覆盖了核心假设验证、超参数敏感性、泛化能力、随机种子鲁棒性。对比方法包含经典和最新基础模型方法，且在不同数据集上均取得显著提升（1-shot mIoU超最佳基线4.2%）。公平性方面，所有对比均采用统一评测协议（1000个测试集）并报告误差条。但未与所有最新方法（如2025年新工作）逐一对比，但已覆盖主流基线。

### 6. 主要结论与发现
- **核心结论**：通过设计PPG解决匹配身份不兼容问题，并结合IMR和SCMA，FSSAM在PASCAL-5$^i$和COCO-20$^i$上达到新的最先进水平（1-shot mIoU分别为81.0%和62.3%），同时参数高效（不引入新参数）。
- **其他发现**：迭代3次IMR达到最佳平衡；SCMA可将查询前景像素与记忆中意外背景像素的注意力得分降低约41.5%；使用SAM 2-S和DINOv2-B在性能和效率间取得最优折中；在更困难的LVIS和PASCAL-Part数据集上也展现强泛化性。

### 7. 优点
- **创新性**：首次系统分析并解决SAM 2视频匹配能力与FSS不兼容问题，提出“伪提示”转换思路，而非简单微调。
- **参数高效**：模块设计均为无参数操作（PPG、IMR、SCMA均不引入可学习参数），仅微调SAM 2已有部分，总可学习参数仅11M，远低于同类基础模型方法。
- **设计合理**：IMR有效补充前景特征同时抑制背景，SCMA进一步校准注意力，两者互补；消融实验清晰地量化了各模块贡献。
- **泛化性强**：在多个基准（PASCAL-5$^i$、COCO-20$^i$、LVIS-92$^i$、PASCAL-Part）上均表现优异，特别是跨数据集（训练于COCO，测试于LVIS）显示良好的零样本泛化能力。

### 8. 不足与局限
- **依赖伪提示质量**：当查询图像前景与背景极其相似时，DINOv2生成的伪提示可能完全失效（如前景被完全遗漏），论文承认此为失败案例，但未提出错误修正机制。
- **计算资源需求**：依赖两个基础模型（SAM 2 + DINOv2），总参数量达132M（虽可学习量少），测试FPS仅约2.8，难以满足实时应用需求。
- **实验覆盖局限**：未在医学影像、遥感等小众领域验证；未与最新基于Diﬀusion的FSS方法（如2024年方法）比较；未提供完整训练时间，对算力消耗的量化不够详细。
- **偏差风险**：由于仅有4折交叉验证且每折只取1000个测试样本，在COCO上标准偏差达0.9（mIoU），表明性能对采样敏感，需要更多测试样本以稳定评估。

（完）
