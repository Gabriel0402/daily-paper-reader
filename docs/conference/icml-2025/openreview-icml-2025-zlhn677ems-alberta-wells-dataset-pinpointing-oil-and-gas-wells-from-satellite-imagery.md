---
title: "Alberta Wells Dataset: Pinpointing Oil and Gas Wells from Satellite Imagery"
title_zh: 阿尔伯塔井数据集：从卫星图像精确定位油气井
authors: "Pratinav Seth, Michelle Lin, BREFO DWAMENA YAW, Jade Boutot, Mary Kang, David Rolnick"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zLHn677EMS"
tags: ["query:mmseg"]
score: 5.0
evidence: 用于油气井检测的遥感图像分割数据集
tldr: 遥感图像分割在废弃油气井定位中具有潜力，但缺乏大规模标注数据集。本文构建了首个大规模遥感井位数据集，包含21.3万口井的高分辨率卫星图像。评估了多种分割基线算法，为遥感语义分割应用提供了基准。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1362, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 558, \"height\": 1154, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 562, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1762, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 625, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1099, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1059, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1063, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1392, \"height\": 2113, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1125, \"height\": 2082, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zlhn677ems/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1586, \"height\": 1932, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 870, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1285, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1260, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1010, \"height\": 115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 843, \"height\": 118, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 691, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1199, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 932, \"height\": 593, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1086, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1075, \"height\": 591, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1116, \"height\": 677, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 881, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zlhn677ems/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 591, \"height\": 283, \"label\": \"Table\"}]"
motivation: 废弃油气井位置未知，遥感分割可辅助定位但缺乏数据。
method: 收集并标注大规模多光谱卫星图像井位数据集。
result: 提供了超过21.3万口井的数据集并评估分割基线。
conclusion: 该数据集可推动遥感图像分割的实证研究。
---

## Abstract
Millions of abandoned oil and gas wells are scattered across the world, leaching methane into the atmosphere and toxic compounds into the groundwater. Many of these locations are unknown, preventing the wells from being plugged and their polluting effects averted. Remote sensing is a relatively unexplored tool for pinpointing abandoned wells at scale. We introduce the first large-scale Benchmark dataset for this problem, leveraging high-resolution multi-spectral satellite imagery from Planet Labs. Our curated Dataset comprises over 213,000 wells (abandoned, suspended, and active) from Alberta, a region with especially high well density, sourced from the Alberta Energy Regulator and verified by domain experts. We evaluate baseline algorithms for well detection and segmentation, showing the promise of computer vision approaches but also significant room for improvement.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：全球有数百万废弃油气井，泄漏甲烷（强温室气体）和有毒物质进入地下水。大量废弃井的位置未知，导致无法封堵和避免污染。现有遥感探测方法缺乏大规模标注数据集。
- **目标**：利用高分辨率多光谱卫星图像，构建首个大规模油气井检测基准数据集，并评估计算机视觉基线方法，推动废弃井的规模化识别，助力气候变化减缓。
- **意义**：填补了现有小规模、仅含活跃井数据集的空白，为机器学习在环境监测中的应用提供关键资源。

## 2. 方法论

### 核心思想
- 融合权威政府数据（阿尔伯塔能源监管局 AER ST37）与 Planet Labs 多光谱卫星图像（4 波段：RGB + 近红外），通过专家质量控制构建大规模标注数据集。
- 将问题建模为 **二值语义分割**（圆形掩膜）和 **目标检测**（边界框）两种任务。

### 关键技术细节
- **数据来源与清洗**：AER 提供约 63.7 万条记录，经专家筛选去除重复、过滤无效条目，最终保留约 21.3 万口井（活跃、暂停、废弃三类）。
- **图像获取**：选取 2023 年夏季（6-9月）无云覆盖的 PlanetScope 影像，分辨率 3 m/像素，每个图块大小 1050×1050 m（约 350×350 像素）。
- **标注生成**：将点坐标扩展为直径 90 米的圆（对应 30 像素），生成二值掩膜和多类掩膜（活跃/暂停/废弃），边界框与掩膜尺寸一致。
- **数据集划分**：提出基于聚类的分层划分算法（Algorithm 1），先形成小簇（k1i），再聚为大簇（k2i），确保训练/验证/测试集地理分布均衡，避免数据泄露。

### 公式/算法流程（文字说明）
1. 对所有含井图块中心点执行 K-Means 聚类（M=300），得到小簇 k1i。
2. 计算每个小簇的质心，再对这些质心执行第二次 K-Means 聚类（N=30），得到超簇 k2i。
3. 在每个超簇中，将包含井最少的两个小簇分别划入验证集和测试集，其余划入训练集。
4. 对每个子集，在对应簇附近添加等量无井图块，并平衡正负样本数量。

## 3. 实验设计

### 数据集
- **Alberta Wells Dataset**：
  - 总计 188,688 个图块（94,343 个含井 + 94,345 个无井），覆盖 213,447 口井。
  - 按 167,436（训练） / 9,463（验证） / 11,789（测试） 划分。
  - 包含活跃井（107,139）、暂停井（55,007）、废弃井（54,947）三种状态。

### Benchmark 与对比方法
#### 二值分割（Binary Segmentation）
| 模型 | 骨干网络 |
|------|----------|
| U-Net | ResNet50, ResNeXt50, SE-ResNet50, EfficientNetB6 |
| PAN | ResNet50 |
| DeepLabV3+ | ResNet50 |
| Segformer | mit-b0-ade |
| UperNet | ConvNeXt-Small, ConvNeXt-Base, Swin-Small |

#### 目标检测（Object Detection）
| 模型 | 骨干网络 |
|------|----------|
| RetinaNet | ResNet50 |
| Faster R-CNN | ResNet50 |
| FCOS | ResNet50 |
| SSD Lite | MobileNet |
| DETR | ResNet50 |

#### 消融实验
1. **多光谱 vs RGB**：U-Net (ResNet50) 和 FCOS 对比 RGB+NIR 与仅 RGB 的差异。
2. **多种井类型 vs 仅活跃井**：U-Net (ResNet50) 训练于仅活跃井 vs 全部井，测试于全部井。

## 4. 资源与算力

- **文中未明确说明使用的 GPU 型号、数量及训练时长**。
- 仅提及使用了 Mila 和 Digital Research Alliance of Canada 的计算设施，以及 NVIDIA 提供的额外计算资源。
- 训练配置：分割模型均训练 50 个 epoch，目标检测模型训练 120 个 epoch；批量大小因模型而异（64~512）。

## 5. 实验数量与充分性

- **实验组数**：共评估 9 种分割架构（含多种骨干）、5 种检测模型、2 组消融实验，总计约 16 组独立训练实验。
- **充分性评价**：
  - ✅ 覆盖主流 CNN 和 Transformer 方法，对比较全面。
  - ✅ 包含多光谱和多种井类型的消融，验证了数据价值。
  - ⚠️ 未进行超参数优化，报告的是“标准设置”下的性能，因此可能未达各模型最佳表现。
  - ⚠️ 未测试更先进的模型（如 YOLOv8、Mask R-CNN、近期视觉 Transformer）。
  - ✅ 使用 IoU、F1、Precision、Recall、mAP 等多指标，评价客观。

## 6. 主要结论与发现

- **分割任务**：UperNet (Swin-Small) 取得最高 Recall（73.1%），U-Net (EfficientNetB6) 取得最高 IoU（60.4%）和 F1（64.8%）。CNN 模型 Precision 高，Transformer 模型 Recall 高。
- **检测任务**：DETR 在 mAP@50:95 上最优（38.45%），SSD Lite 在 IoU@0.5 上最优（65.07%）。整体检测性能低于分割，表明小目标检测的挑战性。
- **近红外波段价值**：RGB+NIR 相比仅 RGB 在分割和检测上均有明显提升（例如分割 IoU 提高约 1.4%）。
- **多种井类型价值**：训练集包含所有井类型比仅用活跃井在测试集上 IoU 提升约 7.4%，Recall 提升约 11.2%，证明废弃/暂停井更难检测。
- **现有方法仍有较大改进空间**：最高 IoU 仅 60%，mAP@50 仅 15%，说明任务极具挑战性。

## 7. 优点

1. **数据集规模大、质量高**：21.3 万口井，覆盖广阔地理区域（比英德面积之和还大），且经领域专家验证。
2. **多任务标注**：同时提供分割（二值和多类）和检测标注，支持多种建模方式。
3. **多光谱数据**：包含近红外波段，证明对井位识别有益。
4. **数据划分策略巧妙**：聚类分簇确保地理多样性并防止数据泄露。
5. **消融实验设计合理**：验证了 NIR 和多种井类型的重要性，具有实用指导意义。
6. **开放可用**：数据集和代码均开源，促进后续研究。

## 8. 不足与局限

1. **依赖单一地区**：仅使用阿尔伯塔省数据，模型向其他地区（如美国阿巴拉契亚、俄罗斯等）的泛化能力未知。
2. **标签噪声**：AER 数据可能遗漏部分废弃井，导致假阴性标签，影响评估准确性（作者已讨论但未定量分析）。
3. **高密度与废弃井检测困难**：当图块中井数量多、或废弃/暂停井视觉特征微弱时，模型性能下降。
4. **仅用光学影像**：多云地区（如热带、北极）难以采集无云图像，限制了实际应用范围。
5. **未进行跨域迁移实验**：未测试在新区域上的零样本或少样本迁移能力。
6. **算力细节缺失**：未提供 GPU 型号、数量、训练时间，不利于复现和能耗评估。
7. **未优化超参数**：所有模型均使用标准超参数，未进行调参，可能低估了某些模型的潜力。
8. **标注简化**：将井点统一为圆形（直径 90 米），实际井场形状可能不规则，可能引入标注误差。

（完）
