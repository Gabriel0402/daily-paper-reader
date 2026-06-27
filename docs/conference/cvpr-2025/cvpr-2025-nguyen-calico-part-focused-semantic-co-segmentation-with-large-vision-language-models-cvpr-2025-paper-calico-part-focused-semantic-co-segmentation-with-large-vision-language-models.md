---
title: "CALICO: Part-Focused Semantic Co-Segmentation with Large Vision-Language Models"
title_zh: CALICO：基于大视觉语言模型的部件聚焦语义共分割
authors: "Nguyen, Kiet A., Juvekar, Adheesh, Yu, Tianjiao, Wahed, Muntasir, Lourentzou, Ismini"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Nguyen_CALICO_Part-Focused_Semantic_Co-Segmentation_with_Large_Vision-Language_Models_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 利用大视觉语言模型实现跨图像的部件级语义共分割
tldr: 现有LVLM难以处理跨图像的细粒度部件级分割推理。CALICO定义了部件聚焦语义共分割新任务，并首次提出能同时分割多图像中共享物体及其共有和独特部件的LVLM。通过新颖的对应提取模块实现跨图像特征对齐，在多个基准上展示了细粒度分割能力的突破。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1801, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1792, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 655, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1789, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 759, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 809, \"height\": 421, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nguyen-calico-part-focused-semantic-co-segmentation-with-large-vision-language-models-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 306, \"label\": \"Table\"}]"
motivation: LVLM在单图像文本驱动分割上表现出色，但跨图像的部件级分割推理能力不足。
method: 提出CALICO，首个专为多图像部件级推理分割设计的LVLM，包含对应提取模块实现跨图像特征对齐。
result: 在多图像部件级分割任务上取得领先性能，验证了细粒度语义推理能力。
conclusion: CALICO推动了LVLM在细粒度跨图像分割中的应用边界。
---

## Abstract
Recent advances in Large Vision-Language Models (LVLMs) have enabled general-purpose vision tasks through visual instruction tuning. While existing LVLMs can generate segmentation masks from text prompts for single images, they struggle with segmentation-grounded reasoning across images, especially at finer granularities such as object parts. In this paper, we introduce the new task of part-focused semantic co-segmentation, which involves identifying and segmenting common objects and their constituent common and unique parts across images. To address this task, we present CALICO, the first LVLM designed for multi-image part-level reasoning segmentation. CALICO features two key components, a novel Correspondence Extraction Module that identifies semantic part-level correspondences, and Correspondence Adaptation Modules that embed this information into the LVLM to facilitate multi-image understanding in a parameter-efficient manner. To support training and evaluation, we curate MixedParts, a large-scale multi-image segmentation dataset containing 2.4M samples across 44K images spanning diverse object and part categories. Experimental results demonstrate that CALICO, with just 0.3% of its parameters finetuned, achieves strong performance on this challenging task.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：现有的Large Vision-Language Models（LVLMs）在单图像文本驱动分割任务中表现优异，但在处理跨图像的多粒度分割推理——尤其是物体部件级别的比较与分割——时存在明显不足。例如，无法同时回答“两张图片中物体的共有部分是什么？”和“各图像中独特的部分是什么？”这类需要跨图像语义对应的问题。
- **整体含义**：本文首次系统定义了 **part-focused semantic co-segmentation（部件聚焦语义共分割）** 这一新任务，旨在跨多张图像识别并分割出共有的物体、共有部件以及独特部件，并为其赋予语义标签。该任务拓展了LVLMs在细粒度、多图像推理场景下的应用边界，对机器人操作、医学图像比较、教育视觉推理等有潜在价值。

## 2. 论文提出的方法论

- **核心思想**：以预训练的LVLM（Vicuna-7B）和SAM解码器为基础，通过引入轻量级的对应提取与适应模块，使模型能够学习跨图像的部件级语义对应，从而同时输出多图像的物体/部件分割图与语义标签。
- **关键技术细节**：
  - **整体架构**：输入多张图像，经EVA-CLIP编码器提取全局特征，再通过Q-Former降维为32个视觉token，与文本token交错输入LLM。LLM输出中包含特殊的`[SEG]` token，经过投影后作为SAM解码器的prompt，生成对应分割掩码。
  - **Correspondence Extraction Module (CEM)**：利用冻结的DINOv2提取富含语义对应关系的特征，与EVA-CLIP特征通过交叉注意力融合，得到语义增强的视觉表示。
  - **Correspondence Adaptation Modules (CAM)**：在LLM的特定中间层（第11层和第22层）注入从CEM获得的语义信息。具体地，将LLM当前层的最后一个文本token线性投影为query更新向量，与Q-Former的查询token相加，重新提取融合后的视觉特征，再残差加回该层的视觉token部分。
  - **训练目标**：联合优化文本下一个token预测损失（交叉熵）和分割掩码损失（focal loss + Dice loss），以平衡语义理解和像素分割。
  - **参数效率**：仅微调0.3%的模型参数（约2900万），保持其他部分冻结。

## 3. 实验设计

- **使用数据集**：作者构建了 **MixedParts** 数据集，包含约 **44,000张图像**、**240万个样本**（物体级和部件级掩码+标签）。来源包括PACO-LVIS、PartImageNet、ADE20K-Part-234等公开数据集，通过人工配对逻辑可比较的物体类别（如椅子和脚凳）生成跨图像对。
- **基准测试**：在MixedParts测试集（约1000对图像）上评估三个子任务（共有物体、共有部件、独特部件）的平均性能。对比方法包括：
  - **Cascade**：组合GPT-4V、DINOv2特征匹配和LISA的分割能力。
  - **PartGLEE**（零样本）
  - **VLPart**（零样本）
  - **Multi-Image GLaMM**（微调）
  - **Multi-Image LISA**（微调）
- **评估指标**：分割性能用AP50、mIoU、Recall；语义标签能力用Semantic Similarity（SS）和Semantic IoU（S-IoU）。

## 4. 资源与算力

- 论文致谢中提到使用了 **美国国家超算应用中心（NCSA）的Delta GPU集群**，通过ACCESS分配（分配号CIS240752等），但**未明确说明具体的GPU型号、总数量或训练时长**。仅提到模型参数量约29M可训练参数，训练开销较低。

## 5. 实验数量与充分性

- **主实验**：在MixedParts测试集上进行了完整的性能对比（Table 1），包含5个基线方法。
- **消融实验**：
  - 组件消融（Table 2）：分别移除Q-Former、DINOv2、CEM、CAM，以及同时移除CEM和CAM，共5组对比。
  - CAM注入层位置消融（Figure 8）：比较单层（16）、两层（11+22）、三层（8+16+24）的配置。
  - 效率对比（Figure 2）：与LISA和GLaMM比较推理时间和TFLOPS。
- **充分性评价**：实验覆盖了主要模块和关键超参数，对比基线包含了强零样本和微调方法，且控制了参数量与计算效率。但**仅在一个数据集上评测**，未在真实场景（如机器人、医学图像）或多于两张图像的情况下验证，通用性有待扩展。

## 6. 论文的主要结论与发现

- CALICO在所有指标上均超过所有基线，相对mIoU提升6.3%，召回率提升7.6%。
- 计算效率优势显著：使用18倍更少图像token，减少32.6% TFLOPS，推理速度加快51.3%。
- 每个组件均贡献显著：Q-Former对多图像处理至关重要；DINOv2和CEM提供了关键的语义对应信号；CAM在CEM存在时能有效注入上下文信息，且两层注入（11+22）效果最佳。
- 具备上下文感知能力：模型能根据输入图像对的组合，自适应地分割出当前语境中相关的物体，而非默认选择最显著物体。

## 7. 优点

- **任务创新**：首次定义并实现“部件聚焦语义共分割”，推动LVLM向细粒度、多图像推理发展。
- **参数高效**：仅微调0.3%参数，达到最优性能，避免灾难性遗忘，适合实际部署。
- **架构简洁有效**：Q-Former降低视觉token数量到32个，极大提升多图像处理效率；CEM+CAM模块轻量且可即插即用。
- **数据集建设**：构建MixedParts为后续研究提供标准化评测基准。
- **实验公平**：所有基线均在同一设置下微调或评估，并公开代码和模型。

## 8. 不足与局限

- **数据局限**：MixedParts来源于有限数量的公开数据集，物体和部件类别可能偏向常见类别，对罕见或域外物体的泛化能力未知。
- **评估范围**：仅在单一数据集上测试，缺乏跨数据集或真实场景（如机器人、医学图像）的验证，实际应用价值待检验。
- **多图像扩展性**：当前设计针对两张图像对，未探索三张及以上图像时的表现及输入长度变化带来的效率影响。
- **标签定义依赖**：部件定义依赖原始数据集的人工标注，可能存在歧义或标注偏差，影响模型学习的一致性。
- **幻觉风险**：LVLM在生成语义标签时可能产生与视觉内容不符的表述（如误标独特部件），论文虽用语义相似度评估，但未深入分析错误模式。
- **可解释性**：CEM和CAM内部的对应机制未可视化分析，难以确认模型是否真正学到语义对应。

（完）
