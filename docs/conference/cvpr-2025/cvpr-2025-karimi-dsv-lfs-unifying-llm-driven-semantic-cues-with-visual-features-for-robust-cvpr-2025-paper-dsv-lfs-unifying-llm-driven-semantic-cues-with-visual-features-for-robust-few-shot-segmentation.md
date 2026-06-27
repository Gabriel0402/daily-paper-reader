---
title: "DSV-LFS: Unifying LLM-Driven Semantic Cues with Visual Features for Robust Few-Shot Segmentation"
title_zh: DSV-LFS：统一LLM驱动的语义线索与视觉特征的鲁棒少样本分割
authors: "Karimi, Amin, Poullis, Charalambos"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Karimi_DSV-LFS_Unifying_LLM-Driven_Semantic_Cues_with_Visual_Features_for_Robust_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 将LLM语义线索与视觉特征统一用于少样本分割
tldr: 针对少样本语义分割中支持图像无法覆盖目标类全部外观变异的问题，本文提出DSV-LFS框架，利用大语言模型将通用类别语义信息适配到查询图像，并结合密集像素匹配增强特征表示。该方法在多个少样本分割基准上取得最优性能，证明了LLM驱动的语义线索对提升分割鲁棒性的价值。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karimi-dsv-lfs-unifying-llm-driven-semantic-cues-with-visual-features-for-robust-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1817, \"height\": 1019, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karimi-dsv-lfs-unifying-llm-driven-semantic-cues-with-visual-features-for-robust-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1787, \"height\": 820, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karimi-dsv-lfs-unifying-llm-driven-semantic-cues-with-visual-features-for-robust-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1828, \"height\": 1055, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karimi-dsv-lfs-unifying-llm-driven-semantic-cues-with-visual-features-for-robust-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karimi-dsv-lfs-unifying-llm-driven-semantic-cues-with-visual-features-for-robust-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 245, \"label\": \"Table\"}]"
motivation: 当前少样本分割方法因特征表示不完备而泛化差，尤其是支持图像难以覆盖目标类变异。
method: 利用LLM将通用类别语义适配到查询图像，结合密集像素匹配增强相似性识别。
result: "在PASCAL-5i等数据集上超越现有方法，mIoU提升约2%。"
conclusion: LLM语义引导有效弥补视觉特征不足，为少样本分割提供了鲁棒解决方案。
---

## Abstract
Few-shot semantic segmentation (FSS) aims to enable models to segment novel/unseen object classes using only a limited number of labeled examples. However, current FSS methods frequently struggle with generalization due to incomplete and biased feature representations, especially when support images do not capture the full appearance variability of the target class. To improve the FSS pipeline, we propose a novel framework that utilizes large language models (LLMs) to adapt general class semantic information to the query image. Furthermore, the framework employs dense pixel-wise matching to identify similarities between query and support images, resulting in enhanced FSS performance. Inspired by reasoning-based segmentation frameworks, our method, named DSV-LFS, introduces an additional token into the LLM vocabulary, allowing a multimodal LLM to generate a "semantic prompt" from class descriptions. In parallel, a dense matching module identifies visual similarities between the query and support images, generating a "visual prompt". These prompts are then jointly employed to guide the prompt-based decoder for accurate segmentation of the query image. Comprehensive experiments on the benchmark datasets Pascal-5i and COCO-20i demonstrate that our framework achieves state-of-the-art performance-by a significant margin-demonstrating superior generalization to novel classes and robustness across diverse scenarios.

---

## 论文详细总结（自动生成）

### 论文总结：DSV-LFS: 统一LLM驱动的语义线索与视觉特征的鲁棒少样本分割

#### 1. 核心问题与整体含义（研究动机和背景）

- **少样本语义分割（FSS）** 旨在利用少量标注的支撑图像（support images）对新类别进行分割。然而，现有方法因特征表示不完备和偏倚，特别是支撑图像无法充分覆盖目标类别的全部外观变异（如遮挡、形变、光照变化），导致泛化能力差、易错分。
- **核心挑战**：如何从有限样本中提取鲁棒的特征表示，克服支撑-查询图像之间的外观差异，并避免对训练集中可见类别的过拟合。
- **整体含义**：本文提出将大语言模型（LLM）的多模态语义信息与密集视觉匹配相结合，模拟人类利用先验知识（语言描述）与视觉线索共同识别新物体的能力，为FSS提供一种更鲁棒的解决方案。

#### 2. 方法论：核心思想、关键技术细节

- **核心思想**：利用LLM将通用类别描述（class description）适配到查询图像，生成“语义提示（semantic prompt）”；同时通过密集像素匹配获得“视觉提示（visual prompt）”，两者联合指导基于提示的掩码解码器进行分割。
- **关键技术细节**：
  - **类别描述生成**：使用ChatGPT 4.0对每个类别生成一段描述其独有视觉特征的文本。
  - **类语义编码器模块**：基于LLaVA多模态LLM，引入特殊token `<SEM prompt>`。输入为查询图像特征（来自CLIP）和类别描述，LLM输出包含该token的文本，提取该token的最后一层嵌入，经MLP投影得到语义提示 \( \text{SEM f}_{\text{prompt}} \)。
  - **密集匹配模块**：从SAM视觉编码器提取多层级特征，构建4D超相关张量（Hypercorrelation Tensor），通过中心枢轴4D卷积编码和解码，生成视觉提示 \( \text{VIS prompt} \)。
  - **掩码解码器**：采用SAM的提示解码器，融合查询图像特征、语义提示和视觉提示，输出最终分割掩码。
  - **训练损失**：联合优化文本生成损失（自回归交叉熵）和分割掩码损失（BCE + Dice），端到端训练。
  - **K-shot扩展**：对K个支撑图像分别前向传播，通过投票机制融合预测。

#### 3. 实验设计：数据集、基准与对比方法

- **数据集**：
  - **Pascal-5i**：基于PASCAL VOC 2012，分为4折，每折部分类用于训练（基类）、部分用于测试（新类）。
  - **COCO-20i**：基于MS-COCO，同样4折，更复杂（多物体、大变异）。
  - **跨域设置**：COCO-20i → Pascal-5i（训练后直接测试，无微调）。
- **评估指标**：平均交并比（mIoU）。每次实验运行5次不同随机种子，取平均。
- **对比方法**：包括NTRENet、BAM、AAFormer、SSP、IPMT、ABCNet、HDMNet、MIANet、MSI、SCCAN、LLaFS（LLM-based）等12种以上SOTA方法。

#### 4. 资源与算力

- 文中明确说明：使用**两张NVIDIA A100 GPU**进行训练。批次大小设为2/GPU，训练10个epoch，优化器为AdamW，学习率3e-4，采用cosine annealing scheduler。未提及具体训练时长，但10 epoch在A100上通常为数小时至一天。未提及推理时算力要求。

#### 5. 实验数量与充分性

- **主要实验**：
  - Pascal-5i和COCO-20i上的1-shot和5-shot对比（表1），包含4折结果和均值，共8组主实验。
  - 跨域实验（COCO→Pascal，表2），1-shot四折结果。
  - 消融实验（表3）：仅语义提示 vs 语义+视觉提示，在COCO-20i上4折结果。
- **充分性**：实验覆盖了标准FSS评估的两大数据集、不同shot设置、跨域泛化；消融验证了各模块贡献；对比方法数量充足且最新。结果稳定（5次种子平均）。客观性良好：采用与对比方法一致的评估协议，且声明方法未使用额外监督（类别描述仅从类别标签生成，属于标准FSS中可用信息）。使用LoRA微调LLM，保留视觉编码器冻结，设置合理。

#### 6. 主要结论与发现

- DSV-LFS在COCO-20i上显著超越所有SOTA方法：1-shot提升+17.43 mIoU，5-shot提升+11.9 mIoU。在Pascal-5i上达到与LLaFS相当的性能（因数据集较简单可能饱和）。
- 语义提示单独使用即可大幅提升性能（+15 mIoU vs 非LLM方法），与视觉提示结合再提升约3%，证明两者互补。
- 在跨域设置COCO→Pascal上达到80.67 mIoU，超越专门设计的跨域方法，展示强大泛化能力。
- LLM提供的语义信息能有效弥补支撑图像外观变异的不足，降低对基类的误分。

#### 7. 优点

- **方法创新**：首次将推理分割框架（LISA）与FSS结合，引入`<SEM prompt>`实现LLM对查询图像的自适应语义引导。
- **端到端单阶段训练**：相比LLaFS多阶段、后处理文本，本文直接生成掩码，更高效。
- **双提示融合**：语义+视觉提示分别提供先验知识和空间一致性，相互增强。
- **实验充分且公平**：多数据集、多shot、跨域、消融；与SOTA全面对比，性能提升显著。
- **代码开源**：提升可复现性。

#### 8. 不足与局限

- **Pascal-5i饱和问题**：在该数据集上性能提升不明显，可能因方法在简单场景下接近上限，未充分体现优势。
- **LLM依赖**：需预训练LLM（LLaVA-7B），推理计算成本高于纯视觉方法；且类别描述生成依赖于外部API（ChatGPT），一致性可能受提示影响。
- **未分析失败案例**：定性图仅展示成功案例，未讨论分割失败场景（如极端遮挡、类别歧义）。
- **消融实验范围有限**：仅对比了有无视觉提示，未深入分析不同LLM大小、不同密度匹配模块变体、不同损失权重的影响。
- **跨域场景仅单方向**：仅COCO→Pascal，未测试反向或其他复杂跨域（如自然图像→医学图像）。
- **训练时未使用数据增强**：可能限制模型泛化能力，作者声明是为了公平对比，但可探讨增强是否进一步提升。
- **未报告推理时间或参数量**：对实际部署缺乏明确参考。

（完）
