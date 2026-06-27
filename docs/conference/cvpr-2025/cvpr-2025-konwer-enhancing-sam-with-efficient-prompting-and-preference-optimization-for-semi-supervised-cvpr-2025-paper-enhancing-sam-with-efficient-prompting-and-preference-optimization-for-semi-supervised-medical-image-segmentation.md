---
title: Enhancing SAM with Efficient Prompting and Preference Optimization for Semi-supervised Medical Image Segmentation
title_zh: 利用高效提示和偏好优化增强SAM的半监督医学图像分割
authors: "Konwer, Aishik, Yang, Zhijian, Bas, Erhan, Xiao, Cao, Prasanna, Prateek, Bhatia, Parminder, Kass-Hout, Taha"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Konwer_Enhancing_SAM_with_Efficient_Prompting_and_Preference_Optimization_for_Semi-supervised_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: SAM微调用于半监督医学图像分割
tldr: SAM等基础模型在医学分割中依赖大量标注或专家提示。本文提出增强型SAM框架，无需监督即可生成高效提示，并结合偏好优化，在减少人工干预的同时保持分割精度。在多个医学数据集上验证了有效性。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-konwer-enhancing-sam-with-efficient-prompting-and-preference-optimization-for-semi-supervised-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-konwer-enhancing-sam-with-efficient-prompting-and-preference-optimization-for-semi-supervised-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1330, \"height\": 1049, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-konwer-enhancing-sam-with-efficient-prompting-and-preference-optimization-for-semi-supervised-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1812, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-konwer-enhancing-sam-with-efficient-prompting-and-preference-optimization-for-semi-supervised-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1633, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-konwer-enhancing-sam-with-efficient-prompting-and-preference-optimization-for-semi-supervised-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 788, \"height\": 408, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-konwer-enhancing-sam-with-efficient-prompting-and-preference-optimization-for-semi-supervised-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-konwer-enhancing-sam-with-efficient-prompting-and-preference-optimization-for-semi-supervised-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 303, \"label\": \"Table\"}]"
motivation: SAM在医学分割中需要大量标注或专家提示，成本高。
method: 无监督生成提示，结合偏好优化微调SAM。
result: 在医学图像分割任务上达到有竞争力的半监督性能。
conclusion: 该方法可降低SAM在特定领域应用的标注需求。
---

## Abstract
Foundational models such as the Segment Anything Model (SAM) are gaining traction in medical imaging segmentation, supporting multiple downstream tasks. However, such models are supervised in nature, still relying on large annotated datasets or prompts supplied by experts. Conventional techniques such as active learning to alleviate such limitations are limited in scope and still necessitate continuous human involvement and complex domain knowledge for label refinement or establishing reward ground truth. To address these challenges, we propose an enhanced Segment Anything Model (SAM) framework that utilizes annotation-efficient prompts generated in a fully unsupervised fashion, while still capturing essential semantic, location, and shape information through contrastive language-image pretraining and visual question answering. We adopt the direct preference optimization technique to design an optimal policy that enables the model to generate high-fidelity segmentations with simple ratings or rankings provided by a virtual annotator simulating the human annotation process. State-of-the-art performance of our framework in tasks such as lung segmentation, breast tumor segmentation, and organ segmentation across various modalities, including X-ray, ultrasound, and abdominal CT, justifies its effectiveness in low-annotation data scenarios.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：基础模型如 Segment Anything Model (SAM) 在医学图像分割中展现了强大潜力，但本质上是监督模型，严重依赖大规模标注数据集或专家提供的提示（点、框等）。传统方法如主动学习尽管试图减少标注需求，但仍需持续的人工参与和复杂领域知识进行标签细化或构建奖励函数。
- **核心问题**：如何在不依赖人类专家提示的情况下，生成高效、信息丰富的提示来引导 SAM 进行医学图像分割？同时，是否能够跳过显式奖励模型训练，利用简单的人类偏好反馈（如评分/排名）实现半监督学习？
- **整体含义**：本文提出一个增强的 SAM 框架，通过完全无监督的方式生成融合语义、位置和形状信息的提示，并引入直接偏好优化（DPO）技术模拟人工标注者的反馈，使得模型在低标注数据场景下仍能达到高保真分割性能，从而大幅降低医学图像分割对大规模标注数据的依赖。

## 2. 方法论：核心思想与关键技术细节

### 核心思想
- 结合多个预训练视觉-语言模型（BiomedCLIP、MedVInT、GPT-4）自动生成几何提示（边界框、点）和文本提示（疾病/器官特征、位置描述），无需人工干预。
- 利用直接偏好优化（DPO）的框架，通过模拟虚拟标注者对多候选分割的评分，直接优化策略网络，无需显式训练奖励模型。

### 关键技术细节
1. **无监督提示生成**
   - **视觉提示**：将图像和对应文本（如“chest X-ray”）输入 BiomedCLIP，使用 gScoreCAM 生成显著性图，经条件随机场（CRF）后处理得到粗分割，提取最大连通分量的边界框和随机点。
   - **文本提示**：
     - 使用 MedVInT（VQA 模型）回答关于目标形状和位置的问题（如“肝脏的形状和位置？”）。
     - 使用 GPT-4 生成关于疾病/器官的通用描述。
     - 将上述两个文本提示拼接后输入 SAM 的提示编码器。
   - **提示编码与掩码解码**：沿用 SAM 的提示编码器（支持点、框、文本），将嵌入投影到 256 维；特征图经下采样后与视觉嵌入逐元素相加，最终由掩码解码器输出分割图。

2. **偏好对齐模块（DPO 激励）**
   - **候选生成**：对 SAM 输出概率进行不同阈值（如 0.3, 0.5, 0.7, 0.9）采样，生成 4 个分割候选 Y1~Y4。
   - **虚拟标注**：基于候选与真实标注的 Dice 重叠度，从高到低赋予评分 (Y1 最佳, Y4 最差)。注意：此阶段不直接使用 GT 进行监督，仅用于模拟人类评分（被动参考）。
   - **DPO 损失函数**：借鉴 DPO 思想，修改为多候选损失：
     \[
     L_{DPO}(\pi_\psi; \pi_{\text{fine}}) = -\mathbb{E}_{(I, Y1, Y2, Y3, Y4) \sim \mathcal{D}} \left[ \log \sigma\left( \beta_1 \log \frac{\pi_\psi(Y1|I)}{\pi_{\text{fine}}(Y1|I)} + \beta_2 \log \frac{\pi_\psi(Y2|I)}{\pi_{\text{fine}}(Y2|I)} - \beta_2 \log \frac{\pi_\psi(Y3|I)}{\pi_{\text{fine}}(Y3|I)} - \beta_1 \log \frac{\pi_\psi(Y4|I)}{\pi_{\text{fine}}(Y4|I)} \right) \right]
     \]
     其中 \(\pi_{\text{fine}}\) 为第一阶段的微调模型，\(\pi_\psi\) 为最终模型，\(\beta_1, \beta_2\) 为权重（最佳和最差惩罚更高）。

3. **两阶段训练流程**
   - **第一阶段**：使用 10% 的标注数据，微调整个框架（视觉编码器、提示编码器、掩码解码器），损失为 Focal Loss : Dice Loss = 20:1。
   - **第二阶段**：利用剩余 90% 的无标注数据（仅需 GT 进行评分模拟），冻结第一阶段参数作为参考策略，使用 DPO 损失微调解码器，实现半监督学习。

## 3. 实验设计

### 数据集与场景
| 任务 | 数据集 | 图像类型 | 规模 |
|------|--------|----------|------|
| 肺分割 | COVID-QU-Ex | X 光（2D） | 27,132 张 |
| 乳腺肿瘤分割 | BUSI + UDIAT | 超声（2D） | 810 张（600 训练, 210 测试） |
| 腹部器官分割 | AMOS-CT | CT（3D） | 200 个标注 CT 扫描 |

### Benchmark 与对比方法
- **对比方法**：U-Net、nnU-Net、SAM、SAM-Med2D、Self-prompt（[57] 变体，去掉知识蒸馏），以及提示仅版本的 baseline。
- **评估指标**：Dice 相似系数、IoU、表面 Dice（SDC）。

## 4. 资源与算力

- **文中明确说明**：实验在 PyTorch 框架下完成，使用 EC2 实例（64 GB NVIDIA T4 Tensor Core GPU）。但未给出具体 GPU 数量、训练总时长或模型参数规模。训练 epoch：第一阶段 15 个 epoch，第二阶段 30 个 epoch，学习率 1e-4（每 10 epoch 减半）。
- **说明**：算力信息不够详细，无法定量评估训练成本。

## 5. 实验数量与充分性

- **实验数量**：
  - 定量对比实验（图 3）：在 3 个数据集上，针对不同标注比例（10%, 20%, 50%, 100%）对比多个 SOTA 方法，共约 4×7=28 个点（含变体）。
  - 消融实验（表 1）：验证 BiomedCLIP、VQA、GPT-4、对齐模块的贡献，共 6 行对比。
  - 偏好评分策略消融（表 2）：比较“仅最佳候选”、“评分制”、“排名制”，以及不同无标注数据量（10%, 20%, 40%）。
  - 噪声评级鲁棒性实验：文中提及但结果放在补充材料，未在正文中展示。
  - 定性结果（图 4、图 5）：展示 3 个数据集的典型分割图和显著性图。

- **充分性与客观性**：
  - 实验覆盖了 2D 和 3D 多模态医学分割任务，对比方法涵盖经典（U-Net, nnU-Net）和最新 SAM 变体。
  - 消融实验系统性地剥离每个模块，支持方法有效性。
  - 在不同数据比例下重复实验，结果具有统计意义。
  - 但缺少对超参数（如 β1, β2）的详细敏感性分析，也未报告方差或置信区间（如箱线图）。

## 6. 主要结论与发现

- 本文提出的无监督提示生成（结合 BiomedCLIP、VQA、GPT-4）显著提升了弱监督信号质量，比 Self-prompt 等仅依赖自提示的方法性能更好。
- DPO 驱动的偏好对齐模块能够在无标注数据上持续提升性能，且优于“仅最佳候选”的简单评分方法。
- 在低标注比例（10%-20%）下，本方法全面超越 U-Net、nnU-Net、SAM、SAM-Med2D、Self-prompt 等 SOTA 模型；在 50% 标注时，性能接近全监督 prompt-only 版本。
- 排名策略（Ranking）比评分（Rating）和最佳候选策略效果更好；增加无标注数据量可进一步提升性能。

## 7. 优点

1. **完全无监督的提示生成**：无需人工标注的几何或文本提示，利用多个预训练模型自动提取语义、位置和形状信息，大幅降低数据准备成本。
2. **新颖的 DPO 偏好对齐**：将语言模型中的 DPO 思想引入医学图像分割，用简单的候选评分替代复杂的奖励函数训练，实现端到端优化，易于实现且训练高效。
3. **弱监督 / 半监督性能突出**：在仅 10%-20% 标注数据下达到甚至超过部分全监督方法，对资源稀缺的医学场景极具实用价值。
4. **跨模态泛化能力**：在 X 光、超声、CT 三种模态上均取得一致优势，方法具有一定的通用性。

## 8. 不足与局限

1. **虚拟标注依赖真实标注**：第二阶段候选的评分仍然需要 GT 来计算重叠度（Dice），因此实验中的“无标注数据”实为“需隐藏 GT 进行评分模拟”，与真正无标注场景存在差距。若没有 GT，如何获取真实人类偏好评分？文中未给出实际替代方案。
2. **计算开销与资源消耗模糊**：未提供 GPU 数量、总训练时间、模型参数量等关键计算指标，难以评估实际部署成本。
3. **超参数与鲁棒性分析不足**：DPO 损失中的 β1, β2 如何选取？对噪声评级的实验仅放在补充材料，缺乏系统性的敏感性分析。
4. **对比不够全面**：未与最近的其他半监督医学分割方法（如基于一致性正则化或伪标签的 SOTA）进行对比；SAM 变体仅对比了 SAM-Med2D 和 Self-prompt，未包含 SAM-Med3D 的完整版（仅在 3D 任务中比较）。
5. **数据集规模与多样性有限**：仅在三个公开数据集上验证，且乳腺超声仅有 810 张图像，腹部 CT 仅 200 例，缺乏更大规模、更多样化（如 MRI、病理切片）的评估。
6. **潜在偏差**：提示生成高度依赖预训练的 CLIP、VQA、GPT-4 模型，这些模型可能带有训练数据自身的偏差（如种族、性别、疾病类型分布），可能导致分割结果对特定人群或病征有倾向性。

（完）
