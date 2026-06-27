---
title: Vision-Language Model Selection and Reuse for Downstream Adaptation
title_zh: 视觉语言模型选择与重用于下游适配
authors: "Hao-Zhe Tan, Zhi Zhou, Yu-feng Li, Lan-Zhe Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=bvrsrvo0Mt"
tags: ["query:mmseg"]
score: 7.0
evidence: 视觉语言模型选择与重用于下游任务
tldr: 针对如何为具体下游任务选择最佳预训练视觉语言模型（VLM）的难题，本文提出模型标签学习（MLL）范式，通过模型标注、模型选择和模型重用水三个模块，自动匹配任务需求与VLM专长。实验表明该方法在不逐一评估所有VLM的情况下，所选VLM性能接近甚至超过穷举选择，显著提升了VLM的部署效率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bvrsrvo0mt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1100, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bvrsrvo0mt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1753, \"height\": 1138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bvrsrvo0mt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 441, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 749, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1418, \"height\": 1066, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1696, \"height\": 2199, \"label\": \"Table\"}]"
motivation: 没有单一VLM能完美适用于所有下游任务，且逐一评估所有VLM不现实。
method: 提出模型标签学习范式，包含标注、选择和重用水三个模块。
result: 在选择任务中，MLL选中的VLM性能与穷举法相当，且效率大幅提升。
conclusion: MLL为VLM的高效部署和迁移提供了一种实用解决方案。
---

## Abstract
Pre-trained Vision-Language Models (VLMs) are becoming increasingly popular across various visual tasks, and several open-sourced VLM variants have been released. However, selecting the best-performing pre-trained VLM for a specific downstream task is challenging since no single VLM can achieve promising performance on all downstream tasks, and evaluating all available VLMs is impossible due to time and data limitations. To address this problem, this paper proposes a novel paradigm to select and reuse VLM for downstream tasks, called **M**odel **L**abel **L**earning (**MLL**). The proposal contains three key modules: *model labeling*, which assigns labels to each VLM to describe their specialty and utility; *model selection*, which matches the requirements of the target task with model labels; and *model reuse*, which applies selected VLMs to the target task in an ensemble manner. The proposal is highly computationally efficient and growable since the model labeling process is completed target task independent and the ability could grow with the number of candidate VLMs. We also introduce a new benchmark for evaluating VLM selection methods, including 49 VLMs and 17 target task datasets. Experimental results clearly demonstrate the effectiveness of the proposed method for selecting and reusing VLMs.

---

## 论文详细总结（自动生成）

# 视觉语言模型选择与重用于下游适配（Vision-Language Model Selection and Reuse for Downstream Adaptation）详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

预训练的视觉语言模型（VLM）在多种视觉任务中展现出强大的零样本能力，但没有任何单一 VLM 能在所有下游任务上都取得最优性能。随着开源社区（如 OpenCLIP）发布了大量 VLM 变体（本文涉及 49 个），用户面临的核心挑战是：在没有时间与数据资源逐一评估所有候选模型的情况下，如何为特定下游任务快速选出最适合的 VLM 并高效复用？已有模型选择方法（如 LEEP、LogME）主要针对单模态模型，无法直接用于 VLM；而首个针对 VLM 的选择方法 LOVM 依赖模型在大规模数据集（如 ImageNet）上的表现，在领域偏移时效果下降。因此，论文提出一种新范式——**模型标签学习（MLL）**，旨在以“为模型打标签”的方式描述每个 VLM 的特长，从而在任务独立阶段完成标注，在任务到来时快速匹配与集成，兼顾精度、效率和可扩展性。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：建立包含常见视觉概念的语义图（Semantic Graph），每个 VLM 在提交时进行预测试，生成描述其在这些概念上能力的“模型标签”。当新下游任务出现时，通过语义匹配将任务类别与语义图节点对齐，利用模型标签预测模型在各类别上的性能，从而选出最适合的模型，并在推理时进行集成。
- **关键技术细节**：
  1. **模型标注（Model Labeling）**：
     - 基于 WordNet 的同义词集构建语义图 G，包含 9055 个节点，每个节点关联其定义作为文本描述（caption），并从 5 个采样数据集（ImageNet、ImageNet-V2、ImageNet-Sketch、ImageNet-A、ImageNet-R）中为每个节点随机选取最多 75 张图片作为样本。
     - 对每个 VLM \( f_m \)，计算其在每个节点上的图像与文本描述（节点 caption）的余弦相似度，得到一组相似度向量 \( s_{v,m} \)，整个节点的集合构成模型标签 \( S_m \)。
  2. **模型选择（Model Selection）**：
     - 对于下游任务 \( T \) 的每个类别 \( y \)，使用 LLM（GPT-4）生成详细描述（caption）；同时为语义图节点也生成 caption。
     - 使用语言模型将两类 caption 嵌入并计算余弦相似度，为每个任务类别选出 top-\( k \) 个最相似的语义节点，构建转移矩阵 \( Z \)。
     - 基于模型标签，计算每个模型在语义节点上的精度 \( p_{m,v} \)，再通过转移矩阵 \( Z \) 加权得到模型在任务类别上的预测精度 \( p_{m,y} \)。
     - 引入权重参数 \( \alpha \) 平衡各类别性能与全局平均性能，得到复用指标 \( r_{m,y} = \alpha p_{m,y} + \frac{1-\alpha}{|Y_T|}\sum_{y'} p_{m,y'} \)。
  3. **模型重用（Model Reuse）**：
     - 对每个类别 \( y \)，选择 top-\( k \) 个 \( r_{m,y} \) 最高的模型组成集成预测器 \( F_y^k \)。
     - 集成时，每个模型的权重 \( w_{m,y} \) 由其输出概率熵的倒数归一化得到，以抑制过自信模型的负面影响。
     - 最终预测为所有类别置信度最高的那个。
- **算法流程**（文字说明）：
  1. 为下游任务生成 caption 数据集 \( D_T \)。
  2. 通过 caption 匹配选出与任务类别相似的语义节点集合 \( V_{\text{Selected}} \)。
  3. 构建转移矩阵 \( Z \)。
  4. 对所有候选模型，计算每个类别的复用指标 \( r_{m,y} \)。
  5. 对每个类别选取 top-\( k \) 模型组成集成预测器，对输入图像进行预测。

## 3. 实验设计

- **数据集与场景**：
  - **采样数据集**：5 个（ImageNet, ImageNet-V2, ImageNet-Sketch, ImageNet-A, ImageNet-R），用于构建语义图节点样本。
  - **目标数据集**：17 个，覆盖自然图像、纹理、人脸表情、医学图像、卫星图像、交通标志、文字识别、动作识别等多种领域，包括 CIFAR100、Country211、CLEVR-D、DTD、DMLab、Flowers102、MNIST、OxfordPet、PCam、FER2013、Food101、GTSRB、RESISC45、Rendered-SST2、StanfordCars、STL10、UCF101。
  - **任务类型**：图像分类、地理定位、目标距离估计、纹理分类、表情识别、光学字符识别、土地覆盖分类等。
- **Benchmark**：构建了包含 49 个 VLM（来自 OpenCLIP，涵盖 RN、ViT、ConvNeXt、EVA 等架构，预训练于 Openai、LAION、Datacomp 等数据集）和 17 个目标数据集的标准化评测平台，并提供每个任务上模型真实排名用于评估。
- **对比方法**：
  - **ImageNet Baseline (INB)**：直接选择在 ImageNet 上表现最好的模型。
  - **ModelGPT (LOVM)**：使用生成 caption 和同义词作为代理文本，评估 VLM 对文本的分类能力，并学习线性模型来预测真实性能。
  - **本方法 (MLL)**：分别测试 \( k=1 \)（单个模型）和 \( k=3 \)（每类集成 3 个模型）。
- **公平性措施**：所有方法均使用相同的零样本推理流程（prompt “a photo of {class}”），且不对模型进行微调。ModelGPT 使用采样数据集上的真实性能训练其线性模型，MLL 则利用已构建的模型标签，不依赖下游任务训练数据。

## 4. 资源与算力

论文明确说明实验在 **NVIDIA A800 GPU** 上完成。但未报告具体 GPU 数量、训练时长或模型预测试的总计算量。仅提及模型标注过程在提交模型时一次性完成，选择阶段仅需运行少量相似度计算和简单算术，因此计算开销很低。

## 5. 实验数量与充分性

- **实验组数**：
  - 主要性能对比：在 17 个目标数据集上，对 \( k=1 \) 和 \( k=3 \) 两种设置，分别报告 INB、ModelGPT 和本方法的准确率（共 2×3×17 = 102 个数据点）。
  - 可扩展性实验：以 30 次随机扩增方案展示模型库从 0 增长到 49 时平均性能变化。
  - 消融实验：对权重 \( \alpha \) 在 {0.5, 0.6, 0.7, 0.8, 0.9} 五组取值下测试平均准确率；对集成模型数 \( k \) 在 1~6 范围内测试平均准确率和接口时间开销比。
- **充分性评价**：
  - 实验覆盖了广泛的 VLM 架构（18 种）和任务类型（17 个），多样性较好。
  - 消融实验分析了关键超参数 \( \alpha \) 和 \( k \) 的影响，表明方法对这些参数鲁棒。
  - 但缺少与更多近年模型选择方法（如 LogME、LEEP 等的 VLM 适配版）的对比；也未在非视觉或非分类任务（如目标检测、分割）上验证。
  - 随机扩增实验仅报告平均性能，未展示方差，统计显著性检验缺乏。

## 6. 论文的主要结论与发现

- MLL 在 17 个下游任务上的平均准确率（\( k=1 \) 时为 0.6620，\( k=3 \) 时为 0.6639）显著优于 INB（0.6434 和 0.6498）和 ModelGPT（0.6367 和 0.6480），尤其在 FER2013、CIFAR100、Country211 等任务上提升明显。
- 随着模型库规模扩大，MLL 的平均性能稳步提升（从约 0.53 升至 0.66），表明方法具有“成长性”（growable）。
- 使用每类单模型（\( k=1 \)）往往能取得较好效果，集成更多模型（\( k>3 \)）时可能引入噪声，平均性能反而微降。
- 模型标注过程与下游任务无关，使得在线选择阶段非常高效（仅需少量矩阵运算和相似度计算）。

## 7. 优点

- **问题新颖**：首次系统研究 VLM 的选择与重用问题，尤其关注类别级细粒度选择。
- **范式创新**：将模型选择抽象为“标注-匹配-集成”三阶段，独立于下游任务完成标注，兼顾效率与精度。
- **可扩展性强**：语义图节点可动态增加，模型库可不断吸纳新 VLM，性能有潜在线性增长。
- **实验构建扎实**：提供了标准化的基准（49 个 VLM + 17 个数据集），并开源代码，有利于后续研究复现和比较。
- **解决过自信问题**：在集成阶段引入熵权机制，抑制错误模型的过度自信，提升了集成鲁棒性。

## 8. 不足与局限

- **实验覆盖不足**：仅验证了图像分类及少数回归类任务（如距离估计），未涉及目标检测、语义分割、视频理解等更复杂任务；也仅涵盖了视觉-语言模型，未推广到其他模态（如纯文本或纯图像模型）。
- **对比方法有限**：未与 LogME、LEEP 等传统模型选择方法在适配 VLM 后对比，也未与最新的基于学习可迁移性度量的方法（如 MetaGL、Model Spider）比较。
- **依赖外部资源**：语义图构建依赖 WordNet 和 5 个采样数据集，节点样本数量有限（最多 75 张/类），可能无法完全覆盖实际分布；caption 生成依赖 GPT-4，带来额外成本与隐私风险。
- **假设信息可获得**：方法假设用户能提供任务类型、领域等一般信息，实际场景下这些信息可能不准确或缺失。
- **消融实验深度不足**：仅调整了 \( \alpha \) 和 \( k \)，未分析语义图节点数量、采样图片数量、匹配 top-\( k \) 选择、LLM 嵌入模型等设计选择对最终性能的影响。
- **统计显著性缺失**：报告的平均性能未提供标准差或置信区间，无法判断提升是否统计显著。
- **资源消耗报告不完整**：未明确标注过程的总计算成本（如 GPU 小时数），也未与逐模型评估的计算时间做定量比较。

（完）
