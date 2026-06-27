---
title: "Keep the Balance: A Parameter-Efficient Symmetrical Framework for RGB+X Semantic Segmentation"
title_zh: 保持平衡：用于RGB+X语义分割的参数高效对称框架
authors: "Cai, Jiaxin, Su, Jingze, Li, Qi, Yang, Wenjie, Wang, Shu, Zhao, Tiesong, He, Shengfeng, Liu, Wenxi"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Cai_Keep_the_Balance_A_Parameter-Efficient_Symmetrical_Framework_for_RGBX_Semantic_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 多模态语义分割方法
tldr: 当前多模态语义分割方法计算成本高且过度依赖RGB模态。本文提出一种对称的参数高效微调框架，通过模态感知提示和自适应机制，同时将预训练模型的能力适配到RGB和X模态。实验表明该方法在多个基准上取得优异分割性能，且大幅减少了可训练参数。为多模态分割提供了一种高效且均衡的新思路。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 834, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1706, \"height\": 973, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 823, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 886, \"height\": 713, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 879, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 874, \"height\": 760, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 874, \"height\": 844, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 874, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 883, \"height\": 1088, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-keep-the-balance-a-parameter-efficient-symmetrical-framework-for-rgbx-semantic-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 873, \"height\": 402, \"label\": \"Table\"}]"
motivation: 现有方法计算成本高且对RGB模态依赖过重，限制了其他模态的潜力。
method: 提出对称参数高效微调框架，包含模态感知提示和自适应方案。
result: 在多个多模态分割数据集上取得优异性能，且参数量大幅降低。
conclusion: 该框架为多模态语义分割提供了一种高效且均衡的解决方案。
---

## Abstract
Multimodal semantic segmentation is a critical challenge in computer vision, with early methods suffering from high computational costs and limited transferability due to full fine-tuning of RGB-based pre-trained parameters. Recent studies, while leveraging additional modalities as supplementary prompts to RGB, still predominantly rely on RGB, which restricts the full potential of other modalities. To address these issues, we propose a novel symmetric parameter-efficient fine-tuning framework for multimodal segmentation, featuring with a modality-aware prompting and adaptation scheme, to simultaneously adapt the capabilities of a powerful pre-trained model to both RGB and X modalities. Furthermore, prevalent approaches use the global cross-modality correlations of attention mechanism for modality fusion, which inadvertently introduces noise across modalities. To mitigate this noise, we propose a dynamic sparse cross-modality fusion module to facilitate effective and efficient cross-modality fusion. To further strengthen the above two modules, we propose a training strategy that leverages accurately predicted dual-modality results to self-teach the single-modality outcomes. In comprehensive experiments, we demonstrate that our method outperforms previous state-of-the-art approaches across six multimodal segmentation scenarios with minimal computation cost.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：多模态语义分割（RGB+X）中，现有方法存在两大痛点：(1) 计算成本高、迁移性差——早期方法对RGB预训练参数进行全量微调（FFT），参数量巨大；(2) 对RGB模态过度依赖——近期基于提示微调（PEFT）的方法采用非对称架构，将X模态（深度、热红外、事件、偏振等）仅视为辅助提示，未能充分发挥其潜力；此外，基于全局注意力的跨模态融合会引入噪声。
- **整体含义**：本文旨在设计一种**对称、参数高效**的微调框架，使RGB和X模态在模型中地位对等，同时通过稀疏动态融合减轻噪声，并借助自教学策略提升模态增强与融合效果。

## 2. 论文提出的方法论

### 核心思想
- 采用**对称双流架构**，以Swin-Transformer为预训练主干（冻结），通过两个轻量级模块（MAPA、DSCF）同时增强RGB和X模态的特征，并引入**掩码模态自教学（MMST）**训练策略，进一步提升模态利用效率。

### 关键技术细节
#### 2.1 模态感知提示与自适应（MAPA）
- **统一双模态特征**：将RGB和X tokens经降维投影后拼接，再通过线性层融合得到低秩统一表示 \(X_{\text{uni}}\)（公式1）。
- **提示生成**：基于 \(X_{\text{uni}}\) 通过可学习缩放因子和偏置为每个模态生成特异性提示 \(P_{\text{rgb}}, P_x\)（公式2），作为残差加到对应模态tokens上。
- **适配器**：在每个Transformer层中插入**模态专属的瓶颈适配器**（hourglass结构，降维→ReLU→升维），使预训练知识有效迁移至各模态（公式3）。

#### 2.2 动态稀疏跨模态融合（DSCF）
- 对双模态特征进行低秩映射，生成变形参考点网格。
- 通过轻量偏移预测网络 \(\phi_{\text{offset}}\) 预测每个参考点的偏移量，得到变形点集 \(p_{\text{rgb}}, p_x\)，聚焦各模态的显著区域（公式4）。
- 联合使用两模态的变形点采样多模态特征，并通过**可学习模态重要性评估函数** \(W(\cdot)\) 计算加权融合特征（公式5），再进行多头注意力建立长程上下文关系。

#### 2.3 掩码模态自教学策略（MMST）
- 训练时**随机掩码整个单模态输入**，强制模型不过度依赖某一模态。
- 利用融合分支的精确预测区域（掩码 \(M\)）作为**教师信号**，指导单模态分支的预测（公式7、8），隐式增强MAPA模块的跨模态表示能力。
- 总损失为三个分割头的加权交叉熵损失（公式9）。

## 3. 实验设计
- **数据集与场景**：6个多模态数据集，覆盖RGB-深度（NYUDv2、SUN RGB-D）、RGB-热红外（MFNet、PST900）、RGB-事件（DeLiVER）、RGB-偏振（MCubeS，含近红外、深度、偏振角）。
- **基准**：与全量微调（FFT）方法（SA-Gate、CMX、CMNeXt、GeminiFusion等）和参数高效微调（PEFT）方法（DPLNet、GoPT）对比。
- **评价指标**：mIoU（平均交并比）为主，也统计可训练参数和推理速度（FPS）。

## 4. 资源与算力
- **文中未明确说明**使用的GPU型号、数量及训练时长。仅提及backbone为Swin-Base和Swin-Large（ImageNet预训练），冻结主干参数，训练模块参数量仅7.5M（Swin-B）和16.1M（Swin-L），推理速度约13 FPS（Swin-B）。全量FFT方法（如GeminiFusion）需369.2M参数且仅7.5 FPS。

## 5. 实验数量与充分性
- **实验数量充足**：在6个异构数据集上进行完整对比，包含室内（NYUDv2、SUN RGB-D）、室外（MFNet）、夜间（PST900）、材料分割（MCubeS）、多模态（DeLiVER）等场景，验证了方法对多种X模态的泛化性。
- **消融实验充分**：对MAPA的提示生成（6种变体）、适配器（共享vs专用、不同维度）、DSCF（删除、替换为FFM/DAT、不同采样策略）、MMST（掩码、辅助监督、掩码方式）进行了系统消融，每个消融在2个数据集上验证。
- **公平性**：与PEFT方法对比时，保证预训练数据一致（ImageNet，而非额外语义分割预训练），并复现了DPLNet。参数和速度对比在同一环境下测试。

## 6. 主要结论与发现
- **性能领先**：在6个数据集上，所提方法均超越现有PEFT方法，且与SOTA的FFT方法相比，能以**极少的可训练参数**（约4%~16%）达到相当甚至更优的mIoU。例如NYUDv2上Swin-L版本59.9% mIoU（FFT GeminiFusion 60.2%，但参数是其4.4%）；PST900上Swin-B版87.6% mIoU（领先PEFT方法7.2%）。
- **效率优势**：对称双流设计+低秩空间运算，使参数量仅增加少量，推理速度达到13 FPS（Swin-B），优于多数FFT方法。
- **模块有效性**：MAPA和DSCF的每项设计（模态专属提示、适配器、动态稀疏融合加权）均被消融实验证实有效；MMST策略显著提升鲁棒性和精度。

## 7. 优点
- **对称架构**：打破以往非对称PEFT方法对RGB的依赖，充分挖掘X模态潜力。
- **参数高效**：仅训练少量额外参数（7.5M/16.1M），可轻松适配下游任务，降低存储和部署成本。
- **噪声抑制**：DSCF通过稀疏动态采样替代全局注意力，避免无关区域噪声干扰，同时降低计算量。
- **训练策略创新**：MMST通过随机掩码+自教学，同时增强模态独立性和融合能力，简单有效。
- **实验覆盖全面**：在深度、热红外、事件、偏振等4种X模态上验证，泛化性强。

## 8. 不足与局限
- **未涉及视觉-语言任务**：论文指出当前未探索语言模态，未来可扩展到视觉-语言多模态任务。
- **表格中部分消融未跨所有数据集**：消融实验仅在NYUDv2和MFNet上进行，其他数据集（如MCubeS、DeLiVER）缺少完整消融，可能存在数据集特定过拟合风险。
- **计算资源未公开**：未报告训练所需GPU型号、数量及时间，不利于复现和公平比较。
- **极端情况验证有限**：MMST虽模拟掩码场景，但实际应用中某些模态可能完全缺失（如传感器故障），本文未做专门缺失模态实验。
- **backbone选择单一**：仅使用Swin-Transformer，未尝试其他预训练模型（如ViT、ConvNeXt）以证明框架的通用性。

（完）
