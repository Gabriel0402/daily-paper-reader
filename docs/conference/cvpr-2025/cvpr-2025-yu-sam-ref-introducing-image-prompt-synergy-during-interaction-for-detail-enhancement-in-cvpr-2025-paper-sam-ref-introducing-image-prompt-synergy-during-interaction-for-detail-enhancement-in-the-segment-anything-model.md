---
title: "SAM-REF: Introducing Image-Prompt Synergy during Interaction for Detail Enhancement in the Segment Anything Model"
title_zh: SAM-REF：交互过程中引入图像-提示协同以增强Segment Anything Model细节
authors: "Yu, Chongkai, Liu, Ting, Li, Anqi, Qu, Xiaochao, Wu, Chengjing, Liu, Luoqi, Hu, Xiaolin"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Yu_SAM-REF_Introducing_Image-Prompt_Synergy_during_Interaction_for_Detail_Enhancement_in_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 通过图像-提示协同增强SAM细节提取
tldr: 本文针对Segment Anything Model（SAM）在交互式分割中细节提取能力不足的问题，提出SAM-REF，在交互过程中引入图像-提示协同机制，在不增加额外延迟的前提下显著提升分割细节质量，为SAM的进一步应用提供了改进方向。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 797, \"height\": 937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1656, \"height\": 1510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1737, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 786, \"height\": 483, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1641, \"height\": 562, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1908, \"height\": 784, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 655, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 696, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-sam-ref-introducing-image-prompt-synergy-during-interaction-for-detail-enhancement-in-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 621, \"height\": 248, \"label\": \"Table\"}]"
motivation: SAM在延迟交互策略中细节提取能力受限。
method: 设计图像-提示协同模块，在每次交互中融合图像和提示特征。
result: 在多个基准上分割细节得到显著提升。
conclusion: 图像-提示协同是提升SAM细节的有效途径。
---

## Abstract
Interactive segmentation is to segment the mask of the target object according to the user's interactive prompts. There are two mainstream strategies: early fusion and late fusion. Current specialist models utilize the early fusion strategy that encodes the combination of images and prompts to target the prompted objects, yet repetitive complex computations on the images result in high latency. Late fusion models extract image embeddings once and merge them with the prompts in later interactions. This strategy avoids redundant image feature extraction and improves efficiency significantly. A recent milestone is the Segment Anything Model (SAM). However, this strategy limits the models ability to extract detailed information from the prompted target zone. To address this issue, we propose SAM-REF, a two-stage refinement framework that fully integrates images and prompts by using a lightweight refiner into the interaction of late fusion, which combines the accuracy of early fusion and maintains the efficiency of late fusion. Through extensive experiments, we show that our SAM-REF model outperforms the current state-of-the-art method in most metrics on segmentation quality without compromising efficiency.

---

## 论文详细总结（自动生成）

# 论文中文总结：SAM-REF：交互过程中引入图像-提示协同以增强Segment Anything Model细节

## 1. 核心问题与研究动机
- **背景**：交互式图像分割分为**早期融合**（Early Fusion）和**晚期融合**（Late Fusion）两大策略。
  - 早期融合（如FocalClick、SimpleClick）在每次交互时联合编码图像和提示，精度高，但计算冗余导致高延迟。
  - 晚期融合（如SAM）仅提取一次图像特征，后续交互时融合提示，效率高，但因缺失图像与提示的深层交互，难以捕捉目标区域的细节信息。
- **核心问题**：SAM等晚期融合模型在分割质量上（尤其是复杂细节、薄物体等）表现不足，而早期融合模型效率低下。
- **整体目标**：设计一个方法，既能保持晚期融合的高效率，又能利用早期融合的精度优势，显著提升细节分割能力。

## 2. 方法论：核心思想与技术细节
- **核心思想**：在SAM的晚期融合框架基础上，增加一个轻量级**细化器**（Lightweight Refiner），在交互过程中重新引入图像与提示的融合，从全局和局部两个角度增强细节。
- **整体流程**：SAM先产生粗分割掩码，然后由细化器进一步处理得到精细掩码。
- **关键模块**：
  - **Global Fusion Refiner (GFR)**：将原始图像、密集表示的提示（disk map）、粗掩码以及SAM的图像嵌入进行融合，通过残差块提取全局细节，并生成一个误差图，用于与SAM粗掩码进行加权融合，替换错误区域。
  - **Local Fusion Refiner (LFR)**：根据提示和交互历史，裁剪目标区域（最大连通差异区域），在该局部区域再次进行图像-提示融合，进一步细化局部细节，并同样使用误差图融合。
  - **Dynamic Selector (DS)**：自适应选择将局部细化结果粘贴到全局结果（M_Gr）还是上一次的掩码（M_{t-1}），以平衡全局重新预测和局部保留。
- **公式环节**（文字说明）：
  - GFR融合特征：F(0) = I + D + \hat{F}_{Enc}
  - 迭代残差块：F(i+1) = ResBlock(F(i)) + \hat{F}_{Enc}
  - 最终掩码融合：M_Gr = σ(E_G) ⊙ \bar{M}_Gr + (1-σ(E_G)) ⊙ M_S_t
  - LFR类似。
  - 动态选择器基于误差比例R_e = ||H(E_G_t)||_0 / ||H(E_G_{t-1})||_0 判断，阈值θ=1.1。
- **损失函数**：包括Normalized Focal Loss、Dice Loss、BCE Loss以及加权NFL损失，分别用于SAM解码器、GFR和LFR的误差头和细化输出。

## 3. 实验设计
- **数据集**：
  - **训练集**：COCO + LVIS（主流配置）和HQSeg-44K（高质量数据集）。
  - **评估集**：零样本测试于GrabCut、Berkeley、DAVIS、SBD以及HQSeg-44K验证集。
- **基准指标**：mIoU（5次点击）、NoC90/NoC95（达到指定IoU所需点击次数）、NoF95（20次内失败数）、SPC（每次点击秒数）、SAT Latency（全任务延迟）。
- **对比方法**：
  - 早期融合：FocalClick、SimpleClick、RITM、PseudoClick等。
  - 晚期融合：SAM、HQ-SAM、FocSAM、InterFormer、SegNext等。
- **公平性**：所有SAM-REF实验均冻结SAM图像编码器，仅训练细化器参数，并与其他SAM-based方法（如FocSAM、HQ-SAM）采用相同冻结方式，确保公平对比。

## 4. 资源与算力
- **硬件**：4块NVIDIA Tesla V100-PCIE-32GB GPU + Intel Xeon Gold 6278C CPU。
- **训练策略**：两阶段训练：先微调SAM解码器320k步（batch size=4），再训练SAM-REF 80k步。利用预提取图像嵌入加速训练。
- **未明确说明总训练时长**，但提及使用预存储嵌入策略极大减少计算开销。

## 5. 实验数量与充分性
- **主要实验结果**：在两个训练配置（COCO+LVIS、HQSeg-44K）下，在四个标准基准（GrabCut等）和一个高质量基准上报告NoC90/NoC95；同时给出SAT Latency和SPC。
- **消融实验**：共3组：
  - 组件消融（是否使用LFR、粘贴策略、动态选择器）——4种设置。
  - ResBlock数量消融（1/3/5/8）——4种设置。
  - 计算分析（参数量、FPS、显存）——对比SAM。
- **定性分析**：提供可视化结果（图3、图4）。
- **充分性评价**：实验覆盖多数据集、多指标、多消融点，且与SOTA方法进行系统对比。但缺少在大规模多样本上的统计显著性检验，也未提供不同初始点或噪声下的鲁棒性分析。

## 6. 主要结论与发现
- SAM-REF在**所有主要基准**（GrabCut、Berkeley、DAVIS、SBD）上，以NoC90为指标达到**最优**；在更严格的NoC95上，除个别数据集略逊于SimpleClick外，整体领先。
- 在高质量数据集HQSeg-44K上，SAM-REF在5-mIoU、NoC90、NoC95、NoF95等所有指标上均超越SAM、HQ-SAM、FocSAM等。
- 计算开销极低：仅增加0.7MB参数、0.1秒SPC（相对SAM），保持晚期融合的高效率。
- 动态选择器有效避免重复修改优良区域，进一步改善精度。

## 7. 优点
- **方法创新**：巧妙结合早期融合和晚期融合优势，通过轻量级细化器在交互过程中重新引入图像-提示协同，避免大规模重计算。
- **高效性**：参数量和推理时间几乎不增加（相比SAM），适合实际部署。
- **通用性**：基于SAM设计，可轻松适配不同规模的SAM主干（ViT-B、ViT-H）。
- **细节增强明显**：从定性结果可见，在薄结构、空洞区域等困难场景提升显著。
- **实验全面**：涵盖多种数据集、指标、消融和计算分析。

## 8. 不足与局限
- **局限性**：
  - 动态选择器的阈值θ=1.1通过实验设定，未做更系统的敏感度分析。
  - 训练仍依赖两阶段策略，需要先微调解码器，增加训练复杂度。
  - 仅在交互式分割任务上验证，未探讨在其他下游任务（如视频分割、医学图像）的泛化性。
  - 未提供对点噪声或异常输入的鲁棒性分析。
  - 未与最近的多模态大模型（如Grounded SAM）结合进行评测。
- **实验覆盖**：虽然数据集多样，但规模不大（GrabCut仅50张，Berkeley约100张），在更大更复杂的数据集（如SA-1B）上的表现未知。
- **偏差风险**：模型训练基于COCO+LVIS或HQSeg-44K，可能存在领域偏差，在边缘场景（如特定纹理、低对比度图像）效果未知。

（完）
