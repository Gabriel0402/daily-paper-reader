---
title: Understanding Fine-tuning CLIP for Open-vocabulary Semantic Segmentation in Hyperbolic Space
title_zh: 理解双曲空间中对CLIP进行开放词汇语义分割的微调
authors: "Peng, Zelin, Xu, Zhengqin, Zeng, Zhilin, Wen, Changsong, Huang, Yu, Yang, Menglin, Tang, Feilong, Shen, Wei"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Peng_Understanding_Fine-tuning_CLIP_for_Open-vocabulary_Semantic_Segmentation_in_Hyperbolic_Space_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 双曲空间中微调CLIP以进行语义分割
tldr: 本文从层次对齐的角度解释为什么联合微调CLIP的视觉和文本编码器能提升开放词汇语义分割性能，利用双曲空间自然编码层次结构的特性，揭示了微调过程中图像嵌入从图像级向像素级转变的机理。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 830, \"height\": 835, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 871, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1790, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1809, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 626, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1855, \"height\": 1195, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 117, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 792, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1640, \"height\": 618, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-understanding-fine-tuning-clip-for-open-vocabulary-semantic-segmentation-in-hyperbolic-space-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 792, \"height\": 207, \"label\": \"Table\"}]"
motivation: 联合微调CLIP两个编码器能显著提升分割性能，但原因不明。
method: 利用双曲空间分析微调过程中图像嵌入层次的变化。
result: 发现微调后图像嵌入的双曲半径发生变化，对应层次对齐。
conclusion: 双曲空间为理解CLIP微调提供了新视角。
---

## Abstract
CLIP, a foundational vision-language model, has emerged as a powerful tool for open-vocabulary semantic segmentation. While freezing the text encoder preserves its powerful embeddings, recent studies show that fine-tuning both the text and image encoders jointly significantly enhances segmentation performance, especially for classes from open sets. In this work, we explain this phenomenon from the perspective of hierarchical alignment, since during fine-tuning, the hierarchy level of image embeddings shifts from image-level to pixel-level. We achieve this by leveraging hyperbolic space, which naturally encoders hierarchical structures. Our key observation is that, during fine-tuning, the hyperbolic radius of CLIP's text embeddings decreases, facilitating better alignment with the pixel-level hierarchical structure of visual data. Building on this insight, we propose HyperCLIP, a novel fine-tuning strategy that adjusts the hyperbolic radius of the text embeddings through scaling transformations. By doing so, HyperCLIP equips CLIP with segmentation capability while introducing only a small number of learnable parameters. Our experiments demonstrate that HyperCLIP achieves state-of-the-art performance on open-vocabulary semantic segmentation tasks across three benchmarks, while fine-tuning only approximately 4% of the total parameters of CLIP. More importantly, we observe that after adjustment, CLIP's text embeddings exhibit a relatively fixed hyperbolic radius across datasets, suggesting that the segmentation task has a characteristic level in hyperbolic space.

---

## 论文详细总结（自动生成）

# 论文《Understanding Fine-tuning CLIP for Open-vocabulary Semantic Segmentation in Hyperbolic Space》详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：开放词汇语义分割需要将预训练的视觉-语言模型（如CLIP）从图像级预测迁移到像素级预测。已有研究发现，联合微调CLIP的图像编码器和文本编码器比仅冻结文本编码器能取得更好的开放集分割性能，但该现象的原因尚不明确。
- **核心问题**：从层次对齐的角度解释这一现象——微调过程中，图像嵌入的层次级别从图像级（高层）转移到像素级（低层），而文本嵌入需要相应调整层次级别以实现更好的跨模态对齐。
- **研究背景**：双曲空间能够自然编码层次结构（距离中心越近，层次越低；越远，层次越高），通过双曲半径可以量化嵌入的层次级别。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：微调过程中文本嵌入的双曲半径会减小（向中心移动），以匹配像素级视觉嵌入的层次。因此，直接调整文本嵌入的双曲半径即可赋予CLIP分割能力，而无需大量微调。
- **关键技术细节**：
  - **HyperCLIP框架**：在CLIP的编码器中引入可学习的块对角缩放矩阵 \( \mathbf{S} \)，通过Möbius矩阵乘法在双曲空间中对特征嵌入进行缩放变换，从而调整其双曲半径。
  - **具体操作**：将欧氏空间的特征嵌入 \( \mathbf{z} \) 通过指数映射映射到双曲空间，应用Möbius矩阵乘法 \( \mathbf{S} \otimes_c \cdot \)，再通过对数映射返回欧氏空间：\( \mathbf{Sz} = \log_0^{D,c}( \mathbf{S} \otimes_c \exp_0^{D,c}(\mathbf{z}) ) \)。
  - **参数效率**：块对角矩阵由 \( K = d/n \) 个 \( n \times n \) 子块组成，总参数量为 \( d^2/K \)；可进一步共享子块或将 \( n=1 \) 降为对角矩阵（仅 \( d \) 个参数）。实验中使用 \( n=128 \)（约5.63M参数），仅占CLIP总参数的约4%。
  - **理论保证**：定理1证明缩放矩阵可以直接调整双曲半径，且满足单调性。

## 3. 实验设计：数据集、基准、对比方法
- **训练集**：COCO-Stuff（约118K张密集标注图像，171个类别）。
- **测试基准**：三个标准语义分割benchmark的六个测试集：
  - ADE20K（A-150、A-847）
  - PASCAL VOC（PAS-20、PAS-20b，含背景类）
  - PASCAL-Context（PC-59、PC-459）
- **评价指标**：mIoU（平均交并比）。
- **对比方法**：
  - 部分微调方法：ZS3Net、LSeg、OpenSeg、ZegFormer、ZSseg、OVSeg、ZegCLIP、ODISE、FC-CLIP等。
  - 选择性微调方法：SED、CAT-Seg。
  - 参数高效微调方法：SAN、LoRA、OFT、VPT、Adapter、SSF、HyperLoRA等。
- **额外任务**：开放词汇目标检测（COCO数据集，对比CLIM、CAT-Seg、LoRA、HyperLoRA）和开放词汇全景分割（ADE20K，对比ODISE、FC-CLIP、MAFT+）。

## 4. 资源与算力
- 论文明确说明：使用4块NVIDIA A800 GPU，训练80,000次迭代，每mini-batch一张图像（batch size=1）。学习率 \( 1\times10^{-5} \)，权重衰减 \( 10^{-4} \)，优化器Adam。
- 未提供训练总时间或显存消耗等细节。

## 5. 实验数量与充分性
- **实验数量**：共约8组主要实验，包括：
  - 与SOTA方法在6个测试集上的全面对比（表1）。
  - 开放词汇目标检测（表2）和全景分割（表3）的扩展实验。
  - 消融实验：块大小 \( n \) 的扫描（表4）、不同微调编码器组合（表6）、与其他PEFT方法对比（表6）、Möbius乘法的必要性（表7）、双曲半径控制（图5）。
  - 参数效率对比（表5）和定性结果可视化（图4）。
- **充分性与客观性**：实验设计较为全面，涵盖了多个数据集、多种任务和多种消融维度。对比方法均为近期公开方法，公平性较好。但未提供统计显著性检验或多次运行的标准差。

## 6. 论文的主要结论与发现
- 微调过程中文本嵌入的双曲半径减小（从约7.5降至约6.0），这是CLIP获得分割能力的关键。
- 通过直接缩放双曲半径（HyperCLIP）可以在仅微调约4%参数的情况下达到SOTA性能（ViT-B/16在A-847上12.3 mIoU，PC-459上19.2等；ViT-L/14上超越所有方法）。
- 调整后的文本嵌入在不同数据集上具有相对固定的双曲半径，表明该任务所需的粒度在双曲空间中可能可量化。
- HyperCLIP可泛化到目标检测和全景分割等其他需要对齐不同层次级别的任务。

## 7. 优点
- **新颖视角**：首次从双曲空间层次对齐角度解释CLIP微调机制，具有可解释性。
- **参数高效**：仅需极少量可学习参数（~4%）即可实现SOTA，优于多种PEFT方法。
- **无需额外架构**：不引入新的解码器或其他网络模块，仅修改前向传播中的矩阵乘法。
- **泛化性强**：在多个数据集、多种任务上均取得最优或次优结果，且定性结果显示分割精度高。

## 8. 不足与局限
- **实验覆盖的局限**：仅使用COCO-Stuff作为单一训练集，未考虑其他训练设置（如不同分割标注数据或零样本设置）下的泛化性。
- **偏差风险**：超参数（如块大小 \( n \)、曲率 \( c=0.01 \)）可能对结果敏感，但未提供详细鲁棒性分析。
- **应用限制**：目前仅验证了语义、检测、全景三种任务，尚未在更细粒度任务（如实例分割）或跨域场景（如医疗图像）中测试。
- **计算开销**：虽然参数量少，但双曲空间的指数/对数映射和Möbius乘法仍需额外计算时间，论文未提供推理速度对比。
- **半径固定性**：结论“固定半径”仅基于三个数据集，需要更多任务验证其普适性。

（完）
