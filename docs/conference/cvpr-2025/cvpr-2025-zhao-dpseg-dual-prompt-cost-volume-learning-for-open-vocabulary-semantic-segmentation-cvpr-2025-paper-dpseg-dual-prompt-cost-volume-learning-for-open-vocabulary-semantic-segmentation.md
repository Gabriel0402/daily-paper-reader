---
title: "DPSeg: Dual-Prompt Cost Volume Learning for Open-Vocabulary Semantic Segmentation"
title_zh: "DPSeg: 双提示代价卷学习用于开放词汇语义分割"
authors: "Zhao, Ziyu, Li, Xiaoguang, Shi, Lingjia, Imanpour, Nasrin, Wang, Song"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhao_DPSeg_Dual-Prompt_Cost_Volume_Learning_for_Open-Vocabulary_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 利用双提示和视觉语言模型的开放词汇语义分割
tldr: 针对开放词汇语义分割中图像与文本域差距以及缺乏浅层特征指导的问题，本文提出双提示框架DPSeg，包含双提示代价卷生成和代价卷引导解码器，弥补域差距并增强小物体和细节检测，提升分割精度。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 871, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1800, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 866, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1809, \"height\": 1056, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 860, \"height\": 248, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1812, \"height\": 990, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 876, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 835, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-dpseg-dual-prompt-cost-volume-learning-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 843, \"height\": 353, \"label\": \"Table\"}]"
motivation: 图像和文本嵌入之间的域差距以及缺乏浅层特征指导。
method: 提出双提示框架，结合双提示代价卷生成和代价卷引导解码器。
result: 提升小物体和细节分割精度。
conclusion: 有效解决开放词汇语义分割中的域差距问题。
---

## Abstract
Open-vocabulary semantic segmentation aims to segment images into distinct semantic regions for both seen and unseen categories at the pixel level. Current methods utilize text embeddings from pre-trained vision-language models like CLIP but struggle with the inherent domain gap between image and text embeddings, even after extensive alignment during training. Additionally, relying solely on deep text-aligned features limits shallow-level feature guidance, which is crucial for detecting small objects and fine details, ultimately reducing segmentation accuracy. To address these limitations, we propose a dual prompting framework, DPSeg, for this task. Our approach combines dual-prompt cost volume generation, a cost volume-guided decoder, and a semantic-guided prompt refinement strategy that leverages our dual prompting scheme to mitigate alignment issues in visual prompt generation. By incorporating visual embeddings from a visual prompt encoder, our approach reduces the domain gap between text and image embeddings while providing multi-level guidance through shallow features. Extensive experiments demonstrate that our method significantly outperforms existing state-of-the-art approaches on multiple public datasets.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：开放词汇语义分割旨在分割图像中所有像素，包括训练时未见过的类别。现有方法依赖CLIP等视觉语言模型的文本嵌入，但文本与图像嵌入之间存在**模态域差距**（modality gap），即使经过大规模对齐训练仍存在。此外，仅使用深层文本对齐特征会丢失浅层特征指导，导致小物体和细节分割不准确。
- **动机**：通过实验发现，视觉提示（由文本生成图像）与图像特征的相似度高于文本提示，且视觉提示生成的代价卷（cost volume）包含更丰富的空间语义信息。因此，提出结合视觉与文本提示的双提示框架，弥补域差距并利用多尺度特征。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用文本提示和由文本生成的视觉提示共同构建代价卷，减少跨模态差异；并通过多尺度视觉代价卷引导解码器，保留浅层细节。
- **关键技术细节**：
  - **双提示代价卷生成**：文本提示经CLIP文本编码器得到文本嵌入T；视觉提示由Stable Diffusion从文本生成，经视觉提示编码器得到视觉嵌入V。平均两者得到统一表示R = Avg(V + T)。与图像特征E计算余弦相似度得到代价卷Fc(x,y,k,m) = E(x,y)·R(k,m) / (||E(x,y)||·||R(k,m)||)。
  - **代价卷引导解码器（CVGD）**：多阶段解码器，每个阶段包含混合膨胀卷积（HD Conv）、MLP和自注意力。将不同尺度的图像特征Ej与对应的视觉提示特征Vj计算视觉代价卷Fjv（使用全局平均池化），然后与上采样后的代价卷特征拼接，逐步恢复分辨率。
  - **语义引导提示精炼**：两阶段推理。第一阶段生成初步分割结果；第二阶段用分割掩码裁剪出的对象替换对应类别的视觉提示，重新推理得到更精细的分割。

## 3. 实验设计
- **训练数据集**：COCO-Stuff（171类，118k训练图像）。
- **评估基准**：五个公开数据集——Pascal VOC (PAS-20)、Pascal Context (PC-59和PC-459)、ADE20K-150 (A-150)、ADE20K-847 (A-847)。
- **对比方法**：包括ZS3Net、LSeg、LSeg+、Han et al.、ZegFormer、SimSeg、OpenSeg、PACL、OVSeg、CAT-Seg、SAN、EBSeg、SCAN、SED等。使用相同骨干网络（ConvNeXt-B或ConvNeXt-L）进行公平对比。
- **评价指标**：mIoU（平均交并比）。

## 4. 资源与算力
- **训练配置**：2块NVIDIA V100 GPU，mini-batch size为4，训练80,000次迭代。
- **优化器**：AdamW，初始学习率2×10⁻⁴，权重衰减1×10⁻⁴，额外系数α=0.01。
- **冻结部分**：文本和视觉提示编码器冻结，只训练图像编码器和代价卷引导解码器。

## 5. 实验数量与充分性
- **定量实验**：在5个测试集上与约20种方法对比（Table 1），包含两种骨干规模（Base和Large）。
- **消融实验**：
  - 提示类型（文本/视觉/双提示）和代价卷生成策略（拼接/平均/双嵌入平均）—— Table 2。
  - 代价卷引导策略（仅Fc、逐步加入多尺度视觉代价卷F2v/F3v/F4v、上采样替代）—— Table 3。
  - 模板数量（1/10/20/40/80）—— Table 4。
  - 视觉提示生成质量（不同噪声/不同生成模型SD-v1.5/SD-v3/LayerDiffuse）—— Table 5。
- **定性实验**：分割可视化对比（Fig. 6）、代价卷可视化（Fig. 8）、两阶段推理效果（Fig. 7）。
- **充分性评价**：实验设计全面，覆盖主要变量，对比方法为当前SOTA且使用相同骨干，消融控制变量，结果客观公平。

## 6. 主要结论与发现
- DPSeg在所有数据集上显著超越现有方法，尤其在大规模VLM配置下（ConvNeXt-L）提升更明显（例如A-847上+1.8 mIoU，PAS-20上+2.4 mIoU）。
- 双提示（平均视觉和文本嵌入）优于单独使用任一模态；平均嵌入后计算代价卷优于其他融合方式。
- 多尺度视觉代价卷的渐进集成比直接上采样代价卷效果更好，能保留细粒度语义。
- 语义引导精炼（Inference II）进一步提升了约0.87-0.92 mIoU。
- 视觉提示即使使用含噪声图像也能优于纯文本提示，表明方法的鲁棒性。

## 7. 优点
- **方法创新**：首次系统性地将视觉提示引入开放词汇语义分割，通过双提示有效缓解模态域差距。
- **细节保留**：利用多尺度视觉代价卷避免了上采样带来的信息损失，在小物体和边界分割上表现突出。
- **两阶段精炼**：利用分割结果动态优化视觉提示，提升了与场景的对齐程度。
- **实验充分**：在多个数据集上进行广泛对比和消融，公平且结果领先；代码和模型开源。

## 8. 不足与局限
- **计算开销**：依赖Stable Diffusion生成视觉提示，且两阶段推理增加运行时间，可能不适合实时应用。
- **训练数据局限性**：仅在COCO-Stuff上训练，在不同场景（如医学、遥感）上的泛化性未验证。
- **模板依赖**：性能随模板数量增加而提升，但大规模模板带来更多计算和存储成本。
- **视觉提示质量敏感度**：虽然实验表明鲁棒，但极端低质量或与文本无关的视觉提示仍可能影响结果（文中未深入探讨）。
- **未见类别处理**：未专门分析对长尾或罕见类别的表现，可能仍存在偏差。

（完）
