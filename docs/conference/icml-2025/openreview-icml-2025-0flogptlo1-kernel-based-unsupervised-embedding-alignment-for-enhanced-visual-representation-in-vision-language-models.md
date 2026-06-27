---
title: Kernel-based Unsupervised Embedding Alignment for Enhanced Visual Representation in Vision-language Models
title_zh: 基于核的无监督嵌入对齐用于增强视觉语言模型的视觉表示
authors: "Shizhan Gong, Yankai Jiang, Qi Dou, Farzan Farnia"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=0fLoGPTLo1"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 改进视觉语言模型的视觉表示以提升下游任务
tldr: 论文指出CLIP视觉表示对细节感知不足，影响下游MLLM性能。提出一种基于核的无监督嵌入对齐方法，将CLIP视觉表示与DINOv2的细粒度特征对齐，同时保持与文本嵌入的兼容性。实验证明该方法在多种感知任务上提升性能，为提升VLM基础能力提供了轻量级解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1737, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 807, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1736, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1736, \"height\": 350, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 784, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1776, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 885, \"height\": 583, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 627, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1562, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 926, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1773, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1616, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 844, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1773, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1773, \"height\": 420, \"label\": \"Table\"}]"
motivation: CLIP等VLM的细粒度感知能力有限，导致下游MLLM失败。
method: 提出基于核的方法，将CLIP的视觉表示与DINOv2的细粒度特征对齐，保持文本兼容性。
result: 对齐后的视觉表示在多个细粒度任务上显著提升性能。
conclusion: 无监督嵌入对齐能有效增强VLM的感知能力，无需重新训练。
---

## Abstract
Vision-language models, such as CLIP, have achieved significant success in aligning visual and textual representations, becoming essential components of many multi-modal large language models (MLLMs) like LLaVA and OpenFlamingo. However, numerous studies have identified CLIP's limited fine-grained perception as a critical drawback, leading to substantial failures in downstream MLLMs. In contrast, vision-centric foundation models like DINOv2 demonstrate remarkable capabilities in capturing fine details from images. In this work, we propose a novel kernel-based method to align CLIP's visual representation with that of DINOv2, ensuring that the resulting embeddings maintain compatibility with text embeddings while enhancing perceptual capabilities. Our alignment objective is designed for efficient stochastic optimization. Following this image-only alignment fine-tuning, the visual encoder retains compatibility with the frozen text encoder and exhibits significant improvements in zero-shot object recognition, fine-grained spatial reasoning, and localization. By integrating the aligned visual encoder, downstream MLLMs also demonstrate enhanced performance. The code and models are available at https://github.com/peterant330/KUEA.

---

## 论文详细总结（自动生成）

# 论文总结：基于核的无监督嵌入对齐用于增强视觉语言模型的视觉表示

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：CLIP等视觉语言模型（VLM）在图像-文本对齐上表现出色，但由于其训练依赖全局图像描述监督，导致对颜色、空间关系、计数等**细粒度视觉细节**的感知能力不足。这影响了CLIP自身在密集预测、零样本分类上的表现，也限制了将其作为视觉编码器的下游多模态大语言模型（MLLM，如LLaVA、OpenFlamingo）的感知能力。
- **现有方案局限**：已有工作尝试融合多个视觉编码器（如CLIP+DINOv2），但带来大量计算开销；或者对CLIP进行有监督微调，但可能破坏其与文本编码器的对齐，且需要重新训练下游模型，成本高昂。
- **整体含义**：本文旨在**仅通过图像数据微调CLIP视觉编码器**，使其获得类似DINOv2的细粒度感知能力，同时**保持与原始文本编码器的兼容性**，从而提升VLM及下游MLLM的性能，且无需重新训练文本/LLM部分。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用核函数（Kernel function）度量两两样本之间的相似性，将CLIP视觉表示与DINOv2视觉表示的**核矩阵**对齐，从而在保持特征空间宏观结构的前提下，调整样本间的相对关系，使CLIP学习到DINOv2所擅长的视觉细节。
- **关键技术细节**：
  - **核函数选择**：使用归一化多项式核（degree=3），可灵活捕捉非线性关系。
  - **对齐损失**：最小化CLIP核函数值与DINOv2核函数值之间的均方误差：
    \[
    \min_\theta \mathbb{E}_{I_i,I_j\sim D}\left[\bigl(k_1(f_\theta(I_i),f_\theta(I_j)) - k_2(g(I_i),g(I_j))\bigr)^2\right]
    \]
    其中 \(k_1\) 为CLIP核（参数可训练），\(k_2\) 为DINOv2核（固定）。
  - **正则项**：添加L2距离约束，防止对齐后的视觉特征偏离原始CLIP特征太远，从而守卫与文本编码器的对齐：
    \[
    \mathbb{E}_{I_i\sim D}\left[\|f_\theta(I_i) - f_{\theta_0}(I_i)\|_2^2\right]
    \]
  - **最终目标**：两项加权求和，权重系数 \(w\) 平衡核对齐与特征保真。
  - **优化方式**：通过随机采样图像对进行小批量梯度下降，利用Hoeffding不等式保证梯度估计的无偏性和收敛性，使得框架可扩展到大规模数据集。
- **算法流程**：固定DINOv2和原始CLIP文本编码器，使用ImageNet-1K训练集，每步随机采样一批图像对，计算核对齐损失和正则损失，更新CLIP视觉编码器参数。微调仅2个epoch即可收敛。

## 3. 实验设计：数据集、Benchmark、对比方法
- **评测任务与数据集**：
  - **零样本图像分类**：12个数据集，包括通用（ImageNet、CIFAR-10/100、CalTech101）、细粒度（OxfordPets、DTD、FER2013）、领域特定（PCAM、RESISC45、EuroSAT）以及分布外（ImageNet-O、ImageNet-Sketch）。
  - **图像-文本检索**：Flickr30K和MSCOCO。
  - **计数/空间/文本感知**：SVHN、GTSRB、CLEVR Distance、CLEVR Counts。
  - **定位能力**：MSCOCO上的局部/全局探测（probing）benchmark（Covert et al. 2025）。
  - **下游MLLM**：LLaVA-1.5-7B（12个VQA基准，包括VQAv2、RefCOCO、POPE、TallyQA等）和OpenFlamingo-3B（7个数据集，如COCO、OK-VQA、HatefulMemes）。
  - **其他VLM**：SigLIP、DFN、MetaCLIP。
- **对比方法**：
  - 线性投影（将DINOv2映射到CLIP空间）
  - 直接特征对齐（Feature-based alignment）
  - DIVA（Wang et al. 2025，基于扩散模型）
  - AM-RADIO（多教师蒸馏）
  - Additive-MoF（简单特征融合）
- **评估标准**：零样本分类准确率、检索R@1/5/10、VQA准确率、CIDEr、ROC AUC等。

## 4. 资源与算力
- 文中明确说明：使用 **2张 NVIDIA RTX 4090 GPU** 对 ViT-L-14 进行对齐微调，耗时约 **30小时**；对于更大模型 ViT-L-14-336 使用4张GPU，训练4个epoch。
- 此外，LLaVA的LoRA微调在4张4090 GPU上进行。
- 总体而言，该方法的计算需求远低于CLIP预训练或DIVA等方法，属于**轻量级微调**。

## 5. 实验数量与充分性
- **数量**：非常充分。包括：
  - 3种CLIP骨干（ViT-B-16、ViT-L-14、ViT-L-14-336）
  - 零样本分类12个数据集 + 检索2个数据集 + 计数/空间4个数据集 + 探测1个数据集 + MLLM两种模型（LLaVA、OpenFlamingo）共约20+数据集
  - 消融实验：训练轮数、正则项系数、核函数类型、数据集大小等
  - 扩展到其他VLM（SigLIP、DFN、MetaCLIP）和其他目标模型（MLCD）
- **充分性与公平性**：
  - 对比基线包括多种主流方法（DIVA、AM-RADIO、Additive-MoF），且使用了官方或标准评估代码（CLIP-Benchmark）。
  - 消融实验系统探讨了各组件作用，结果稳健。
  - 在MLLM评测中，控制了LLM部分是否微调的条件，证明增益主要来自视觉编码器的改进。
- **客观性**：实验结果报告了多数情况下的平均准确率，并展示了提升幅度的一致性和细节（如低分辨率、小物体数据集提升更明显）。

## 6. 主要结论与发现
- 所提出的**核对齐微调**能够在不使用任何文本数据的情况下，显著增强CLIP视觉编码器的细粒度感知能力，零样本分类平均准确率提升约1-1.3%（ViT-L系列）。
- 对齐后的视觉编码器**保持与原始文本编码器的兼容性**，检索任务性能不降反升。
- 在计数、空间推理、文本识别等CLIP弱项上，对齐后提升显著（如CLEVR Counts线性探针从41.25%提升至49.67%）。
- 将对齐后的视觉编码器直接替换到LLaVA和OpenFlamingo中，无需额外训练LLM即可提升VQA性能，若结合LoRA微调则进一步提升（平均+1.66%）。
- 方法对不同的VLM（SigLIP、DFN、MetaCLIP）和不同的目标模型（MLCD）均适用，具有良好泛化性。
- 核函数的选择对性能影响不大，但多项式核效果最优；正则项对保持文本对齐至关重要。

## 7. 优点
- **轻量高效**：仅需少量图像数据（ImageNet-1K）和短时间微调（2 epoch），计算成本远低于预训练或基于扩散的方法。
- **保持兼容性**：通过正则化项的设计，对齐后的特征能与原始文本编码器及下游MLLM无缝衔接，无需重新训练文本/LLM部分。
- **通用性强**：适用于多种CLIP同族模型（SigLIP等）和多种目标模型（DINOv2、MLCD），展示了方法的可迁移性。
- **理论支撑**：基于Hoeffding不等式给出了随机梯度估计的收敛保证，并证明了正则项对语言-图像对齐的保界。
- **充分的实验验证**：覆盖了大量标准和细粒度基准，并通过消融实验验证了各组件的必要性。

## 8. 不足与局限
- **训练数据规模有限**：仅在ImageNet-1K（1.28M图像）上微调，作者指出在更大规模数据集（如DataComp）上可能获得更优结果，但未验证。
- **下游MLLM仅测试较小规模**：仅测试了LLaVA-1.5-7B和OpenFlamingo-3B，未在70B级大模型上验证，可扩展性未知。
- **目标模型依赖单一**：主要使用DINOv2作为目标，虽尝试了MLCD，但未充分探索更多自监督视觉模型（如MAE、iBot等）。
- **核函数选择有待优化**：仅比较了三种核函数，未尝试组合核或自适应核，可能仍有提升空间。
- **潜在偏差风险**：ImageNet-1K数据集本身存在分布偏差，对齐后可能继承DINOv2的某些偏差，文中未讨论公平性分析。
- **应用限制**：方法仅优化视觉表示，无法解决LLM本身的幻觉或推理错误，且需要目标模型（如DINOv2）存在并提取特征。

（完）
