---
title: Adapter Naturally Serves as Decoupler for Cross-Domain Few-Shot Semantic Segmentation
title_zh: 适配器天然作为跨域少样本语义分割的解耦器
authors: "Jintao Tong, Ran Ma, Yixiong Zou, Guangyao Chen, Yuhua Li, Ruixuan Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Pokj70ZAxJ"
tags: ["query:mmseg"]
score: 7.0
evidence: 使用适配器的跨域少样本语义分割
tldr: 本文发现适配器在跨域少样本语义分割中不仅帮助微调，还能自然解耦域信息。通过重新审视适配器结构，揭示了模型固有结构导致域信息分离的机制。在多个跨域分割任务上验证了该发现的有效性，为域自适应分割提供了新见解。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 833, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 806, \"height\": 217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1777, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 844, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 635, \"height\": 277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 860, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 835, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 772, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 775, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 865, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 902, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 443, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 618, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pokj70zaxj/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 779, \"height\": 241, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 834, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 737, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 431, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 394, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 859, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 842, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 856, \"height\": 100, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 851, \"height\": 100, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 400, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 859, \"height\": 129, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 861, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 861, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pokj70zaxj/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 857, \"height\": 177, \"label\": \"Table\"}]"
motivation: 跨域少样本分割面临域差距和数据稀缺双重挑战。
method: 基于适配器结构，利用其天然解耦域信息的能力进行高效微调。
result: 在多个跨域少样本分割数据集上取得优异性能。
conclusion: 适配器可作为域解耦器，有效提升跨域分割的迁移能力。
---

## Abstract
Cross-domain few-shot segmentation (CD-FSS) is proposed to first pre-train the model on a source-domain dataset with sufficient samples, and then transfer the model to target-domain datasets where only a few training samples are available for efficient finetuning. There are majorly two challenges in this task: (1) the domain gap and (2) finetuning with scarce data. To solve these challenges, we revisit the adapter-based methods, and discover an intriguing insight not explored in previous works: the adapter not only helps the fine-tuning of downstream tasks but also naturally serves as a domain information decoupler. Then, we delve into this finding for an interpretation, and we find the model's inherent structure could lead to a natural decoupling of domain information. Building upon this insight, we propose the Domain Feature Navigator (DFN), which is a structure-based decoupler instead of loss-based ones like current works, to capture domain-specific information, thereby directing the model's attention towards domain-agnostic knowledge. Moreover, to prevent the potential excessive overfitting of DFN during the source-domain training, we further design the SAM-SVN method to constrain DFN from learning sample-specific knowledge. On target domains, we freeze the model and fine-tune the DFN to learn knowledge specific to target domains. Extensive experiments demonstrate that our method surpasses the state-of-the-art method in CD-FSS significantly by 2.69% and 4.68% average MIoU in 1-shot and 5-shot scenarios, respectively.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义

**研究动机**：
跨域少样本语义分割（CD-FSS）旨在解决两个关键挑战：
- **域差距**：源域（如自然图像PASCAL）与目标域（如医疗图像、卫星图像）之间存在显著分布差异。
- **数据稀缺**：目标域仅提供少量标注样本，难以进行全模型微调。

**整体含义**：
本文发现适配器（Adapter）不仅是一种参数高效微调手段，更能**天然地充当域信息解耦器**——其结构特性（残差连接、深层插入）使其自动吸收域特异性信息，从而引导主干网络和编解码器专注于域无关知识。基于此洞察，作者提出结构化的域特征导航器（DFN）和锐度感知奇异值扰动（SAM-SVN），在解耦域信息的同时防止过拟合，显著提升了跨域分割性能。

## 2. 方法论

### 核心思想
- **适配器天然解耦器**：通过实验发现，插入在冻结主干网络深层的、带残差连接的适配器，其输出特征会吸收域特异性信息（降低主干输出域相似度CKA），同时使编码器输出更具域不变性（提高编码器输出CKA）。这一能力源于：（1）主干固定而适配器随机初始化，适配器倾向于学习更复杂的信息；（2）深层特征语义更丰富，更易捕捉域相关模式；（3）残差连接将主干通用特征与适配器域特征显式分离后共同送入后续模块。
- **DFN（Domain Feature Navigator）**：将满足上述条件的适配器作为结构化解耦器，插入到特征提取器的低、中、高层，通过残差连接融合。在源域训练时，DFN吸收域特定知识，迫使模型学习域无关特征。
- **SAM-SVN（Sharpness-Aware Minimization on Singular Value Matrix）**：为缓解DFN在源域训练中可能过度拟合样本（而非域）的风险，对DFN的权重进行奇异值分解，然后仅对奇异值矩阵应用SAM优化。这样既能抑制过拟合，又保留其余参数吸收域信息的能力。

### 关键技术细节
1. **DFN实现**：一个1×1卷积（C×C×1×1），输入输出通道数相同，带残差连接。
2. **特征导航**：对支持/查询特征图，先经过DFN（`NF = F + N_α(F)`），再计算4D相关矩阵用于后续超相关金字塔。
3. **SAM-SVN流程**：
   - 将DFN权重张量 `α ∈ R^{C_o × C_i × 1×1}` 展平成矩阵 `α' ∈ R^{C_o × C_i}`。
   - 做SVD：`α' = U S V^T`。
   - 仅对奇异值矩阵S应用SAM的梯度扰动：`S' = S + ρ ∇L/‖∇L‖`，再重构 `α' = U S' V^T`。
   - 只更新重构后的权重（即等价于用SAM约束奇异值）。
4. **目标域微调**：冻结整个模型，仅对DFN进行少量迭代（50步）微调，以捕捉目标域特定特征。

### 公式与算法流程（文字说明）
- 源域训练：输入支持图像和查询图像 → 提取多级特征 → 经DFN（残差连接） → 计算4D相关矩阵 → 超相关编码器+解码器 → BCE损失 → 其中DFN权重SVD后仅对S施加SAM扰动更新。
- 目标域微调：冻结主干和编解码器，仅更新DFN参数（无需SAM）以适配目标域。

## 3. 实验设计

### 使用数据集与场景
- **源域**：PASCAL-5ⁱ（基于PASCAL VOC 2012扩展）
- **目标域（4个）**：FSS-1000（自然图像）、Deepglobe（卫星图像）、ISIC2018（皮肤镜图像）、Chest X-ray（X光图像）
- **任务设定**：1-shot 和 5-shot 语义分割（1-way设置）

### Benchmark
采用PATNet (Lei et al., 2022) 提出的CD-FSS标准评测协议。

### 对比方法
包括：CaNet、PANet、RPMMs、PFENet、RePRI、HSNet、PATNet、RestNet、PerSAM、ABCDFSS、APSeg、APM 等14种方法，涵盖ResNet-50和ViT-Base两种骨干。

### 实验结果
- 在ResNet-50骨干下，DFN在1-shot平均MIoU达到61.98%，5-shot平均68.81%，超过最优的APSeg分别高出2.69%（1-shot）和4.68%（5-shot）。
- 在ViT-Base骨干下，DFN同样取得最佳平均性能（1-shot 63.99%，5-shot 69.77%）。

## 4. 资源与算力

文中明确提及：
- 使用**单张NVIDIA 4090 GPU**进行训练和测试。
- 训练时resize图像为400×400，使用Adam优化器，学习率1e-3。
- 附录F给出了计算复杂度分析：基线模型（HSNet）参数量26,174K，FLOPs 20.11G；本文方法增加约21%参数量（31,679K），FLOPs仅增加0.02%（20.51G）。
- SAM-SVN仅用于源域训练，且只作用于奇异值矩阵，额外计算开销很小（附录表13显示仅增加1.99% FLOPs）。
- 未明确报告总训练时长，但可推断在单卡4090上可较快完成（通常数小时）。

## 5. 实验数量与充分性

### 实验数量
总共进行了**大量实验**，包括：
- **主表对比**：在4个目标域、2种骨干、2种shot设置下的性能对比（表6）。
- **消融实验**：
  - 组件消融：DFN、SAM、SVD的有无（表7左）。
  - SAM扰动目标比较：全模型vs DFN vs SVN（表7右）。
  - DFN使用方式：移除、随机初始化、本文方法（表9）。
  - 适配器位置/结构对解耦能力的影响（表2、表4）。
  - 超参数ρ实验（附录表12左）。
  - 学习率调参（附录图14）。
  - 更多块骨干实验（ViT，表15）。
  - 与IFA在batch=96下的额外对比（表16）。
- **可视化分析**：
  - 特征图可视化（图4、图9、图11-12）。
  - 域距离（CKA/MMD）变化（图8、图15）。
  - 损失景观锐度测量（表5、表8、表10、表11）。
  - 鲁棒性测试（风格迁移扰动，图10）。
- **复杂度分析**（附录F、表12右、表13）。

### 充分性与公平性
- **充分性**：消融覆盖了所有核心设计选择，包括不同基准（CNN和Transformer）、不同目标域、不同shot数；可视化验证了域解耦机制；锐度/鲁棒性实验直接支撑了方法动机。
- **公平性**：与所有对比方法采用相同基准（HSNet/PATNet）和相同预处理。与IFA的额外对比专门说明了batch size差异并设置了匹配条件。代码未开源但方法描述详细，可复现。
- **客观性**：所有消融和对比均基于标准CKA、MMD、MIoU等经典指标，结果报告完整（包括小数点后两位），无明显选择性报告。

## 6. 主要结论与发现

1. **现象发现**：适配器（带残差、深层插入）天然可以作为域信息解耦器，无需额外域损失。
2. **机制解释**：该能力源于结构特性（深层语义丰富性、残差连接显式分离、主干冻结与适配器随机初始化差异），并由信息瓶颈理论分析支持。
3. **方法有效性**：提出的DFN+SAM-SVN在4个目标域上大幅超越现有SOTA，平均提升2.69% ~ 4.68%（MIoU）。
4. **锐度控制必要性**：仅靠结构化解耦会导致过度过拟合，SAM-SVN通过约束奇异值矩阵的平坦性，在保持解耦能力的同时提升泛化稳定性。
5. **迁移能力**：DFN在目标域微调后能有效对齐特征空间，降低域距离。

## 7. 优点

- **新颖视角**：首次揭示适配器天然作为解耦器，为跨域学习提供了新理解。
- **结构化解耦**：区别于现有基于损失（如CCSA、DIFEX）的解耦方法，本文仅通过结构调整实现，训练更简单且无域标签依赖。
- **SAM-SVN设计巧妙**：仅对奇异值矩阵应用SAM，在限制过拟合的同时保留其余参数吸收入域信息的能力，实现了精准调控。
- **理论支撑**：利用信息瓶颈理论进行了数学推导（附录A），增强了说服力。
- **轻量高效**：仅增加21%参数、0.02%FLOPs，且SAM-SVN几乎不增加训练负担。
- **全面实验**：涵盖多种骨干、多个域、多种shot、可视化以及锐度/鲁棒性验证，结果可靠。

## 8. 不足与局限

- **仅聚焦少样本场景**：作者在Impact Statement中承认忽略了“many-shot”场景，这在现实应用中也可能具有价值。需要额外调整才能适应更多样本情况。
- **部分域性能提升不均**：在ISIC（皮肤镜）数据集上，本文方法的1-shot MIoU（36.30%）反而低于APSeg（45.43%），提升主要集中在大自然、卫星和医疗影像的X光域。可能该域数据噪声大或类别分布极端，结构化解耦器不够有效。
- **单GPU实验**：虽然单卡4090可完成实验，但未报告多卡训练或更大规模消融，可能限制了方法的极致调优。
- **理论基础尚需强化**：信息瓶颈推导基于理想化假设（如正交投影），实际中域不变/特化成分未必可完美分离。
- **对比方法不全**：如未与近年基于MAML的元学习方法（如CAML等）对比，尽管它们可能不太适用于跨域分割任务。
- **代码未开源**：虽然论文描述详细，但缺乏开源代码可能影响可复现性。

（完）
