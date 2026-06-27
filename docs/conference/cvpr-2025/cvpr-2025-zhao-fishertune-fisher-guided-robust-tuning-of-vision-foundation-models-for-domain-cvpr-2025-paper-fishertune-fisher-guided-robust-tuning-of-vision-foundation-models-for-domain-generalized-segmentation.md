---
title: "FisherTune: Fisher-Guided Robust Tuning of Vision Foundation Models for Domain Generalized Segmentation"
title_zh: "FisherTune: 基于Fisher引导的视觉基础模型鲁棒调优用于域泛化分割"
authors: "Zhao, Dong, Li, Jinlong, Wang, Shuang, Wu, Mengyao, Zang, Qi, Sebe, Nicu, Zhong, Zhun"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhao_FisherTune_Fisher-Guided_Robust_Tuning_of_Vision_Foundation_Models_for_Domain_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 视觉基础模型用于域泛化语义分割的鲁棒调优
tldr: 针对视觉基础模型微调后泛化能力下降的问题，本文提出FisherTune方法，利用域相关Fisher信息矩阵度量参数在各任务和域上的敏感性，指导选择性调优，在域泛化语义分割任务中既充分利用VFM潜力又保持泛化能力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 894, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 898, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 827, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 891, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 767, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 831, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 810, \"height\": 383, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 1494, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1809, \"height\": 765, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1807, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-fishertune-fisher-guided-robust-tuning-of-vision-foundation-models-for-domain-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 833, \"height\": 228, \"label\": \"Table\"}]"
motivation: 微调视觉基础模型进行域泛化语义分割时保持泛化能力困难。
method: 提出FisherTune，利用域相关Fisher信息矩阵指导参数调优。
result: 在域泛化分割任务上有效。
conclusion: 实现对VFM的鲁棒微调，适用于域泛化语义分割。
---

## Abstract
Vision Foundation Models (VFMs) excel in generalization due to large-scale pretraining, but fine-tuning them for Domain Generalized Semantic Segmentation (DGSS) while maintaining this ability remains a challenge. Existing approaches either selectively fine-tune parameters or freeze the VFMs and update only the adapters, both of which may underutilize the VFMs' full potential in DGSS tasks. We observe that domain-sensitive parameters in VFMs, arising from task and distribution differences, can hinder generalization. To address this, we propose FisherTune, a robust fine-tuning method guided by the Domain-Related Fisher Information Matrix (DR-FIM). DR-FIM measures parameter sensitivity across tasks and domains, enabling selective updates that preserve generalization and enhance DGSS adaptability. To stabilize DR-FIM estimation, FisherTune incorporates variational inference, treating parameters as Gaussian-distributed variables and leveraging pretrained priors. Extensive experiments show that FisherTune achieves superior cross-domain segmentation while maintaining generalization, outperforming both selective-parameter and adapter-based methods.

---

## 论文详细总结（自动生成）

# FisherTune 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：视觉基础模型（VFM）经过大规模预训练后具有强大的泛化能力，但在面向域泛化语义分割（DGSS）任务进行微调时，如何在激活其对下游任务的适应性的同时，保持其原有的泛化能力，是一个关键挑战。
- **现有方法不足**：
  - 基于适配器（Adapter）的方法（如Rein）仅修改少量外部参数，未能充分利用VFM的内部表示；
  - 基于选择性微调的方法（如手动或自动选择参数）只关注任务敏感参数，可能破坏VFM的泛化能力。
- **动机**：实验发现，VFM中某些参数对域变化高度敏感（域敏感参数），而另一些参数保持通用；识别并仅微调这些域敏感参数，可以在保留预训练知识的同时提升跨域适应能力。

## 2. 方法论：核心思想、关键技术细节与算法流程

### 核心思想
提出 **FisherTune**，利用**域相关Fisher信息矩阵（DR-FIM）**度量每个参数对任务和域变化的敏感度，据此选择性微调最敏感的少量参数，保持模型泛化能力。

### 关键技术细节

1. **域相关Fisher信息矩阵（DR-FIM）**
   - 传统FIM仅衡量任务敏感性，不能反映跨域行为。DR-FIM改进为任务敏感项与域敏感项的线性组合：
     \[
     \text{DRF}_\theta = \underbrace{F_\theta(x,y)}_{\text{task-sensitive}} + e^{-(\epsilon_\mu+\epsilon_\sigma)}\frac{|F_\theta(x,y)-F_\theta(x',y)|}{\min(F_{\theta_i}(x),F_{\theta_i}(x'))+\epsilon}
     \]
     其中 \(x'\) 是通过特征扰动（改变均值和方差）模拟的未见域样本；\(F_\theta\) 为Fisher信息矩阵；第二项衡量参数对域漂移的敏感性。

2. **稳定的DR-FIM估计**
   - 直接计算DR-FIM维度高且不稳定。采用**变分推理**：将参数视为服从高斯分布的随机变量，引入预训练参数作为先验（\(\mathcal{N}(\theta_{pt}, \tau^2 I)\)），通过优化变分自由能（ELBO）学习协方差矩阵 \(\Lambda\)，进而导出稳定的DR-FIM表达式：
     \[
     \text{DRF}_\theta = \gamma\left( \Lambda_x - \tau^{-2} I \right) + e^{-(\epsilon_\mu+\epsilon_\sigma)} \frac{|\Lambda_x - \Lambda_{x'}|}{\min(\Lambda_x,\Lambda_{x'})+\epsilon}\gamma
     \]
     该方法计算高效，且利用先验防止估计退化。

3. **动态训练调度**
   - 初始阶段只微调DR-FIM值最高的 \(\delta_{\min}\%\) 参数；随训练进行，逐步扩大至 \(\delta_{\max}\%\)。阈值按指数衰减更新，确保模型从关键参数开始稳定适应。

### 算法流程（文字描述）
1. 冻结VFM骨干，预热训练分割解码器 \(T_1\) 步。
2. 对每个batch：采样源域数据 \((x,y)\)，通过特征扰动模拟未见域数据 \(x'\)；优化协方差矩阵 \(\Lambda\)；计算DR-FIM。
3. 根据当前DR-FIM阈值选择参数，与解码器一起基于分割损失联合微调 \(T_3\) 步。

## 3. 实验设计

### 数据集与场景
- **源域**：GTAV（合成数据）、Cityscapes（真实数据）。
- **目标域**：
  - 混合域：Cityscapes、BDD100K、Mapillary；
  - 跨数据集：Cityscapes → BDD100K、Cityscapes → ACDC（恶劣天气）；
  - 恶劣天气：Foggy Zurich、Foggy Driving、Dark Zurich、Nighttime Driving、ACDC-Rain、ACDC-Snow。
- **评测基准**：域泛化语义分割（DGSS）标准设定，训练时不使用目标域标签。

### 对比方法
- 全微调（Full）、冻结（Freeze）、LoRA、VPT、AdaptFormer、Rein（适配器类）、VQT、ChildTune（选择性微调类）。
- 在多种VFM骨干上测试：CLIP (ViT-L)、MAE (Huge)、SAM (Huge)、EVA02 (Large)、DINOv2 (ViT-L)。
- 额外对比最新方法：EVA02+VLTSeg、DINOv2+SDT、CLOUDS、tqdm等。

### 评价指标
平均交并比（mIoU）。

## 4. 资源与算力

文中**未明确说明**所使用的GPU型号、数量及训练时长。仅在算法1中给出了迭代步数（\(T_1, T_2, T_3\)）等超参数，但未提供具体的硬件配置信息。

## 5. 实验数量与充分性

- **实验数量丰富**：
  - 主表（Table 1）：5种VFM×8种方法，在GTAV→三个目标域上对比；
  - Table 2：两种VFM在Cityscapes→BDD100K/ACDC上细致类别结果；
  - Table 3：Cityscapes→6种恶劣天气场景；
  - 消融实验（Table 4）：随机选择、FIM、\(\Delta F\)、DR-FIM对比；
  - 估计方法消融（Fig. 5）：有/无稳定估计；
  - 特征扰动消融（Table 5）：对现有方法公平比较；
  - 参数敏感性可视化（Fig. 6）、特征分布可视化（Fig. 7）等。
- **充分性与公平性**：
  - 对比了最先进的方法，并控制可训练参数量（如15.21M）；
  - 对适配器类方法也应用了特征扰动进行公平比较（Table 5）；
  - 消融实验验证了各组件贡献；
  - 实验设计全面，覆盖多种域漂移程度和VFM类型，结论具有说服力。

## 6. 主要结论与发现

- FisherTune在所有实验设置中**显著优于**现有的适配器方法和选择性微调方法。
  - 在GTAV→Cityscapes+BDD+Mapillary上，平均mIoU达66.5%（DINOv2骨干），比Rein高2.2%，比ChildTune高3.1%。
  - 在Cityscapes→ACDC上达77.5%，比Rein高约5%。
  - 跨五种VFM骨干，平均提升约4.3% mIoU。
- DR-FIM比传统FIM更有效识别域敏感参数，变分推理进一步稳定估计，动态调度逐步放宽微调范围。
- 域敏感参数主要集中在深层块的Q、K和FFN参数上，且Q、K敏感性高于V。

## 7. 优点

- **创新性**：首次将Fisher信息矩阵扩展到跨域敏感性度量（DR-FIM），并引入变分推理实现稳定高效估计。
- **有效性**：在多个VFM和多种域泛化场景下均取得SOTA结果，且可训练参数量与选择性方法持平（15.21M）。
- **鲁棒性**：通过先验正则化防止过拟合，动态调度使微调过程稳定。
- **通用性**：不仅适用于DGSS，提出的选择性微调框架可推广至其他下游任务（如分类、检测）。
- **实验充分**：消融和可视化清晰证明了各组件的必要性。

## 8. 不足与局限

- **计算资源未披露**：论文未说明训练所需的GPU型号、数量及时间，难以评估实际部署成本。
- **超参数敏感性**：DR-FIM计算涉及 \(\gamma, \tau, \epsilon_\mu, \epsilon_\sigma\) 等多个超参数，文中仅给出默认设置，未做详细敏感性分析（附录E虽有提及但未在给定文本中展示）。
- **仅验证语义分割**：所有实验集中于DGSS任务，方法在分类、检测等任务上的泛化能力尚未验证。
- **域模拟依赖**：使用特征扰动模拟未见域，若扰动方式与真实域漂移差异较大，可能影响DR-FIM质量。
- **缺乏更大规模模型验证**：实验中最大骨干为ViT-Huge（SAM 632M参数），但未在更大规模模型（如GPT-4V类）上测试。

（完）
