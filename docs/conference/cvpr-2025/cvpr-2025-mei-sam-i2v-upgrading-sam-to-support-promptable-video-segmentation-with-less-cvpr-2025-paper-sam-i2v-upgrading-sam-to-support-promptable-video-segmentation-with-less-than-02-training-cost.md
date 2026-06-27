---
title: "SAM-I2V: Upgrading SAM to Support Promptable Video Segmentation with Less than 0.2% Training Cost"
title_zh: "SAM-I2V: 以低于0.2%训练成本升级SAM实现可提示视频分割"
authors: "Mei, Haiyang, Zhang, Pengyu, Shou, Mike Zheng"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Mei_SAM-I2V_Upgrading_SAM_to_Support_Promptable_Video_Segmentation_with_Less_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: SAM模型升级到视频分割，极低训练成本
tldr: "针对视频分割中SAM 2从零训练成本过高的问题，本文提出SAM-I2V图像到视频升级方法，基于预训练SAM进行高效迁移，以低于0.2%的训练成本实现可提示视频分割，确保动态场景中精确且时空一致的掩膜传播。"
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 846, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1803, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 830, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1793, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 840, \"height\": 274, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1812, \"height\": 564, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1811, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 859, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-mei-sam-i2v-upgrading-sam-to-support-promptable-video-segmentation-with-less-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 263, \"label\": \"Table\"}]"
motivation: SAM 2从零训练视频分割模型成本过高。
method: 提出SAM-I2V图像到视频升级方法，基于预训练SAM进行高效迁移。
result: 以极低训练成本实现可提示视频分割。
conclusion: 为SAM在视频分割中的实用部署提供高效方案。
---

## Abstract
Foundation models like the Segment Anything Model (SAM) have significantly advanced promptable image segmentation in computer vision. However, extending these capabilities to videos presents substantial challenges, particularly in ensuring precise and temporally consistent mask propagation in dynamic scenes. SAM 2 attempts to address this by training a model on massive image and video data from scratch to learn complex spatiotemporal associations, resulting in huge training costs that hinder research and practical deployment. In this paper, we introduce SAM-I2V, an effective image-to-video upgradation method for cultivating a promptable video segmentation (PVS) model. Our approach strategically upgrades the pre-trained SAM to support PVS, significantly reducing training complexity and resource requirements. To achieve this, we introduce three key innovations: (i) an image-to-video feature extraction upgrader built upon SAM's static image encoder to enable spatiotemporal video perception, (ii) a memory filtering strategy that selects the most relevant past frames for more effective utilization of historical information, and (iii) a memory-as-prompt mechanism leveraging object memory to ensure temporally consistent mask propagation in dynamic scenes. Comprehensive experiments demonstrate that our method achieves over 90% of SAM 2's performance while using only 0.2% of its training cost. Our work presents a resource-efficient pathway to PVS, lowering barriers for further research in PVS model design and enabling broader applications and advancements in the field. Code and model will be available at: https://github.com/showlab/SAM-I2V.

---

## 论文详细总结（自动生成）

# 论文总结：SAM-I2V: Upgrading SAM to Support Promptable Video Segmentation with Less than 0.2% Training Cost

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有 Promptable Video Segmentation（PVS）模型 SAM 2 从零开始在大量图像和视频数据上训练，虽然性能强大，但训练成本极其高昂（256 块 A100 GPU × 108 小时），严重阻碍了学术研究和实际部署。
- **整体含义**：本文提出一种资源高效的图像到视频（image-to-video）升级方法，将预训练的 SAM 图像分割模型改造为可提示视频分割模型，大幅降低训练成本，同时保持接近 SAM 2 的性能，为 PVS 模型的设计和应用提供了一条可行且低门槛的路径。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 基于预训练的 SAM（如 TinySAM）固定主干网络，设计轻量级可训练模块，使其具备时空感知和记忆驱动的分割能力，实现从图像到视频的平滑升级。

### 关键技术细节
- **Temporal Feature Integrator (TFI)**：
  - 包含 temporal branch（3D 卷积）和 integration branch（2D 卷积加融合操作），对 SAM 的图像编码器进行升级，提取时空特征。
  - 过程：当前帧经 SAM 2D stem + spatial blocks 得到空间特征 \(S_l\)，TFI 通过 temporal branch 捕获时序信息，integration branch 融合两者得到增强的时空特征 \(I_l\)。
- **Memory Selective Associator (MSA)**：
  - 不再使用固定连续帧作为记忆，而是基于与当前帧特征的相似度，从局部（短期）和全局（长期）帧中分别采样最相关的帧。
  - 通过相似度计算 → 概率分布 → 采样，选择 \(x\) 个局部帧和 \(y\) 个全局帧 (\(x+y=z\))，随后利用 memory attention 将选中的历史特征与当前帧特征进行交叉注意力融合。
- **Memory Prompt Generator (MPG)**：
  - 引入可学习的 memory prompt tokens，利用掩码交叉注意力（Masked Cross-Attention）从历史帧特征中提取前景信息，再经自注意力和 MLP 生成最终的记忆提示嵌入。
  - 该提示被送入 mask decoder，作为额外 prompt 以保证时序一致性。

### 公式/算法流程（文字说明）
- 输入视频帧 → SAM 图像编码器提取多级空间特征 → TFI 结合 temporal branch 输出时空特征 → MSA 根据相似性选择历史帧并生成记忆增强特征 → MPG 将记忆特征编码为 prompt tokens → 与用户输入 prompt（可选）一起送入 mask decoder → 输出当前帧分割掩码。

## 3. 实验设计

### 数据集与基准
- **训练**：SA-1B（10,000 张图像）+ SA-V（50,583 个视频）
- **测试**：四个 benchmark 数据集——ESD [18]、PUMaVOS [1]、LV-VIS [41]、SAV-Test [36]
- **评估指标**：J&F（区域相似度 Jaccard + 边界精度 F-measure）
- **评估设置**：Online PVS（单次传播 + 交互修正）和 Offline PVS（多次传播，每次选择错误最大帧修正），分别使用 1-click、3-click、5-click 交互。

### 对比方法
1. SAM 2.1（强基线）
2. SAM（base）+ XMem++、SAM + Cutie
3. TinySAM + XMem++、TinySAM + Cutie
4. TinySAM + Temporal Adapter（TA）、TinySAM + Spatial Adapter（SA）+ TA
5. 本文方法：TinySAM + SAM-I2V（以及 EdgeSAM + SAM-I2V）

## 4. 资源与算力

- **训练硬件**：8 块 RTX A5000 GPU（24GB 显存）
- **训练时长**：10 个 epoch（具体时间未明确给出，但总训练成本为 **4.6k GPU·Hour**，计算方式为 GPU 数 × 显存 × 训练小时）
- **对比**：SAM 2.1 训练成本为 **2.2m GPU·Hour**（256 A100 × 108h），本文仅为其 **0.2%**
- **模型参数量**：SAM-I2V 仅 **18.9M**（TinySAM 主干 + 升级模块），而 SAM 2.1 为 38.9M，SAM+XMem++ 高达 157.0M

## 5. 实验数量与充分性

- **主要对比实验**：表 1（Online PVS，三种交互数，四个数据集，共 4×3=12 个准确率数值）和表 2（Offline PVS，同样设置）展示了与 7 种方法的对比。
- **消融实验**：
  - 适用性消融（表 3）：验证 SAM-I2V 可升级不同 SAM 变体（TinySAM、EdgeSAM）
  - TFI 有效性（表 4）：对比 ST-Adapter、Parallel Adapter
  - MSA 设计（表 5）：不同局部/全局帧比例、均匀采样 vs 相似度采样
  - MPG 设计（表 6）：不同 token 数量、是否使用掩码交叉注意力
- **充分性**：实验覆盖了主要组件、不同交互级别、多种 backbone 及公平对比，结论具有说服力。缺少与 SAM 2 在多点击融合策略上的直接消融，但总体充分。

## 6. 主要结论与发现

- SAM-I2V 在 Online PVS 中达到 **65.3** 平均 J&F（SAM 2.1 为 71.9），即 **90.8%** 性能；在 Offline PVS 中达到 **66.0**（SAM 2.1 为 73.3），即 **90.0%** 性能。
- 训练成本仅 SAM 2.1 的 **0.2%**，参数仅为其 **48.6%**（18.9M vs 38.9M）。
- 各模块（TFI、MSA、MPG）均能带来显著增益，且 MSA 中的相似度筛选优于均匀选择，MPG 中的掩码注意力至关重要。
- SAM-I2V 可稳定迁移至不同 SAM 变体（TinySAM、EdgeSAM），具有良好通用性。

## 7. 优点

- **极低训练成本**：为 PVS 的研究和部署提供经济可行的方案，尤其适合资源受限的学术场景。
- **设计简洁高效**：固定预训练骨干，仅新增少量可学习参数（~18.9M），无需大规模重训练。
- **模块化升级**：各组件（TFI、MSA、MPG）可独立替换或改进，便于后续拓展。
- **记忆筛选创新**：基于相似度的帧选择策略相比简单连续帧更有效地利用历史信息，提升时序一致性。
- **实验丰富**：在四个不同数据集、两种评估模式（Online/Offline）、多种交互设置下验证了方法的鲁棒性。

## 8. 不足与局限

- **性能差距**：总体 J&F仍比 SAM 2.1 低约 7-8 个百分点，尤其在 PUMaVOS 等部分数据集上差距较大。
- **数据限制**：未使用 SAM 2.1 训练中的 62.9k 非公开优质视频，这可能限制了潜力。
- **交互设置细节缺失**：在线上评估中，修正点击对后续帧的影响方式与 SAM 2 不同，可能带来不公平比较（但文中已解释）。
- **仅测试 TinySAM 与 EdgeSAM**：未在 SAM base/large 上进行升级实验，通用性验证有限。
- **训练时长未精确给出**：仅通过成本计算间接反映，未提供具体 wall-clock time。
- **应用限制**：若需与 SAM 2.1 完全相同性能，本方法尚无法替代，更适合快速原型开发或资源受限场景。

（完）
