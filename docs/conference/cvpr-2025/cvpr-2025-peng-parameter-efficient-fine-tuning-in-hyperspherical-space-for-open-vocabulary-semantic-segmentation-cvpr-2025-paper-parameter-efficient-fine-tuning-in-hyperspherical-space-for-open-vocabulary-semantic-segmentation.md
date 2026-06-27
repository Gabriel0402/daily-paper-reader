---
title: Parameter-efficient Fine-tuning in Hyperspherical Space for Open-vocabulary Semantic Segmentation
title_zh: 超球空间中的参数高效微调用于开放词汇语义分割
authors: "Peng, Zelin, Xu, Zhengqin, Zeng, Zhilin, Huang, Yu, Wang, Yaoming, Shen, Wei"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Peng_Parameter-efficient_Fine-tuning_in_Hyperspherical_Space_for_Open-vocabulary_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 视觉基础模型微调用于语义分割
tldr: 开放词汇语义分割需要将CLIP等视觉语言基础模型适配到像素级预测，但全微调计算量大、模态对齐易受损、泛化能力下降。本文提出在超球空间中进行对称参数高效微调（PEFT），同时优化CLIP的双模态，通过一系列高效模块保持对齐并降低计算开销。实验表明该方法在多个分割基准上显著优于全微调及其他PEFT方法，保持了良好的开放词汇泛化能力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-peng-parameter-efficient-fine-tuning-in-hyperspherical-space-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1804, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-peng-parameter-efficient-fine-tuning-in-hyperspherical-space-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1810, \"height\": 1006, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-parameter-efficient-fine-tuning-in-hyperspherical-space-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-parameter-efficient-fine-tuning-in-hyperspherical-space-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1801, \"height\": 1112, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-parameter-efficient-fine-tuning-in-hyperspherical-space-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 551, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-parameter-efficient-fine-tuning-in-hyperspherical-space-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1533, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-peng-parameter-efficient-fine-tuning-in-hyperspherical-space-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1478, \"height\": 416, \"label\": \"Table\"}]"
motivation: CLIP微调用于分割存在计算成本高、模态对齐破坏和泛化下降问题。
method: 在超球空间中进行对称参数高效微调，同时优化视觉和语言模态。
result: 多个分割数据集上性能优于全微调和现有PEFT方法。
conclusion: 超球空间PEFT有效平衡了微调效率与分割性能。
---

## Abstract
Open-vocabulary semantic segmentation seeks to label each pixel in an image with arbitrary text descriptions. Vision-language foundation models, especially CLIP, have recently emerged as powerful tools for acquiring open-vocabulary capabilities. However, fine-tuning CLIP to equip it with pixel-level prediction ability often suffers three issues: 1) high computational cost, 2) misalignment between the two inherent modalities of CLIP, and 3) degraded generalization ability on unseen categories. To address these issues, we propose \alg, a symmetrical parameter-efficient fine-tuning (PEFT) strategy conducted in hyperspherical space for both of the two CLIP modalities. Specifically, the PEFT strategy is achieved by a series of efficient block-diagonal learnable transformation matrices and a dual cross-relation communication module among all learnable matrices. Since the PEFT strategy is conducted symmetrically to the two CLIP modalities, the misalignment between them is mitigated. Furthermore, we apply an additional constraint to PEFT on the CLIP text encoder according to the hyperspherical energy principle, i.e., minimizing hyperspherical energy during fine-tuning preserves the intrinsic structure of the original parameter space, to prevent the destruction of the generalization ability offered by the CLIP text encoder. Extensive evaluations across various benchmarks show that H-CLIP achieves new SOTA open-vocabulary semantic segmentation results while only requiring updating approximately 4% of the total parameters of CLIP.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机
论文聚焦于**开放词汇语义分割**（Open-vocabulary Semantic Segmentation, OVSS），其目标是用任意文本描述对图像中每个像素进行分类。当前主流方法基于视觉‑语言基础模型（如CLIP）进行微调，以赋予其像素级预测能力。然而，现有微调策略面临三大问题：
- **高计算成本**：全参数微调参数量巨大，资源消耗高。
- **模态不对齐**：多数方法仅微调图像编码器而冻结文本编码器，导致图像编码器追求“像素‑文本”对齐，而文本编码器仍保持“图像‑文本”对齐，两者优化目标不一致，阻碍性能。
- **泛化能力下降**：有限类别上的微调会破坏CLIP对未见类别的泛化能力。

## 2. 方法论：H‑CLIP框架
### 核心思想
在**超球空间**（Hyperspherical Space）中对CLIP的两个模态（图像和文本）执行**对称参数高效微调**（Symmetric PEFT），同时利用**超球能量**（Hyperspherical Energy）原理保留文本编码器的泛化能力，并通过**双交叉关系通信模块**（Dual Cross-Relation Communication, DCRC）增强跨模态、跨层的对齐。

### 关键技术细节
- **部分正交参数化（Partial Orthogonal Parameterization, POP）**  
  - 对CLIP每个Transformer层的预训练权重矩阵\(W_\ell\)，附加一个**块对角可学习变换矩阵**\(R\)，即：\(\tilde{M}_\ell = F_\ell(M_\ell; T_\ell W_\ell)\)，其中\(T_\ell\)是由所有\(R\)构成的三阶张量。  
  - 对于**文本编码器**，\(R\)被强制为正交矩阵（采用Cayley参数化），使得微调前后的超球能量不变（\(\min \|HE(W)-HE(W_0)\|\)），从而保留预训练语义结构。  
  - 对于**图像编码器**，\(R\)不施加正交约束以允许学习分割能力，但参数数量与文本编码器对称，缓解模态不对齐。  
  - 块对角结构（每块维度\(q=128\)）显著降低参数量。

- **双交叉关系通信（DCRC）**  
  - 将各层中所有块对角矩阵组织为**高阶张量**\(T\)（维度\(q \times q \times (b+b) \times L\)，\(b\)为块数，\(L\)为层数）。  
  - 利用**高阶张量乘积**（Higher‑order T‑product）定义可学习的变换：\(T_w = T \times_3 S_3 \times_4 S_4\)，其中\(S_3\in\mathbb{R}^{(b+b)\times(b+b)}\)捕捉跨模态关系，\(S_4\in\mathbb{R}^{L\times L}\)捕捉跨层关系。  
  - 进一步用两层MLP（\(f_3, f_4\)）替代线性变换，加入非线性，最终输出\(T = T + \alpha T_w\)，\(\alpha\)可学习。  
  - DCRC仅引入约0.01M额外参数，却显著提升了模态对齐。

### 算法流程（文字说明）
1. 冻结CLIP全部预训练权重。  
2. 为每个Transformer层（图像和文本）添加块对角可学习矩阵\(R\)（文本编码器的\(R\)为正交）。  
3. 将所有\(R\)组织成四阶张量，通过DCRC进行跨模态、跨层通信，更新后的张量再与原始预训练权重结合，生成调整后的特征。  
4. 在COCO‑Stuff数据集上使用交叉熵损失\(L_{ce}\)微调（仅训练可学习矩阵和DCRC参数）。  
5. 推理时直接使用微调后的CLIP特征进行像素‑文本匹配。

## 3. 实验设计
### 数据集与基准
- **训练集**：COCO‑Stuff（约118,000张密集标注图像，171个语义类别）。  
- **测试基准**（6个测试集）：  
  - ADE20K（A‑847, A‑150）  
  - PASCAL Context（PC‑459, PC‑59）  
  - PASCAL VOC（PAS‑20, PAS‑20b）  
- **评价指标**：平均交并比（mIoU）。

### 对比方法
- **传统全/部分微调**：ZS3Net, LSeg, ZegFormer, ZSseg, OpenSeg, OVSeg, ZegCLIP, SED, CAT‑Seg。  
- **参数高效微调（PEFT）**：SAN, LoRA, OFT, VPT, Adapter, LST, SSF。  
- **额外泛化实验**：在COCO数据集上测试开放词汇目标检测（对比CLIM, LoRA, OFT）。

### 主要结果（Table 1）
- 使用ViT‑B/16时，H‑CLIP在A‑847, PC‑459, A‑150, PC‑59, PAS‑20, PAS‑20b上分别达到12.5, 19.4, 32.4, 57.9, 95.2, 78.2 mIoU，全面超越所有对比方法。  
- 使用ViT‑L/14时，同样取得最佳（16.5, 24.2, 38.4, 64.1, 97.7, 83.2）。  
- 可训练参数仅约5.6M（CLIP总参数的4%），远少于OVSeg (147.2M)、CAT‑Seg (39.5M) 和 SAN (8.4M)。

## 4. 资源与算力
- **GPU**：4块 NVIDIA RTX 3090。  
- **训练时长**：约12.2小时（80,000次迭代，batch size=1）。  
- **优化器**：Adam，初始学习率5e‑6，权重衰减1e‑4。  
- **其他**：块维度\(q=128\)，DCRC使用2层MLP。论文未提及推理时长，但指出推理开销可忽略。

## 5. 实验数量与充分性
- **主实验**：两个backbone（ViT‑B/16, ViT‑L/14）在6个测试集上的SOTA对比（Table 1）。  
- **消融研究**：  
  - 组件消融（POP, DCRC, 组合）对比6种主流PEFT方法（Table 3）。  
  - POP内部设计：不同块维度\(q\)（256,128,64）和正交约束策略（Table 4）。  
- **泛化实验**：开放词汇目标检测（Table 5），验证任务迁移能力。  
- **定性结果**：Fig.2可视化与CAT‑Seg的对比。  
- **效率对比**：可训练参数和训练时间（Table 2）。  
实验设计全面，与多种SOTA方法在同一基准下公平比较，消融实验覆盖了核心组件和超参数，泛化实验验证了跨任务通用性，客观性良好。

## 6. 主要结论与发现
- 对称PEFT（同时微调图像和文本编码器）能有效缓解模态不对齐，优于非对称微调。  
- 在文本编码器中施加正交约束（基于超球能量保持原理）成功保留了CLIP对未见类别的泛化能力。  
- DCRC通过张量乘积实现跨模态、跨层通信，以极小参数开销显著提升对齐性能。  
- H‑CLIP仅更新约4%的CLIP总参数，即在6个分割测试集上达到新SOTA，并在目标检测任务上也取得竞争力。

## 7. 优点
- **创新性**：首次将超球空间与超球能量原理引入CLIP的PEFT，理论动机清晰（保持预训练语义结构）。  
- **对称设计**：同时更新图像和文本编码器，从根本上缓解了模态不对齐。  
- **高效性**：参数量极少（5.6M），训练时间短（12.2h），推理开销可忽略。  
- **泛化性强**：在多个未见类别的数据集上均表现最佳，且能迁移到检测任务。  
- **可解释性**：基于Thomson问题推导超球能量保持等价于正交变换，数学严谨。

## 8. 不足与局限
- **实验覆盖**：仅在一个训练集（COCO‑Stuff）上微调，未验证在更小或更多样化训练集上的鲁棒性；跨域泛化（如遥感、医学图像）未测试。  
- **正交约束的倾向性**：仅对文本编码器施加正交，图像编码器自由学习，可能仍存在轻微不对齐（但DCRC部分弥补）。  
- **块对角结构的限制**：块维度\(q=128\)是一种折中，更小的块会降低性能，更大的块增加参数量，最优选择依赖经验。  
- **依赖CLIP**：方法基于CLIP架构，若替换其他VLM（如ALIGN, BLIP）需重新适配。  
- **未讨论失败案例**：论文未分析在哪些场景下性能仍旧不佳（如小物体或长尾类别）。  
- **计算资源**：虽然参数少，但仍需4块3090 GPU，对个人研究者并非完全低门槛。

（完）
