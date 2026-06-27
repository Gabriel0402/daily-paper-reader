---
title: "VladVA: Discriminative Fine-tuning of LVLMs"
title_zh: "VladVA: 大型视觉语言模型的判别性微调"
authors: "Ouali, Yassine, Bulat, Adrian, Xenos, Alexandros, Zaganidis, Anestis, Metaxas, Ioannis Maniadis, Martinez, Brais, Tzimiropoulos, Georgios"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Ouali_VladVA_Discriminative_Fine-tuning_of_LVLMs_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 4.0
evidence: 大型视觉语言模型的判别性微调方法
tldr: 针对生成式LVLM不适合判别任务而对比式VLM语言理解有限的问题，本文提出将生成式LVLM转换为判别式模型的微调方法，保留详细推理能力的同时获得强判别性和组合能力，为VLM在多种应用中的使用提供新思路。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1200, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 873, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1805, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 539, \"height\": 294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1279, \"height\": 372, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1802, \"height\": 684, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1621, \"height\": 768, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 775, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-ouali-vladva-discriminative-fine-tuning-of-lvlms-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 336, \"label\": \"Table\"}]"
motivation: 生成式LVLM不适合判别任务，而对比式VLM语言理解有限。
method: 提出将生成式LVLM转换为判别式模型的微调方法，结合两者优势。
result: 获得强判别性和组合能力。
conclusion: 实现判别式LVLM的有效微调，可应用于VLM系统。
---

## Abstract
Contrastively-trained Vision-Language Models (VLMs) like CLIP have become the de facto approach for discriminative vision-language representation learning. However, these models have limited language understanding, often exhibiting a "bag of words" behavior. At the same time, Large Vision-Language Models (LVLMs), which combine vision encoders with LLMs, have been shown to be capable of detailed vision-language reasoning, yet their autoregressive nature renders them less suitable for discriminative tasks. In this work, we propose to combine "the best of both worlds": a new training approach for discriminative fine-tuning of LVLMs that results in strong discriminative and compositional capabilities. Essentially, our approach converts a generative LVLM into a discriminative one, unlocking its capability for powerful image-text discrimination combined with enhanced language understanding. Our contributions include (1) A carefully designed training/optimization framework that utilizes image-text pairs of variable length and granularity for training the model with both contrastive and next-token prediction losses. This is accompanied by ablation studies that justify the necessity of our framework's components. (2) A parameter-efficient adaptation method using a combination of soft prompting and LoRA adapters. (3) Significant improvements over state-of-the-art CLIP-like models of similar size, including standard image-text retrieval benchmarks and notable gains in compositionality.

---

## 论文详细总结（自动生成）

# VladVA: 大型视觉语言模型的判别性微调 —— 详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：对比学习训练的视觉语言模型（如 CLIP）在判别性视觉语言表示学习中占主导地位，但存在语言理解能力有限、“词袋”行为、组合性理解差等缺陷。而大型视觉语言模型（LVLM，如 LLaVA）虽具备详细的视觉语言推理能力，但其自回归生成本质使其不适合直接用于图像-文本判别任务（如检索）。
- **核心目标**：将生成式 LVLM 转化为判别式模型，同时保留其强大的语言理解与组合推理能力，实现“两全其美”。
- **整体贡献**：提出一种新的判别性微调框架 VladVA，通过精心设计的训练策略（结合对比损失和自回归损失）和参数高效适配方法，显著提升了 LVLM 在图像-文本检索和组合性基准上的表现，超越同规模 CLIP 类模型。

## 2. 方法论

### 2.1 核心思想
- 保留 LVLM 的架构（视觉编码器 + 投影器 + LLM），但在判别模式下，通过特定提示（prompt）获得图像嵌入和文本嵌入（取最后一个 token 的表示），然后计算余弦相似度。
- 训练时同时利用短标题（<30 tokens）和长标题（30-500 tokens），分别采用对比损失和自回归损失，实现粗粒度与细粒度信息的联合学习。

### 2.2 关键技术细节
- **数据策略**：对每张图像，人工或自动生成短标题（粗粒度）和长标题（细粒度）。短标题用于对比学习，长标题用于自回归生成学习。
- **对比损失**（用于短标题）：对称的图像-文本和文本-图像对比损失，促使匹配的图像-文本对嵌入相近，不匹配的对远离。
- **自回归损失**（用于长标题）：在长标题上应用下一个 token 预测损失（交叉熵），使模型学会将细粒度信息压缩到起始 summary token 中，同时保留生成能力。
- **联合训练**：如图 1 所示，图像分支：用户提示+图像 → summary token → 进而生成长标题；文本分支：用户提示+短标题 → summary token。对比损失施加于 summary token，自回归损失施加于长标题。
- **参数高效适配**：使用**软提示**（soft prompting，用可学习向量替换手工提示）和 **LoRA 适配器**（低秩适配，附加到 LLM 的线性层）联合微调，仅更新少量参数。

### 2.3 关键公式（文字说明）
- 对比损失：在一个 mini-batch 内，分别计算图像到文本和文本到图像的余弦相似度，然后计算对称的 InfoNCE 损失。
- 自回归损失：在长标题的每个 token 上计算预测概率的对数似然之和。

## 3. 实验设计

### 3.1 使用的数据集与基准
- **零样本图像-文本检索**：Flickr30k（1k 测试样本）、MS-COCO（5k 测试样本）、nocaps（15.1k 样本，取三个分区平均）。
- **组合性（compositionality）**：SugarCrepe 和 SugarCrepe++（其中重点关注 Image-to-Text 设置）。
- **训练数据**：使用 OpenImages（4M 子集，自动生成短标题）、ShareGPT-4V（长标题数据）、CC3M（~2.8M 图像），合计约 8.1M 样本。

### 3.2 对比方法
- **两塔模型**：CLIP（ViT-L）、BLIP（ViT-L）、BLIP2（T5-XXL）、OpenCLIP（ViT-G/14、ViT-BigG/14）、EVA-02-CLIP（ViT-E/14+）、EVA-CLIP（8B、18B）等。
- **LVLM 基方法**：LLaVA-1.5-7B（原始生成模型）、VLM2Vec（Mistral-7B）、E5-V（LLaVA-Next-8B 和 LLaVA-1.5-7B）。
- **组合性专项**：NegCLIP、CLIP-SVLC、BLIP-SGVL 等。

## 4. 资源与算力

- 论文明确说明：使用 **32 块 A100 GPU**，训练时 batch size 为 1024，学习率 1e-4，采用 AdamW 优化器，余弦学习率衰减。
- 训练数据规模从 1M 到 8.1M 样本，训练 7 个 epoch。
- 未详细说明单次训练总时长，但提到由于 LVLM 规模大（7B 参数），训练成本高昂。

## 5. 实验数量与充分性

- **主要实验**：两个核心任务（检索和组合性）在两个基准（Flickr30k、COCO、nocaps；SugarCrepe、SugarCrepe++）上，对比了十余种 SOTA 方法。
- **消融实验**：
  - 组件消融（表 4）：对比软提示、LoRA、自回归损失的效果，共 5 组对比。
  - 数据规模消融（表 5）：从 0M → 1M → 4M → +ShareGPT-4V → +CC3M，共 5 组，展示性能持续提升。
  - 提示质量分析（图 2-5）：通过熵、累积方差、检索分数分析 prompt 影响，作为方法论支撑。
- **充分性**：实验设计较为全面，覆盖主要任务、核心组件、数据规模、模型变体。但在更多 LVLM 基模型（如不同 LLM 类型）上的泛化性验证不足；仅在 LLaVA-1.5-7B 上训练，未尝试其他架构。消融实验在 1M 子集上进行，规模较小，但与完整训练趋势一致。

## 6. 主要结论与发现

- VladVA 显著超越同规模 CLIP 类模型：在 Flickr30k 图像检索 R@1 上达 85.0%（超越 EVA-CLIP 18B 的 83.3%），在 COCO 和 nocaps 上分别提升 7.0% 和 6.4%。
- 在组合性基准 SugarCrepe 上，VladVA 在所有子类别上均优于 EVA-CLIP 18B 和 E5-V，尤其在物体交换（object swap）上提升约 14%。
- 对比损失+自回归损失的联合训练至关重要：单独使用对比损失处理长标题会导致损失迅速下降为零，而自回归损失能有效学习细粒度信息。
- 参数高效适配（软提示+LoRA）有效，两者联合使用效果最佳。
- 数据规模增大带来持续收益，未见饱和迹象。

## 7. 优点

- **方法创新**：首次在 LVLM 上有效结合对比损失和自回归损失进行判别性微调，解决了长标题对比学习易崩溃的问题。
- **性能突出**：以 7B 参数模型超越 18B 参数的双塔模型，证明了转换生成模型为判别模型的巨大潜力。
- **参数高效**：仅微调软提示和 LoRA，降低了训练成本和过拟合风险。
- **分析深入**：通过熵、累积方差、注意力图等指标揭示了模型行为变化（摘要 token 的注意力密度增加、嵌入秩提高），为方法提供了理论依据。
- **实验设计严谨**：消融实验系统，数据规模实验展示了可扩展性。

## 8. 不足与局限

- **实验覆盖**：仅在 LLaVA-1.5-7B 单一架构上验证，未测试其他 LVLM（如 Qwen-VL、MiniGPT-4）的泛化性。也未与更大规模的 LVLM（如 13B、70B）对比。
- **训练数据规模**：最大 8.1M 样本，远小于 CLIP 类模型的数亿级训练数据，可能限制了下游任务泛化能力。
- **组合性基准局限性**：在 SugarCrepe++ 的 Text-to-Text 设置上，E5-V 因采用文本-文本对比损失表现更好，作者承认可结合但未实现，存在改进空间。
- **零样本评估范围**：仅评估检索和组合性，未涵盖更多判别任务（如分类、视觉问答中的判别形式）。
- **计算资源**：虽参数高效，但训练仍需 32 块 A100 GPU，对普通研究者仍昂贵。
- **潜在偏差**：自动生成的短/长标题可能引入额外噪声，且依赖 BLIP2 和 ShareGPT-4V，这些生成器本身有偏差。

（完）
