---
title: Efficient Transfer Learning for Video-language Foundation Models
title_zh: 视频语言基础模型的高效迁移学习
authors: "Chen, Haoxing, Huang, Zizheng, Hong, Yan, Wang, Yanshuo, Lyu, Zhongcai, Xu, Zhuoer, Lan, Jun, Gu, Zhangxuan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Chen_Efficient_Transfer_Learning_for_Video-language_Foundation_Models_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 5.0
evidence: 视频语言基础模型的参数高效迁移
tldr: 视频语言基础模型迁移时引入额外模块易导致遗忘。MSTA提出多模态时空适配器，仅用少量参数对齐文本与视觉表示，平衡通用知识与任务特定学习。在视频动作识别任务上验证了高效性。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 844, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 784, \"height\": 454, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1809, \"height\": 861, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1810, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 870, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 453, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 465, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 499, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 506, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-efficient-transfer-learning-for-video-language-foundation-models-cvpr-2025-paper/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 821, \"height\": 229, \"label\": \"Table\"}]"
motivation: 现有迁移方法引入大量参数且易遗忘通用知识。
method: 设计参数高效的多模态时空适配器（MSTA）。
result: 在视频动作识别中以极少参数达到高迁移性能。
conclusion: 轻量适配器可有效缓解灾难性遗忘并保持泛化性。
---

## Abstract
Pre-trained vision-language models provide a robust foundation for efficient transfer learning across various downstream tasks. In the field of video action recognition, mainstream approaches often introduce additional modules to capture temporal information. Although the additional modules increase the capacity of model, enabling it to better capture video-specific inductive biases, existing methods typically introduce a substantial number of new parameters and are prone to catastrophic forgetting of previously acquired generalizable knowledge. In this paper, we propose a parameter-efficient Multi-modal Spatio-Temporal Adapter (MSTA) to enhance the alignment between textual and visual representations, achieving a balance between generalizable knowledge and task-specific adaptation. Furthermore, to mitigate over-fitting and enhance generalizability, we introduce a spatio-temporal description-guided consistency constraint. This constraint involves providing template inputs (e.g., "a video of \ cls\ ") to the trainable language branch and LLM-generated spatio-temporal descriptions to the pre-trained language branch, enforcing output consistency between the branches. This approach reduces overfitting to downstream tasks and enhances the distinguishability of the trainable branch within the spatio-temporal semantic space. We evaluate the effectiveness of our approach across four tasks: zero-shot transfer, few-shot learning, base-to-novel generalization, and fully-supervised learning. Compared to many state-of-the-art methods, our MSTA achieves outstanding performance across all evaluations, while using only 2-7% of the trainable parameters in the original model.

---

## 论文详细总结（自动生成）

## 详细中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：在视频动作识别任务中，预训练的视觉-语言基础模型（如CLIP、ViCLIP）具备强大的泛化能力。然而，现有迁移学习方法通常引入大量额外的可训练参数（如跨帧注意力模块、提示工程等），这不仅增加了计算负担，还容易导致**灾难性遗忘**，即丢失预训练模型习得的通用知识，从而削弱对未见类别的泛化能力。
- **核心问题**：如何在保持预训练模型泛化性能的同时，高效地将其适配到视频下游任务（尤其是少样本场景）？现有单模态的PEFT方法（如LoRA、AdaptFormer）无法有效利用多模态信息，而直接为视觉和语言分支独立添加适配器则忽略了跨模态对齐。
- **整体意义**：本文提出参数高效的**多模态时空适配器（MSTA）**，旨在平衡通用知识与任务特定知识，仅用极少参数实现视频理解任务上的高迁移性能，推动了视频基础模型高效迁移学习的发展。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：
  - 设计双向（视觉、语言）且带共享投影层的**多模态时空适配器**，实现跨模态对齐与时空特征捕捉。
  - 引入**时空描述引导的一致性约束**，利用LLM生成的丰富描述对预训练语言分支和可训练语言分支进行蒸馏，减轻过拟合，提升泛化。
- **关键技术细节**：
  1. **适配器插入位置**：仅在视频和文本编码器的高层（第k层到第L层）插入MSTA，保留低层预训练特征。
  2. **适配器结构**：
     - 视觉分支适配器：包含下投影层（Down）、共享特征层（Shared）、**空间上投影层（Spatial Up）**和**时间上投影层（Temporal Up）**。空间上投影为线性层，时间上投影为3D卷积层，用以分别捕捉空间和时间信息。
     - 文本分支适配器：包含下投影层、共享特征层、上投影层（线性层）。
     - 共享投影层（W<sup>s</sup>）同时被视觉和语言分支共用，在微调时接收来自两模态的梯度，促进对齐。
  3. **前向公式**：
     - 视频特征：\[ [c_i, x_i] = \text{E}_i^v([c_{i-1}, x_{i-1}]) \quad (i<k) \]  
       \[ [c_j, x_j] = \text{E}_j^v([c_{j-1}, x_{j-1}]) + \lambda \cdot \text{A}_j^v([c_{j-1}, x_{j-1}]) \quad (j \ge k) \]
     - 文本特征类似。
     - 适配器内部：\[ \text{A}_k^v(h_k) = W_{u-s}^v \cdot h_k + W_{u-t}^v \cdot h_k ,\quad h_k = \sigma(W^s \cdot \sigma(W_{d}^v \cdot [c_k, x_k])) \]
  4. **时空描述引导的一致性约束**：
     - 利用LLM（如DeepSeek）生成两类描述：空间描述（静态视觉外观）和时间描述（动作步骤分解），每个类别生成N句。
     - 将标准模板（“a video of {cls}”）输入可训练语言分支，将LLM生成的时空描述输入冻结的预训练语言分支。
     - 一致性损失：\[ \mathcal{L}_{CC} = 2 - \frac{w_c \cdot D_c^s}{\|w_c\|\|D_c^s\|} - \frac{w_c \cdot D_c^t}{\|w_c\|\|D_c^t\|} \] 其中 \(w_c\) 是预训练分支对类别c的标准模板输出，\(D_c^s, D_c^t\) 分别是空间/时间描述的平均嵌入。
  5. **最终损失**：\[ \mathcal{L} = \mathcal{L}_{CE} + \alpha \mathcal{L}_{CC} \]，其中 \(\mathcal{L}_{CE}\) 为对比损失（softmax over cosine similarity）。

### 3. 实验设计：数据集、Benchmark、对比方法
- **数据集**：
  - Kinetics-400 (K400), Kinetics-600 (K600), UCF-101, HMDB-51, Something-Something V2 (SSv2), ActivityNet（仅提及，未在主要结果表中列出）。
- **Benchmark设置**：
  1. **零样本迁移**：在K400上微调后，直接在UCF-101、HMDB-51、K600上评估。
  2. **少样本学习**：在UCF-101、HMDB-51、SSv2上设置K=2,4,8,16样本/类。
  3. **基类到新类泛化**：在K400、UCF-101、HMDB-51、SSv2上分割基类/新类，报告基类准确率、新类准确率及调和平均（HM）。
  4. **全监督学习**：在K400上使用全部训练数据。
- **对比方法**：
  - 传统PEFT：AdaptFormer、LoRA（在ViCLIP上实现）。
  - 视频专用方法：ActionCLIP、XCLIP、A5、ViFi-CLIP、OST、MoTE、Vita-CLIP、ViCLIP等。
  - 零样本基线：Vanilla CLIP、ER-ZSAR、JigsawNet等。
- **评估指标**：Top-1准确率（部分报告Top-5），零样本用单视图，少样本和基类-新类用多视图。

### 4. 资源与算力
- **硬件**：所有实验在8张Nvidia Tesla-A100-80G GPU上运行。
- **配置细节**：
  - 基类-新类泛化：Batch size 32，学习率1e-3，训练11个epochs。
  - 少样本学习：Batch size 32，学习率1e-3，训练50个epochs。
  - 零样本迁移：Batch size 256，学习率8e-3，训练100个epochs。
  - 全监督：Batch size 256，学习率8e-3，训练100个epochs（根据表1推断）。
- 训练时间未明确给出，但使用了5个epoch的线性预热。

### 5. 实验数量与充分性
- **实验数量**：覆盖4种任务（零样本、少样本、基类-新类、全监督），共多个数据集（每个任务2-4个数据集），少样本设置含4种K值，基类-新类含4个数据集。此外执行了6组消融实验（组件分析、共享层维度、缩放因子λ、权重α、描述数量N、适配器插入层位置）。
- **充分性与公平性**：
  - 对比方法覆盖当时SOTA，且在同一backbone（ViCLIP ViT-B/16）下进行比较。
  - 消融实验全面，验证了每个设计决策的必要性。
  - 报告多次运行的平均值和标准差（零样本实验），体现稳定性。
- **结论**：实验充分、设计合理，公平性较好。

### 6. 论文的主要结论与发现
- **MSTA在几乎所有任务上取得SOTA**，仅使用原模型2-7%的可训练参数（例如全监督K400仅8.7M可训练参数，远低于XCLIP的132M）。
- **共享投影层**能有效促进视觉与文本模态的对齐，提升泛化表现。
- **时空描述一致性约束**进一步提升了新类性能，在SSv2等时间敏感数据集上增益尤其显著（30%+改进）。
- **最佳实践**：将MSTA插入高层（如8-12层）、设置λ=0.005、α=1.0、共享层维度256、描述数量N=2可取得最优平衡。
- **与经典PEFT方法相比**：MSTA在少样本和基类-新类任务上均显著优于AdaptFormer和LoRA。

### 7. 优点：方法或实验设计上的亮点
- **参数高效**：仅训练极少参数（2-7%），大幅降低微调成本，同时避免灾难性遗忘。
- **多模态对齐设计**：共享投影层使得两个模态在微调时交互，优于独立适配器。
- **时空双路设计**：在视觉分支中分离空间和时间上投影，灵活捕捉不同粒度的视频特征。
- **LLM引导蒸馏**：利用LLM生成高质量描述，在不增加训练样本的情况下提升泛化，且与基础任务无关，可扩展。
- **实验全面**：涵盖多种任务和数据集，消融实验系统，对比SOTA方法，结果具有说服力。

### 8. 不足与局限
- **LLM依赖性**：时空描述的质量依赖于所选的LLM（本文使用DeepSeek），如果LLM产生幻觉或噪声，可能影响一致性约束效果。实验发现N=2最佳，更多描述反会降低性能，暗示了该问题。
- **模型适用性**：所有实验基于ViCLIP（ViT-B/16），未验证在其他视频基础模型（如InternVideo、VideoMAE）上的有效性。
- **超参数敏感**：λ、α、插入层数等需要针对具体任务调优，缺乏自动化选择策略。
- **任务范围有限**：仅评估动作识别（分类），未在视频问答、时序定位等更复杂的视频理解任务上验证。
- **公平性潜在风险**：部分对比方法的实现可能未针对ViCLIP优化（如直接移植原论文结果），但作者通过复现AdaptFormer/LoRA在ViCLIP上进行了补充比较，部分缓解了该问题。

（完）
