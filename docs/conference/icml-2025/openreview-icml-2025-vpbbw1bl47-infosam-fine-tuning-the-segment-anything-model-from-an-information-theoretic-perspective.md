---
title: "InfoSAM: Fine-Tuning the Segment Anything Model from An Information-Theoretic Perspective"
title_zh: InfoSAM：从信息论角度微调Segment Anything模型
authors: "yuanhong zhang, Muyao Yuan, Weizhan Zhang, Tieliang Gong, Wen Wen, Jiangyong Ying, Weijie Shi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=VpBBw1bL47"
tags: ["query:mmseg"]
score: 9.0
evidence: 通过信息论方法对SAM进行领域特定微调
tldr: SAM在通用任务上表现优异但专业领域微调效果不佳。本文提出InfoSAM，从信息论视角出发，通过互信息目标压缩并保留预训练SAM中的域不变关系，同时适应新领域。实验证明该方法在多个专业数据集上超越现有参数高效微调方法，为SAM在特定领域的应用提供了理论指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 832, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1556, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 798, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1367, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1268, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1320, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1662, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1779, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1759, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1759, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vpbbw1bl47/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1763, \"height\": 598, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1653, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1639, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 770, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 794, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 805, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 765, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 644, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1023, \"height\": 684, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1409, \"height\": 684, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1102, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1127, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 832, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 576, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vpbbw1bl47/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 600, \"height\": 284, \"label\": \"Table\"}]"
motivation: 现有SAM微调方法忽略了预训练模型中的域不变知识。
method: 提出基于互信息的目标，压缩域不变关系并保留分割知识。
result: 在多个专业领域数据集上超越已有参数高效微调方法。
conclusion: 信息论可指导SAM更有效地保留通用知识并适应新领域。
---

## Abstract
The Segment Anything Model (SAM), a vision foundation model, exhibits impressive zero-shot capabilities in general tasks but struggles in specialized domains. Parameter-efficient fine-tuning (PEFT) is a promising approach to unleash the potential of SAM in novel scenarios. However, existing PEFT methods for SAM neglect the domain-invariant relations encoded in the pre-trained model. To bridge this gap, we propose InfoSAM, an information-theoretic approach that enhances SAM fine-tuning by distilling and preserving its pre-trained segmentation knowledge. Specifically, we formulate the knowledge transfer process as two novel mutual information-based objectives: (i) to compress the domain-invariant relation extracted from pre-trained SAM, excluding pseudo-invariant information as possible, and (ii) to maximize mutual information between the relational knowledge learned by the teacher (pre-trained SAM) and the student (fine-tuned model).  The proposed InfoSAM establishes a robust distillation framework for PEFT of SAM. Extensive experiments across diverse benchmarks validate InfoSAM's effectiveness in improving SAM family's performance on real-world tasks, demonstrating its adaptability and superiority in handling specialized scenarios. The code and models are available at https://muyaoyuan.github.io/InfoSAM_Page.

---

## 论文详细总结（自动生成）

好的，以下是对论文《InfoSAM: Fine-Tuning the Segment Anything Model from An Information-Theoretic Perspective》的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：Segment Anything Model (SAM) 作为视觉基础模型，在通用分割任务上表现出色，但在医学、农业、遥感等专业领域效果不佳。现有针对 SAM 的参数高效微调（PEFT）方法，如 Adapter 或 LoRA，主要关注调整各模块参数以适配新任务，却忽略了预训练模型中编码的、至关重要的**域不变关系知识**。这种关系（例如图像编码器与掩码解码器之间的隐含联系）在微调过程中容易被新任务的扰动所破坏。

*   **整体含义**：该论文旨在解决“如何在微调 SAM 时，有效地提取、保留并迁移预训练模型中的域不变知识，以提升其在专业领域的性能”。论文从信息论的角度出发，提出了一种新颖的蒸馏框架，通过控制信息流来优化微调过程。

### 2. 论文提出的方法论

*   **核心思想**：借鉴信息瓶颈（Information Bottleneck）原理，通过两个互补的互信息目标来管理预训练SAM（教师）与微调SAM（学生）之间的知识迁移。
    1.  **关系压缩**：从预训练 SAM 中提取域不变的关系，同时抑制域相关的伪信息。
    2.  **关系蒸馏**：将压缩后的关系知识从教师模型有效地蒸馏到学生模型中。

*   **关键技术细节**：
    1.  **关系模块**：设计了一个基于注意力机制的关系模块，用于捕捉图像编码器输出（$z^T_i$）与掩码解码器标记（$z^T_m$）之间的高阶结构性关系（$r_T$）。
    2.  **互信息度量**：利用基于矩阵的 Rényi 熵来计算互信息，从而避免了复杂的高维概率密度估计，使计算更高效。
    3.  **损失函数**：
        *   **关系压缩损失 $L_r$**：通过最小化 $I_\alpha(z^T_i, z^T_m; r_T)$ 来约束关系模块。这迫使模块学习一个紧凑的、包含最小充分统计量的表示 $r_T$，从而过滤掉不必要的域相关信息，保留最核心的域不变关系。在高阶 $\alpha=2$ 时，该损失简化为对 Gram 矩阵的 Frobenius 范数运算。
        *   **关系蒸馏损失 $L_d$**：通过最大化 $I_\alpha(r_T; r_S)$ 来迁移关系知识，其中 $r_S$ 是学生模型的关系表示。这确保了学生模型能学习到教师模型中的结构性知识。该目标同样可以转化为 Gram 矩阵的 Frobenius 范数运算。
    4.  **最终目标**：将以上两个损失结合，得到总的信息论损失 $L_{info}$，并与下游任务的结构损失 $L_{ce}$ 一同用于优化。

### 3. 实验设计

*   **使用的数据集与场景**：涉及 **4 个领域、8 个数据集**。
    *   **自然图像**：COD10K, CHAMELEON, CAMO（用于伪装物体分割）
    *   **医学影像**：Kvasir, CVC-ClinicDB（息肉分割）；ISIC 2017（皮肤病变分割）
    *   **农业**：Leaf Disease Segmentation（叶片分割）
    *   **遥感**：Massachusetts Roads（道路分割）

*   **Benchmark**：主要评测方法是平均值和标准差，使用了包括 $S_\alpha$, $E_\phi$, $F_\omega^\beta$, IoU, Dice 等常用分割指标。

*   **对比方法**：分为两大类。
    *   **PEFT 方法**：SAM（零样本）、Decoder-only, BitFit, AdaptFormer, LoRA, Adapter, HQ-SAM, SU-SAM, ConvLoRA-SAM。
    *   **蒸馏方法**：Logit, PKD, PKT, IBD, VID, SemCKD, ReviewKD, MobileSAM, TinySAM。

### 4. 资源与算力

*   论文中**未明确说明**使用的 GPU 型号、数量和具体训练时长。
*   仅在附录中提到训练配置为：batch size 为 4，使用 Adam 优化器，初始学习率为 $2 \times 10^{-4}$，采用余弦退火调度器，所有方法默认训练 10 个 epochs。这些信息不足以精确评估所需算力。

### 5. 实验数量与充分性

*   **实验数量**：非常充分。论文进行了以下多组实验：
    1.  **主要对比实验**：在 SAM 和 SAM2 两个基础模型上，与 8 种 PEFT 方法和 9 种蒸馏方法在多个数据集上进行了全面对比。
    2.  **跨域扩展实验**：将方法迁移到 SAM2 模型上，验证了其通用性。
    3.  **跨尺寸蒸馏实验**：使用更大规模的教师模型（ViT-L, ViT-H）进行蒸馏。
    4.  **消融实验**：分析了两个主要损失组件 ($L_r$ 和 $L_d$) 的作用、关系模块 (RM) 的有效性、RM 的跨领域迁移能力。
    5.  **超参数分析**：对两个关键超参数 $\lambda_1, \lambda_2$ 以及不同的 Rényi 熵阶数 $\alpha$ 进行了敏感性分析。
    6.  **架构探索**：探索了不同关系模块架构的影响。

*   **客观性与公平性**：实验设计较为客观和公平。作者报告了三次独立运行的平均值和标准差，使用了统一的训练设置以确保公平比较。对比方法全面，且包括了 PEFT 和蒸馏两个类别的代表性工作。

### 6. 论文的主要结论与发现

1.  **InfoSAM 有效**：InfoSAM 在大多数场景下显着优于现有的 PEFT 和蒸馏基线方法，尤其在医学、农业、遥感等 SAM 原本表现不佳的专业领域，证明了域不变关系蒸馏的重要性。
2.  **传统蒸馏在 PEFT 中的局限性**：部分现有蒸馏方法（如传统的 Logit 蒸馏、PKD、TinySAM 等）在 PEFT 场景下可能损害性能，甚至不如不进行蒸馏。其可能原因是：当教师模型本身在某些任务上表现很差时（如SAM在遥感任务上的7.2% IoU），强迫学生完全模仿教师反而有害。
3.  **关系模块的跨域迁移性**：在一个领域训练好的关系模块可以直接应用于另一个完全不同领域，仍能有效提升性能，这验证了其提取的知识确实具有域不变性。
4.  **信息瓶颈理论的有效性**：论文提出的信息压缩与蒸馏机制，有效平衡了保留预训练知识和适应新任务之间的关系，是提升模型泛化能力的关键。

### 7. 优点

1.  **创新性强**：首次将信息论原理系统地应用于 SAM 的 PEFT 问题，提出了一个理论驱动的蒸馏框架，视角新颖。
2.  **方法有效且通用**：在多个领域及 SAM、SAM2 模型上均取得了 SOTA 或极具竞争力的结果，证明了方法的泛化能力。该方法可轻松集成于 Adapter 或 LoRA 等现成 PEFT 模块。
3.  **理论完善**：基于 Rényi 熵的互信息目标定义严谨，且在实际计算时可通过 Frobenius 范数高效实现，兼顾了理论深度与实践效率。
4.  **实验设计全面**：对比方法多，消融实验覆盖广，论证充分，结果可靠。

### 8. 不足与局限

1.  **算力成本不透明**：论文未明确报告训练所需的 GPU 类型和具体时长，增加了后续研究者复现和评估资源需求的难度。
2.  **超参数敏感性**：虽然进行了超参数（$\lambda_1, \lambda_2$）分析，但实验中提到某些设置（如 $\lambda_1=1, \lambda_2=0.5$）是手动选择的。其在不同任务上的最优超参数可能不同，这增加了应用的调参成本。
3.  **实验覆盖范围**：虽然覆盖了多个领域，但主要集中在图像分割。其在其他 CV 任务（如深度估计、检测）或 NLP 模型上的适用性未被验证。基础实验（10个epochs）较为充分，但未展示更长时间训练后的性能饱和情况。
4.  **对域不变关系的本质解释有限**：论文通过实验（如边界 F1 分数）间接展示了关系模块保留了结构信息，但对于“域不变关系”到底是什么（是形状、边缘还是其他更高维的特征模式），缺乏更本质和深入的可视化或理论解释。

（完）
