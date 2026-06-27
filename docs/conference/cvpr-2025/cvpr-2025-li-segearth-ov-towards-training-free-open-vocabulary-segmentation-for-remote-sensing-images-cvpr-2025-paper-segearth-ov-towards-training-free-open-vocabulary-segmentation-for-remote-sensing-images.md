---
title: "SegEarth-OV: Towards Training-Free Open-Vocabulary Segmentation for Remote Sensing Images"
title_zh: SegEarth-OV：面向遥感图像的无训练开词汇分割
authors: "Li, Kaiyu, Liu, Ruixun, Cao, Xiangyong, Bai, Xueru, Zhou, Feng, Meng, Deyu, Wang, Zhi"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Li_SegEarth-OV_Towards_Training-Free_Open-Vocabulary_Segmentation_for_Remote_Sensing_Images_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 遥感开放词汇分割
tldr: 遥感图像语义分割常局限于预定义类别，无法识别未见类别。本文首次将训练免开词汇语义分割引入遥感领域，并针对遥感图像低分辨率特征导致的目标形状扭曲和边界不匹配问题，提出简单通用的上采样器SimFeatUp以恢复空间信息。实验表明SegEarth-OV无需额外训练即可实现遥感图像开放词汇分割，在多个数据集上超越了现有方法。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1621, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 911, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 741, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 819, \"height\": 776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1544, \"height\": 489, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1633, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1755, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 788, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 862, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-segearth-ov-towards-training-free-open-vocabulary-segmentation-for-remote-sensing-images-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 883, \"height\": 384, \"label\": \"Table\"}]"
motivation: 遥感分割局限于闭集假设，无法处理实际中大量未见类别。
method: 提出基于CLIP的训练免开词汇分割框架，并设计SimFeatUp上采样器恢复细节。
result: 无需训练即可在遥感图像上实现精确的开放词汇分割。
conclusion: 该工作为遥感应用中的开词汇分割提供了高效灵活的新范式。
---

## Abstract
Current remote sensing semantic segmentation methods are mostly built on the close-set assumption, meaning that the model can only recognize pre-defined categories that exist in the training set. However, in practical Earth observation, there are countless unseen categories, and manual annotation is impractical. To address this challenge, we first attempt to introduce training-free open-vocabulary semantic segmentation (OVSS) into the remote sensing context. However, due to the sensitivity of remote sensing images to low-resolution features, distorted target shapes and ill-fitting boundaries are exhibited in the prediction mask. To tackle these issues, we propose a simple and universal upsampler, i.e. SimFeatUp, to restore lost spatial information of deep features. Specifically, SimFeatUp only needs to learn from a few unlabeled images, and can upsample arbitrary remote sensing image features. Furthermore, based on the observation of the abnormal response of patch tokens to the [CLS] token in CLIP, we propose to execute a simple subtraction operation to alleviate the global bias in patch tokens. Extensive experiments are conducted on 17 remote sensing datasets of 4 tasks, including semantic segmentation, building extraction, road detection, and flood detection. Our method achieves an average of 5.8%, 8.2%, 4.0%, and 15.3% improvement over state-of-the-art methods on the 4 tasks.

---

## 论文详细总结（自动生成）

# SegEarth-OV: 面向遥感图像的无训练开词汇分割 — 详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有遥感语义分割方法大多基于**闭集假设**，模型只能识别训练集中预定义的类别（如建筑、植被等）。然而在实际地球观测中，存在**无数未见类别**，人工标注成本极高且不可行。
- **研究动机**：将**无训练（training‑free）开词汇语义分割（OVSS）**引入遥感领域，使模型能识别任意类别而不需针对遥感数据额外训练。但直接应用为自然图像设计的OVSS方法（如 MaskCLIP、ClearCLIP）会导致**目标形状扭曲、边界不匹配**，根本原因是遥感图像对**低分辨率特征**更为敏感。
- **整体含义**：首次证明基于自然图像预训练的视觉‑语言模型（VLM，如CLIP）可直接用于遥感开词汇分割，并提出两种通用技巧显著提升分割质量。

## 2. 论文提出的方法论：核心思想、关键技术细节
### 2.1 SimFeatUp — 通用特征上采样器
- **目标**：恢复CLIP深层特征中丢失的空间信息，CLIP输出特征分辨率仅为原图的1/16（ViT‑B/16）。
- **训练方式**：仅需少量**无标注图像**（来自Million‑AID，随机选取16k张），学习一个轻量级上采样网络。
- **结构**：
  - 使用**参数化联合双边上采样（JBU）**，将上采样核替换为单个JBU模块（JBU One），可重复执行多次实现任意倍率上采样（如16×需执行4次）。
  - 扩大JBU窗口至**11×11**（原FeatUp为7×7），以适应遥感目标尺度跨度大的特点（从米级树木到千米级森林）。
- **损失函数**（公式5）：
  - 重建损失 \( L_{\text{rec}} = \|O - \sigma_\downarrow(\sigma_\uparrow(O))\|_2^2 \) （保持低分辨率特征的语义一致性）
  - 图像重建损失 \( L_{\text{img}} = \|I - \text{CRN}(\sigma_\uparrow(O))\|_2^2 \)（通过内容保留网络CRN约束高分辨率特征与原始图像内容一致，防止目标丢失）
  - 总损失 \( L = L_{\text{rec}} + \gamma L_{\text{img}} \)，其中 \( \gamma = 0.1 \)。
- **上采样特征选择**：取CLIP**最后一个Transformer块输入**的特征 \( X[1:hw+1] \) 经投影层后上采样（而非最终输出），避免与后续注意力修改冲突。

### 2.2 全局偏差缓解
- **问题**：CLIP的[CLS] token包含整图全局信息，导致patch token也沾染全局偏差，在密集预测中产生响应异常（如非建筑区域也被高亮）。
- **方法**：对patch token减去全局特征（公式9）：
  \[
  \hat{O} = O[1:hw+1] - \lambda \, O[0]
  \]
  其中 \(\lambda = 0.3\) 为强度因子，\(O[0]\) 为[CLS] token。

### 2.3 整体推理流程（图3b）
- 输入图像 → CLIP图像编码器 → 提取早期特征 \( X \) → 投影得 \( O' \) → SimFeatUp上采样 → 减去[CLS] token → 与文本编码器生成的所有类别文本特征计算相似度 → 逐像素分类。

## 3. 实验设计
### 3.1 数据集
- **语义分割（8个数据集）**：OpenEarthMap、LoveDA、iSAID、Potsdam、Vaihingen、UAVid、UDD5、VDD。
- **单类提取**：
  - 建筑提取（4个）：WHU Aerial、WHU Sat. II、Inria、xBD。
  - 道路提取（4个）：CHN6‑CUG、DeepGlobe、Massachusetts、SpaceNet。
  - 洪水检测（1个）：WBS‑SI。
- **SimFeatUp训练数据**：仅使用Million‑AID中随机抽取的16k张无标注遥感图像。

### 3.2 对比方法（Baseline）
- 5种SOTA无训练OVSS方法：**CLIP**、**MaskCLIP**、**SCLIP**、**GEM**、**ClearCLIP**。
- 此外还比较了遥感CLIP变体：RemoteCLIP、GeoRSCLIP、SkyCLIP（ViT‑B/32版本）。

### 3.3 评估指标
- 语义分割：**mIoU**（均交并比）
- 单类提取：**前景类IoU**

### 3.4 实现细节
- 使用MMSegmentation工具，CLIP ViT‑B/16（OpenAI预训练权重），文本模板“a photo of {class name}”。
- 图像预处理：长边缩放至448，滑动推理窗口224×224，步长112。
- 单类提取任务中额外测试了**大尺寸输入（896×896）**。

## 4. 资源与算力
- **明确说明**：使用**两张NVIDIA 4090 GPU**，**batch size = 8**，SimFeatUp训练**1个epoch**。
- **未说明**：训练总时长、推理时间和参数量（仅提到SimFeatUp参数<0.3M）。

## 5. 实验数量与充分性
- **全面性**：
  - 共在**17个遥感数据集、4类任务**上评估，远超同类工作。
  - 语义分割8个数据集全取得最佳。
  - 单类提取任务每个都有多个数据集。
- **消融实验**（表5）：
  - 逐步验证：原始FeatUp vs. 改进的SimFeatUp（分别用CLIP/MaskCLIP特征）、输入层选择、遥感数据训练、JBU One、CRN+图像重建损失、全局偏差缓解、大核JBU。
- **即插即用实验**（表4）：将方法附加到MaskCLIP、SCLIP、ClearCLIP上均显著提升。
- **自然图像验证**（表6）：在PASCAL Context59、COCOStuff、Cityscapes上测试SimFeatUp，mIoU提升1.2%~5.7%。
- **公平性**：所有对比方法使用相同文本模板、图像尺寸和滑窗策略，仅替换特征处理模块。

## 6. 论文的主要结论与发现
- 现有自然图像OVSS方法在遥感图像上表现**次优**，主要因低分辨率特征导致几何失真。
- 提出的 **SimFeatUp** 和 **全局偏差减法** 可**即插即用**，显著提升所有对比方法（表4）。
- SegEarth‑OV在所有17个遥感数据集上超越SOTA，平均提升：语义分割5.8%、建筑提取8.2%、道路提取4.0%、洪水检测15.3%。
- 遥感领域专用CLIP（如RemoteCLIP）因训练数据规模较小，在OVSS任务上未必优于自然CLIP；而更大规模数据的GeoRSCLIP表现更好。
- OVSS可作为遥感VLM的**评估能力**。

## 7. 优点
- **创新性**：首次将无训练OVSS系统性地引入遥感，指出并解决低分辨率特征和全局偏差两大核心问题。
- **方法简洁有效**：SimFeatUp仅需少量无标注图像预训练一次，即可用于任意遥感数据；全局偏差减法仅一行公式。
- **即插即用**：作为外部模块可无缝集成到任意CLIP‑based OVSS方法中。
- **实验极其充分**：覆盖4类任务、17个数据集，消融、即插即用、自然图像泛化、遥感CLIP对比等均包含，验证可靠。
- **对遥感社区贡献**：提供了开源代码，有望启发更多遥感开词汇分割和遥感VLM研究。

## 8. 不足与局限
- **iSAID数据集性能低**（mIoU仅21.7%），因该数据集含16个细粒度类别，表明当前无训练方法对复杂场景仍有瓶颈。
- **道路提取整体不理想**（最佳IoU仅35.4%），作者指出可能由于道路特殊长条形状以及基于OpenStreetMap的标签本身不精确。
- **依赖自然图像预训练CLIP**：虽然效果不错，但专门针对遥感优化的VLM（如RemoteCLIP）在某些数据上表现反而不如自然CLIP，说明领域适配仍需进一步研究。
- **SimFeatUp仍需要预训练**（尽管仅用无标注图像且一次训练可通用），严格来说不属于完全“训练‑free”，但作者认为其预训练独立于分割任务，因此可视为无训练。
- **未讨论计算开销**：虽提及参数少，但未给出推理时间或显存占用对比，可能影响部署评估。

（完）
